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


-- **Encontrar los clientes que han comprado coches con precios superiores al promedio de todos los coches vendidos.**
  -- *Cosas que debo de tener en cuenta:*
    -- *Precios superiores.*
    -- *Obtener la media. AVG(precio)*

-- **Mostrar los modelos de coches y sus precios que no han sido vendidos aún:**
  -- *Cosas que debo de tener en cuenta:*
    -- *Coches que han sido vendidos.*
    -- *Quiero los coches que no han sido vendidos. NOT id_coche IN ventas*

-- **Calcu*lar el total gastado por todos los clientes en coches:**
  -- *Cosas que debo de tener en cuenta:*
    -- *Me estan pidiendo la suma total de todos los coches vendidos, NO de aquellos que aún no se han vendido.*

-- **Listar los coches vendidos junto con la fecha de venta y el nombre del cliente, ordenados por fecha de venta de forma descendente:**
  -- *Cosas que debo de tener en cuenta:*
    -- *¿Qué me están pidiendo?. ¿Por qué campo tengo que ordenadar. Es uno o más campos?*

-- **Encontrar el modelo de coche más caro.**
  -- *Cosas que debo de tener en cuenta:*
    -- *¿Qué me están pidiendo?. MAX*

-- **Mostrar los clientes que han comprado al menos un coche (un coche o más) y la cantidad de coches comprados.**
  -- *Cosas que debo de tener en cuenta:*
    -- *¿Qué me están pidiendo?. COUNT*

-- **Encontrar los clientes que han comprado coches de la marca 'Toyota':**
  -- *Cosas que debo de tener en cuenta:*
    -- *¿Qué me están pidiendo?. Like | regexp | =. Tabla normalizada ?.*

-- **Calcular el promedio de edad de los clientes que han comprado coches de más de 25,000.**
  -- *Cosas que debo de tener en cuenta:*
    -- *¿Qué me están pidiendo?.*

-- **Mostrar los modelos de coches y sus precios que fueron comprados por clientes mayores de 30 años.**
  -- *Cosas que debo de tener en cuenta:*
    -- *¿Qué me están pidiendo?.*

-- **Encontrar los coches vendidos en el año 2022 junto con la cantidad total de ventas en ese año.**
  -- *Cosas que debo de tener en cuenta:*
    -- *¿Qué me están pidiendo?.*

-- **Listar los coches cuyos precios son mayores que el precio promedio de coches vendidos a clientes menores de 30 años.**
  -- *Cosas que debo de tener en cuenta:*
    -- *¿Qué me están pidiendo?. AVG*

-- **Calcular el total de ventas por marca de coche, ordenado de forma descendente por el total de ventas:**
  -- *Cosas que debo de tener en cuenta:*
    -- *¿Qué me están pidiendo?. COUNT| DESC|ASC precio*

