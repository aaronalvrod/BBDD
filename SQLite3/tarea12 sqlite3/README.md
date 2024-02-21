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
SELECT nombre, apellido1 FROM comercial WHERE categoria BETWEEN 0.05 and 0.11;
```

*Resultado*

``` sql
┌─────────┬───────────┐
│ NOMBRE  │ apellido1 │
├─────────┼───────────┤
│ Diego   │ Flores    │
│ Antonio │ Vega      │
│ Alfredo │ Ruiz      │
└─────────┴───────────┘
```

6. **Devuelve el valor de la comisión de mayor valor que existe en la tabla comercial.**

*Consulta*

``` sql
SELECT MAX(categoria) FROM comercial;
```

*Resultado*

``` sql
┌────────────────┐
│ MAX(categoria) │
├────────────────┤
│ 0.15           │
└────────────────┘
```

7. **Devuelve el identificador, nombre y primer apellido de aquellos clientes cuyo segundo apellido no es NULL. El listado deberá estar ordenado alfabéticamente por apellidos y nombre.**

*Consulta*

``` sql
SELECT ID, nombre, apellido1 FROM cliente WHERE apellido2 IS NOT NULL ORDER BY apellido2, nombre;
```

*Resultado*

``` sql
┌────┬───────────┬───────────┐
│ ID │  nombre   │ apellido1 │
├────┼───────────┼───────────┤
│ 2  │ Adela     │ Salas     │
│ 3  │ Adolfo    │ Rubio     │
│ 1  │ Aarón     │ Rivero    │
│ 9  │ Guillermo │ López     │
│ 10 │ Daniel    │ Santana   │
│ 6  │ María     │ Santana   │
│ 5  │ Marcos    │ Loyola    │
│ 8  │ Pepe      │ Ruiz      │
└────┴───────────┴───────────┘
```

8. **Devuelve un listado de los nombres de los clientes que empiezan por A y terminan por n y también los nombres que empiezan por P. El listado deberá estar ordenado alfabéticamente.**

*Consulta*

``` sql
SELECT nombre FROM cliente WHERE (nombre LIKE 'A%n' OR nombre LIKE 'P%') ORDER BY nombre;
```

*Resultado*

``` sql
┌────────┐
│ nombre │
├────────┤
│ Aarón  │
│ Adrián │
│ Pepe   │
│ Pilar  │
└────────┘
```

9. **Devuelve un listado de los nombres de los clientes que no empiezan por A. El listado deberá estar ordenado alfabéticamente.**

*Consulta*

``` sql
SELECT nombre FROM cliente WHERE nombre NOT LIKE 'A%' ORDER BY nombre;
```

*Resultado*

``` sql
┌───────────┐
│  nombre   │
├───────────┤
│ Daniel    │
│ Guillermo │
│ Marcos    │
│ María     │
│ Pepe      │
│ Pilar     │
└───────────┘
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
SELECT DISTINCT c.ID, c.nombre, c.apellido1, c.apellido2 FROM cliente c INNER JOIN pedido p ON c.ID = p.id_cliente ORDER BY c.nombre, c.apellido1, c.apellido2;
```

*Resultado*

``` sql
┌────┬────────┬───────────┬───────────┐
│ ID │ nombre │ apellido1 │ apellido2 │
├────┼────────┼───────────┼───────────┤
│ 1  │ Aarón  │ Rivero    │ Gómez     │
│ 2  │ Adela  │ Salas     │ Díaz      │
│ 3  │ Adolfo │ Rubio     │ Flores    │
│ 4  │ Adrián │ Suárez    │           │
│ 5  │ Marcos │ Loyola    │ Méndez    │
│ 6  │ María  │ Santana   │ Moreno    │
│ 8  │ Pepe   │ Ruiz      │ Santana   │
│ 7  │ Pilar  │ Ruiz      │           │
└────┴────────┴───────────┴───────────┘
```

2. **Devuelve un listado que muestre todos los pedidos que ha realizado cada cliente. El resultado debe mostrar todos los datos de los pedidos y del cliente. El listado debe mostrar los datos de los clientes ordenados alfabéticamente.**

*Consulta*

``` sql
SELECT * FROM cliente c INNER JOIN pedido p ON c.ID = p.id_cliente ORDER BY c.nombre, c.apellido1, c.apellido2;
```

*Resultado*

``` sql
┌────┬────────┬───────────┬───────────┬─────────┬───────────┬────┬─────────┬────────────┬────────────┬──────────────┐
│ ID │ nombre │ apellido1 │ apellido2 │ ciudad  │ categoria │ ID │  total  │   fecha    │ id_cliente │ id_comercial │
├────┼────────┼───────────┼───────────┼─────────┼───────────┼────┼─────────┼────────────┼────────────┼──────────────┤
│ 1  │ Aarón  │ Rivero    │ Gómez     │ Almería │ 100       │ 2  │ 270.65  │ 2016-09-10 │ 1          │ 5            │
│ 1  │ Aarón  │ Rivero    │ Gómez     │ Almería │ 100       │ 15 │ 370.85  │ 2019-03-11 │ 1          │ 5            │
│ 1  │ Aarón  │ Rivero    │ Gómez     │ Almería │ 100       │ 16 │ 2389.23 │ 2019-03-11 │ 1          │ 5            │
│ 2  │ Adela  │ Salas     │ Díaz      │ Granada │ 200       │ 3  │ 65.26   │ 2017-10-05 │ 2          │ 1            │
│ 2  │ Adela  │ Salas     │ Díaz      │ Granada │ 200       │ 7  │ 5760.0  │ 2015-09-10 │ 2          │ 1            │
│ 2  │ Adela  │ Salas     │ Díaz      │ Granada │ 200       │ 12 │ 3045.6  │ 2017-04-25 │ 2          │ 1            │
│ 3  │ Adolfo │ Rubio     │ Flores    │ Sevilla │           │ 11 │ 75.29   │ 2016-08-17 │ 3          │ 7            │
│ 4  │ Adrián │ Suárez    │           │ Jaén    │ 300       │ 8  │ 1983.43 │ 2017-10-10 │ 4          │ 6            │
│ 5  │ Marcos │ Loyola    │ Méndez    │ Almería │ 200       │ 1  │ 150.5   │ 2017-10-05 │ 5          │ 2            │
│ 5  │ Marcos │ Loyola    │ Méndez    │ Almería │ 200       │ 5  │ 948.5   │ 2017-09-10 │ 5          │ 2            │
│ 6  │ María  │ Santana   │ Moreno    │ Cádiz   │ 100       │ 13 │ 545.75  │ 2019-01-25 │ 6          │ 1            │
│ 6  │ María  │ Santana   │ Moreno    │ Cádiz   │ 100       │ 14 │ 145.82  │ 2017-02-02 │ 6          │ 1            │
│ 8  │ Pepe   │ Ruiz      │ Santana   │ Huelva  │ 200       │ 4  │ 110.5   │ 2016-08-17 │ 8          │ 3            │
│ 8  │ Pepe   │ Ruiz      │ Santana   │ Huelva  │ 200       │ 9  │ 2480.4  │ 2016-10-10 │ 8          │ 3            │
│ 8  │ Pepe   │ Ruiz      │ Santana   │ Huelva  │ 200       │ 10 │ 250.45  │ 2015-06-27 │ 8          │ 2            │
│ 7  │ Pilar  │ Ruiz      │           │ Sevilla │ 300       │ 6  │ 2400.6  │ 2016-07-27 │ 7          │ 1            │
└────┴────────┴───────────┴───────────┴─────────┴───────────┴────┴─────────┴────────────┴────────────┴──────────────┘
```

3. **Devuelve un listado que muestre todos los pedidos en los que ha participado un comercial. El resultado debe mostrar todos los datos de los pedidos y de los comerciales. El listado debe mostrar los datos de los comerciales ordenados alfabéticamente.**


*Consulta*

``` sql
SELECT * FROM pedido p INNER JOIN cliente c ON p.id_cliente = c.ID INNER JOIN comercial co ON p.id_comercial = co.ID ORDER BY co.nombre, co.apellido1, co.apellido2;
```

*Resultado*

``` sql
┌────┬─────────┬────────────┬────────────┬──────────────┬────┬────────┬───────────┬───────────┬─────────┬───────────┬────┬─────────┬───────────┬───────────┬───────────┐
│ ID │  total  │   fecha    │ id_cliente │ id_comercial │ ID │ nombre │ apellido1 │ apellido2 │ ciudad  │ categoria │ ID │ NOMBRE  │ apellido1 │ apellido2 │ categoria │
├────┼─────────┼────────────┼────────────┼──────────────┼────┼────────┼───────────┼───────────┼─────────┼───────────┼────┼─────────┼───────────┼───────────┼───────────┤
│ 2  │ 270.65  │ 2016-09-10 │ 1          │ 5            │ 1  │ Aarón  │ Rivero    │ Gómez     │ Almería │ 100       │ 5  │ Antonio │ Carretero │ Ortega    │ 0.12      │
│ 15 │ 370.85  │ 2019-03-11 │ 1          │ 5            │ 1  │ Aarón  │ Rivero    │ Gómez     │ Almería │ 100       │ 5  │ Antonio │ Carretero │ Ortega    │ 0.12      │
│ 16 │ 2389.23 │ 2019-03-11 │ 1          │ 5            │ 1  │ Aarón  │ Rivero    │ Gómez     │ Almería │ 100       │ 5  │ Antonio │ Carretero │ Ortega    │ 0.12      │
│ 11 │ 75.29   │ 2016-08-17 │ 3          │ 7            │ 3  │ Adolfo │ Rubio     │ Flores    │ Sevilla │           │ 7  │ Antonio │ Vega      │ Hernández │ 0.11      │
│ 3  │ 65.26   │ 2017-10-05 │ 2          │ 1            │ 2  │ Adela  │ Salas     │ Díaz      │ Granada │ 200       │ 1  │ Daniel  │ Sáez      │ Vega      │ 0.15      │
│ 6  │ 2400.6  │ 2016-07-27 │ 7          │ 1            │ 7  │ Pilar  │ Ruiz      │           │ Sevilla │ 300       │ 1  │ Daniel  │ Sáez      │ Vega      │ 0.15      │
│ 7  │ 5760.0  │ 2015-09-10 │ 2          │ 1            │ 2  │ Adela  │ Salas     │ Díaz      │ Granada │ 200       │ 1  │ Daniel  │ Sáez      │ Vega      │ 0.15      │
│ 12 │ 3045.6  │ 2017-04-25 │ 2          │ 1            │ 2  │ Adela  │ Salas     │ Díaz      │ Granada │ 200       │ 1  │ Daniel  │ Sáez      │ Vega      │ 0.15      │
│ 13 │ 545.75  │ 2019-01-25 │ 6          │ 1            │ 6  │ María  │ Santana   │ Moreno    │ Cádiz   │ 100       │ 1  │ Daniel  │ Sáez      │ Vega      │ 0.15      │
│ 14 │ 145.82  │ 2017-02-02 │ 6          │ 1            │ 6  │ María  │ Santana   │ Moreno    │ Cádiz   │ 100       │ 1  │ Daniel  │ Sáez      │ Vega      │ 0.15      │
│ 4  │ 110.5   │ 2016-08-17 │ 8          │ 3            │ 8  │ Pepe   │ Ruiz      │ Santana   │ Huelva  │ 200       │ 3  │ Diego   │ Flores    │ Salas     │ 0.11      │
│ 9  │ 2480.4  │ 2016-10-10 │ 8          │ 3            │ 8  │ Pepe   │ Ruiz      │ Santana   │ Huelva  │ 200       │ 3  │ Diego   │ Flores    │ Salas     │ 0.11      │
│ 1  │ 150.5   │ 2017-10-05 │ 5          │ 2            │ 5  │ Marcos │ Loyola    │ Méndez    │ Almería │ 200       │ 2  │ Juan    │ Gómez     │ López     │ 0.13      │
│ 5  │ 948.5   │ 2017-09-10 │ 5          │ 2            │ 5  │ Marcos │ Loyola    │ Méndez    │ Almería │ 200       │ 2  │ Juan    │ Gómez     │ López     │ 0.13      │
│ 10 │ 250.45  │ 2015-06-27 │ 8          │ 2            │ 8  │ Pepe   │ Ruiz      │ Santana   │ Huelva  │ 200       │ 2  │ Juan    │ Gómez     │ López     │ 0.13      │
│ 8  │ 1983.43 │ 2017-10-10 │ 4          │ 6            │ 4  │ Adrián │ Suárez    │           │ Jaén    │ 300       │ 6  │ Manuel  │ Domínguez │ Hernández │ 0.13      │
└────┴─────────┴────────────┴────────────┴──────────────┴────┴────────┴───────────┴───────────┴─────────┴───────────┴────┴─────────┴───────────┴───────────┴───────────┘
```

4. **Devuelve un listado que muestre todos los clientes, con todos los pedidos que han realizado y con los datos de los comerciales asociados a cada pedido.**

*Consulta*

``` sql
SELECT * FROM cliente c LEFT JOIN pedido p ON c.ID = p.id_cliente LEFT JOIN comercial co ON p.id_comercial = co.ID;
```

*Resultado*

``` sql
┌────┬───────────┬───────────┬───────────┬─────────┬───────────┬────┬─────────┬────────────┬────────────┬──────────────┬────┬─────────┬───────────┬───────────┬───────────┐
│ ID │  nombre   │ apellido1 │ apellido2 │ ciudad  │ categoria │ ID │  total  │   fecha    │ id_cliente │ id_comercial │ ID │ NOMBRE  │ apellido1 │ apellido2 │ categoria │
├────┼───────────┼───────────┼───────────┼─────────┼───────────┼────┼─────────┼────────────┼────────────┼──────────────┼────┼─────────┼───────────┼───────────┼───────────┤
│ 1  │ Aarón     │ Rivero    │ Gómez     │ Almería │ 100       │ 2  │ 270.65  │ 2016-09-10 │ 1          │ 5            │ 5  │ Antonio │ Carretero │ Ortega    │ 0.12      │
│ 1  │ Aarón     │ Rivero    │ Gómez     │ Almería │ 100       │ 15 │ 370.85  │ 2019-03-11 │ 1          │ 5            │ 5  │ Antonio │ Carretero │ Ortega    │ 0.12      │
│ 1  │ Aarón     │ Rivero    │ Gómez     │ Almería │ 100       │ 16 │ 2389.23 │ 2019-03-11 │ 1          │ 5            │ 5  │ Antonio │ Carretero │ Ortega    │ 0.12      │
│ 2  │ Adela     │ Salas     │ Díaz      │ Granada │ 200       │ 3  │ 65.26   │ 2017-10-05 │ 2          │ 1            │ 1  │ Daniel  │ Sáez      │ Vega      │ 0.15      │
│ 2  │ Adela     │ Salas     │ Díaz      │ Granada │ 200       │ 12 │ 3045.6  │ 2017-04-25 │ 2          │ 1            │ 1  │ Daniel  │ Sáez      │ Vega      │ 0.15      │
│ 2  │ Adela     │ Salas     │ Díaz      │ Granada │ 200       │ 7  │ 5760.0  │ 2015-09-10 │ 2          │ 1            │ 1  │ Daniel  │ Sáez      │ Vega      │ 0.15      │
│ 3  │ Adolfo    │ Rubio     │ Flores    │ Sevilla │           │ 11 │ 75.29   │ 2016-08-17 │ 3          │ 7            │ 7  │ Antonio │ Vega      │ Hernández │ 0.11      │
│ 4  │ Adrián    │ Suárez    │           │ Jaén    │ 300       │ 8  │ 1983.43 │ 2017-10-10 │ 4          │ 6            │ 6  │ Manuel  │ Domínguez │ Hernández │ 0.13      │
│ 5  │ Marcos    │ Loyola    │ Méndez    │ Almería │ 200       │ 1  │ 150.5   │ 2017-10-05 │ 5          │ 2            │ 2  │ Juan    │ Gómez     │ López     │ 0.13      │
│ 5  │ Marcos    │ Loyola    │ Méndez    │ Almería │ 200       │ 5  │ 948.5   │ 2017-09-10 │ 5          │ 2            │ 2  │ Juan    │ Gómez     │ López     │ 0.13      │
│ 6  │ María     │ Santana   │ Moreno    │ Cádiz   │ 100       │ 14 │ 145.82  │ 2017-02-02 │ 6          │ 1            │ 1  │ Daniel  │ Sáez      │ Vega      │ 0.15      │
│ 6  │ María     │ Santana   │ Moreno    │ Cádiz   │ 100       │ 13 │ 545.75  │ 2019-01-25 │ 6          │ 1            │ 1  │ Daniel  │ Sáez      │ Vega      │ 0.15      │
│ 7  │ Pilar     │ Ruiz      │           │ Sevilla │ 300       │ 6  │ 2400.6  │ 2016-07-27 │ 7          │ 1            │ 1  │ Daniel  │ Sáez      │ Vega      │ 0.15      │
│ 8  │ Pepe      │ Ruiz      │ Santana   │ Huelva  │ 200       │ 4  │ 110.5   │ 2016-08-17 │ 8          │ 3            │ 3  │ Diego   │ Flores    │ Salas     │ 0.11      │
│ 8  │ Pepe      │ Ruiz      │ Santana   │ Huelva  │ 200       │ 10 │ 250.45  │ 2015-06-27 │ 8          │ 2            │ 2  │ Juan    │ Gómez     │ López     │ 0.13      │
│ 8  │ Pepe      │ Ruiz      │ Santana   │ Huelva  │ 200       │ 9  │ 2480.4  │ 2016-10-10 │ 8          │ 3            │ 3  │ Diego   │ Flores    │ Salas     │ 0.11      │
│ 9  │ Guillermo │ López     │ Gómez     │ Granada │ 225       │    │         │            │            │              │    │         │           │           │           │
│ 10 │ Daniel    │ Santana   │ Loyola    │ Sevilla │ 125       │    │         │            │            │              │    │         │           │           │           │
└────┴───────────┴───────────┴───────────┴─────────┴───────────┴────┴─────────┴────────────┴────────────┴──────────────┴────┴─────────┴───────────┴───────────┴───────────┘
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
SELECT DISTINCT co.nombre FROM cliente c INNER JOIN pedido p ON c.ID = p.id_cliente INNER JOIN comercial co ON p.id_comercial = co.ID WHERE c.nombre = 'María' AND c.apellido1 = 'Santana' AND c.apellido2 = 'Moreno';
```

*Resultado*

``` sql
┌────────┐
│ NOMBRE │
├────────┤
│ Daniel │
└────────┘
```

7. **Devuelve el nombre de todos los clientes que han realizado algún pedido con el comercial Daniel Sáez Vega.**

*Consulta*

``` sql
SELECT DISTINCT c.nombre FROM cliente c INNER JOIN pedido p ON c.ID = p.id_cliente INNER JOIN comercial co ON p.id_comercial = co.ID WHERE co.nombre = 'Daniel' AND co.apellido1 = 'Sáez' AND co.apellido2 = 'Vega';
```

*Resultado*

``` sql
┌────────┐
│ nombre │
├────────┤
│ Adela  │
│ Pilar  │
│ María  │
└────────┘
```

--- 

## Consultas resumen (Funciones)

1. **Calcula la cantidad total que suman todos los pedidos que aparecen en la tabla pedido.**

*Consulta*

``` sql
SELECT SUM(total) AS "Cantidad Total" FROM pedido;
```

*Resultado*

``` sql
┌────────────────┐
│ Cantidad Total │
├────────────────┤
│ 20992.83       │
└────────────────┘
```

2. **Calcula la cantidad media de todos los pedidos que aparecen en la tabla pedido.**

*Consulta*

``` sql
SELECT AVG(total) AS "Cantidad Media" FROM pedido;
```

*Resultado*

``` sql
┌────────────────┐
│ Cantidad Media │
├────────────────┤
│ 1312.051875    │
└────────────────┘
```

3. **Calcula el número total de comerciales distintos que aparecen en la tabla pedido.**

*Consulta*

``` sql
SELECT COUNT(DISTINCT id_comercial) AS "Total Comerciales" FROM pedido;
```

*Resultado*

``` sql
┌───────────────────┐
│ Total Comerciales │
├───────────────────┤
│ 6                 │
└───────────────────┘
```

4. **Calcula el número total de clientes que aparecen en la tabla cliente.**

*Consulta*

``` sql
SELECT COUNT(*) AS "Total Clientes" FROM cliente;
```

*Resultado*

``` sql
┌────────────────┐
│ Total Clientes │
├────────────────┤
│ 10             │
└────────────────┘
```

5. **Calcula cuál es la mayor cantidad que aparece en la tabla pedido.**

*Consulta*

``` sql
SELECT MAX(total) AS "Mayor Cantidad" FROM pedido;
```

*Resultado*

``` sql
┌────────────────┐
│ Mayor Cantidad │
├────────────────┤
│ 5760.0         │
└────────────────┘
```

6. **Calcula cuál es la menor cantidad que aparece en la tabla pedido.**

*Consulta*

``` sql
SELECT MIN(total) AS "Menor Cantidad" FROM pedido;
```

*Resultado*

``` sql
┌────────────────┐
│ Menor Cantidad │
├────────────────┤
│ 65.26          │
└────────────────┘
```

7. **Calcula cuál es el valor máximo de categoría para cada una de las ciudades que aparece en la tabla cliente.**

*Consulta*

``` sql
SELECT ciudad, MAX(categoria) AS "Máximo Valor Categoría" FROM cliente GROUP BY ciudad;
```

*Resultado*

``` sql
┌─────────┬────────────────────────┐
│ ciudad  │ Máximo Valor Categoría │
├─────────┼────────────────────────┤
│ Almería │ 200                    │
│ Cádiz   │ 100                    │
│ Granada │ 225                    │
│ Huelva  │ 200                    │
│ Jaén    │ 300                    │
│ Sevilla │ 300                    │
└─────────┴────────────────────────┘
```

8. **Calcula cuál es el máximo valor de los pedidos realizados durante el mismo día para cada uno de los clientes. Es decir, el mismo cliente puede haber realizado varios pedidos de diferentes cantidades el mismo día. Se pide que se calcule cuál es el pedido de máximo valor para cada uno de los días en los que un cliente ha realizado un pedido. Muestra el identificador del cliente, nombre, apellidos, la fecha y el valor de la cantidad.**

*Consulta*

``` sql
SELECT id_cliente, nombre, apellido1, apellido2, fecha, MAX(total) AS "Máximo Valor Pedido" FROM pedido INNER JOIN cliente ON pedido.id_cliente = cliente.ID GROUP BY id_cliente, fecha;
```

*Resultado*

``` sql
┌────────────┬────────┬───────────┬───────────┬────────────┬─────────────────────┐
│ id_cliente │ nombre │ apellido1 │ apellido2 │   fecha    │ Máximo Valor Pedido │
├────────────┼────────┼───────────┼───────────┼────────────┼─────────────────────┤
│ 1          │ Aarón  │ Rivero    │ Gómez     │ 2016-09-10 │ 270.65              
│
│ 1          │ Aarón  │ Rivero    │ Gómez     │ 2019-03-11 │ 2389.23             
│
│ 2          │ Adela  │ Salas     │ Díaz      │ 2015-09-10 │ 5760.0              
│
│ 2          │ Adela  │ Salas     │ Díaz      │ 2017-04-25 │ 3045.6              
│
│ 2          │ Adela  │ Salas     │ Díaz      │ 2017-10-05 │ 65.26               
│
│ 3          │ Adolfo │ Rubio     │ Flores    │ 2016-08-17 │ 75.29               
│
│ 4          │ Adrián │ Suárez    │           │ 2017-10-10 │ 1983.43             
│
│ 5          │ Marcos │ Loyola    │ Méndez    │ 2017-09-10 │ 948.5               
│
│ 5          │ Marcos │ Loyola    │ Méndez    │ 2017-10-05 │ 150.5               
│
│ 6          │ María  │ Santana   │ Moreno    │ 2017-02-02 │ 145.82              
│
│ 6          │ María  │ Santana   │ Moreno    │ 2019-01-25 │ 545.75              
│
│ 7          │ Pilar  │ Ruiz      │           │ 2016-07-27 │ 2400.6              
│
│ 8          │ Pepe   │ Ruiz      │ Santana   │ 2015-06-27 │ 250.45              
│
│ 8          │ Pepe   │ Ruiz      │ Santana   │ 2016-08-17 │ 110.5               
│
│ 8          │ Pepe   │ Ruiz      │ Santana   │ 2016-10-10 │ 2480.4              
│
└────────────┴────────┴───────────┴───────────┴────────────┴─────────────────────┘
```

9. **Calcula cuál es el máximo valor de los pedidos realizados durante el mismo día para cada uno de los clientes, teniendo en cuenta que sólo queremos mostrar aquellos pedidos que superen la cantidad de 2000 €.**

*Consulta*

``` sql
SELECT id_cliente, nombre, apellido1, apellido2, fecha, MAX(total) AS "Máximo Valor Pedido" FROM pedido INNER JOIN cliente ON pedido.id_cliente = cliente.ID WHERE total > 2000 GROUP BY id_cliente, fecha;
```

*Resultado*

``` sql
┌────────────┬────────┬───────────┬───────────┬────────────┬─────────────────────┐
│ id_cliente │ nombre │ apellido1 │ apellido2 │   fecha    │ Máximo Valor Pedido │
├────────────┼────────┼───────────┼───────────┼────────────┼─────────────────────┤
│ 1          │ Aarón  │ Rivero    │ Gómez     │ 2019-03-11 │ 2389.23             │
│ 2          │ Adela  │ Salas     │ Díaz      │ 2015-09-10 │ 5760.0              │
│ 2          │ Adela  │ Salas     │ Díaz      │ 2017-04-25 │ 3045.6              │
│ 7          │ Pilar  │ Ruiz      │           │ 2016-07-27 │ 2400.6              │
│ 8          │ Pepe   │ Ruiz      │ Santana   │ 2016-10-10 │ 2480.4              │
└────────────┴────────┴───────────┴───────────┴────────────┴─────────────────────┘
```

10. **Calcula el máximo valor de los pedidos realizados para cada uno de los comerciales durante la fecha 2016-08-17. Muestra el identificador del comercial, nombre, apellidos y total.**

*Consulta*

``` sql
SELECT id_comercial, nombre, apellido1, apellido2, MAX(total) AS "Máximo Valor Pedido" FROM pedido INNER JOIN comercial ON pedido.id_comercial = comercial.ID WHERE fecha = '2016-08-17' GROUP BY id_comercial;
```

*Resultado*

``` sql
┌──────────────┬─────────┬───────────┬───────────┬─────────────────────┐
│ id_comercial │ NOMBRE  │ apellido1 │ apellido2 │ Máximo Valor Pedido │
├──────────────┼─────────┼───────────┼───────────┼─────────────────────┤
│ 3            │ Diego   │ Flores    │ Salas     │ 110.5               │
│ 7            │ Antonio │ Vega      │ Hernández │ 75.29               │
└──────────────┴─────────┴───────────┴───────────┴─────────────────────┘
```

11. **Devuelve un listado con el identificador de cliente, nombre y apellidos y el número total de pedidos que ha realizado cada uno de clientes. Tenga en cuenta que pueden existir clientes que no han realizado ningún pedido. Estos clientes también deben aparecer en el listado indicando que el número de pedidos realizados es 0.**

*Consulta*

``` sql
SELECT c.ID, c.nombre, c.apellido1, c.apellido2, COUNT(p.id_cliente) AS "Número de Pedidos" FROM cliente c LEFT JOIN pedido p ON c.ID = p.id_cliente GROUP BY c.ID;
```

*Resultado*

``` sql
┌────┬───────────┬───────────┬───────────┬───────────────────┐
│ ID │  nombre   │ apellido1 │ apellido2 │ Número de Pedidos │
├────┼───────────┼───────────┼───────────┼───────────────────┤
│ 1  │ Aarón     │ Rivero    │ Gómez     │ 3                 │
│ 2  │ Adela     │ Salas     │ Díaz      │ 3                 │
│ 3  │ Adolfo    │ Rubio     │ Flores    │ 1                 │
│ 4  │ Adrián    │ Suárez    │           │ 1                 │
│ 5  │ Marcos    │ Loyola    │ Méndez    │ 2                 │
│ 6  │ María     │ Santana   │ Moreno    │ 2                 │
│ 7  │ Pilar     │ Ruiz      │           │ 1                 │
│ 8  │ Pepe      │ Ruiz      │ Santana   │ 3                 │
│ 9  │ Guillermo │ López     │ Gómez     │ 0                 │
│ 10 │ Daniel    │ Santana   │ Loyola    │ 0                 │
└────┴───────────┴───────────┴───────────┴───────────────────┘
```

12. **Devuelve un listado con el identificador de cliente, nombre y apellidos y el número total de pedidos que ha realizado cada uno de clientes durante el año 2017.**

*Consulta*

``` sql

```

*Resultado*

``` sql

```

13. **Devuelve un listado que muestre el identificador de cliente, nombre, primer apellido y el valor de la máxima cantidad del pedido realizado por cada uno de los clientes. El resultado debe mostrar aquellos clientes que no han realizado ningún pedido indicando que la máxima cantidad de sus pedidos realizados es 0.**

*Consulta*

``` sql
SELECT c.ID AS "Identificador de Cliente", c.nombre AS "Nombre", c.apellido1 AS "Primer Apellido", MAX(p.total) AS "Máxima Cantidad de Pedido" FROM cliente c LEFT JOIN pedido p ON c.ID = p.id_cliente GROUP BY c.ID, c.nombre, c.apellido1;
```

*Resultado*

``` sql
┌──────────────────────────┬───────────┬─────────────────┬───────────────────────────┐
│ Identificador de Cliente │  Nombre   │ Primer Apellido │ Máxima Cantidad de Pedido │
├──────────────────────────┼───────────┼─────────────────┼───────────────────────────┤
│ 1                        │ Aarón     │ Rivero          │ 2389.23                   │
│ 2                        │ Adela     │ Salas           │ 5760.0                    │
│ 3                        │ Adolfo    │ Rubio           │ 75.29                     │
│ 4                        │ Adrián    │ Suárez          │ 1983.43                   │
│ 5                        │ Marcos    │ Loyola          │ 948.5                     │
│ 6                        │ María     │ Santana         │ 545.75                    │
│ 7                        │ Pilar     │ Ruiz            │ 2400.6                    │
│ 8                        │ Pepe      │ Ruiz            │ 2480.4                    │
│ 9                        │ Guillermo │ López           │                           │
│ 10                       │ Daniel    │ Santana         │                           │
└──────────────────────────┴───────────┴─────────────────┴───────────────────────────┘
```

14. **Devuelve cuál ha sido el pedido de máximo valor que se ha realizado cada año.**

*Consulta*

``` sql

```

*Resultado*

``` sql

```

15. **Devuelve el número total de pedidos que se han realizado cada año.**

*Consulta*

``` sql

```

*Resultado*

``` sql

```

---

## Subconsultas

1. **Devuelve un listado con todos los pedidos que ha realizado Adela Salas Díaz. (Sin utilizar INNER JOIN).**

*Consulta*

``` sql
SELECT *
FROM pedido
WHERE id_cliente = (
    SELECT ID
    FROM cliente
    WHERE nombre = 'Adela' AND apellido1 = 'Salas' AND apellido2 = 'Díaz'
);
```

*Resultado*

``` sql
┌────┬────────┬────────────┬────────────┬──────────────┐
│ ID │ total  │   fecha    │ id_cliente │ id_comercial │
├────┼────────┼────────────┼────────────┼──────────────┤
│ 3  │ 65.26  │ 2017-10-05 │ 2          │ 1            │
│ 7  │ 5760.0 │ 2015-09-10 │ 2          │ 1            │
│ 12 │ 3045.6 │ 2017-04-25 │ 2          │ 1            │
└────┴────────┴────────────┴────────────┴──────────────┘
```


2. **Devuelve el número de pedidos en los que ha participado el comercial Daniel Sáez Vega. (Sin utilizar INNER JOIN)**

*Consulta*

``` sql
SELECT COUNT(*)
FROM pedido
WHERE id_comercial = (
    SELECT ID
    FROM comercial
    WHERE nombre = 'Daniel' AND apellido1 = 'Sáez' AND apellido2 = 'Vega'
);
```

*Resultado*

``` sql
┌──────────┐
│ COUNT(*) │
├──────────┤
│ 6        │
└──────────┘
```

3. **Devuelve los datos del cliente que realizó el pedido más caro en el año 2019. (Sin utilizar INNER JOIN)**

*Consulta*

``` sql
SELECT c.*
FROM cliente c
WHERE c.ID = (
    SELECT id_cliente
    FROM pedido
    WHERE fecha BETWEEN '2019-01-01' AND '2019-12-31'
    ORDER BY total DESC
    LIMIT 1
);

```

*Resultado*

``` sql
┌────┬────────┬───────────┬───────────┬─────────┬───────────┐
│ ID │ nombre │ apellido1 │ apellido2 │ ciudad  │ categoria │
├────┼────────┼───────────┼───────────┼─────────┼───────────┤
│ 1  │ Aarón  │ Rivero    │ Gómez     │ Almería │ 100       │
└────┴────────┴───────────┴───────────┴─────────┴───────────┘
```

4. **Devuelve la fecha y la cantidad del pedido de menor valor realizado por el cliente Pepe Ruiz Santana.**

*Consulta*

``` sql
SELECT fecha, total
FROM pedido
WHERE id_cliente = (
    SELECT ID
    FROM cliente
    WHERE nombre = 'Pepe' AND apellido1 = 'Ruiz' AND apellido2 = 'Santana'
)
ORDER BY total ASC
LIMIT 1;

```

*Resultado*

``` sql
┌────────────┬───────┐
│   fecha    │ total │
├────────────┼───────┤
│ 2016-08-17 │ 110.5 │
└────────────┴───────┘
```

5. **Devuelve un listado con los datos de los clientes y los pedidos, de todos los clientes que han realizado un pedido durante el año 2017 con un valor mayor o igual al valor medio de los pedidos realizados durante ese mismo año.**

*Consulta*

``` sql

```

*Resultado*

``` sql

```

6. **Devuelve un listado de los clientes que no han realizado ningún pedido. (Utilizando IN o NOT IN).**

*Consulta*

``` sql
SELECT *
FROM cliente
WHERE ID NOT IN (
    SELECT DISTINCT id_cliente
    FROM pedido
);

```

*Resultado*

``` sql
┌────┬───────────┬───────────┬───────────┬─────────┬───────────┐
│ ID │  nombre   │ apellido1 │ apellido2 │ ciudad  │ categoria │
├────┼───────────┼───────────┼───────────┼─────────┼───────────┤
│ 9  │ Guillermo │ López     │ Gómez     │ Granada │ 225       │
│ 10 │ Daniel    │ Santana   │ Loyola    │ Sevilla │ 125       │
└────┴───────────┴───────────┴───────────┴─────────┴───────────┘
```

7. **Devuelve un listado de los comerciales que no han realizado ningún pedido. (Utilizando IN o NOT IN).**

*Consulta*

``` sql
SELECT *
FROM comercial
WHERE ID NOT IN (
    SELECT DISTINCT id_comercial
    FROM pedido
);

```

*Resultado*

``` sql
┌────┬─────────┬───────────┬───────────┬───────────┐
│ ID │ NOMBRE  │ apellido1 │ apellido2 │ categoria │
├────┼─────────┼───────────┼───────────┼───────────┤
│ 4  │ Marta   │ Herrera   │ Gil       │ 0.14      │
│ 8  │ Alfredo │ Ruiz      │ Flores    │ 0.05      │
└────┴─────────┴───────────┴───────────┴───────────┘
```

8. **Devuelve un listado de los clientes que no han realizado ningún pedido. (Utilizando IN o NOT IN).**

*Consulta*

``` sql
SELECT *
FROM cliente
WHERE ID NOT IN (
    SELECT DISTINCT id_cliente
    FROM pedido
);

```

*Resultado*

``` sql
┌────┬───────────┬───────────┬───────────┬─────────┬───────────┐
│ ID │  nombre   │ apellido1 │ apellido2 │ ciudad  │ categoria │
├────┼───────────┼───────────┼───────────┼─────────┼───────────┤
│ 9  │ Guillermo │ López     │ Gómez     │ Granada │ 225       │
│ 10 │ Daniel    │ Santana   │ Loyola    │ Sevilla │ 125       │
└────┴───────────┴───────────┴───────────┴─────────┴───────────┘
```

9. **Devuelve un listado de los comerciales que no han realizado ningún pedido. (Utilizando IN o NOT IN).**

*Consulta*

``` sql
SELECT *
FROM comercial
WHERE ID NOT IN (
    SELECT DISTINCT id_comercial
    FROM pedido
);

```

*Resultado*

``` sql
┌────┬─────────┬───────────┬───────────┬───────────┐
│ ID │ NOMBRE  │ apellido1 │ apellido2 │ categoria │
├────┼─────────┼───────────┼───────────┼───────────┤
│ 4  │ Marta   │ Herrera   │ Gil       │ 0.14      │
│ 8  │ Alfredo │ Ruiz      │ Flores    │ 0.05      │
└────┴─────────┴───────────┴───────────┴───────────┘
```
