# Trabajo con cursores la BBDD Empleados

## Especificación

La base de datos de __"empleados"__ es un sistema diseñado para gestionar información relacionada con los empleados de una empresa. Esta base de datos está estructurada en torno a la entidad principal "empleados", que contiene información detallada sobre cada empleado. La estructura de la base de datos se compone de una única tabla principal llamada "empleados".

La tabla "empleados" está diseñada con las siguientes columnas:

- __id__: Esta columna sirve como identificador único para cada empleado. Es de tipo entero y se genera automáticamente utilizando la propiedad AUTO_INCREMENT.
- __nombre__: Almacena el nombre completo de cada empleado. Es de tipo cadena de caracteres (VARCHAR) con una longitud máxima de 100 caracteres.
- __salario__: Esta columna registra el salario de cada empleado. Se define como un número decimal (DECIMAL) con una precisión de 10 dígitos en total y 2 dígitos después del punto decimal.


``` sql
CREATE DATABASE IF NOT EXISTS empresa;
USE empresa;

CREATE TABLE empleados (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(100),
    salario DECIMAL(10, 2)
);

INSERT INTO empleados (nombre, salario) VALUES
('Juan', 3000.00),
('María', 3500.00),
('Pedro', 3200.00);
```

``` sql
mysql> select * from empleados;
+----+--------+---------+
| id | nombre | salario |
+----+--------+---------+
|  1 | Juan   | 3300.00 |
|  2 | María  | 3850.00 |
|  3 | Pedro  | 3520.00 |
+----+--------+---------+
```

# Consultas

1. **Escribe un procedimiento almacenado que copie los nombres de todos los empleados cuyo salario sea superior a 3000 en una nueva tabla llamada 'empleados_destino'. Es necesario crear la tabla empleados_destiono.**

*Entrada*

``` sql
CREATE TABLE empleados_copy (
    id INT,
    nombre VARCHAR(100),
    salario DECIMAL(10, 2)
);
```

``` sql
DELIMITER //
CREATE PROCEDURE copiar_nombres ()
BEGIN
    DECLARE done INT DEFAULT FALSE;
    DECLARE emp_id INT;
    DECLARE emp_nombre VARCHAR(100);
    DECLARE emp_salario DECIMAL(10,2);
    DECLARE cur CURSOR FOR SELECT id, nombre, salario FROM empleados WHERE salario > 3000;
    DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = TRUE;
    OPEN cur;
    read_loop: LOOP
        FETCH cur INTO emp_id, emp_nombre, emp_salario;
        IF done THEN
            LEAVE read_loop;
        END IF;
        INSERT INTO empleados_copy (id,nombre,salario) VALUES
        (emp_id, emp_nombre, emp_salario);
    END LOOP;
    CLOSE cur;
END //
DELIMITER ;
```

``` sql
CALL copiar_nombres();
```

*Salida*

``` sql
+------+--------+---------+
| id   | nombre | salario |
+------+--------+---------+
|    2 | María  | 3500.00 |
|    3 | Pedro  | 3200.00 |
+------+--------+---------+
```

---

2. **Escribe un procedimiento almacenado que seleccione los empleados cuyos nombres contienen la letra 'a' y aumente sus salarios en un 10%.**

*Entrada*

``` sql
DELIMITER //
CREATE PROCEDURE empleados_a_10 ()
BEGIN
    DECLARE done INT DEFAULT FALSE;
    DECLARE emp_id INT;
    DECLARE emp_nombre VARCHAR(100);
    DECLARE emp_salario DECIMAL(10,2);
    DECLARE cur CURSOR FOR SELECT id, nombre, salario FROM empleados WHERE nombre REGEXP ('a');
    DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = TRUE;
    OPEN cur;
    read_loop: LOOP
        FETCH cur INTO emp_id, emp_nombre, emp_salario;
        IF done THEN
            LEAVE read_loop;
        END IF;
        UPDATE empleados SET salario = salario * (1 + 10 / 100) WHERE id = emp_id;
    END LOOP;
    CLOSE cur;
END //
DELIMITER ;
```

``` sql
CALL empleados_a_10 ();
```

*Salida*

``` sql
+----+--------+---------+
| id | nombre | salario |
+----+--------+---------+
|  1 | Juan   | 3300.00 |
|  2 | María  | 3850.00 |
|  3 | Pedro  | 3200.00 |
+----+--------+---------+
```

---

3. **Escribe un procedimiento almacenado que seleccione empleados cuyos IDs estén en un rango específico, por ejemplo, entre 2 y 3.**

*Entrada*

``` sql
DELIMITER //
CREATE PROCEDURE select_empleados (IN valor1 INT, IN valor2 INT)
BEGIN
    DECLARE done INT DEFAULT FALSE;
    DECLARE emp_id INT;
    DECLARE emp_nombre VARCHAR(100);
    DECLARE emp_salario DECIMAL(10,2);
    DECLARE cur CURSOR FOR SELECT id, nombre, salario FROM empleados WHERE id BETWEEN valor1 and valor2;
    DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = TRUE;
    OPEN cur;
    read_loop: LOOP
        FETCH cur INTO emp_id, emp_nombre, emp_salario;
        IF done THEN
            LEAVE read_loop;
        END IF;
        SELECT id, nombre, salario FROM empleados WHERE id = emp_id;
    END LOOP;
    CLOSE cur;
END //
DELIMITER ;
```

``` sql
CALL select_empleados (2, 3);
```

*Salida*

``` sql
+----+--------+---------+
| id | nombre | salario |
+----+--------+---------+
|  2 | María  | 3850.00 |
+----+--------+---------+

+----+--------+---------+
| id | nombre | salario |
+----+--------+---------+
|  3 | Pedro  | 3200.00 |
+----+--------+---------+
```

---

4.**Escribe un procedimiento almacenado que elimine todos los empleados cuyo salario esté entre 2000 y 2500.**

*Entrada*

``` sql
DELIMITER //
CREATE PROCEDURE eliminar_empleados ()
BEGIN
    DECLARE done INT DEFAULT FALSE;
    DECLARE emp_id INT;
    DECLARE emp_nombre VARCHAR(100);
    DECLARE emp_salario DECIMAL(10,2);
    DECLARE cur CURSOR FOR SELECT id, nombre, salario FROM empleados WHERE salario BETWEEN 2000 AND 2500;
    DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = TRUE;
    OPEN cur;
    read_loop: LOOP
        FETCH cur INTO emp_id, emp_nombre, emp_salario;
        IF done THEN
            LEAVE read_loop;
        END IF;
        DELETE FROM empleados WHERE id = emp_id;
    END LOOP;
    CLOSE cur;
END //
DELIMITER ;
```

``` sql
CALL eliminar_empleados ();
```

*Salida*

``` sql
+----+--------+---------+
| id | nombre | salario |
+----+--------+---------+
|  1 | Juan   | 3300.00 |
|  2 | María  | 3850.00 |
|  3 | Pedro  | 3200.00 |
+----+--------+---------+
```

---

5. **Escribe un procedimiento almacenado que aumente el salario de un empleado específico cuyo nombre se pasa como parámetro en un 20%.**

*Entrada*

``` sql
DELIMITER //
CREATE PROCEDURE aumentar_salario2 (IN emp_nombre2 VARCHAR(100))
BEGIN
    DECLARE done INT DEFAULT FALSE;
    DECLARE emp_id INT;
    DECLARE emp_nombre VARCHAR(100);
    DECLARE emp_salario DECIMAL(10,2);
    DECLARE cur CURSOR FOR SELECT id, nombre, salario FROM empleados WHERE nombre = emp_nombre2;
    DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = TRUE;
    OPEN cur;
    read_loop: LOOP
        FETCH cur INTO emp_id, emp_nombre, emp_salario;
        IF done THEN
            LEAVE read_loop;
        END IF;
        UPDATE empleados SET salario = salario * (1 + 20 / 100) WHERE id = emp_id;
    END LOOP;
    CLOSE cur;
END //
DELIMITER ;
```

``` sql
CALL aumentar_salario ('Juan');
```

*Salida*

``` sql
+----+--------+---------+
| id | nombre | salario |
+----+--------+---------+
|  1 | Juan   | 3960.00 |
|  2 | María  | 3850.00 |
|  3 | Pedro  | 3200.00 |
+----+--------+---------+
```