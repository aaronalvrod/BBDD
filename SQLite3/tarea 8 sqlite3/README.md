# Trabajo con subconsultas y funciones matemáticas

## Tablas

**Tabla cliente**

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

**Tabla Reparacion**

``` sql
┌───────────────┬────────────┬──────────┬──────────────────┬────────────────────────────────────────┐
│ id_reparación │ id_cliente │ id_coche │ fecha_reparación │              descripción               │
├───────────────┼────────────┼──────────┼──────────────────┼────────────────────────────────────────┤
│ 1             │ 1          │ 1        │ 2023-05-15       │ Reparación de motor                    │
│ 2             │ 2          │ 3        │ 2023-06-20       │ Cambio de neumáticos                   │
│ 3             │ 3          │ 5        │ 2023-07-25       │ Reparación de frenos                   │
│ 4             │ 4          │ 2        │ 2023-08-10       │ Revisión general                       │
│ 5             │ 5          │ 4        │ 2023-09-05       │ Cambio de aceite                       │
│ 6             │ 6          │ 7        │ 2023-10-15       │ Alineación y balanceo                  │
│ 7             │ 7          │ 6        │ 2023-11-20       │ Reparación de sistema eléctrico        │
│ 8             │ 8          │ 8        │ 2023-12-25       │ Reparación de transmisión              │
│ 9             │ 9          │ 9        │ 2024-01-05       │ Reemplazo de bujías                    │
│ 10            │ 10         │ 10       │ 2024-02-10       │ Reparación de sistema de refrigeración │
│ 11            │ 1          │ 3        │ 2024-03-15       │ Cambio de filtro de aire               │
│ 12            │ 2          │ 2        │ 2024-04-20       │ Reparación de sistema de suspensión    │
│ 13            │ 3          │ 4        │ 2024-05-25       │ Reparación de sistema de escape        │
│ 14            │ 4          │ 5        │ 2024-06-10       │ Reemplazo de batería                   │
│ 15            │ 5          │ 6        │ 2024-07-05       │ Reparación de sistema de dirección     │
│ 16            │ 6          │ 8        │ 2024-08-15       │ Cambio de pastillas de freno           │
│ 17            │ 7          │ 10       │ 2024-09-20       │ Reparación de sistema de inyección     │
│ 18            │ 8          │ 1        │ 2024-10-25       │ Reparación de sistema de dirección     │
│ 19            │ 9          │ 3        │ 2024-11-05       │ Cambio de bujías                       │
│ 20            │ 10         │ 4        │ 2024-12-10       │ Reparación de sistema de refrigeración │
└───────────────┴────────────┴──────────┴──────────────────┴────────────────────────────────────────┘
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

- **Consulta para obtener el nombre y la edad de los clientes que han comprado coches de la marca Toyota.**

*Consulta*

``` sql
SELECT nombre, edad 
FROM clientes
WHERE id_cliente IN (SELECT id_cliente FROM coches WHERE marca = 'Toyota');
```

*Resultado*

``` sql
┌─────────────────┬──────┐
│     nombre      │ edad │
├─────────────────┼──────┤
│ Juan Pérez      │ 30   │
│ María Gómez     │ 25   │
│ Carlos López    │ 35   │
│ Ana Martínez    │ 28   │
│ Pedro Rodríguez │ 40   │
│ Laura Sánchez   │ 32   │
│ Miguel González │ 27   │
│ Isabel Díaz     │ 38   │
│ Francisco Ruiz  │ 33   │
│ Elena Torres    │ 29   │
└─────────────────┴──────┘
```

- **Consulta para calcular el precio promedio de los coches vendidos.**

*Consulta*

``` sql
SELECT AVG(precio) AS precio_promedio 
FROM coches;
```

*Resultado*

``` sql
┌─────────────────┐
│ precio_promedio │
├─────────────────┤
│ 29000.0         │
└─────────────────┘
```

- **Consulta para obtener el modelo y la marca de los coches vendidos a clientes menores de 30 años.**

*Consulta*

``` sql
SELECT modelo, marca 
FROM coches 
WHERE id_coche IN (SELECT id_coche FROM reparacion WHERE id_cliente IN (SELECT id_cliente FROM clientes WHERE edad < 30));
```

*Resultado*

``` sql
┌────────────────┬────────────┐
│     modelo     │   marca    │
├────────────────┼────────────┤
│ Hatchback 2021 │ Honda      │
│ SUV 2023       │ Ford       │
│ Coupé 2022     │ Chevrolet  │
│ Camioneta 2023 │ Nissan     │
│ Compacto 2021  │ Volkswagen │
│ Eléctrico 2021 │ Tesla      │
└────────────────┴────────────┘
```

- **Consulta para contar el número de coches vendidos de cada marca.**

*Consulta*

``` sql
SELECT marca, COUNT(*) AS num_coches_vendidos 
FROM coches 
GROUP BY marca;
```

*Resultado*

``` sql
┌────────────┬─────────────────────┐
│   marca    │ num_coches_vendidos │
├────────────┼─────────────────────┤
│ Chevrolet  │ 1                   │
│ Ford       │ 1                   │
│ Honda      │ 1                   │
│ Hyundai    │ 1                   │
│ Mazda      │ 1                   │
│ Nissan     │ 1                   │
│ Ram        │ 1                   │
│ Tesla      │ 1                   │
│ Toyota     │ 1                   │
│ Volkswagen │ 1                   │
└────────────┴─────────────────────┘
```

- **Consulta para obtener el nombre y la dirección de los clientes que han llevado a reparar sus coches en 2024.**

*Consulta*

``` sql
SELECT clientes.nombre, clientes.direccion
FROM clientes, reparacion
WHERE clientes.id_cliente = reparacion.id_cliente
AND reparacion.fecha_reparación BETWEEN '2024-01-01' AND '2024-12-31';
```

*Resultado*

``` sql
┌─────────────────┬────────────────┐
│     nombre      │   direccion    │
├─────────────────┼────────────────┤
│ Francisco Ruiz  │ Calle I #222   │
│ Elena Torres    │ Avenida J #333 │
│ Juan Pérez      │ Calle A #123   │
│ María Gómez     │ Avenida B #456 │
│ Carlos López    │ Calle C #789   │
│ Ana Martínez    │ Avenida D #101 │
│ Pedro Rodríguez │ Calle E #234   │
│ Laura Sánchez   │ Avenida F #567 │
│ Miguel González │ Calle G #890   │
│ Isabel Díaz     │ Avenida H #111 │
│ Francisco Ruiz  │ Calle I #222   │
│ Elena Torres    │ Avenida J #333 │
└─────────────────┴────────────────┘
```

- **Consulta para calcular el total gastado en reparaciones por cada cliente.**

*Consulta*

``` sql
SELECT nombre, (SELECT SUM(precio) FROM coches WHERE id_coche IN (SELECT id_coche FROM reparacion WHERE id_cliente = clientes.id_cliente)) AS total_gastado
FROM clientes;
```

*Resultado*

``` sql
┌─────────────────┬───────────────┐
│     nombre      │ total_gastado │
├─────────────────┼───────────────┤
│ Juan Pérez      │ 55000.0       │
│ María Gómez     │ 52000.0       │
│ Carlos López    │ 60000.0       │
│ Ana Martínez    │ 54000.0       │
│ Pedro Rodríguez │ 48000.0       │
│ Laura Sánchez   │ 62000.0       │
│ Miguel González │ 60000.0       │
│ Isabel Díaz     │ 60000.0       │
│ Francisco Ruiz  │ 61000.0       │
│ Elena Torres    │ 68000.0       │
└─────────────────┴───────────────┘
```

- **Consulta para obtener el nombre y la edad de los clientes que han comprado coches de más de 30000 euros.**

*Consulta*

``` sql
SELECT nombre, edad 
FROM clientes
WHERE id_cliente IN (SELECT id_cliente FROM coches WHERE precio > 30000);
```

*Resultado*

``` sql
┌─────────────────┬──────┐
│     nombre      │ edad │
├─────────────────┼──────┤
│ Juan Pérez      │ 30   │
│ María Gómez     │ 25   │
│ Carlos López    │ 35   │
│ Ana Martínez    │ 28   │
│ Pedro Rodríguez │ 40   │
│ Laura Sánchez   │ 32   │
│ Miguel González │ 27   │
│ Isabel Díaz     │ 38   │
│ Francisco Ruiz  │ 33   │
│ Elena Torres    │ 29   │
└─────────────────┴──────┘
```

- **Consulta para calcular el precio medio de los coches vendidos en 2023.**

*Consulta*

``` sql
SELECT AVG(precio) AS precio_medio 
FROM coches 
WHERE año = 2023;
```

*Resultado*

``` sql
┌──────────────────┐
│   precio_medio   │
├──────────────────┤
│ 32333.3333333333 │
└──────────────────┘
```

- **Consulta para obtener el nombre y la dirección de los clientes que han comprado coches de la marca Ford.**

*Consulta*

``` sql
SELECT nombre, direccion 
FROM clientes 
WHERE id_cliente IN (SELECT id_cliente FROM coches WHERE marca = 'Ford');
```

*Resultado*

``` sql
┌─────────────────┬────────────────┐
│     nombre      │   direccion    │
├─────────────────┼────────────────┤
│ Juan Pérez      │ Calle A #123   │
│ María Gómez     │ Avenida B #456 │
│ Carlos López    │ Calle C #789   │
│ Ana Martínez    │ Avenida D #101 │
│ Pedro Rodríguez │ Calle E #234   │
│ Laura Sánchez   │ Avenida F #567 │
│ Miguel González │ Calle G #890   │
│ Isabel Díaz     │ Avenida H #111 │
│ Francisco Ruiz  │ Calle I #222   │
│ Elena Torres    │ Avenida J #333 │
└─────────────────┴────────────────┘
```

- **Consulta para contar el número de coches vendidos por año.**

*Consulta*

``` sql
SELECT año, COUNT(*) AS num_coches_vendidos 
FROM coches 
GROUP BY año;
```

*Resultado*

``` sql
┌──────┬─────────────────────┐
│ año  │ num_coches_vendidos │
├──────┼─────────────────────┤
│ 2021 │ 3                   │
│ 2022 │ 4                   │
│ 2023 │ 3                   │
└──────┴─────────────────────┘
```

- **Consulta para obtener el nombre y la edad de los clientes que han comprado coches de más de 30000 euros y llevado a reparar sus coches.**

*Consulta*

``` sql
SELECT nombre, edad 
FROM clientes 
WHERE id_cliente IN (SELECT id_cliente FROM coches WHERE precio > 30000) 
AND id_cliente IN (SELECT id_cliente FROM reparacion);
```

*Resultado*

``` sql
┌─────────────────┬──────┐
│     nombre      │ edad │
├─────────────────┼──────┤
│ Juan Pérez      │ 30   │
│ María Gómez     │ 25   │
│ Carlos López    │ 35   │
│ Ana Martínez    │ 28   │
│ Pedro Rodríguez │ 40   │
│ Laura Sánchez   │ 32   │
│ Miguel González │ 27   │
│ Isabel Díaz     │ 38   │
│ Francisco Ruiz  │ 33   │
│ Elena Torres    │ 29   │
└─────────────────┴──────┘
```

- **Consulta para calcular el precio total de los coches vendidos a clientes menores de 30 años.**

*Consulta*

``` sql
SELECT SUM(precio) AS precio_total 
FROM coches 
WHERE id_coche IN (SELECT id_coche FROM reparacion WHERE id_cliente IN (SELECT id_cliente FROM clientes WHERE edad < 30));
```

*Resultado*

``` sql
┌──────────────┐
│ precio_total │
├──────────────┤
│ 172000.0     │
└──────────────┘
```

- **Consulta para obtener el modelo y el año de los coches vendidos en 2023 y llevados a reparar.**

*Consulta*

``` sql
SELECT coches.modelo, coches.año
FROM coches, reparacion, ventas
WHERE reparacion.id_coche = coches.id_coche
AND reparacion.id_cliente = ventas.id_cliente
AND reparacion.id_coche = ventas.id_coche
AND ventas.fecha_venta BETWEEN '2023-01-01' AND '2023-12-31'
AND reparacion.fecha_reparación BETWEEN '2023-01-01' AND '2023-12-31';
```

*Resultado*

``` sql
┌────────────────┬──────┐
│     modelo     │ año  │
├────────────────┼──────┤
│ Sedán 2022     │ 2022 │
│ Deportivo 2023 │ 2023 │
└────────────────┴──────┘
```

- **Consulta para contar el número de coches vendidos por cliente.**

*Consulta*

``` sql
SELECT clientes.nombre, COUNT(ventas.id_coche) AS num_coches_vendidos
FROM clientes, ventas
WHERE clientes.id_cliente = ventas.id_cliente
GROUP BY clientes.id_cliente;
```

*Resultado*

``` sql
┌─────────────────┬─────────────────────┐
│     nombre      │ num_coches_vendidos │
├─────────────────┼─────────────────────┤
│ Juan Pérez      │ 1                   │
│ María Gómez     │ 1                   │
│ Carlos López    │ 1                   │
│ Ana Martínez    │ 1                   │
│ Pedro Rodríguez │ 1                   │
│ Laura Sánchez   │ 1                   │
│ Miguel González │ 1                   │
│ Isabel Díaz     │ 1                   │
│ Elena Torres    │ 1                   │
└─────────────────┴─────────────────────┘
```

- **Consulta para obtener el nombre y el precio de los coches vendidos a clientes mayores de 35 años.**

*Consulta*

``` sql
SELECT coches.modelo, coches.precio
FROM coches, ventas, clientes
WHERE ventas.id_cliente = clientes.id_cliente
AND ventas.id_coche = coches.id_coche
AND clientes.edad > 35;
```

*Resultado*

``` sql
┌────────────────┬─────────┐
│     modelo     │ precio  │
├────────────────┼─────────┤
│ Camioneta 2023 │ 32000.0 │
│ Deportivo 2023 │ 35000.0 │
└────────────────┴─────────┘
```

- **Consulta para calcular el precio medio de los coches vendidos en 2023 y llevados a reparar por clientes menores de 30 años.**

*Consulta*

``` sql
SELECT AVG(precio) AS precio_medio 
FROM coches 
WHERE id_coche IN (SELECT id_coche FROM reparacion WHERE id_cliente IN (SELECT id_cliente FROM clientes WHERE edad < 30)) 
AND año = 2023;
```

*Resultado*

``` sql
┌──────────────┐
│ precio_medio │
├──────────────┤
│ 31000.0      │
└──────────────┘
```

- **Consulta para obtener el modelo y el año de los coches vendidos por clientes que tienen una dirección que contiene la palabra "Avenida".**

*Consulta*

``` sql
SELECT coches.modelo, coches.año
FROM coches, clientes, reparacion
WHERE reparacion.id_cliente = clientes.id_cliente
  AND reparacion.id_coche = coches.id_coche
  AND clientes.direccion LIKE '%Avenida%';
```

*Resultado*

``` sql
┌────────────────┬──────┐
│     modelo     │ año  │
├────────────────┼──────┤
│ SUV 2023       │ 2023 │
│ Hatchback 2021 │ 2021 │
│ Híbrido 2022   │ 2022 │
│ Deportivo 2023 │ 2023 │
│ Eléctrico 2021 │ 2021 │
│ Hatchback 2021 │ 2021 │
│ Camioneta 2023 │ 2023 │
│ Deportivo 2023 │ 2023 │
│ Sedán 2022     │ 2022 │
│ Coupé 2022     │ 2022 │
└────────────────┴──────┘
```

- **Consulta para contar el número de reparaciones realizadas en 2024 por cada cliente.**

*Consulta*

``` sql
SELECT coches.modelo, coches.año
FROM coches, reparacion
WHERE coches.id_coche = reparacion.id_coche
AND reparacion.fecha_reparacion >= '2024-01-01' 
AND reparacion.fecha_reparacion <= '2024-12-31';
```

*Resultado*

``` sql
┌─────────────────┬───────────────────────┐
│     nombre      │ cantidad_reparaciones │
├─────────────────┼───────────────────────┤
│ Ana Martínez    │ 1                     │
│ Carlos López    │ 1                     │
│ Elena Torres    │ 2                     │
│ Francisco Ruiz  │ 2                     │
│ Isabel Díaz     │ 1                     │
│ Juan Pérez      │ 1                     │
│ Laura Sánchez   │ 1                     │
│ María Gómez     │ 1                     │
│ Miguel González │ 1                     │
│ Pedro Rodríguez │ 1                     │
└─────────────────┴───────────────────────┘
```
