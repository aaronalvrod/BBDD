# Consultas
## Consultas simples:

- Mostrar todos los clientes.

*Consulta*

``` sql
SELECT * FROM clientes;
```

*Resultado*

``` sql
+------------+------------+---------------+
| id_cliente | nombre     | direccion     |
+------------+------------+---------------+
|          1 | Cliente 1  | Dirección 1   |
|          2 | Cliente 2  | Dirección 2   |
|          3 | Cliente 3  | Dirección 3   |
|          4 | Cliente 4  | Dirección 4   |
|          5 | Cliente 5  | Dirección 5   |
|          6 | Cliente 6  | Dirección 6   |
|          7 | Cliente 7  | Dirección 7   |
|          8 | Cliente 8  | Dirección 8   |
|          9 | Cliente 9  | Dirección 9   |
|         10 | Cliente 10 | Dirección 10  |
|         11 | Cliente 11 | Dirección 11  |
|         12 | Cliente 12 | Dirección 12  |
|         13 | Cliente 13 | Dirección 13  |
|         14 | Cliente 14 | Dirección 14  |
|         15 | Cliente 15 | Dirección 15  |
|         16 | Cliente 16 | Dirección 16  |
|         17 | Cliente 17 | Dirección 17  |
|         18 | Cliente 18 | Dirección 18  |
|         19 | Cliente 19 | Dirección 19  |
|         20 | Cliente 20 | Dirección 20  |
+------------+------------+---------------+
```

- Mostrar todos los productos.

*Consulta*

``` sql
SELECT * FROM productos;
```

*Resultado*

``` sql
+-------------+-------------+--------+
| id_producto | nombre      | precio |
+-------------+-------------+--------+
|           1 | Producto 1  |  10.99 |
|           2 | Producto 2  |   20.5 |
|           3 | Producto 3  |  30.99 |
|           4 | Producto 4  |   40.5 |
|           5 | Producto 5  |  50.99 |
|           6 | Producto 6  |   60.5 |
|           7 | Producto 7  |  70.99 |
|           8 | Producto 8  |   80.5 |
|           9 | Producto 9  |  90.99 |
|          10 | Producto 10 |  100.5 |
|          11 | Producto 11 | 110.99 |
|          12 | Producto 12 |  120.5 |
|          13 | Producto 13 | 130.99 |
|          14 | Producto 14 |  140.5 |
|          15 | Producto 15 | 150.99 |
|          16 | Producto 16 |  160.5 |
|          17 | Producto 17 | 170.99 |
|          18 | Producto 18 |  180.5 |
|          19 | Producto 19 | 190.99 |
|          20 | Producto 20 |  200.5 |
+-------------+-------------+--------+

```

- Mostrar todas las órdenes.

*Consulta*

``` sql
SELECT * FROM ordenes;
```

*Resultado*

``` sql
+----------+------------+-------------+----------+
| id_orden | id_cliente | id_producto | cantidad |
+----------+------------+-------------+----------+
|        1 |          1 |           1 |        2 |
|        2 |          2 |           2 |        1 |
|        3 |          3 |           3 |        3 |
|        4 |          4 |           4 |        2 |
|        5 |          5 |           5 |        1 |
|        6 |          6 |           6 |        2 |
|        7 |          7 |           7 |        3 |
|        8 |          8 |           8 |        2 |
|        9 |          9 |           9 |        1 |
|       10 |         10 |          10 |        2 |
|       11 |         11 |          11 |        3 |
|       12 |         12 |          12 |        2 |
|       13 |         13 |          13 |        1 |
|       14 |         14 |          14 |        2 |
|       15 |         15 |          15 |        3 |
|       16 |         16 |          16 |        2 |
|       17 |         17 |          17 |        1 |
|       18 |         18 |          18 |        2 |
|       19 |         19 |          19 |        3 |
|       20 |         20 |          20 |        2 |
+----------+------------+-------------+----------+
```

- Mostrar los primeros 5 clientes ordenados por nombre.

*Consulta*

``` sql
SELECT * FROM clientes ORDER BY nombre LIMIT 5;
```

*Resultado*

``` sql
+------------+------------+---------------+
| id_cliente | nombre     | direccion     |
+------------+------------+---------------+
|          1 | Cliente 1  | Dirección 1   |
|         10 | Cliente 10 | Dirección 10  |
|         11 | Cliente 11 | Dirección 11  |
|         12 | Cliente 12 | Dirección 12  |
|         13 | Cliente 13 | Dirección 13  |
+------------+------------+---------------+
```

- Mostrar los productos con un precio mayor a 50.

*Consulta*

``` sql
SELECT * FROM productos WHERE precio > 50;
```

*Resultado*

``` sql
+-------------+-------------+--------+
| id_producto | nombre      | precio |
+-------------+-------------+--------+
|           5 | Producto 5  |  50.99 |
|           6 | Producto 6  |   60.5 |
|           7 | Producto 7  |  70.99 |
|           8 | Producto 8  |   80.5 |
|           9 | Producto 9  |  90.99 |
|          10 | Producto 10 |  100.5 |
|          11 | Producto 11 | 110.99 |
|          12 | Producto 12 |  120.5 |
|          13 | Producto 13 | 130.99 |
|          14 | Producto 14 |  140.5 |
|          15 | Producto 15 | 150.99 |
|          16 | Producto 16 |  160.5 |
|          17 | Producto 17 | 170.99 |
|          18 | Producto 18 |  180.5 |
|          19 | Producto 19 | 190.99 |
|          20 | Producto 20 |  200.5 |
+-------------+-------------+--------+
```

- Mostrar todas las órdenes realizadas por el cliente con ID 1.

*Consulta*

``` sql
SELECT * FROM ordenes WHERE id_cliente = 1;
```

*Resultado*

``` sql
+----------+------------+-------------+----------+
| id_orden | id_cliente | id_producto | cantidad |
+----------+------------+-------------+----------+
|        1 |          1 |           1 |        2 |
+----------+------------+-------------+----------+
```

- Mostrar los clientes cuyos nombres comienzan con la letra "M".

*Consulta*

``` sql
SELECT * FROM clientes WHERE nombre REGEXP "^M^;
```

*Resultado*

``` sql
No hay resultado ya que los clientes no estan ordenados por nombre sino por Cliente y su número.
```

- Mostrar las órdenes que contienen más de 2 productos.

*Consulta*

``` sql
SELECT * FROM ordenes where cantidad >= 2;
```

*Resultado*

``` sql
+----------+------------+-------------+----------+
| id_orden | id_cliente | id_producto | cantidad |
+----------+------------+-------------+----------+
|        1 |          1 |           1 |        2 |
|        3 |          3 |           3 |        3 |
|        4 |          4 |           4 |        2 |
|        6 |          6 |           6 |        2 |
|        7 |          7 |           7 |        3 |
|        8 |          8 |           8 |        2 |
|       10 |         10 |          10 |        2 |
|       11 |         11 |          11 |        3 |
|       12 |         12 |          12 |        2 |
|       14 |         14 |          14 |        2 |
|       15 |         15 |          15 |        3 |
|       16 |         16 |          16 |        2 |
|       18 |         18 |          18 |        2 |
|       19 |         19 |          19 |        3 |
|       20 |         20 |          20 |        2 |
+----------+------------+-------------+----------+

```

- Mostrar los productos ordenados por precio de forma descendente.

*Consulta*

``` sql
SELECT * FROM productos ORDER BY precio DESC;
```

*Resultado*

``` sql
+-------------+-------------+--------+
| id_producto | nombre      | precio |
+-------------+-------------+--------+
|          20 | Producto 20 |  200.5 |
|          19 | Producto 19 | 190.99 |
|          18 | Producto 18 |  180.5 |
|          17 | Producto 17 | 170.99 |
|          16 | Producto 16 |  160.5 |
|          15 | Producto 15 | 150.99 |
|          14 | Producto 14 |  140.5 |
|          13 | Producto 13 | 130.99 |
|          12 | Producto 12 |  120.5 |
|          11 | Producto 11 | 110.99 |
|          10 | Producto 10 |  100.5 |
|           9 | Producto 9  |  90.99 |
|           8 | Producto 8  |   80.5 |
|           7 | Producto 7  |  70.99 |
|           6 | Producto 6  |   60.5 |
|           5 | Producto 5  |  50.99 |
|           4 | Producto 4  |   40.5 |
|           3 | Producto 3  |  30.99 |
|           2 | Producto 2  |   20.5 |
|           1 | Producto 1  |  10.99 |
+-------------+-------------+--------+
```


## Consultas de ejemplo para practicar joins

- **Seleccionar todos los clientes y sus órdenes, incluso si no tienen órdenes**

*Consulta*

``` sql
SELECT clientes.*, ordenes.*
FROM clientes
FULL JOIN ordenes
ON clientes.id_cliente = ordenes.id_cliente;
```

*Resultado*

``` sql
```

- **Seleccionar todas las órdenes junto con los productos correspondientes**

*Consulta*

``` sql
SELECT ord.*, pro.* FROM ordenes ord JOIN productos pro on ord.id_producto = pro.id_producto;
```

*Resultado*

``` sql
+----------+------------+-------------+----------+-------------+-------------+--------+
| id_orden | id_cliente | id_producto | cantidad | id_producto | nombre      | precio |
+----------+------------+-------------+----------+-------------+-------------+--------+
|        1 |          1 |           1 |        2 |           1 | Producto 1  |  10.99 |
|        2 |          2 |           2 |        1 |           2 | Producto 2  |   20.5 |
|        3 |          3 |           3 |        3 |           3 | Producto 3  |  30.99 |
|        4 |          4 |           4 |        2 |           4 | Producto 4  |   40.5 |
|        5 |          5 |           5 |        1 |           5 | Producto 5  |  50.99 |
|        6 |          6 |           6 |        2 |           6 | Producto 6  |   60.5 |
|        7 |          7 |           7 |        3 |           7 | Producto 7  |  70.99 |
|        8 |          8 |           8 |        2 |           8 | Producto 8  |   80.5 |
|        9 |          9 |           9 |        1 |           9 | Producto 9  |  90.99 |
|       10 |         10 |          10 |        2 |          10 | Producto 10 |  100.5 |
|       11 |         11 |          11 |        3 |          11 | Producto 11 | 110.99 |
|       12 |         12 |          12 |        2 |          12 | Producto 12 |  120.5 |
|       13 |         13 |          13 |        1 |          13 | Producto 13 | 130.99 |
|       14 |         14 |          14 |        2 |          14 | Producto 14 |  140.5 |
|       15 |         15 |          15 |        3 |          15 | Producto 15 | 150.99 |
|       16 |         16 |          16 |        2 |          16 | Producto 16 |  160.5 |
|       17 |         17 |          17 |        1 |          17 | Producto 17 | 170.99 |
|       18 |         18 |          18 |        2 |          18 | Producto 18 |  180.5 |
|       19 |         19 |          19 |        3 |          19 | Producto 19 | 190.99 |
|       20 |         20 |          20 |        2 |          20 | Producto 20 |  200.5 |
+----------+------------+-------------+----------+-------------+-------------+--------+

```

- **Mostrar el nombre de los clientes que han realizado órdenes de productos que cuestan más de 50**

*Consulta*

``` sql
SELECT clientes.nombre FROM clientes JOIN ordenes ON clientes.id_cliente;
```

*Resultado*

``` sql

```

- **Obtener el nombre de los productos que no se han ordenado aún.**

*Consulta*

``` sql
SELECT productos.nombre FROM productos JOIN ordenes ON ordenes.id_producto != productos.id_producto;
```

*Resultado*

``` sql
+-------------+
| nombre      |
+-------------+
| Producto 20 |
| Producto 19 |
| Producto 18 |
| Producto 17 |
| Producto 16 |
| Producto 15 |
| Producto 14 |
| Producto 13 |
| Producto 12 |
| Producto 11 |
| Producto 10 |
| Producto 9  |
| Producto 8  |
| Producto 7  |
| Producto 6  |
| Producto 5  |
| Producto 4  |
| Producto 3  |
| Producto 2  |
| Producto 20 |
| Producto 19 |
| Producto 18 |
| Producto 17 |
| Producto 16 |
| Producto 15 |
| Producto 14 |
| Producto 13 |
| Producto 12 |
| Producto 11 |
| Producto 10 |
| Producto 9  |
| Producto 8  |
| Producto 7  |
| Producto 6  |
| Producto 5  |
| Producto 4  |
| Producto 3  |
| Producto 1  |
| Producto 20 |
| Producto 19 |
| Producto 18 |
| Producto 17 |
| Producto 16 |
| Producto 15 |
| Producto 14 |
| Producto 13 |
| Producto 12 |
| Producto 11 |
| Producto 10 |
| Producto 9  |
| Producto 8  |
| Producto 7  |
| Producto 6  |
| Producto 5  |
| Producto 4  |
| Producto 2  |
| Producto 1  |
| Producto 20 |
| Producto 19 |
| Producto 18 |
| Producto 17 |
| Producto 16 |
| Producto 15 |
| Producto 14 |
| Producto 13 |
| Producto 12 |
| Producto 11 |
| Producto 10 |
| Producto 9  |
| Producto 8  |
| Producto 7  |
| Producto 6  |
| Producto 5  |
| Producto 3  |
| Producto 2  |
| Producto 1  |
| Producto 20 |
| Producto 19 |
| Producto 18 |
| Producto 17 |
| Producto 16 |
| Producto 15 |
| Producto 14 |
| Producto 13 |
| Producto 12 |
| Producto 11 |
| Producto 10 |
| Producto 9  |
| Producto 8  |
| Producto 7  |
| Producto 6  |
| Producto 4  |
| Producto 3  |
| Producto 2  |
| Producto 1  |
| Producto 20 |
| Producto 19 |
| Producto 18 |
| Producto 17 |
| Producto 16 |
| Producto 15 |
| Producto 14 |
| Producto 13 |
| Producto 12 |
| Producto 11 |
| Producto 10 |
| Producto 9  |
| Producto 8  |
| Producto 7  |
| Producto 5  |
| Producto 4  |
| Producto 3  |
| Producto 2  |
| Producto 1  |
| Producto 20 |
| Producto 19 |
| Producto 18 |
| Producto 17 |
| Producto 16 |
| Producto 15 |
| Producto 14 |
| Producto 13 |
| Producto 12 |
| Producto 11 |
| Producto 10 |
| Producto 9  |
| Producto 8  |
| Producto 6  |
| Producto 5  |
| Producto 4  |
| Producto 3  |
| Producto 2  |
| Producto 1  |
| Producto 20 |
| Producto 19 |
| Producto 18 |
| Producto 17 |
| Producto 16 |
| Producto 15 |
| Producto 14 |
| Producto 13 |
| Producto 12 |
| Producto 11 |
| Producto 10 |
| Producto 9  |
| Producto 7  |
| Producto 6  |
| Producto 5  |
| Producto 4  |
| Producto 3  |
| Producto 2  |
| Producto 1  |
| Producto 20 |
| Producto 19 |
| Producto 18 |
| Producto 17 |
| Producto 16 |
| Producto 15 |
| Producto 14 |
| Producto 13 |
| Producto 12 |
| Producto 11 |
| Producto 10 |
| Producto 8  |
| Producto 7  |
| Producto 6  |
| Producto 5  |
| Producto 4  |
| Producto 3  |
| Producto 2  |
| Producto 1  |
| Producto 20 |
| Producto 19 |
| Producto 18 |
| Producto 17 |
| Producto 16 |
| Producto 15 |
| Producto 14 |
| Producto 13 |
| Producto 12 |
| Producto 11 |
| Producto 9  |
| Producto 8  |
| Producto 7  |
| Producto 6  |
| Producto 5  |
| Producto 4  |
| Producto 3  |
| Producto 2  |
| Producto 1  |
| Producto 20 |
| Producto 19 |
| Producto 18 |
| Producto 17 |
| Producto 16 |
| Producto 15 |
| Producto 14 |
| Producto 13 |
| Producto 12 |
| Producto 10 |
| Producto 9  |
| Producto 8  |
| Producto 7  |
| Producto 6  |
| Producto 5  |
| Producto 4  |
| Producto 3  |
| Producto 2  |
| Producto 1  |
| Producto 20 |
| Producto 19 |
| Producto 18 |
| Producto 17 |
| Producto 16 |
| Producto 15 |
| Producto 14 |
| Producto 13 |
| Producto 11 |
| Producto 10 |
| Producto 9  |
| Producto 8  |
| Producto 7  |
| Producto 6  |
| Producto 5  |
| Producto 4  |
| Producto 3  |
| Producto 2  |
| Producto 1  |
| Producto 20 |
| Producto 19 |
| Producto 18 |
| Producto 17 |
| Producto 16 |
| Producto 15 |
| Producto 14 |
| Producto 12 |
| Producto 11 |
| Producto 10 |
| Producto 9  |
| Producto 8  |
| Producto 7  |
| Producto 6  |
| Producto 5  |
| Producto 4  |
| Producto 3  |
| Producto 2  |
| Producto 1  |
| Producto 20 |
| Producto 19 |
| Producto 18 |
| Producto 17 |
| Producto 16 |
| Producto 15 |
| Producto 13 |
| Producto 12 |
| Producto 11 |
| Producto 10 |
| Producto 9  |
| Producto 8  |
| Producto 7  |
| Producto 6  |
| Producto 5  |
| Producto 4  |
| Producto 3  |
| Producto 2  |
| Producto 1  |
| Producto 20 |
| Producto 19 |
| Producto 18 |
| Producto 17 |
| Producto 16 |
| Producto 14 |
| Producto 13 |
| Producto 12 |
| Producto 11 |
| Producto 10 |
| Producto 9  |
| Producto 8  |
| Producto 7  |
| Producto 6  |
| Producto 5  |
| Producto 4  |
| Producto 3  |
| Producto 2  |
| Producto 1  |
| Producto 20 |
| Producto 19 |
| Producto 18 |
| Producto 17 |
| Producto 15 |
| Producto 14 |
| Producto 13 |
| Producto 12 |
| Producto 11 |
| Producto 10 |
| Producto 9  |
| Producto 8  |
| Producto 7  |
| Producto 6  |
| Producto 5  |
| Producto 4  |
| Producto 3  |
| Producto 2  |
| Producto 1  |
| Producto 20 |
| Producto 19 |
| Producto 18 |
| Producto 16 |
| Producto 15 |
| Producto 14 |
| Producto 13 |
| Producto 12 |
| Producto 11 |
| Producto 10 |
| Producto 9  |
| Producto 8  |
| Producto 7  |
| Producto 6  |
| Producto 5  |
| Producto 4  |
| Producto 3  |
| Producto 2  |
| Producto 1  |
| Producto 20 |
| Producto 19 |
| Producto 17 |
| Producto 16 |
| Producto 15 |
| Producto 14 |
| Producto 13 |
| Producto 12 |
| Producto 11 |
| Producto 10 |
| Producto 9  |
| Producto 8  |
| Producto 7  |
| Producto 6  |
| Producto 5  |
| Producto 4  |
| Producto 3  |
| Producto 2  |
| Producto 1  |
| Producto 20 |
| Producto 18 |
| Producto 17 |
| Producto 16 |
| Producto 15 |
| Producto 14 |
| Producto 13 |
| Producto 12 |
| Producto 11 |
| Producto 10 |
| Producto 9  |
| Producto 8  |
| Producto 7  |
| Producto 6  |
| Producto 5  |
| Producto 4  |
| Producto 3  |
| Producto 2  |
| Producto 1  |
| Producto 19 |
| Producto 18 |
| Producto 17 |
| Producto 16 |
| Producto 15 |
| Producto 14 |
| Producto 13 |
| Producto 12 |
| Producto 11 |
| Producto 10 |
| Producto 9  |
| Producto 8  |
| Producto 7  |
| Producto 6  |
| Producto 5  |
| Producto 4  |
| Producto 3  |
| Producto 2  |
| Producto 1  |
+-------------+
```

- **Mostrar el nombre del cliente, el producto y la cantidad para todas las órdenes**

*Consulta*

``` sql
SELECT clientes.nombre, productos.nombre, ordenes.cantidad FROM clientes JOIN productos ON productos.id_producto 
```

*Resultado*

``` sql
```

- **Obtener el nombre de los productos junto con los nombres de los clientes que han realizado órdenes de esos productos**

*Consulta*

``` sql
```

*Resultado*

``` sql
```

- **Mostrar todas las órdenes con sus clientes y productos, incluso si no hay órdenes**

*Consulta*

``` sql
```

*Resultado*

``` sql
```

- **Obtener el nombre de los clientes junto con el número total de órdenes que han realizado**

*Consulta*

``` sql
```

*Resultado*

``` sql
```

- **Mostrar todas las órdenes junto con el nombre del cliente y el nombre del producto**

*Consulta*

``` sql
```

*Resultado*

``` sql
```

- **Mostrar todas las órdenes con sus productos y clientes, incluso si no hay información de cliente.**

*Consulta*

``` sql
```

*Resultado*

``` sql
```

- **Obtener el nombre de los productos junto con el nombre de los clientes que han realizado órdenes de esos productos, incluyendo los productos que no han sido ordenados**

*Consulta*

``` sql
```

*Resultado*

``` sql
```

- **Mostrar todas las órdenes junto con el nombre del cliente y el nombre del producto, incluyendo las órdenes sin productos**

*Consulta*

``` sql
```

*Resultado*

``` sql
```

- **Obtener el nombre de los clientes junto con el número total de órdenes que han realizado, incluyendo los clientes que no han realizado órdenes.**

*Consulta*

``` sql
```

*Resultado*

``` sql
```

- **Mostrar todas las órdenes con sus clientes y productos, incluyendo las órdenes y productos que no tienen información.**

*Consulta*

``` sql
```

*Resultado*

``` sql
```
