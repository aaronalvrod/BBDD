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
│ 11         │ Juan Pérez      │ 30   │ Calle A #123   │
│ 12         │ María Gómez     │ 25   │ Avenida B #456 │
│ 13         │ Carlos López    │ 35   │ Calle C #789   │
│ 14         │ Ana Martínez    │ 28   │ Avenida D #101 │
│ 15         │ Pedro Rodríguez │ 40   │ Calle E #234   │
│ 16         │ Laura Sánchez   │ 32   │ Avenida F #567 │
│ 17         │ Miguel González │ 27   │ Calle G #890   │
│ 18         │ Isabel Díaz     │ 38   │ Avenida H #111 │
│ 19         │ Francisco Ruiz  │ 33   │ Calle I #222   │
│ 20         │ Elena Torres    │ 29   │ Avenida J #333 │
│ 21         │ Juan Pérez      │ 30   │ Calle A #123   │
│ 22         │ María Gómez     │ 25   │ Avenida B #456 │
│ 23         │ Carlos López    │ 35   │ Calle C #789   │
│ 24         │ Ana Martínez    │ 28   │ Avenida D #101 │
│ 25         │ Pedro Rodríguez │ 40   │ Calle E #234   │
│ 26         │ Laura Sánchez   │ 32   │ Avenida F #567 │
│ 27         │ Miguel González │ 27   │ Calle G #890   │
│ 28         │ Isabel Díaz     │ 38   │ Avenida H #111 │
│ 29         │ Francisco Ruiz  │ 33   │ Calle I #222   │
│ 30         │ Elena Torres    │ 29   │ Avenida J #333 │
│ 31         │ Juan Pérez      │ 30   │ Calle A #123   │
│ 32         │ María Gómez     │ 25   │ Avenida B #456 │
│ 33         │ Carlos López    │ 35   │ Calle C #789   │
│ 34         │ Ana Martínez    │ 28   │ Avenida D #101 │
│ 35         │ Pedro Rodríguez │ 40   │ Calle E #234   │
│ 36         │ Laura Sánchez   │ 32   │ Avenida F #567 │
│ 37         │ Miguel González │ 27   │ Calle G #890   │
│ 38         │ Isabel Díaz     │ 38   │ Avenida H #111 │
│ 39         │ Francisco Ruiz  │ 33   │ Calle I #222   │
│ 40         │ Elena Torres    │ 29   │ Avenida J #333 │
│ 41         │ Juan Pérez      │ 30   │ Calle A #123   │
│ 42         │ María Gómez     │ 25   │ Avenida B #456 │
│ 43         │ Carlos López    │ 35   │ Calle C #789   │
│ 44         │ Ana Martínez    │ 28   │ Avenida D #101 │
│ 45         │ Pedro Rodríguez │ 40   │ Calle E #234   │
│ 46         │ Laura Sánchez   │ 32   │ Avenida F #567 │
│ 47         │ Miguel González │ 27   │ Calle G #890   │
│ 48         │ Isabel Díaz     │ 38   │ Avenida H #111 │
│ 49         │ Francisco Ruiz  │ 33   │ Calle I #222   │
│ 50         │ Elena Torres    │ 29   │ Avenida J #333 │
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
│ 11       │ Sedán 2022     │ Toyota     │ 2022 │ 25000.0 │
│ 12       │ Hatchback 2021 │ Honda      │ 2021 │ 22000.0 │
│ 13       │ SUV 2023       │ Ford       │ 2023 │ 30000.0 │
│ 14       │ Coupé 2022     │ Chevrolet  │ 2022 │ 28000.0 │
│ 15       │ Camioneta 2023 │ Nissan     │ 2023 │ 32000.0 │
│ 16       │ Compacto 2021  │ Volkswagen │ 2021 │ 20000.0 │
│ 17       │ Híbrido 2022   │ Hyundai    │ 2022 │ 27000.0 │
│ 18       │ Deportivo 2023 │ Mazda      │ 2023 │ 35000.0 │
│ 19       │ Pickup 2022    │ Ram        │ 2022 │ 31000.0 │
│ 20       │ Eléctrico 2021 │ Tesla      │ 2021 │ 40000.0 │
│ 21       │ Sedán 2022     │ Toyota     │ 2022 │ 25000.0 │
│ 22       │ Hatchback 2021 │ Honda      │ 2021 │ 22000.0 │
│ 23       │ SUV 2023       │ Ford       │ 2023 │ 30000.0 │
│ 24       │ Coupé 2022     │ Chevrolet  │ 2022 │ 28000.0 │
│ 25       │ Camioneta 2023 │ Nissan     │ 2023 │ 32000.0 │
│ 26       │ Compacto 2021  │ Volkswagen │ 2021 │ 20000.0 │
│ 27       │ Híbrido 2022   │ Hyundai    │ 2022 │ 27000.0 │
│ 28       │ Deportivo 2023 │ Mazda      │ 2023 │ 35000.0 │
│ 29       │ Pickup 2022    │ Ram        │ 2022 │ 31000.0 │
│ 30       │ Eléctrico 2021 │ Tesla      │ 2021 │ 40000.0 │
│ 31       │ Sedán 2022     │ Toyota     │ 2022 │ 25000.0 │
│ 32       │ Hatchback 2021 │ Honda      │ 2021 │ 22000.0 │
│ 33       │ SUV 2023       │ Ford       │ 2023 │ 30000.0 │
│ 34       │ Coupé 2022     │ Chevrolet  │ 2022 │ 28000.0 │
│ 35       │ Camioneta 2023 │ Nissan     │ 2023 │ 32000.0 │
│ 36       │ Compacto 2021  │ Volkswagen │ 2021 │ 20000.0 │
│ 37       │ Híbrido 2022   │ Hyundai    │ 2022 │ 27000.0 │
│ 38       │ Deportivo 2023 │ Mazda      │ 2023 │ 35000.0 │
│ 39       │ Pickup 2022    │ Ram        │ 2022 │ 31000.0 │
│ 40       │ Eléctrico 2021 │ Tesla      │ 2021 │ 40000.0 │
│ 41       │ Sedán 2022     │ Toyota     │ 2022 │ 25000.0 │
│ 42       │ Hatchback 2021 │ Honda      │ 2021 │ 22000.0 │
│ 43       │ SUV 2023       │ Ford       │ 2023 │ 30000.0 │
│ 44       │ Coupé 2022     │ Chevrolet  │ 2022 │ 28000.0 │
│ 45       │ Camioneta 2023 │ Nissan     │ 2023 │ 32000.0 │
│ 46       │ Compacto 2021  │ Volkswagen │ 2021 │ 20000.0 │
│ 47       │ Híbrido 2022   │ Hyundai    │ 2022 │ 27000.0 │
│ 48       │ Deportivo 2023 │ Mazda      │ 2023 │ 35000.0 │
│ 49       │ Pickup 2022    │ Ram        │ 2022 │ 31000.0 │
│ 50       │ Eléctrico 2021 │ Tesla      │ 2021 │ 40000.0 │
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
│ 10       │ 1          │ 1        │ 2023-01-15  │
│ 11       │ 2          │ 2        │ 2023-02-20  │
│ 12       │ 3          │ 3        │ 2023-03-25  │
│ 13       │ 4          │ 4        │ 2023-04-10  │
│ 14       │ 5          │ 5        │ 2023-05-05  │
│ 15       │ 6          │ 6        │ 2023-06-15  │
│ 16       │ 7          │ 7        │ 2023-07-20  │
│ 17       │ 8          │ 8        │ 2023-08-25  │
│ 18       │ 10         │ 10       │ 2023-10-05  │
│ 19       │ 1          │ 1        │ 2023-01-15  │
│ 20       │ 2          │ 2        │ 2023-02-20  │
│ 21       │ 3          │ 3        │ 2023-03-25  │
│ 22       │ 4          │ 4        │ 2023-04-10  │
│ 23       │ 5          │ 5        │ 2023-05-05  │
│ 24       │ 6          │ 6        │ 2023-06-15  │
│ 25       │ 7          │ 7        │ 2023-07-20  │
│ 26       │ 8          │ 8        │ 2023-08-25  │
│ 27       │ 10         │ 10       │ 2023-10-05  │
│ 28       │ 1          │ 1        │ 2023-01-15  │
│ 29       │ 2          │ 2        │ 2023-02-20  │
│ 30       │ 3          │ 3        │ 2023-03-25  │
│ 31       │ 4          │ 4        │ 2023-04-10  │
│ 32       │ 5          │ 5        │ 2023-05-05  │
│ 33       │ 6          │ 6        │ 2023-06-15  │
│ 34       │ 7          │ 7        │ 2023-07-20  │
│ 35       │ 8          │ 8        │ 2023-08-25  │
│ 36       │ 10         │ 10       │ 2023-10-05  │
│ 37       │ 1          │ 1        │ 2023-01-15  │
│ 38       │ 2          │ 2        │ 2023-02-20  │
│ 39       │ 3          │ 3        │ 2023-03-25  │
│ 40       │ 4          │ 4        │ 2023-04-10  │
│ 41       │ 5          │ 5        │ 2023-05-05  │
│ 42       │ 6          │ 6        │ 2023-06-15  │
│ 43       │ 7          │ 7        │ 2023-07-20  │
│ 44       │ 8          │ 8        │ 2023-08-25  │
│ 45       │ 10         │ 10       │ 2023-10-05  │
└──────────┴────────────┴──────────┴─────────────┘
```
# Consultas

-- **Listar los coches vendidos con sus modelos y precios, junto con los nombres de los clientes que los compraron.**
  -- *Cosas que debo de tener en cuenta:*
    -- *¿Qué me están pidiendo?. ¿Qué es lo que no me han pedido?*

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


-- **Encontrar los clientes que han comprado coches con precios superiores al promedio de todos los coches vendidos.**
  -- *Cosas que debo de tener en cuenta:*
    -- *Precios superiores.*
    -- *Obtener la media. AVG(precio)*

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

-- **Mostrar los modelos de coches y sus precios que no han sido vendidos aún:**
  -- *Cosas que debo de tener en cuenta:*
    -- *Coches que han sido vendidos.*
    -- *Quiero los coches que no han sido vendidos. NOT id_coche IN ventas*

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

-- **Calcu*lar el total gastado por todos los clientes en coches:**
  -- *Cosas que debo de tener en cuenta:*
    -- *Me estan pidiendo la suma total de todos los coches vendidos, NO de aquellos que aún no se han vendido.*

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

-- **Listar los coches vendidos junto con la fecha de venta y el nombre del cliente, ordenados por fecha de venta de forma descendente:**
  -- *Cosas que debo de tener en cuenta:*
    -- *¿Qué me están pidiendo?. ¿Por qué campo tengo que ordenadar. Es uno o más campos?*

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

-- **Encontrar el modelo de coche más caro.**
  -- *Cosas que debo de tener en cuenta:*
    -- *¿Qué me están pidiendo?. MAX*

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

-- **Mostrar los clientes que han comprado al menos un coche (un coche o más) y la cantidad de coches comprados.**
  -- *Cosas que debo de tener en cuenta:*
    -- *¿Qué me están pidiendo?. COUNT*

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

-- **Encontrar los clientes que han comprado coches de la marca 'Toyota':**
  -- *Cosas que debo de tener en cuenta:*
    -- *¿Qué me están pidiendo?. Like | regexp | =. Tabla normalizada ?.*

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

-- **Calcular el promedio de edad de los clientes que han comprado coches de más de 25,000.**
  -- *Cosas que debo de tener en cuenta:*
    -- *¿Qué me están pidiendo?.*

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

-- **Mostrar los modelos de coches y sus precios que fueron comprados por clientes mayores de 30 años.**
  -- *Cosas que debo de tener en cuenta:*
    -- *¿Qué me están pidiendo?.*

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

-- **Encontrar los coches vendidos en el año 2022 junto con la cantidad total de ventas en ese año.**
  -- *Cosas que debo de tener en cuenta:*
    -- *¿Qué me están pidiendo?.*

*Consulta*

``` sql


```

*Resultado*

``` sql

```

-- **Listar los coches cuyos precios son mayores que el precio promedio de coches vendidos a clientes menores de 30 años.**
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

-- **Calcular el total de ventas por marca de coche, ordenado de forma descendente por el total de ventas:**
  -- *Cosas que debo de tener en cuenta:*
    -- *¿Qué me están pidiendo?. COUNT| DESC|ASC precio*

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