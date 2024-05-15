# Trabajo con procedimientos de generación de información

Dado el procedmiento base:

``` sql
DELIMITER //

CREATE PROCEDURE my_loop(IN iterations INT)
BEGIN
    DECLARE counter INT DEFAULT 0;

    WHILE counter < iterations DO
        -- Coloca aquí el código que deseas ejecutar en cada iteración del bucle
        -- Por ejemplo, puedes imprimir el valor del contador
        SELECT counter;

        SET counter = counter + 1;
    END WHILE;
END//

DELIMITER ;

-- Llama al procedimiento 
CALL my_loop(5);
```

Realiza los siguientes procedimientos, que realizen las siguientes operaciones.

# Procedimientos.

1. **Insertar cinco filas en la tabla empleados con nombre aleatorios generados usando la función `CONCAT()` junto con `RAND()`.**

*Procedimiento*

``` sql
DELIMITER //
DROP PROCEDURE IF EXISTS insertar_nombres_aleatorios;
CREATE PROCEDURE insertar_nombres_aleatorios(IN iterations INT)
BEGIN
    DECLARE counter INT DEFAULT 0;

    WHILE counter < iterations DO
        INSERT INTO empleados (nombre, salario)
        VALUES (CONCAT('Empleado', RAND()), FLOOR(RAND() * (10000 - 2000 + 1)) + 2000);
        SELECT counter;
        SET counter = counter + 1;
    END WHILE;
END //
DELIMITER ;
```

*Llamada*

``` sql
CALL insertar_nombres_aleatorios(5);
```

*Salida*

``` sql
+----+-----------------------------+---------+
| id | nombre                      | salario |
+----+-----------------------------+---------+
|  1 | Juan                        | 3960.00 |
|  2 | María                       | 3850.00 |
|  3 | Pedro                       | 3200.00 |
|  4 | Empleado0.5812369301740424  | 4366.00 |
|  5 | Empleado0.735200851909072   | 8310.00 |
|  6 | Empleado0.7376840913087913  | 4579.00 |
|  7 | Empleado0.39919034428819117 | 2228.00 |
|  8 | Empleado0.9454599962993152  | 7132.00 |
+----+-----------------------------+---------+
```

2. **Insertar tres filas en la tabla empleados con nombre aleatorios generados usando la función `UUID()`**

*Procedimiento*

``` sql
DELIMITER //
DROP PROCEDURE IF EXISTS insertar_nombres_aleatorios;
CREATE PROCEDURE insertar_nombres_aleatorios(IN iterations INT)
BEGIN
    DECLARE counter INT DEFAULT 0;

    WHILE counter < iterations DO
        INSERT INTO empleados (nombre, salario)
        VALUES (UUID(), FLOOR(RAND() * (10000 - 2000 + 1)) + 2000);
        SELECT counter;
        SET counter = counter + 1;
    END WHILE;
END //
DELIMITER ;
```

*Llamada*

``` sql
CALL insertar_nombres_aleatorios(3);
```

*Salida*

``` sql
+----+--------------------------------------+---------+
| id | nombre                               | salario |
+----+--------------------------------------+---------+
|  1 | Juan                                 | 3960.00 |
|  2 | María                                | 3850.00 |
|  3 | Pedro                                | 3200.00 |
|  4 | Empleado0.5812369301740424           | 4366.00 |
|  5 | Empleado0.735200851909072            | 8310.00 |
|  6 | Empleado0.7376840913087913           | 4579.00 |
|  7 | Empleado0.39919034428819117          | 2228.00 |
|  8 | Empleado0.9454599962993152           | 7132.00 |
|  9 | 72c40b33-12e5-11ef-be85-080027077231 | 9331.00 |
| 10 | 72c72dc1-12e5-11ef-be85-080027077231 | 9011.00 |
| 11 | 72c8a4ed-12e5-11ef-be85-080027077231 | 7062.00 |
+----+--------------------------------------+---------+
```

3. **Inserta dos filas en la tabla empleados con nombres aleatorios generados usand la función `RAND()` junto con `ORDER BY RAND()`.**

*Procedimiento*

``` sql
DELIMITER //
DROP PROCEDURE IF EXISTS insertar_nombres_aleatorios;
CREATE PROCEDURE insertar_nombres_aleatorios(IN iterations INT)
BEGIN
    DECLARE counter INT DEFAULT 0;
    WHILE counter < iterations DO
        INSERT INTO empleados (nombre, salario)
        SELECT CONCAT('Empleado', RAND()), FLOOR(RAND() * (10000 - 2000 + 1)) + 2000 FROM (SELECT 1 UNION SELECT 2) AS sub ORDER BY RAND() LIMIT 2;
        SELECT counter;
        SET counter = counter + 1;
    END WHILE;
END //
DELIMITER ;
```

*Llamada*

``` sql
CALL insertar_nombres_aleatorios(2);
```

*Salida*

``` sql
+----+--------------------------------------+---------+
| id | nombre                               | salario |
+----+--------------------------------------+---------+
|  1 | Juan                                 | 3960.00 |
|  2 | María                                | 3850.00 |
|  3 | Pedro                                | 3200.00 |
|  4 | Empleado0.5812369301740424           | 4366.00 |
|  5 | Empleado0.735200851909072            | 8310.00 |
|  6 | Empleado0.7376840913087913           | 4579.00 |
|  7 | Empleado0.39919034428819117          | 2228.00 |
|  8 | Empleado0.9454599962993152           | 7132.00 |
|  9 | 72c40b33-12e5-11ef-be85-080027077231 | 9331.00 |
| 10 | 72c72dc1-12e5-11ef-be85-080027077231 | 9011.00 |
| 11 | 72c8a4ed-12e5-11ef-be85-080027077231 | 7062.00 |
| 12 | Empleado0.3340828365963724           | 6660.00 |
| 13 | Empleado0.7749532989924338           | 4166.00 |
| 14 | Empleado0.2109212551367667           | 2130.00 |
| 15 | Empleado0.802889453063616            | 4274.00 |
+----+--------------------------------------+---------+
```

4. **Inserta cuatro filas en la tabla empleados con nombre aleatorios generados usando la función `RAND()`junto con `ORDER BY RAND()`.**

*Procedimiento*

``` sql
DELIMITER //
DROP PROCEDURE IF EXISTS insertar_nombres_aleatorios;
CREATE PROCEDURE insertar_nombres_aleatorios(IN iterations INT)
BEGIN
    DECLARE counter INT DEFAULT 0;
    WHILE counter < iterations DO
        INSERT INTO empleados (nombre, salario)
        VALUES (SUBSTRING_INDEX(UUID(), '-', -1), FLOOR(RAND() * (10000 - 2000 + 1)) + 2000);
        SELECT counter;
        SET counter = counter + 1;
    END WHILE;
END //
DELIMITER ;
```

*Llamada*

``` sql
CALL insertar_nombres_aleatorios(4);
```

*Salida*

``` sql
+----+--------------------------------------+---------+
| id | nombre                               | salario |
+----+--------------------------------------+---------+
|  1 | Juan                                 | 3960.00 |
|  2 | María                                | 3850.00 |
|  3 | Pedro                                | 3200.00 |
|  4 | Empleado0.5812369301740424           | 4366.00 |
|  5 | Empleado0.735200851909072            | 8310.00 |
|  6 | Empleado0.7376840913087913           | 4579.00 |
|  7 | Empleado0.39919034428819117          | 2228.00 |
|  8 | Empleado0.9454599962993152           | 7132.00 |
|  9 | 72c40b33-12e5-11ef-be85-080027077231 | 9331.00 |
| 10 | 72c72dc1-12e5-11ef-be85-080027077231 | 9011.00 |
| 11 | 72c8a4ed-12e5-11ef-be85-080027077231 | 7062.00 |
| 12 | Empleado0.3340828365963724           | 6660.00 |
| 13 | Empleado0.7749532989924338           | 4166.00 |
| 14 | Empleado0.2109212551367667           | 2130.00 |
| 15 | Empleado0.802889453063616            | 4274.00 |
| 16 | 080027077231                         | 5591.00 |
| 17 | 080027077231                         | 3565.00 |
| 18 | 080027077231                         | 7053.00 |
| 19 | 080027077231                         | 6568.00 |
+----+--------------------------------------+---------+
```

5. **Inserta seis filas en la tabla empleados con nombres aleatorios generados usando la función `RAND()`y una semilla diferente.**

*Procedimiento*

``` sql
DELIMITER //
DROP PROCEDURE IF EXISTS insertar_nombres_aleatorios;
CREATE PROCEDURE insertar_nombres_aleatorios(IN iterations INT)
BEGIN
    DECLARE counter INT DEFAULT 0;

    WHILE counter < iterations DO
        INSERT INTO empleados (nombre, salario)
        VALUES (CONCAT('Empleado', RAND(1)), FLOOR(RAND(1) * (10000 - 2000 + 1)) + 2000);
        SELECT counter;
        SET counter = counter + 1;
    END WHILE;
END //
DELIMITER ;
```

*Llamada*

``` sql
CALL insertar_nombres_aleatorios(6);
```

*Salida*

``` sql
+----+--------------------------------------+---------+
| id | nombre                               | salario |
+----+--------------------------------------+---------+
|  1 | Juan                                 | 3960.00 |
|  2 | María                                | 3850.00 |
|  3 | Pedro                                | 3200.00 |
|  4 | Empleado0.5812369301740424           | 4366.00 |
|  5 | Empleado0.735200851909072            | 8310.00 |
|  6 | Empleado0.7376840913087913           | 4579.00 |
|  7 | Empleado0.39919034428819117          | 2228.00 |
|  8 | Empleado0.9454599962993152           | 7132.00 |
|  9 | 72c40b33-12e5-11ef-be85-080027077231 | 9331.00 |
| 10 | 72c72dc1-12e5-11ef-be85-080027077231 | 9011.00 |
| 11 | 72c8a4ed-12e5-11ef-be85-080027077231 | 7062.00 |
| 12 | Empleado0.3340828365963724           | 6660.00 |
| 13 | Empleado0.7749532989924338           | 4166.00 |
| 14 | Empleado0.2109212551367667           | 2130.00 |
| 15 | Empleado0.802889453063616            | 4274.00 |
| 16 | 080027077231                         | 5591.00 |
| 17 | 080027077231                         | 3565.00 |
| 18 | 080027077231                         | 7053.00 |
| 19 | 080027077231                         | 6568.00 |
| 20 | Empleado0.40540353712197724          | 5243.00 |
| 21 | Empleado0.40540353712197724          | 5243.00 |
| 22 | Empleado0.40540353712197724          | 5243.00 |
| 23 | Empleado0.40540353712197724          | 5243.00 |
| 24 | Empleado0.40540353712197724          | 5243.00 |
| 25 | Empleado0.40540353712197724          | 5243.00 |
+----+--------------------------------------+---------+
```