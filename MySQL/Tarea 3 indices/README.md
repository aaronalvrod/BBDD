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

- **Utilizando EXPLAIN observa el plan de ejecución de la consulta que devuelve toda la información de los movimientos con identificador=3. Tanto en la tabla MOVIMIENTOS como en la tabla MOVIMIENTOS_bis. Escribe tus conclusiones al respecto.**

*Comando*

``` sql
EXPLAIN SELECT * FROM MOVIMIENTO WHERE identificador = 3;
```

*Salida*

``` sql
+----+-------------+------------+------------+-------+---------------+---------+---------+-------+------+----------+-------+
| id | select_type | table      | partitions | type  | possible_keys | key     | key_len | ref   | rows | filtered | Extra |
+----+-------------+------------+------------+-------+---------------+---------+---------+-------+------+----------+-------+
|  1 | SIMPLE      | MOVIMIENTO | NULL       | const | PRIMARY       | PRIMARY | 4       | const |    1 |   100.00 | NULL  |
+----+-------------+------------+------------+-------+---------------+---------+---------+-------+------+----------+-------+
```

*Comando*

``` sql
EXPLAIN SELECT * FROM MOVIMIENTO_BIS WHERE identificador = 3;
```

*Salida*

``` sql
+----+-------------+----------------+------------+------+---------------+------+---------+------+------+----------+-------------+
| id | select_type | table          | partitions | type | possible_keys | key  | key_len | ref  | rows | filtered | Extra       |
+----+-------------+----------------+------------+------+---------------+------+---------+------+------+----------+-------------+
|  1 | SIMPLE      | MOVIMIENTO_BIS | NULL       | ALL  | NULL          | NULL | NULL    | NULL | 3563 |    10.00 | Using where |
+----+-------------+----------------+------------+------+---------------+------+---------+------+------+----------+-------------+

```

- **Supongamos que las consultas de rango que se van a hacer en nuestra tabla son frecuentes y además no por el identificador, sino por la fecha. Este es motivo suficiente para que sea la fecha un índice de tabla y así mejorar el tiempo de respuesta de nuestras consultas. En la tabla MOVIMIENTO_BIS creamos un índice para la fecha (IX_FECHA_BIS) y otro índice para el identificador (IX_IDENTIFICADOR).**

*Comando*

``` sql
CREATE INDEX IX_FECHA_BIS ON MOVIMIENTO_BIS (fecha);
```

*Salida*

``` sql
+---------------+-------------+------+-----+---------+-------+
| Field         | Type        | Null | Key | Default | Extra |
+---------------+-------------+------+-----+---------+-------+
| Identificador | int         | NO   |     | 0       |       |
| Articulo      | varchar(50) | YES  |     | NULL    |       |
| Fecha         | date        | YES  | MUL | NULL    |       |
| Cantidad      | int         | YES  |     | NULL    |       |
+---------------+-------------+------+-----+---------+-------+
```

*Comando*

``` sql
CREATE INDEX IX_IDENTIFICADOR ON MOVIMIENTO_BIS (identificador);
```

*Salida*

``` sql
+---------------+-------------+------+-----+---------+-------+
| Field         | Type        | Null | Key | Default | Extra |
+---------------+-------------+------+-----+---------+-------+
| Identificador | int         | NO   | MUL | 0       |       |
| Articulo      | varchar(50) | YES  |     | NULL    |       |
| Fecha         | date        | YES  | MUL | NULL    |       |
| Cantidad      | int         | YES  |     | NULL    |       |
+---------------+-------------+------+-----+---------+-------+
```

- **Analiza el plan de ejecución de las siguientes consultas y observa la diferencia: Consulta1**

`Consulta 1`

*Comando*

``` sql
SELECT * FROM MOVIMIENTO_BIS WHERE identificador=3;
```

*Salida*

``` sql
+---------------+-----------+------------+----------+
| Identificador | Articulo  | Fecha      | Cantidad |
+---------------+-----------+------------+----------+
|             3 | Producto3 | 2012-02-07 |   123051 |
+---------------+-----------+------------+----------+
```

`Consulta 2`

*Comando*

``` sql
SELECT identificador FROM MOVIMIENTO_BIS WHERE identificador=3;
```

*Salida*

``` sql
+---------------+
| identificador |
+---------------+
|             3 |
+---------------+
```

- **Analiza el plan de ejecución de las siguientes consultas y observa la diferencia:**

`Consulta 1`

*Comando*

``` sql
EXPLAIN SELECT fecha FROM MOVIMIENTO WHERE fecha BETWEEN '01/01/2012' and '01/03/2012';
```

*Salida*

``` sql
+----+-------------+------------+------------+------+---------------+------+---------+------+------+----------+-------------+
| id | select_type | table      | partitions | type | possible_keys | key  | key_len | ref  | rows | filtered | Extra       |
+----+-------------+------------+------------+------+---------------+------+---------+------+------+----------+-------------+
|  1 | SIMPLE      | MOVIMIENTO | NULL       | ALL  | NULL          | NULL | NULL    | NULL | 3563 |    11.11 | Using where |
+----+-------------+------------+------------+------+---------------+------+---------+------+------+----------+-------------+
```

`Consulta 2`

*Comando*

``` sql
EXPLAIN SELECT * FROM MOVIMIENTO WHERE fecha BETWEEN '01/01/2012' and '01/03/2012';
```

*Salida*

``` sql
+----+-------------+------------+------------+------+---------------+------+---------+------+------+----------+-------------+
| id | select_type | table      | partitions | type | possible_keys | key  | key_len | ref  | rows | filtered | Extra       |
+----+-------------+------------+------------+------+---------------+------+---------+------+------+----------+-------------+
|  1 | SIMPLE      | MOVIMIENTO | NULL       | ALL  | NULL          | NULL | NULL    | NULL | 3563 |    11.11 | Using where |
+----+-------------+------------+------------+------+---------------+------+---------+------+------+----------+-------------+
```

- **Vamos a crear un índice por fecha (IX_FECHA) en la tabla MOVIMIENTO, puesto que no lo tenía, en este caso la tabla ya tenía un indice, la clave primaria.**

*Comando*

``` sql
CREATE INDEX IX_FECHA ON MOVIMIENTO (fecha);
```

*Salida*

``` sql
+---------------+-------------+------+-----+---------+----------------+
| Field         | Type        | Null | Key | Default | Extra          |
+---------------+-------------+------+-----+---------+----------------+
| Identificador | int         | NO   | PRI | NULL    | auto_increment |
| Articulo      | varchar(50) | YES  |     | NULL    |                |
| Fecha         | date        | YES  | MUL | NULL    |                |
| Cantidad      | int         | YES  |     | NULL    |                |
+---------------+-------------+------+-----+---------+----------------+
```

- **Visualiza los indices de las tablas MOVIMIENTO y MOVIMIENTO_BIS.**

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
| MOVIMIENTO |          1 | IX_FECHA |            1 | Fecha         | A         |         120 |     NULL |   NULL | YES  | BTREE      |         |               | YES     | NULL       |
+------------+------------+----------+--------------+---------------+-----------+-------------+----------+--------+------+------------+---------+---------------+---------+------------+
```

*Comando*

``` sql
SHOW INDEX FROM MOVIMIENTO_BIS;
```

*Salida*

``` sql
+----------------+------------+------------------+--------------+---------------+-----------+-------------+----------+--------+------+------------+---------+---------------+---------+------------+
| Table          | Non_unique | Key_name         | Seq_in_index | Column_name   | Collation | Cardinality | Sub_part | Packed | Null | Index_type | Comment | Index_comment | Visible | Expression |
+----------------+------------+------------------+--------------+---------------+-----------+-------------+----------+--------+------+------------+---------+---------------+---------+------------+
| MOVIMIENTO_BIS |          1 | IX_FECHA_BIS     |            1 | Fecha         | A         |         120 |     NULL |   NULL | YES  | BTREE      |         |               | YES     | NULL       |
| MOVIMIENTO_BIS |          1 | IX_IDENTIFICADOR |            1 | Identificador | A         |        3563 |     NULL |   NULL |      | BTREE      |         |               | YES     | NULL       |
+----------------+------------+------------------+--------------+---------------+-----------+-------------+----------+--------+------+------------+---------+---------------+---------+------------+
```