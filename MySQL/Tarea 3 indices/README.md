# Tarea 3 Indices


*Comando*

``` sql

```

*Salida*

``` sql

```

- **Crea una base de datos que tendrá por nombre Base_Indices.**

*Comando*

``` sql
CREATE DATABASE Base_Indices;
```

*Salida*

``` sql
Query OK, 1 row affected (0,02 sec)
```

- **En la BD crea una tabla de nombre MOVIMIENTO con la siguiente estructura:**

    | Nombre del campo | Tipo de dato | Propiedades                |
    |------------------|--------------|----------------------------|
    | Identificador    | int          | AUTO_INCREMENT,PRIMARY KEY |
    | Articulo         | varchar(50)  | Obligatorio                |
    | Fecha            | date         | Obligatorio                |
    | Cantidad         | int          | Obligatorio                |

*Comando*

``` sql
CREATE TABLE MOVIMIENTO (
    Identificador INT AUTO_INCREMENT PRIMARY KEY,
    Articulo VARCHAR(50),
    Fecha DATE,
    Cantidad INT
);
```

*Salida*

``` sql
Query OK, 0 rows affected (0,03 sec)
```

- **Aplica la sentencia adecuada para visualizar los índices que hay en la tabla.**

*Comando*

``` sql
SHOW INDEX FROM MOVIMIENTO;
```

*Salida*

``` sql
+------------+------------+----------+--------------+---------------+-----------+-------------+----------+--------+------+------------+---------+---------------+---------+------------+
| Table      | Non_unique | Key_name | Seq_in_index | Column_name   | Collation | Cardinality | Sub_part | Packed | Null | Index_type | Comment | Index_comment | Visible | Expression |
+------------+------------+----------+--------------+---------------+-----------+-------------+----------+--------+------+------------+---------+---------------+---------+------------+
| MOVIMIENTO |          0 | PRIMARY  |            1 | Identificador | A         |        3563 |     NULL |   NULL |      | BTREE      |         |               | YES     | NULL       |
+------------+------------+----------+--------------+---------------+-----------+-------------+----------+--------+------+------------+---------+---------------+---------+------------+
```

- **Ejecuta la siguiente sentencia sql para generar datos de prueba:**

*Comando*

``` sql
CREATE TABLE NumerosUnicos (
Numero INT AUTO_INCREMENT PRIMARY KEY
);

INSERT INTO NumerosUnicos (Numero)
SELECT NULL FROM INFORMATION_SCHEMA.COLUMNS LIMIT 5000;

INSERT INTO MOVIMIENTO (Identificador, Articulo, Fecha, Cantidad)
SELECT 
    n.Numero,
    CONCAT('Producto', n.Numero),
    DATE_ADD('2012-01-01', INTERVAL FLOOR(RAND() * 120) DAY),
    FLOOR(RAND() * 1000000) + 1
FROM 
    NumerosUnicos n;

    DROP TABLE NumerosUnicos;
```

*Salida*

``` sql
Query OK, 3559 rows affected (0,04 sec)
Records: 3559  Duplicates: 0  Warnings: 0
```

*Comando*

``` sql
SELECT count(*) as Entradas FROM MOVIMIENTO;
```

*Salida*

``` sql
+----------+
| Entradas |
+----------+
|     3563 |
+----------+
```

- **Crea con la sentencia CREATE TABLE…SELECT… un duplicado de la tabla MOVIMIENTO a la que llamaremos MOVIMIENTO_BIS.**

*Consulta*

``` sql
CREATE TABLE MOVIMIENTO_BIS SELECT * FROM MOVIMIENTO;
```

*Salida*

``` sql
Query OK, 3563 rows affected (0,07 sec)
Records: 3563  Duplicates: 0  Warnings: 0
```

- **Con la cláusula DESCRIBE observa cuál es la situación de la tabla clonada, ¿Qué le pasa al índice y a la propiedad AUTO_INCREMENT?**

*Comando*

``` sql
DESCRIBE MOVIMIENTO;
```
*Salida*

``` sql
+---------------+-------------+------+-----+---------+----------------+
| Field         | Type        | Null | Key | Default | Extra          |
+---------------+-------------+------+-----+---------+----------------+
| Identificador | int         | NO   | PRI | NULL    | auto_increment |
| Articulo      | varchar(50) | YES  |     | NULL    |                |
| Fecha         | date        | YES  |     | NULL    |                |
| Cantidad      | int         | YES  |     | NULL    |                |
+---------------+-------------+------+-----+---------+----------------+
```

*Comando*

``` sql
DESCRIBE MOVIMIENTO_BIS;
```

*Salida*

``` sql
+---------------+-------------+------+-----+---------+-------+
| Field         | Type        | Null | Key | Default | Extra |
+---------------+-------------+------+-----+---------+-------+
| Identificador | int         | NO   |     | 0       |       |
| Articulo      | varchar(50) | YES  |     | NULL    |       |
| Fecha         | date        | YES  |     | NULL    |       |
| Cantidad      | int         | YES  |     | NULL    |       |
+---------------+-------------+------+-----+---------+-------+
```