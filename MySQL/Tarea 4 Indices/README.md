# Tarea 4 Indices

Vamos a realizar el trabajo con una BBDD existente en la documentación oficial de MySql. Su nombre es Sakila.

![Alt text](sakila-er.png)

La base de datos está disponible en la web oficial de MySQL.

A continuación se debe de realizar la carga de la BBDD.

``` sql
SOURCE sakila.sql
```

Sigue los siguientes pasos para la carga del esquema y los datos.

1. Nos conectamos a MySQL

``` bash
$> mysql -u root -p
```

2. Ejecutamos sakila-schema.sql para crear la estructura de la base de datos, seguidamente ejecutamos sakila-data.sql.

``` sql
SOURCE sakila-schema.sql;
```

``` sql
SOURCE sakila-data.sql;
```

3. Confirmamos que la carga de la base de datos fue instalada correctamente.

- Primero usaremos la base de datos.

``` sql
USE sakila;
```

- Comprobamos si las tablas fueron insertadas correctamente.

``` sql
SHOW tables;
```

---

Se pide:

- **Realiza la carga de la BBDD de Sakila, tal y como se muestra en los enlaces proporcionados.**

    *Comando*

    ``` sql
    source sakila-schema.sql;
    ```

    *Salida*

    ``` sql
    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected, 1 warning (0,00 sec)

    Query OK, 1 row affected (0,01 sec)

    Database changed
    Query OK, 0 rows affected (0,04 sec)

    Query OK, 0 rows affected (0,02 sec)

    Query OK, 0 rows affected (0,02 sec)

    Query OK, 0 rows affected (0,02 sec)

    Query OK, 0 rows affected (0,02 sec)

    Query OK, 0 rows affected (0,04 sec)

    Query OK, 0 rows affected (0,03 sec)

    Query OK, 0 rows affected (0,03 sec)

    Query OK, 0 rows affected (0,02 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,13 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,03 sec)

    Query OK, 0 rows affected (0,02 sec)

    Query OK, 0 rows affected (0,03 sec)

    Query OK, 0 rows affected (0,04 sec)

    Query OK, 0 rows affected (0,03 sec)

    Query OK, 0 rows affected (0,02 sec)

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,00 sec)

    ```

    *Comando*

    ``` sql
    SOURCE sakila-data.sql;
    ```

    *Salida*

    ``` sql
    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,00 sec)

    Database changed
    Query OK, 0 rows affected (0,00 sec)

    Query OK, 200 rows affected (0,00 sec)
    Records: 200  Duplicates: 0  Warnings: 0

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 603 rows affected (0,04 sec)
    Records: 603  Duplicates: 0  Warnings: 0

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 16 rows affected (0,00 sec)
    Records: 16  Duplicates: 0  Warnings: 0

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 600 rows affected (0,00 sec)
    Records: 600  Duplicates: 0  Warnings: 0

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 109 rows affected (0,00 sec)
    Records: 109  Duplicates: 0  Warnings: 0

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 599 rows affected (0,01 sec)
    Records: 599  Duplicates: 0  Warnings: 0

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 1000 rows affected (0,06 sec)
    Records: 1000  Duplicates: 0  Warnings: 0

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 5462 rows affected (0,07 sec)
    Records: 5462  Duplicates: 0  Warnings: 0

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 1000 rows affected (0,01 sec)
    Records: 1000  Duplicates: 0  Warnings: 0

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 4581 rows affected (0,07 sec)
    Records: 4581  Duplicates: 0  Warnings: 0

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 6 rows affected (0,00 sec)
    Records: 6  Duplicates: 0  Warnings: 0

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 14881 rows affected (0,31 sec)
    Records: 14881  Duplicates: 0  Warnings: 0

    Query OK, 1163 rows affected (0,00 sec)
    Records: 1163  Duplicates: 0  Warnings: 0

    Query OK, 0 rows affected (0,03 sec)

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 12377 rows affected (0,29 sec)
    Records: 12377  Duplicates: 0  Warnings: 0

    Query OK, 3667 rows affected (0,03 sec)
    Records: 3667  Duplicates: 0  Warnings: 0

    Query OK, 0 rows affected (0,02 sec)

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 2 rows affected (0,00 sec)
    Records: 2  Duplicates: 0  Warnings: 0

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,01 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 2 rows affected (0,00 sec)
    Records: 2  Duplicates: 0  Warnings: 0

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,00 sec)

    Query OK, 0 rows affected (0,00 sec)

    ```

- **Realiza cada una de las siguientes consultas:**

    - **Actores que tienen de primer nombre Scarlett.**

        *Comando*

        ``` sql

        ```

        *Salida*

        ``` sql

        ```
    - **Actores que tienen de apellido Johansson.**
        Actores que contengan una O en su nombre.
        Actores que contengan una O en su nombre y en una A en su apellido.
        Actores que contengan dos O en su nombre y en una A en su apellido.
        Actores donde su tercera letra sea B.
        Ciudades que empiezan por a.
        Ciudades que acaban por s.
        Ciudades del country 61.
        Ciudades del country Spain.
        Ciudades con nombres compuestos.
        Películas con una duración entre 80 y 100.
        Peliculas con un rental_rate entre 1 y 3.
        Películas con un titulo de más de 12 letras.
        Peliculas con un rating de PG o G.
        Peliculas que no tengan un rating de NC-17.
        Peliculas con un rating PG y duracion de más de 120.
        ¿Cuantos actores hay?
        ¿Cuántas ciudades tiene el country Spain?
        ¿Cuántos countries hay que empiezan por a?
        Media de duración de peliculas con PG.
        Suma de rental_rate de todas las peliculas.
        Pelicula con mayor duración.
        Película con menor duración.
        Mostrar las ciudades del country Spain (multitabla).
        Mostrar el nombre de la película y el nombre de los actores.
        Mostrar el nombre de la película y el de sus categorías.
        Mostrar el country, la ciudad y dirección de cada miembro del staff.
        Mostrar el country, la ciudad y dirección de cada customer.
        Numero de películas de cada rating
        Cuantas películas ha realizado el actor ED CHASE.
        Media de duración de las películas cada categoría.





