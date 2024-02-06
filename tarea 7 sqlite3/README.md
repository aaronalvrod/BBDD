# Trabajo con subconsultas y funciones matemáticas

## Tablas

**Tabla Clientes**

``` sql
┌────────────┬─────────────────┬──────┬────────────────┐
│ id_cliente │     nombre      │ edad │   direccion    │
├────────────┼─────────────────┼──────┼────────────────┤
│ 1          │ Juan Pérez      │ 30   │ Calle A #123   │
│ 2          │ María Gómez     │ 25   │ Avenida B #456 │
│ 3          │ Carlos López    │ 35   │ Calle C #789   │
│ 4          │ Ana Martínez    │ 28   │ Avenida D #101 │
│ 5          │ Pedro Rodríguez │ 40   │ Calle E #234   │
│ 6          │ Laura Sánchez   │ 32   │ Avenida F #567 │
│ 7          │ Miguel González │ 27   │ Calle G #890   │
│ 8          │ Isabel Díaz     │ 38   │ Avenida H #111 │
│ 9          │ Francisco Ruiz  │ 33   │ Calle I #222   │
│ 10         │ Elena Torres    │ 29   │ Avenida J #333 │
└────────────┴─────────────────┴──────┴────────────────┘
```

**Tabla Coches**

``` sql
┌──────────┬────────────────┬────────────┬──────┬─────────┐
│ id_coche │     modelo     │   marca    │ año  │ precio  │
├──────────┼────────────────┼────────────┼──────┼─────────┤
│ 1        │ Sedán 2022     │ Toyota     │ 2022 │ 25000.0 │
│ 2        │ Hatchback 2021 │ Honda      │ 2021 │ 22000.0 │
│ 3        │ SUV 2023       │ Ford       │ 2023 │ 30000.0 │
│ 4        │ Coupé 2022     │ Chevrolet  │ 2022 │ 28000.0 │
│ 5        │ Camioneta 2023 │ Nissan     │ 2023 │ 32000.0 │
│ 6        │ Compacto 2021  │ Volkswagen │ 2021 │ 20000.0 │
│ 7        │ Híbrido 2022   │ Hyundai    │ 2022 │ 27000.0 │
│ 8        │ Deportivo 2023 │ Mazda      │ 2023 │ 35000.0 │
│ 9        │ Pickup 2022    │ Ram        │ 2022 │ 31000.0 │
│ 10       │ Eléctrico 2021 │ Tesla      │ 2021 │ 40000.0 │
└──────────┴────────────────┴────────────┴──────┴─────────┘
```

**Tabla Ventas**

``` sql
┌──────────┬────────────┬──────────┬─────────────┐
│ id_venta │ id_cliente │ id_coche │ fecha_venta │
├──────────┼────────────┼──────────┼─────────────┤
│ 1        │ 1          │ 1        │ 2023-01-15  │
│ 2        │ 2          │ 2        │ 2023-02-20  │
│ 3        │ 3          │ 3        │ 2023-03-25  │
│ 4        │ 4          │ 4        │ 2023-04-10  │
│ 5        │ 5          │ 5        │ 2023-05-05  │
│ 6        │ 6          │ 6        │ 2023-06-15  │
│ 7        │ 7          │ 7        │ 2023-07-20  │
│ 8        │ 8          │ 8        │ 2023-08-25  │
│ 9        │ 10         │ 10       │ 2023-10-05  │
└──────────┴────────────┴──────────┴─────────────┘
```
# Consultas

1º **Listar los coches vendidos con sus modelos y precios, junto con los nombres de los clientes que los compraron.**
  - *Cosas que debo de tener en cuenta:*
  - *¿Qué me están pidiendo?. ¿Qué es lo que no me han pedido?*

*Consulta* 

``` sql
SELECT V.id_venta, (SELECT modelo FROM Coches WHERE id_coche = V.id_coche) AS modelo, 
    (SELECT precio FROM Coches WHERE id_coche = V.id_coche) AS precio, 
    (SELECT nombre FROM Clientes WHERE id_cliente = V.id_cliente) AS nombre_cliente
FROM Ventas V;
``` 

*Resultado*

``` sql
┌──────────┬────────────────┬─────────┬─────────────────┐
│ id_venta │     modelo     │ precio  │ nombre_cliente  │
├──────────┼────────────────┼─────────┼─────────────────┤
│ 1        │ Sedán 2022     │ 25000.0 │ Juan Pérez      │
│ 2        │ Hatchback 2021 │ 22000.0 │ María Gómez     │
│ 3        │ SUV 2023       │ 30000.0 │ Carlos López    │
│ 4        │ Coupé 2022     │ 28000.0 │ Ana Martínez    │
│ 5        │ Camioneta 2023 │ 32000.0 │ Pedro Rodríguez │
│ 6        │ Compacto 2021  │ 20000.0 │ Laura Sánchez   │
│ 7        │ Híbrido 2022   │ 27000.0 │ Miguel González │
│ 8        │ Deportivo 2023 │ 35000.0 │ Isabel Díaz     │
│ 9        │ Eléctrico 2021 │ 40000.0 │ Elena Torres    │
└──────────┴────────────────┴─────────┴─────────────────┘
```


2º **Encontrar los clientes que han comprado coches con precios superiores al promedio de todos los coches vendidos.**
  - *Cosas que debo de tener en cuenta:*
    - *Precios superiores.*
    - *Obtener la media. AVG(precio)*

*Consulta*

``` sql
SELECT DISTINCT id_cliente, (SELECT nombre FROM Clientes WHERE id_cliente = id_cliente) AS nombre
FROM Ventas
WHERE (SELECT precio FROM Coches WHERE id_coche = Ventas.id_coche) > 
    (SELECT AVG(precio) FROM Coches);
```

*Resultado*

``` sql
┌────────────┬────────────┐
│ id_cliente │   nombre   │
├────────────┼────────────┤
│ 3          │ Juan Pérez │
│ 5          │ Juan Pérez │
│ 8          │ Juan Pérez │
│ 10         │ Juan Pérez │
└────────────┴────────────┘
```

3º **Mostrar los modelos de coches y sus precios que no han sido vendidos aún:**
  - *Cosas que debo de tener en cuenta:*
    - *Coches que han sido vendidos.*
    - *Quiero los coches que no han sido vendidos. NOT id_coche IN ventas*

*Consulta*

``` sql
SELECT modelo, precio
FROM Coches
WHERE id_coche NOT IN (SELECT id_coche FROM Ventas);
```

*Resultado*

``` sql
┌─────────────┬─────────┐
│   modelo    │ precio  │
├─────────────┼─────────┤
│ Pickup 2022 │ 31000.0 │
└─────────────┴─────────┘
```

4º **Calcular el total gastado por todos los clientes en coches:**
  - *Cosas que debo de tener en cuenta:*
    - *Me estan pidiendo la suma total de todos los coches vendidos, NO de aquellos que aún no se han vendido.*

*Consulta*

``` sql
SELECT SUM((SELECT precio FROM Coches WHERE id_coche = Ventas.id_coche)) AS total_gastado
FROM Ventas;
```

*Resultado*

``` sql
┌───────────────┐
│ total_gastado │
├───────────────┤
│ 259000.0      │
└───────────────┘
```

5º **Listar los coches vendidos junto con la fecha de venta y el nombre del cliente, ordenados por fecha de venta de forma descendente:**
  - *Cosas que debo de tener en cuenta:*
    - *¿Qué me están pidiendo?. ¿Por qué campo tengo que ordenadar. Es uno o más campos?*

*Consulta*

``` sql
SELECT id_venta, 
    (SELECT modelo FROM Coches WHERE id_coche = Ventas.id_coche) AS modelo, 
    fecha_venta, 
    (SELECT nombre FROM Clientes WHERE id_cliente = Ventas.id_cliente) AS nombre_cliente
FROM Ventas
ORDER BY fecha_venta DESC;
```

*Resultado*

``` sql
┌──────────┬────────────────┬─────────────┬─────────────────┐
│ id_venta │     modelo     │ fecha_venta │ nombre_cliente  │
├──────────┼────────────────┼─────────────┼─────────────────┤
│ 9        │ Eléctrico 2021 │ 2023-10-05  │ Elena Torres    │
│ 8        │ Deportivo 2023 │ 2023-08-25  │ Isabel Díaz     │
│ 7        │ Híbrido 2022   │ 2023-07-20  │ Miguel González │
│ 6        │ Compacto 2021  │ 2023-06-15  │ Laura Sánchez   │
│ 5        │ Camioneta 2023 │ 2023-05-05  │ Pedro Rodríguez │
│ 4        │ Coupé 2022     │ 2023-04-10  │ Ana Martínez    │
│ 3        │ SUV 2023       │ 2023-03-25  │ Carlos López    │
│ 2        │ Hatchback 2021 │ 2023-02-20  │ María Gómez     │
│ 1        │ Sedán 2022     │ 2023-01-15  │ Juan Pérez      │
└──────────┴────────────────┴─────────────┴─────────────────┘
```

6º **Encontrar el modelo de coche más caro.**
  - *Cosas que debo de tener en cuenta:*
    - *¿Qué me están pidiendo?. MAX*

*Consulta*

``` sql
SELECT modelo
FROM Coches
WHERE precio = (SELECT MAX(precio) FROM Coches);
```

*Resultado*

``` sql
┌────────────────┐
│     modelo     │
├────────────────┤
│ Eléctrico 2021 │
└────────────────┘
```

7º **Mostrar los clientes que han comprado al menos un coche (un coche o más) y la cantidad de coches comprados.**
  - *Cosas que debo de tener en cuenta:*
    - *¿Qué me están pidiendo?. COUNT*

*Consulta*

``` sql
SELECT id_cliente, (SELECT nombre FROM Clientes WHERE id_cliente = Ventas.id_cliente) AS nombre, 
    COUNT(id_coche) AS cantidad_coches_comprados
FROM Ventas
GROUP BY id_cliente
HAVING COUNT(id_coche) >= 1;
```

*Resultado*

``` sql
┌────────────┬─────────────────┬───────────────────────────┐
│ id_cliente │     nombre      │ cantidad_coches_comprados │
├────────────┼─────────────────┼───────────────────────────┤
│ 1          │ Juan Pérez      │ 1                         │
│ 2          │ María Gómez     │ 1                         │
│ 3          │ Carlos López    │ 1                         │
│ 4          │ Ana Martínez    │ 1                         │
│ 5          │ Pedro Rodríguez │ 1                         │
│ 6          │ Laura Sánchez   │ 1                         │
│ 7          │ Miguel González │ 1                         │
│ 8          │ Isabel Díaz     │ 1                         │
│ 10         │ Elena Torres    │ 1                         │
└────────────┴─────────────────┴───────────────────────────┘
```

8º **Encontrar los clientes que han comprado coches de la marca 'Toyota':**
  - *Cosas que debo de tener en cuenta:*
    - *¿Qué me están pidiendo?. Like | regexp | =. Tabla normalizada ?.*

*Consulta*

``` sql
SELECT DISTINCT id_cliente, (SELECT nombre FROM Clientes WHERE id_cliente = Ventas.id_cliente) AS nombre
FROM Ventas
WHERE id_coche IN (SELECT id_coche FROM Coches WHERE marca = 'Toyota');

```

*Resultado*

``` sql
┌────────────┬────────────┐
│ id_cliente │   nombre   │
├────────────┼────────────┤
│ 1          │ Juan Pérez │
└────────────┴────────────┘
```

9º **Calcular el promedio de edad de los clientes que han comprado coches de más de 25,000.**
  - *Cosas que debo de tener en cuenta:*
    - *¿Qué me están pidiendo?.*

*Consulta*

``` sql
SELECT AVG(edad) AS promedio_edad
FROM Clientes
WHERE id_cliente IN (SELECT id_cliente FROM Ventas WHERE id_coche IN (SELECT id_coche FROM Coches WHERE precio > 25000));
```

*Resultado*

``` sql
┌──────────────────┐
│  promedio_edad   │
├──────────────────┤
│ 32.8333333333333 │
└──────────────────┘
```

10º **Mostrar los modelos de coches y sus precios que fueron comprados por clientes mayores de 30 años.**
  - *Cosas que debo de tener en cuenta:*
    - *¿Qué me están pidiendo?.*

*Consulta*

``` sql
SELECT modelo, precio
FROM Coches
WHERE id_coche IN (SELECT id_coche FROM Ventas WHERE id_cliente IN (SELECT id_cliente FROM Clientes WHERE edad > 30));

```

*Resultado*

``` sql
┌────────────────┬─────────┐
│     modelo     │ precio  │
├────────────────┼─────────┤
│ SUV 2023       │ 30000.0 │
│ Camioneta 2023 │ 32000.0 │
│ Compacto 2021  │ 20000.0 │
│ Deportivo 2023 │ 35000.0 │
└────────────────┴─────────┘
```

11º **Encontrar los coches vendidos en el año 2022 junto con la cantidad total de ventas en ese año.**
  - *Cosas que debo de tener en cuenta:*
    - *¿Qué me están pidiendo?.*

*Consulta*

``` sql


```

*Resultado*

``` sql

```

12º **Listar los coches cuyos precios son mayores que el precio promedio de coches vendidos a clientes menores de 30 años.**
  -- *Cosas que debo de tener en cuenta:*
    -- *¿Qué me están pidiendo?. AVG*

*Consulta*

``` sql
SELECT modelo, precio
FROM Coches
WHERE precio > (SELECT AVG(precio) 
FROM Coches 
WHERE id_coche IN (SELECT id_coche 
FROM Ventas 
WHERE id_cliente IN (SELECT id_cliente 
FROM Clientes 
WHERE edad < 30)));
```

*Resultado*

``` sql
┌────────────────┬─────────┐
│     modelo     │ precio  │
├────────────────┼─────────┤
│ SUV 2023       │ 30000.0 │
│ Camioneta 2023 │ 32000.0 │
│ Deportivo 2023 │ 35000.0 │
│ Pickup 2022    │ 31000.0 │
│ Eléctrico 2021 │ 40000.0 │
└────────────────┴─────────┘
```

13º **Calcular el total de ventas por marca de coche, ordenado de forma descendente por el total de ventas:**
  - *Cosas que debo de tener en cuenta:*
    - *¿Qué me están pidiendo?. COUNT| DESC|ASC precio*

*Consulta*

``` sql
SELECT marca, COUNT(id_venta) AS total_ventas
FROM Coches
JOIN Ventas ON Coches.id_coche = Ventas.id_coche
GROUP BY marca
ORDER BY total_ventas DESC;
```

*Resultado*

``` sql
┌────────────┬──────────────┐
│   marca    │ total_ventas │
├────────────┼──────────────┤
│ Volkswagen │ 1            │
│ Toyota     │ 1            │
│ Tesla      │ 1            │
│ Nissan     │ 1            │
│ Mazda      │ 1            │
│ Hyundai    │ 1            │
│ Honda      │ 1            │
│ Ford       │ 1            │
│ Chevrolet  │ 1            │
└────────────┴──────────────┘
```