# Trabajo con la BBDD Jardineria

### Carga de datos

``` sql
source jardineria.sql
```

### Índices

- **Consulte cuáles son los índices que hay en la tabla producto utilizando las instrucciones SQL que nos permiten obtener esta información de la tabla.**

*Comando*

``` sql
SHOW INDEX FROM producto;
```

*Salida*

``` sql
+----------+------------+----------+--------------+-----------------+-----------+-------------+----------+--------+------+------------+---------+---------------+---------+------------+
| Table    | Non_unique | Key_name | Seq_in_index | Column_name     | Collation | Cardinality | Sub_part | Packed | Null | Index_type | Comment | Index_comment | Visible | Expression |
+----------+------------+----------+--------------+-----------------+-----------+-------------+----------+--------+------+------------+---------+---------------+---------+------------+
| producto |          0 | PRIMARY  |            1 | codigo_producto | A         |         276 |     NULL |   NULL |      | BTREE      |         |               | YES     | NULL       |
| producto |          1 | gama     |            1 | gama            | A         |           4 |     NULL |   NULL |      | BTREE      |         |               | YES     | NULL       |
+----------+------------+----------+--------------+-----------------+-----------+-------------+----------+--------+------+------------+---------+---------------+---------+------------+
```

- **Haga uso de EXPLAIN para obtener información sobre cómo se están realizando las consultas y diga cuál de las dos consultas realizará menos comparaciones para encontrar el producto que estamos buscando. ¿Cuántas comparaciones se realizan en cada caso? ¿Por qué?.**

*Comando*

``` sql
EXPLAIN SELECT * FROM producto WHERE codigo_producto = 'OR-114';
```

*Salida*

``` sql
+----+-------------+----------+------------+-------+---------------+---------+---------+-------+------+----------+-------+
| id | select_type | table    | partitions | type  | possible_keys | key     | key_len | ref   | rows | filtered | Extra |
+----+-------------+----------+------------+-------+---------------+---------+---------+-------+------+----------+-------+
|  1 | SIMPLE      | producto | NULL       | const | PRIMARY       | PRIMARY | 62      | const |    1 |   100.00 | NULL  |
+----+-------------+----------+------------+-------+---------------+---------+---------+-------+------+----------+-------+
```

*Comando*

``` sql
EXPLAIN SELECT * FROM producto WHERE nombre = 'Evonimus Pulchellus';
```

*Salida*

``` sql
+----+-------------+----------+------------+------+---------------+------+---------+------+------+----------+-------------+
| id | select_type | table    | partitions | type | possible_keys | key  | key_len | ref  | rows | filtered | Extra       |
+----+-------------+----------+------------+------+---------------+------+---------+------+------+----------+-------------+
|  1 | SIMPLE      | producto | NULL       | ALL  | NULL          | NULL | NULL    | NULL |  276 |    10.00 | Using where |
+----+-------------+----------+------------+------+---------------+------+---------+------+------+----------+-------------+
```

`Como podemos observar en el primer explain, dicha cosulta `

- **Suponga que estamos trabajando con la base de datos jardineria y queremos saber optimizar las siguientes consultas. ¿Cuál de las dos sería más eficiente?. Se recomienda hacer uso de EXPLAIN para obtener información sobre cómo se están realizando las consultas.**

*Comando*

``` sql
EXPLAIN SELECT AVG(total) FROM pago WHERE YEAR(fecha_pago) = 2008;
```

*Salida*

``` sql
+----+-------------+-------+------------+------+---------------+------+---------+------+------+----------+-------------+
| id | select_type | table | partitions | type | possible_keys | key  | key_len | ref  | rows | filtered | Extra       |
+----+-------------+-------+------------+------+---------------+------+---------+------+------+----------+-------------+
|  1 | SIMPLE      | pago  | NULL       | ALL  | NULL          | NULL | NULL    | NULL |   26 |   100.00 | Using where |
+----+-------------+-------+------------+------+---------------+------+---------+------+------+----------+-------------+
```

*Comando*

``` sql
EXPLAIN SELECT AVG(total) FROM pago WHERE fecha_pago >= '2008-01-01' AND fecha_pago <= '2008-12-31';
```

*Salida*

``` sql
+----+-------------+-------+------------+------+---------------+------+---------+------+------+----------+-------------+
| id | select_type | table | partitions | type | possible_keys | key  | key_len | ref  | rows | filtered | Extra       |
+----+-------------+-------+------------+------+---------------+------+---------+------+------+----------+-------------+
|  1 | SIMPLE      | pago  | NULL       | ALL  | NULL          | NULL | NULL    | NULL |   26 |    11.11 | Using where |
+----+-------------+-------+------------+------+---------------+------+---------+------+------+----------+-------------+
```

`Explicacion`

- **Optimiza la siguiente consulta creando índices cuando sea necesario. Se recomienda hacer uso de EXPLAIN para obtener información sobre cómo se están realizando las consultas.**

*Comando*

``` sql
EXPLAIN SELECT * FROM cliente INNER JOIN pedido ON cliente.codigo_cliente = pedido.codigo_cliente WHERE cliente.nombre_cliente LIKE 'A%';
```

*Salida*

``` sql
+----+-------------+---------+------------+------+----------------+----------------+---------+-----------------------------------+------+----------+-------------+
| id | select_type | table   | partitions | type | possible_keys  | key            | key_len | ref                               | rows | filtered | Extra       |
+----+-------------+---------+------------+------+----------------+----------------+---------+-----------------------------------+------+----------+-------------+
|  1 | SIMPLE      | cliente | NULL       | ALL  | PRIMARY        | NULL           | NULL    | NULL                              |   36 |    11.11 | Using where |
|  1 | SIMPLE      | pedido  | NULL       | ref  | codigo_cliente | codigo_cliente | 4       | jardineria.cliente.codigo_cliente |    1 |   100.00 | NULL        |
+----+-------------+---------+------------+------+----------------+----------------+---------+-----------------------------------+------+----------+-------------+
```

- **¿Por qué no es posible optimizar el tiempo de ejecución de las siguientes consultas, incluso haciendo uso de índices?**

*Comando*

``` sql
SELECT *
FROM cliente INNER JOIN pedido
ON cliente.codigo_cliente = pedido.codigo_cliente
WHERE cliente.nombre_cliente LIKE '%A%';

SELECT *
FROM cliente INNER JOIN pedido
ON cliente.codigo_cliente = pedido.codigo_cliente
WHERE cliente.nombre_cliente LIKE '%A';
```

- **Crea un índice de tipo FULLTEXT sobre las columnas nombre y descripcion de la tabla producto.**

*Comando*

``` sql

```

*Salida*

``` sql

```

- **Una vez creado el índice del ejercicio anterior realiza las siguientes consultas haciendo uso de la función MATCH, para buscar todos los productos que:**

    - **Contienen la palabra planta en el nombre o en la descripción. - Realice una consulta para cada uno de los modos de búsqueda full-text que existen en MySQL (IN NATURAL LANGUAGE MODE, IN BOOLEAN MODE y WITH QUERY EXPANSION) y compare los resultados que ha obtenido en cada caso.**

    *Comando*

    ``` sql

    ```

    *Salida*

    ``` sql

    ```

    - **Contienen la palabra planta seguida de cualquier carácter o conjunto de caracteres, en el nombre o en la descripción.**

     *Comando*

    ``` sql

    ```

    *Salida*

    ``` sql

    ```

    - **Empiezan con la palabra planta en el nombre o en la descripción.**

     *Comando*

    ``` sql

    ```

    *Salida*

    ``` sql

    ```

    - **Contienen la palabra tronco o la palabra árbol en el nombre o en la descripción.**

     *Comando*

    ``` sql

    ```

    *Salida*

    ``` sql

    ```

    - **Contienen la palabra tronco y la palabra árbol en el nombre o en la descripción.**

     *Comando*

    ``` sql

    ```

    *Salida*

    ``` sql

    ```

    - **Contienen la palabra tronco pero no contienen la palabra árbol en el nombre o en la descripción.**

     *Comando*

    ``` sql

    ```

    *Salida*

    ``` sql

    ```

    - **Contiene la frase proviene de las costas en el nombre o en la descripción.**

     *Comando*

    ``` sql

    ```

    *Salida*

    ``` sql

    ```

    - **Crea un índice de tipo INDEX compuesto por las columnas apellido_contacto y nombre_contacto de la tabla cliente.**

     *Comando*

    ``` sql

    ```

    *Salida*

    ``` sql

    ```

    - **Una vez creado el índice del ejercicio anterior realice las siguientes consultas haciendo uso de EXPLAIN:**

        - **Busca el cliente Javier Villar. ¿Cuántas filas se han examinado hasta encontrar el resultado?**

        *Comando*

        ``` sql

        ```

        *Salida*

        ``` sql

        ```

        - **Busca el cliente anterior utilizando solamente el apellido Villar.**

         *Comando*

        ``` sql

        ```

        *Salida*

        ``` sql

        ```

        - **¿Cuántas filas se han examinado hasta encontrar el resultado?**

         *Comando*

        ``` sql

        ```

        *Salida*

        ``` sql

        ```

        - **Busca el cliente anterior utilizando solamente el nombre Javier. ¿Cuántas filas se han examinado hasta encontrar el resultado? ¿Qué ha ocurrido en este caso?**

         *Comando*

        ``` sql

        ```

        *Salida*

        ``` sql

        ```

    - **Calcula cuál podría ser un buen valor para crear un índice sobre un prefijo de la columna nombre_cliente de la tabla cliente. Tenga en cuenta que un buen valor será aquel que nos permita utilizar el menor número de caracteres para diferenciar todos los valores que existen en la columna sobre la que estamos creando el índice.**

        - **En primer lugar calculamos cuántos valores distintos existen en la columna nombre_cliente. Necesitarás utilizar la función COUNT y DISTINCT.**

         *Comando*

        ``` sql

        ```

        *Salida*

        ``` sql

        ```

        - **Haciendo uso de la función LEFT ve calculando el número de caracteres que necesitas utilizar como prefijo para diferenciar todos los valores de la columna. Necesitarás la función COUNT, DISTINCT y LEFT.**

         *Comando*

        ``` sql

        ```

        *Salida*

        ``` sql

        ```

        - **Una vez que hayas encontrado el valor adecuado para el prefijo, crea el índice sobre la columna nombre_cliente de la tabla cliente.**

         *Comando*

        ``` sql

        ```

        *Salida*

        ``` sql

        ```

        - **Ejecuta algunas consultas de prueba sobre el índice que acabas de crear.**

         *Comando*

        ``` sql

        ```

        *Salida*

        ``` sql

        ```

### Vistas

- **Escriba una vista que se llame listado_pagos_clientes que muestre un listado donde aparezcan todos los clientes y los pagos que ha realizado cada uno de ellos. La vista deberá tener las siguientes columnas: nombre y apellidos del cliente concatenados, teléfono, ciudad, pais, fecha_pago, total del pago, id de la transacción**

*Comando*

``` sql

```

*Salida*

``` sql

```

- **Escriba una vista que se llame listado_pedidos_clientes que muestre un listado donde aparezcan todos los clientes y los pedidos que ha realizado cada uno de ellos. La vista deberá tener las siguientes columnas: código del cliente, nombre y apellidos del cliente concatendados, teléfono, ciudad, pais, código del pedido, fecha del pedido, fecha esperada, fecha de entrega y la cantidad total del pedido, que será la suma del producto de todas las cantidades por el precio de cada unidad, que aparecen en cada línea de pedido.**

*Comando*

``` sql

```

*Salida*

``` sql

```

- **Utilice las vistas que ha creado en los pasos anteriores para devolver un listado de los clientes de la ciudad de Madrid que han realizado pagos.**

*Comando*

``` sql

```

*Salida*

``` sql

```

- **Utilice las vistas que ha creado en los pasos anteriores para devolver un listado de los clientes que todavía no han recibido su pedido.**

*Comando*

``` sql

```

*Salida*

``` sql

```

- **Utilice las vistas que ha creado en los pasos anteriores para calcular el número de pedidos que se ha realizado cada uno de los clientes.**

*Comando*

``` sql

```

*Salida*

``` sql

```

- **Utilice las vistas que ha creado en los pasos anteriores para calcular el valor del pedido máximo y mínimo que ha realizado cada cliente.**

*Comando*

``` sql

```

*Salida*

``` sql

```

- **Modifique el nombre de las vista listado_pagos_clientes y asígnele el nombre listado_de_pagos. Una vez que haya modificado el nombre de la vista ejecute una consulta utilizando el nuevo nombre de la vista para comprobar que sigue funcionando correctamente.**

*Comando*

``` sql

```

*Salida*

``` sql

```

- **Elimine las vistas que ha creado en los pasos anteriores.**

*Comando*

``` sql

```

*Salida*

``` sql

```









