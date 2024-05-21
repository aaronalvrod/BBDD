<div align="justify">

# Trabajo con la BBDD Alumnos

**Crea una base de datos llamada test que contenga una tabla llamada alumnos con las siguientes columnas:**

``` sql
CREATE DATABASE test;
```

---

- **Tabla alumnos:**
  - id (entero sin signo)
  - nombre (cadena de caracteres)
  - apellido1 (cadena de caracteres)
  - apellido2 (cadena de caracteres)
  - nota (número real)

*Comando*

``` sql
CREATE TABLE alumnos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(20),
    apellido1 VARCHAR(20),
    apellido2 VARCHAR(20),
    nota FLOAT
);
```

---
  
Crea los siguientes __triggers__:

- Trigger1:_trigger_check_nota_before_insert_.

  - Se ejecuta sobre la tabla alumnos.
  - Se ejecuta antes de una operación de inserción.
  - Si el nuevo valor de la nota que se quiere insertar es negativo, se guarda como 0.
  - Si el nuevo valor de la nota que se quiere insertar es mayor que 10, se guarda como 10.


*Trigger 1*

``` sql
DELIMITER $$
CREATE TRIGER trigger_check_nota_before_insert
BEFORE INSERT ON alumnos
FOR EACH ROW
BEGIN
    IF NEW.nota<0
        THEN SET NEW.nota = 0;
    END IF;
    IF NEW.nota>10
        THEN SET NEW.nota = 10;
    END IF;
END; $$
```

- __Trigger2__ : 
_trigger_check_nota_before_update_.

  - Se ejecuta sobre la tabla alumnos.
  - Se ejecuta antes de una operación de actualización.
  - Si el nuevo valor de la nota que se quiere actualizar es negativo, se guarda como 0.
  - Si el nuevo valor de la nota que se quiere actualizar es mayor que 10, se guarda como 10.

*Trigger 2*

``` sql
DELIMITER $$
CREATE TRIGER trigger_check_nota_before_insert
BEFORE UPDATE ON alumnos
FOR EACH ROW
BEGIN
    IF NEW.nota<0
        THEN SET NEW.nota = 0;
    END IF;
    IF NEW.nota>10
        THEN SET NEW.nota = 10;
    END IF;
END; $$
```

Una vez creados los triggers escriba varias sentencias de inserción y actualización sobre la tabla alumnos y verifica que los triggers se están ejecutando correctamente.


---

Crea el siguiente procedimiento:

- __Procedimiento 1__:

  - Crea un procedimiento que permita realizar la inserción de un número de alumnos, con una nota mímina y máxima. Estos valores pueden oscilar entre 3, y 10.

 *Procedimiento*

  ``` sql
  DELIMITER //
  CREATE PROCEDURE insert_alumnos(IN num_alum INT, IN nota_min FLOAT, IN nota_max FLOAT)
  BEGIN
    DECLARE counter INT DEFAULT 0;
    DECLARE new_nota FLOAT;
    WHILE counter < num_alum DO
      SET new_nota = ROUND(nota_min + (nota_max - nota_min) * RAND(), 2);
      INSERT INTO alumnos (nombre, apellido1, apellido2, nota) 
      VALUES (CONCAT('Alumno', counter), 'Apellido1', 'Apellido2', new_nota);
      SET counter = counter + 1;
    END WHILE;
  END;
  //
  ```

  *Llamada*

  ``` sql
  CALL insert_alumnos(10, 3, 10);
  ```

  - Crea un procedimiento que permita realizar la inserción de un número de alumnos, con una nota mímina y máxima. Estos valores pueden oscilar entre -10, y 12.

 *Procedimiento*

 ``` sql
 Creado anteriormente
 ```

 *Llamada*

 ``` sql
 CALL insert_alumnos(10, -10, 2);
 ```

Realiza los procedimientos y verifica el comportamiento llamando a este con los parámetros adecuados.
