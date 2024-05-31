Examen Procedimientos y funciones


¿Sabías que la mayoría de los adultos sanos pueden ser donantes? Aunque existen ciertas condiciones que debes cumplir para realizar con éxito una donación. Descubre los requisitos básicos para donar sangre.

Para la poder donar sangre se deben cumplir varias condiciones:

    Tener un peso superior a 50Kg.
    No haber donado en un periodo anterior a 90 días en caso de ser hombre y 120 días en caso de mujer.

Teniendo en cuenta esta información se pide:

Crea una base datos llamada donación.

Crea una tabla llamada persona con los siguientes campos:

    Identificador Auto Incremental (Integer) PK
    Identificador (Texto) 
    Peso. (Entero)
    Admitido. Texto(Si/No).(Valores de dominio:Si/No)
    Sexo. Texto (H/M).(Valores de dominio:H/M)
    Fecha Última Donación.

``` sql
CREATE DATABASE donacion;

USE donacion;

CREATE TABLE persona (
    Id INT PRIMARY KEY AUTO_INCREMENT,
    Identificador TEXT,
    Peso INT,
    Admitido TEXT CHECK (Admitido IN ('Si', 'No')),
    Sexo TEXT CHECK (Sexo IN ('H', 'M')),
    Fecha_ultima_donacion DATE
);

CREATE TABLE total_donaciones(
    id_persona TEXT,
    cantidad_total INT
);
```

Se pide:

- Realiza los siguientes procedimientos:

- (1) Realizar un procedimiento que realice la inserción de datos aleatorios en la tabla. El procedimiento debe de recibir como parámetro de entrada, al menos, el número de registros que se desea insertar y se debe de lanzar, al menos, en dos ocasiones, para verificar su correcto funcionamiento. Los datos deben de ser aleatorios, es decir, en cada inserción de debe de auto generar o seleccionar uno al azar, de los campos requeridos.

``` sql
DELIMITER //
DROP PROCEDURE IF EXISTS insertar_datos_random //
CREATE PROCEDURE insertar_datos_random(IN num_registros INT)
BEGIN
    DECLARE counter INT DEFAULT 0;
    
    WHILE counter < num_registros DO
        DECLARE admitido TEXT;
        DECLARE sexo TEXT;
        DECLARE ultima_donacion DATE;
        
        SET admitido = IF(FLOOR(RAND() * 2) = 1, 'Si', 'No');
        SET sexo = IF(FLOOR(RAND() * 2) = 1, 'H', 'M');
        SET ultima_donacion = DATE_SUB(CURDATE(), INTERVAL FLOOR(RAND() * 365) DAY);
        
        INSERT INTO persona (Identificador, Peso, Admitido, Sexo, Fecha_ultima_donacion)
        VALUES(CONCAT('Donante-', UUID()), FLOOR(RAND() * 51) + 50, admitido, sexo, ultima_donacion);
        
        SET counter = counter + 1;
    END WHILE;
END //
DELIMITER ;

```

- (2) Realiza un procedimiento que permita actualizar el la fecha de última donación, teniendo como parámetro de entrada el identificador de la persona, y una fecha.

``` sql
DELIMITER //
DROP PROCEDURE IF EXISTS actualizar_fecha_donacion //
CREATE PROCEDURE actualizar_fecha_donacion(IN new_id INT, IN Fecha_donacion_reciente DATE)
BEGIN
    UPDATE persona SET Fecha_ultima_donacion = Fecha_donacion_reciente WHERE Id = new_id;
END //
DELIMITER ;
``` 

- (3) Crea un procedimiento llamado CalcularTotalDonaciones que calcule la cantidad total de donaciones realizadas por cada persona y la almacene en una tabla llamada total_donaciones. La tabla total_donaciones debe tener dos columnas: id_persona (texto) y cantidad_total (integer).

``` sql
DELIMITER //
DROP PROCEDURE IF EXISTS CalcularTotalDonaciones //
CREATE PROCEDURE CalcularTotalDonaciones()
BEGIN
    TRUNCATE TABLE total_donaciones;
    INSERT INTO total_donaciones (id_persona, cantidad_total)
    SELECT Identificador, COUNT(*) FROM persona
    GROUP BY Identificador;
END //
DELIMITER ;
```

- (4) Crea un procedimiento que me permita eliminar una persona de la tabla total_donaciones.

``` sql
DELIMITER //
DROP PROCEDURE IF EXISTS borrar_personas //
CREATE PROCEDURE borrar_personas(IN id_pers TEXT)
BEGIN
    DELETE FROM total_donaciones WHERE id_persona = id_pers;
END //
DELIMITER ;
```

- Realizar cada una de las siguientes funciones:

- (1) Realiza una función que determine si una persona almacenada en la tabla persona puede realizar una donación. Para ello la función recibe como parámetro de entrada el identificador de esta persona, y una fecha de donación. Revisa las condiciones para que una persona pueda o no donar. Posteriormente actualice el valor de la última donación de la persona indicada con el parámetro de entrada.

``` sql
DELIMITER //
DROP FUNCTION IF EXISTS puede_donar //
CREATE FUNCTION puede_donar(identificador TEXT, fecha_donacion DATE) 
RETURNS BOOLEAN
BEGIN
    DECLARE ultima_donacion DATE;
    DECLARE peso INT;
    DECLARE sexo TEXT;
    
    SELECT Fecha_ultima_donacion, Peso, Sexo INTO ultima_donacion, peso, sexo 
    FROM persona WHERE Identificador = identificador;
    
    IF peso < 50 THEN
        RETURN FALSE;
    END IF;
    
    IF sexo = 'H' AND DATEDIFF(fecha_donacion, ultima_donacion) < 90 THEN
        RETURN FALSE;
    END IF;
    
    IF sexo = 'M' AND DATEDIFF(fecha_donacion, ultima_donacion) < 120 THEN
        RETURN FALSE;
    END IF;
    
    UPDATE persona SET Fecha_ultima_donacion = fecha_donacion WHERE Identificador = identificador;
    RETURN TRUE;
END //
DELIMITER ;
```
- (2) Realiza una función que determine que persona es la que más donaciones ha realizado.

``` sql
DELIMITER //
DROP FUNCTION IF EXISTS persona_mas_donaciones //
CREATE FUNCTION persona_mas_donaciones() 
RETURNS TEXT
BEGIN
    DECLARE id_persona TEXT;
    
    SELECT id_persona INTO id_persona 
    FROM total_donaciones 
    ORDER BY cantidad_total DESC 
    LIMIT 1;
    
    RETURN id_persona;
END //
DELIMITER ;
```

- Triggers

      - (1) Realiza un trigger que actualiza total_donaciones con cada una de las inserciones que se realicen en la tabla Persona.

``` sql
DELIMITER //
DROP TRIGGER IF EXISTS actualizar_donaciones //
CREATE TRIGGER actualizar_donaciones
AFTER INSERT ON persona
FOR EACH ROW
BEGIN
    INSERT INTO total_donaciones (id_persona, cantidad_total)
    VALUES (NEW.Identificador, 1)
    ON DUPLICATE KEY UPDATE cantidad_total = cantidad_total + 1;
END //
DELIMITER ;
```

      - (2) Realiza un trigger que elimine todos los registros en la tabla persona cuando se elimine un registro de la tabla total_donaciones.

``` sql
DELIMITER //
DROP TRIGGER IF EXISTS eliminar_registros //
CREATE TRIGGER eliminar_registros
AFTER DELETE ON total_donaciones
FOR EACH ROW
BEGIN
    DELETE FROM persona WHERE Identificador = OLD.id_persona;
END //
DELIMITER ;
```