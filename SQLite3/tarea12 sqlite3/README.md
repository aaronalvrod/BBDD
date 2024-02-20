# Repasando consultas II

## Tablas

**Tabla cliente**

``` sql
┌────┬───────────┬───────────┬───────────┬─────────┬───────────┐
│ ID │  nombre   │ apellido1 │ apellido2 │ ciudad  │ categoria │
├────┼───────────┼───────────┼───────────┼─────────┼───────────┤
│ 1  │ Aarón     │ Rivero    │ Gómez     │ Almería │ 100       │
│ 2  │ Adela     │ Salas     │ Díaz      │ Granada │ 200       │
│ 3  │ Adolfo    │ Rubio     │ Flores    │ Sevilla │           │
│ 4  │ Adrián    │ Suárez    │           │ Jaén    │ 300       │
│ 5  │ Marcos    │ Loyola    │ Méndez    │ Almería │ 200       │
│ 6  │ María     │ Santana   │ Moreno    │ Cádiz   │ 100       │
│ 7  │ Pilar     │ Ruiz      │           │ Sevilla │ 300       │
│ 8  │ Pepe      │ Ruiz      │ Santana   │ Huelva  │ 200       │
│ 9  │ Guillermo │ López     │ Gómez     │ Granada │ 225       │
│ 10 │ Daniel    │ Santana   │ Loyola    │ Sevilla │ 125       │
└────┴───────────┴───────────┴───────────┴─────────┴───────────┘
```

**Tabla comercial**

``` sql
┌────┬─────────┬───────────┬───────────┬───────────┐
│ ID │ NOMBRE  │ apellido1 │ apellido2 │ categoria │
├────┼─────────┼───────────┼───────────┼───────────┤
│ 1  │ Daniel  │ Sáez      │ Vega      │ 0.15      │
│ 2  │ Juan    │ Gómez     │ López     │ 0.13      │
│ 3  │ Diego   │ Flores    │ Salas     │ 0.11      │
│ 4  │ Marta   │ Herrera   │ Gil       │ 0.14      │
│ 5  │ Antonio │ Carretero │ Ortega    │ 0.12      │
│ 6  │ Manuel  │ Domínguez │ Hernández │ 0.13      │
│ 7  │ Antonio │ Vega      │ Hernández │ 0.11      │
│ 8  │ Alfredo │ Ruiz      │ Flores    │ 0.05      │
└────┴─────────┴───────────┴───────────┴───────────┘
```

**Tabla pedido**

``` sql
┌────┬─────────┬────────────┬────────────┬──────────────┐
│ ID │  total  │   fecha    │ id_cliente │ id_comercial │
├────┼─────────┼────────────┼────────────┼──────────────┤
│ 1  │ 150.5   │ 2017-10-05 │ 5          │ 2            │
│ 2  │ 270.65  │ 2016-09-10 │ 1          │ 5            │
│ 3  │ 65.26   │ 2017-10-05 │ 2          │ 1            │
│ 4  │ 110.5   │ 2016-08-17 │ 8          │ 3            │
│ 5  │ 948.5   │ 2017-09-10 │ 5          │ 2            │
│ 6  │ 2400.6  │ 2016-07-27 │ 7          │ 1            │
│ 7  │ 5760.0  │ 2015-09-10 │ 2          │ 1            │
│ 8  │ 1983.43 │ 2017-10-10 │ 4          │ 6            │
│ 9  │ 2480.4  │ 2016-10-10 │ 8          │ 3            │
│ 10 │ 250.45  │ 2015-06-27 │ 8          │ 2            │
│ 11 │ 75.29   │ 2016-08-17 │ 3          │ 7            │
│ 12 │ 3045.6  │ 2017-04-25 │ 2          │ 1            │
│ 13 │ 545.75  │ 2019-01-25 │ 6          │ 1            │
│ 14 │ 145.82  │ 2017-02-02 │ 6          │ 1            │
│ 15 │ 370.85  │ 2019-03-11 │ 1          │ 5            │
│ 16 │ 2389.23 │ 2019-03-11 │ 1          │ 5            │
└────┴─────────┴────────────┴────────────┴──────────────┘
```

## Consultas sobre una tabla

1. **Devuelve un listado con todos los pedidos que se han realizado. Los pedidos deben estar ordenados por la fecha de realización, mostrando en primer lugar los pedidos más recientes.**

*Consulta*

``` sql
SELECT * FROM pedido ORDER BY fecha DESC;
```

*Resultado*

``` sql
┌────┬─────────┬────────────┬────────────┬──────────────┐
│ ID │  total  │   fecha    │ id_cliente │ id_comercial │
├────┼─────────┼────────────┼────────────┼──────────────┤
│ 15 │ 370.85  │ 2019-03-11 │ 1          │ 5            │
│ 16 │ 2389.23 │ 2019-03-11 │ 1          │ 5            │
│ 13 │ 545.75  │ 2019-01-25 │ 6          │ 1            │
│ 8  │ 1983.43 │ 2017-10-10 │ 4          │ 6            │
│ 1  │ 150.5   │ 2017-10-05 │ 5          │ 2            │
│ 3  │ 65.26   │ 2017-10-05 │ 2          │ 1            │
│ 5  │ 948.5   │ 2017-09-10 │ 5          │ 2            │
│ 12 │ 3045.6  │ 2017-04-25 │ 2          │ 1            │
│ 14 │ 145.82  │ 2017-02-02 │ 6          │ 1            │
│ 9  │ 2480.4  │ 2016-10-10 │ 8          │ 3            │
│ 2  │ 270.65  │ 2016-09-10 │ 1          │ 5            │
│ 4  │ 110.5   │ 2016-08-17 │ 8          │ 3            │
│ 11 │ 75.29   │ 2016-08-17 │ 3          │ 7            │
│ 6  │ 2400.6  │ 2016-07-27 │ 7          │ 1            │
│ 7  │ 5760.0  │ 2015-09-10 │ 2          │ 1            │
│ 10 │ 250.45  │ 2015-06-27 │ 8          │ 2            │
└────┴─────────┴────────────┴────────────┴──────────────┘
```

2. **Devuelve todos los datos de los dos pedidos de mayor valor.**

*Consulta*

``` sql
SELECT * FROM pedido ORDER BY total DESC LIMIT 2; 
```

*Resultado*

``` sql
┌────┬────────┬────────────┬────────────┬──────────────┐
│ ID │ total  │   fecha    │ id_cliente │ id_comercial │
├────┼────────┼────────────┼────────────┼──────────────┤
│ 7  │ 5760.0 │ 2015-09-10 │ 2          │ 1            │
│ 12 │ 3045.6 │ 2017-04-25 │ 2          │ 1            │
└────┴────────┴────────────┴────────────┴──────────────┘
```

3. **Devuelve un listado con los identificadores de los clientes que han realizado algún pedido. Tenga en cuenta que no debe mostrar identificadores que estén repetidos.**

*Consulta*

``` sql
SELECT DISTINCT id_cliente FROM pedido ORDER BY id_cliente ASC;
```

*Resultado*

``` sql
┌────────────┐
│ id_cliente │
├────────────┤
│ 1          │
│ 2          │
│ 3          │
│ 4          │
│ 5          │
│ 6          │
│ 7          │
│ 8          │
└────────────┘
```

4. **Devuelve un listado de todos los pedidos que se realizaron durante el año 2017, cuya cantidad total sea superior a 500€.**

*Consulta*

``` sql
SELECT * FROM pedido WHERE fecha REGEXP "^2017" and total >= 500;
```

*Resultado*

``` sql
┌────┬─────────┬────────────┬────────────┬──────────────┐
│ ID │  total  │   fecha    │ id_cliente │ id_comercial │
├────┼─────────┼────────────┼────────────┼──────────────┤
│ 5  │ 948.5   │ 2017-09-10 │ 5          │ 2            │
│ 8  │ 1983.43 │ 2017-10-10 │ 4          │ 6            │
│ 12 │ 3045.6  │ 2017-04-25 │ 2          │ 1            │
└────┴─────────┴────────────┴────────────┴──────────────┘
```

5. **Devuelve un listado con el nombre y los apellidos de los comerciales que tienen una comisión entre 0.05 y 0.11.**

*Consulta*

``` sql

```

*Resultado*

``` sql

```

6. **Devuelve el valor de la comisión de mayor valor que existe en la tabla comercial.**

*Consulta*

``` sql

```

*Resultado*

``` sql

```

7. **Devuelve el identificador, nombre y primer apellido de aquellos clientes cuyo segundo apellido no es NULL. El listado deberá estar ordenado alfabéticamente por apellidos y nombre.**

*Consulta*

``` sql

```

*Resultado*

``` sql

```

8. **Devuelve un listado de los nombres de los clientes que empiezan por A y terminan por n y también los nombres que empiezan por P. El listado deberá estar ordenado alfabéticamente.**

*Consulta*

``` sql

```

*Resultado*

``` sql

```

9. **Devuelve un listado de los nombres de los clientes que no empiezan por A. El listado deberá estar ordenado alfabéticamente.**

*Consulta*

``` sql

```

*Resultado*

``` sql

```

10. **Devuelve un listado con los nombres de los comerciales que terminan por el o o. Tenga en cuenta que se deberán eliminar los nombres repetidos.**

*Consulta*

``` sql

```

*Resultado*

``` sql

```

---

## Consultas multitabla

1. **Devuelve un listado con el identificador, nombre y los apellidos de todos los clientes que han realizado algún pedido. El listado debe estar ordenado alfabéticamente y se deben eliminar los elementos repetidos.**

*Consulta*

``` sql

```

*Resultado*

``` sql

```

2. **Devuelve un listado que muestre todos los pedidos que ha realizado cada cliente. El resultado debe mostrar todos los datos de los pedidos y del cliente. El listado debe mostrar los datos de los clientes ordenados alfabéticamente.**

*Consulta*

``` sql

```

*Resultado*

``` sql

```

3. **Devuelve un listado que muestre todos los pedidos en los que ha participado un comercial. El resultado debe mostrar todos los datos de los pedidos y de los comerciales. El listado debe mostrar los datos de los comerciales ordenados alfabéticamente.**


*Consulta*

``` sql

```

*Resultado*

``` sql

```

4. **Devuelve un listado que muestre todos los clientes, con todos los pedidos que han realizado y con los datos de los comerciales asociados a cada pedido.**

*Consulta*

``` sql

```

*Resultado*

``` sql

```

5. **Devuelve un listado de todos los clientes que realizaron un pedido durante el año 2017, cuya cantidad esté entre 300 € y 1000 €.**

*Consulta*

``` sql

```

*Resultado*

``` sql

```

6. **Devuelve el nombre y los apellidos de todos los comerciales que ha participado en algún pedido realizado por María Santana Moreno.**

*Consulta*

``` sql

```

*Resultado*

``` sql

```

7. **Devuelve el nombre de todos los clientes que han realizado algún pedido con el comercial Daniel Sáez Vega.**

*Consulta*

``` sql

```

*Resultado*

``` sql

```

--- 

