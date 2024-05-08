# Trabajo con cursores la BBDD Empleados

```sql
-- Crear la base de datos
CREATE DATABASE IF NOT EXISTS empresa;
USE empresa;

-- Crear la tabla empleados
CREATE TABLE empleados (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(100),
    salario DECIMAL(10, 2)
);

-- Insertar algunos datos de ejemplo
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

---

1. **Escribe un procedimiento almacenado que aumente los salarios de todos los empleados un 5%, pero excluya a aquellos cuyo salario sea superior a 3200. El procedimiento debe tener parámetros de entrada.**

*Entrada*

``` sql
DELIMITER //
CREATE PROCEDURE aumentar_salarios(IN PROCENTAJE DECIMAL(5,2))
BEGIN
    DECLARE done INT DEFAULT FALSE;
    DECLARE emp_id INT;
    DECLARE emp_nombre VARCHAR(100)
    DECLARE emp_salario DECIMAL(10, 2);
    DECLARE cur CURSOR FOR SELECT id, nombre, salario FROM empleados;
    DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = TRUE;

    OPEN cur;
    read_loop: LOOP
        FETCH cur INTO emp_id, emp_nombre, emp_salario;
        IF done THEN
            LEAVE read_loop;
        END IF;
        IF emp_salario <= 3200.0 THEN
        UPDATE empleados SET salario = salario * (1 + porcentaje / 100) WHERE id = emp_id;
        END IF;
    END LOOP;
    CLOSE cur;
END //
DELIMITER ;
```

*Salida*

``` sql

```

2. **Escribe un procedimiento almacenado que calcule el salario anual de cada empleado (asumiendo que trabajan todo el año) y lo imprima.**

*Entrada*

``` sql
DELIMITER //
CREATE PROCEDURE calcular_salario_anual()
BEGIN
    DECLARE emp_id INT;
    DECLARE emp_nombre VARCHAR(100);
    DECLARE emp_salario DECIMAL(10, 2);
    DECLARE done INT DEFAULT FALSE;
    DECLARE cur CURSOR FOR SELECT id, nombre, salario FROM empleados;
    DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = TRUE;

    OPEN cur;
    read_loop: LOOP
        FETCH cur INTO emp_id, emp_nombre, emp_salario;
        IF done THEN
            LEAVE read_loop;
        END IF;
        SELECT emp_nombre AS Empleado, emp_salario * 12 AS Salario;
    END LOOP;
    CLOSE cur;
END //
DELIMITER ;
```

*Salida*

``` sql

```

3. **Escribe un procedimiento almacenado que cuente y muestre el número de empleados en cada rango de salario (por ejemplo, menos de 3000, entre 3000 y 5000, más de 5000). El procedimiento debe tener parámetros de entrada.**


*Entrada*

``` sql
DELIMITER //
CREATE PROCEDURE contar_empleados_por_rango_salario(
    IN salario_min DECIMAL(10, 2),
    IN salario_max DECIMAL(10, 2)
)
BEGIN
    DECLARE emp_id INT;
    DECLARE emp_salario DECIMAL(10, 2);
    DECLARE done INT DEFAULT FALSE;
    DECLARE empleados_menor_salario INT DEFAULT 0;
    DECLARE empleados_entre_salario INT DEFAULT 0;
    DECLARE empleados_mayor_salario INT DEFAULT 0;

    DECLARE cur CURSOR FOR SELECT id, salario FROM empleados;
    DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = TRUE;

    OPEN cur;
    read_loop: LOOP
        FETCH cur INTO emp_id, emp_salario;
        IF done THEN
            LEAVE read_loop;
        END IF;
        IF emp_salario < salario_min THEN
            SET empleados_menor_salario = empleados_menor_salario + 1;
        ELSEIF emp_salario BETWEEN salario_min AND salario_max THEN
            SET empleados_entre_salario = empleados_entre_salario + 1;
        ELSE
            SET empleados_mayor_salario = empleados_mayor_salario + 1;
        END IF;
    END LOOP;
    CLOSE cur;

    SELECT CONCAT('Menos de ', salario_min, ': ', empleados_menor) AS rango_salario;
    SELECT CONCAT('Entre ', salario_min, ' y ', salario_max, ': ', empleados_entre) AS rango_salario;
    SELECT CONCAT('Más de ', salario_max, ': ', empleados_mayor) AS rango_salario;
END //
DELIMITER ;
```

*Salida*

``` sql

```

