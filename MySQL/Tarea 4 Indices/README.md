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
        SELECT * FROM actor WHERE first_name = "Scarlett";
        ```

        *Salida*

        ``` sql
        +----------+------------+-----------+---------------------+
        | actor_id | first_name | last_name | last_update         |
        +----------+------------+-----------+---------------------+
        |       81 | SCARLETT   | DAMON     | 2006-02-15 04:34:33 |
        |      124 | SCARLETT   | BENING    | 2006-02-15 04:34:33 |
        +----------+------------+-----------+---------------------+
        ```

    - **Actores que tienen de apellido Johansson.**

        *Comando*

        ``` sql
        SELECT * FROM actor WHERE last_name = "Johansson";
        ```

        *Salida*

        ``` sql
        +----------+------------+-----------+---------------------+
        | actor_id | first_name | last_name | last_update         |
        +----------+------------+-----------+---------------------+
        |        8 | MATTHEW    | JOHANSSON | 2006-02-15 04:34:33 |
        |       64 | RAY        | JOHANSSON | 2006-02-15 04:34:33 |
        |      146 | ALBERT     | JOHANSSON | 2006-02-15 04:34:33 |
        +----------+------------+-----------+---------------------+
        ```

    - **Actores que contengan una O en su nombre.**

        *Comando*

        ``` sql
        SELECT * FROM actor WHERE first_name LIKE "%O%";
        ```

        *Salida*

        ``` sql
        +----------+-------------+--------------+---------------------+
        | actor_id | first_name  | last_name    | last_update         |
        +----------+-------------+--------------+---------------------+
        |        1 | PENELOPE    | GUINESS      | 2006-02-15 04:34:33 |
        |        5 | JOHNNY      | LOLLOBRIGIDA | 2006-02-15 04:34:33 |
        |        9 | JOE         | SWANK        | 2006-02-15 04:34:33 |
        |       11 | ZERO        | CAGE         | 2006-02-15 04:34:33 |
        |       19 | BOB         | FAWCETT      | 2006-02-15 04:34:33 |
        |       24 | CAMERON     | STREEP       | 2006-02-15 04:34:33 |
        |       28 | WOODY       | HOFFMAN      | 2006-02-15 04:34:33 |
        |       38 | TOM         | MCKELLEN     | 2006-02-15 04:34:33 |
        |       39 | GOLDIE      | BRODY        | 2006-02-15 04:34:33 |
        |       40 | JOHNNY      | CAGE         | 2006-02-15 04:34:33 |
        |       41 | JODIE       | DEGENERES    | 2006-02-15 04:34:33 |
        |       42 | TOM         | MIRANDA      | 2006-02-15 04:34:33 |
        |       54 | PENELOPE    | PINKETT      | 2006-02-15 04:34:33 |
        |       63 | CAMERON     | WRAY         | 2006-02-15 04:34:33 |
        |       78 | GROUCHO     | SINATRA      | 2006-02-15 04:34:33 |
        |       82 | WOODY       | JOLIE        | 2006-02-15 04:34:33 |
        |       91 | CHRISTOPHER | BERRY        | 2006-02-15 04:34:33 |
        |      104 | PENELOPE    | CRONYN       | 2006-02-15 04:34:33 |
        |      106 | GROUCHO     | DUNST        | 2006-02-15 04:34:33 |
        |      111 | CAMERON     | ZELLWEGER    | 2006-02-15 04:34:33 |
        |      113 | MORGAN      | HOPKINS      | 2006-02-15 04:34:33 |
        |      114 | MORGAN      | MCDORMAND    | 2006-02-15 04:34:33 |
        |      115 | HARRISON    | BALE         | 2006-02-15 04:34:33 |
        |      120 | PENELOPE    | MONROE       | 2006-02-15 04:34:33 |
        |      137 | MORGAN      | WILLIAMS     | 2006-02-15 04:34:33 |
        |      140 | WHOOPI      | HURT         | 2006-02-15 04:34:33 |
        |      151 | GEOFFREY    | HESTON       | 2006-02-15 04:34:33 |
        |      162 | OPRAH       | KILMER       | 2006-02-15 04:34:33 |
        |      163 | CHRISTOPHER | WEST         | 2006-02-15 04:34:33 |
        |      171 | OLYMPIA     | PFEIFFER     | 2006-02-15 04:34:33 |
        |      172 | GROUCHO     | WILLIAMS     | 2006-02-15 04:34:33 |
        |      176 | JON         | CHASE        | 2006-02-15 04:34:33 |
        |      188 | ROCK        | DUKAKIS      | 2006-02-15 04:34:33 |
        |      191 | GREGORY     | GOODING      | 2006-02-15 04:34:33 |
        |      192 | JOHN        | SUVARI       | 2006-02-15 04:34:33 |
        |      200 | THORA       | TEMPLE       | 2006-02-15 04:34:33 |
        +----------+-------------+--------------+---------------------+
        ```

    - **Actores que contengan una O en su nombre y en una A en su apellido.**

        *Comando*

        ``` sql
        SELECT * FROM actor WHERE first_name LIKE "%O%" AND last_name LIKE "%A";
        ```

        *Salida*

        ``` sql
        +----------+------------+--------------+---------------------+
        | actor_id | first_name | last_name    | last_update         |
        +----------+------------+--------------+---------------------+
        |        5 | JOHNNY     | LOLLOBRIGIDA | 2006-02-15 04:34:33 |
        |       42 | TOM        | MIRANDA      | 2006-02-15 04:34:33 |
        |       78 | GROUCHO    | SINATRA      | 2006-02-15 04:34:33 |
        +----------+------------+--------------+---------------------+
        ```

    - **Actores que contengan dos O en su nombre y en una A en su apellido.**

        *Comando*

        ``` sql
        SELECT * FROM actor WHERE first_name LIKE "%O%%O%" AND last_name LIKE "%A";
        ```

        *Salida*

        ``` sql
        +----------+------------+-----------+---------------------+
        | actor_id | first_name | last_name | last_update         |
        +----------+------------+-----------+---------------------+
        |       78 | GROUCHO    | SINATRA   | 2006-02-15 04:34:33 |
        +----------+------------+-----------+---------------------+
        ```

    - **Actores donde su tercera letra sea B.**

        *Comando*

        ``` sql
        SELECT * FROM actor WHERE first_name REGEXP "...B";
        ```

        *Salida*

        ``` sql
        +----------+------------+-----------+---------------------+
        | actor_id | first_name | last_name | last_update         |
        +----------+------------+-----------+---------------------+
        |      182 | DEBBIE     | AKROYD    | 2006-02-15 04:34:33 |
        +----------+------------+-----------+---------------------+
        ```

    - **Ciudades que empiezan por a.**

        *Comando*

        ``` sql
        SELECT * FROM city WHERE city REGEXP "^a";
        ```

        *Salida*

        ``` sql
        +---------+-------------------------+------------+---------------------+
        | city_id | city                    | country_id | last_update         |
        +---------+-------------------------+------------+---------------------+
        |       1 | A Coruña (La Coruña)    |         87 | 2006-02-15 04:45:25 |
        |       2 | Abha                    |         82 | 2006-02-15 04:45:25 |
        |       3 | Abu Dhabi               |        101 | 2006-02-15 04:45:25 |
        |       4 | Acuña                   |         60 | 2006-02-15 04:45:25 |
        |       5 | Adana                   |         97 | 2006-02-15 04:45:25 |
        |       6 | Addis Abeba             |         31 | 2006-02-15 04:45:25 |
        |       7 | Aden                    |        107 | 2006-02-15 04:45:25 |
        |       8 | Adoni                   |         44 | 2006-02-15 04:45:25 |
        |       9 | Ahmadnagar              |         44 | 2006-02-15 04:45:25 |
        |      10 | Akishima                |         50 | 2006-02-15 04:45:25 |
        |      11 | Akron                   |        103 | 2006-02-15 04:45:25 |
        |      12 | al-Ayn                  |        101 | 2006-02-15 04:45:25 |
        |      13 | al-Hawiya               |         82 | 2006-02-15 04:45:25 |
        |      14 | al-Manama               |         11 | 2006-02-15 04:45:25 |
        |      15 | al-Qadarif              |         89 | 2006-02-15 04:45:25 |
        |      16 | al-Qatif                |         82 | 2006-02-15 04:45:25 |
        |      17 | Alessandria             |         49 | 2006-02-15 04:45:25 |
        |      18 | Allappuzha (Alleppey)   |         44 | 2006-02-15 04:45:25 |
        |      19 | Allende                 |         60 | 2006-02-15 04:45:25 |
        |      20 | Almirante Brown         |          6 | 2006-02-15 04:45:25 |
        |      21 | Alvorada                |         15 | 2006-02-15 04:45:25 |
        |      22 | Ambattur                |         44 | 2006-02-15 04:45:25 |
        |      23 | Amersfoort              |         67 | 2006-02-15 04:45:25 |
        |      24 | Amroha                  |         44 | 2006-02-15 04:45:25 |
        |      25 | Angra dos Reis          |         15 | 2006-02-15 04:45:25 |
        |      26 | Anápolis                |         15 | 2006-02-15 04:45:25 |
        |      27 | Antofagasta             |         22 | 2006-02-15 04:45:25 |
        |      28 | Aparecida de Goiânia    |         15 | 2006-02-15 04:45:25 |
        |      29 | Apeldoorn               |         67 | 2006-02-15 04:45:25 |
        |      30 | Araçatuba               |         15 | 2006-02-15 04:45:25 |
        |      31 | Arak                    |         46 | 2006-02-15 04:45:25 |
        |      32 | Arecibo                 |         77 | 2006-02-15 04:45:25 |
        |      33 | Arlington               |        103 | 2006-02-15 04:45:25 |
        |      34 | Ashdod                  |         48 | 2006-02-15 04:45:25 |
        |      35 | Ashgabat                |         98 | 2006-02-15 04:45:25 |
        |      36 | Ashqelon                |         48 | 2006-02-15 04:45:25 |
        |      37 | Asunción                |         73 | 2006-02-15 04:45:25 |
        |      38 | Athenai                 |         39 | 2006-02-15 04:45:25 |
        |      39 | Atšinsk                 |         80 | 2006-02-15 04:45:25 |
        |      40 | Atlixco                 |         60 | 2006-02-15 04:45:25 |
        |      41 | Augusta-Richmond County |        103 | 2006-02-15 04:45:25 |
        |      42 | Aurora                  |        103 | 2006-02-15 04:45:25 |
        |      43 | Avellaneda              |          6 | 2006-02-15 04:45:25 |
        +---------+-------------------------+------------+---------------------+
        ```

    - **Ciudades que acaban por s.**

        *Comando*

        ``` sql
        SELECT * FROM city WHERE city REGEXP "s$";
        ```

        *Salida*

        ``` sql
        +---------+----------------------------+------------+---------------------+
        | city_id | city                       | country_id | last_update         |
        +---------+----------------------------+------------+---------------------+
        |      25 | Angra dos Reis             |         15 | 2006-02-15 04:45:25 |
        |      26 | Anápolis                   |         15 | 2006-02-15 04:45:25 |
        |      79 | Bilbays                    |         29 | 2006-02-15 04:45:25 |
        |     102 | Caracas                    |        104 | 2006-02-15 04:45:25 |
        |     118 | Ciomas                     |         45 | 2006-02-15 04:45:25 |
        |     120 | Citrus Heights             |        103 | 2006-02-15 04:45:25 |
        |     125 | Coatzacoalcos              |         60 | 2006-02-15 04:45:25 |
        |     135 | Dallas                     |        103 | 2006-02-15 04:45:25 |
        |     137 | Daugavpils                 |         54 | 2006-02-15 04:45:25 |
        |     147 | Dos Quebradas              |         24 | 2006-02-15 04:45:25 |
        |     190 | Águas Lindas de Goiás      |         15 | 2006-02-15 04:45:25 |
        |     212 | Huejutla de Reyes          |         60 | 2006-02-15 04:45:25 |
        |     221 | Imus                       |         75 | 2006-02-15 04:45:25 |
        |     238 | Jelets                     |         80 | 2006-02-15 04:45:25 |
        |     266 | Kilis                      |         97 | 2006-02-15 04:45:25 |
        |     297 | Le Mans                    |         34 | 2006-02-15 04:45:25 |
        |     330 | Matamoros                  |         60 | 2006-02-15 04:45:25 |
        |     333 | Memphis                    |        103 | 2006-02-15 04:45:25 |
        |     391 | Ozamis                     |         75 | 2006-02-15 04:45:25 |
        |     401 | Patras                     |         39 | 2006-02-15 04:45:25 |
        |     413 | Poços de Caldas            |         15 | 2006-02-15 04:45:25 |
        |     424 | Quilmes                    |          6 | 2006-02-15 04:45:25 |
        |     441 | Saint Louis                |        103 | 2006-02-15 04:45:25 |
        |     442 | Saint-Denis                |         79 | 2006-02-15 04:45:25 |
        |     446 | Salinas                    |        103 | 2006-02-15 04:45:25 |
        |     460 | Santiago de los Caballeros |         27 | 2006-02-15 04:45:25 |
        |     482 | Sivas                      |         97 | 2006-02-15 04:45:25 |
        |     497 | Springs                    |         85 | 2006-02-15 04:45:25 |
        |     499 | Sterling Heights           |        103 | 2006-02-15 04:45:25 |
        |     529 | Tarsus                     |         97 | 2006-02-15 04:45:25 |
        |     570 | Vilnius                    |         56 | 2006-02-15 04:45:25 |
        +---------+----------------------------+------------+---------------------+
        ```

    - **Ciudades del country 61.**

        *Comando*

        ``` sql
        SELECT * FROM city WHERE country_id = 61;
        ```

        *Salida*

        ``` sql
       +---------+----------+------------+---------------------+
        | city_id | city     | country_id | last_update         |
        +---------+----------+------------+---------------------+
        |     115 | Chisinau |         61 | 2006-02-15 04:45:25 |
        +---------+----------+------------+---------------------+
        ```

    - **Ciudades del country Spain.**

        *Comando*

        ``` sql
        SELECT ci.city FROM city AS ci JOIN country as co on ci.country_id = co.country_id WHERE co.country = "Spain";
        ```

        *Salida*

        ``` sql
        +-------------------------+
        | city                    |
        +-------------------------+
        | A Coruña (La Coruña)    |
        | Donostia-San Sebastián  |
        | Gijón                   |
        | Ourense (Orense)        |
        | Santiago de Compostela  |
        +-------------------------+
        ```

    - **Ciudades con nombres compuestos.**

        *Comando*

        ``` sql

        ```

        *Salida*

        ``` sql

        ```

    - **Películas con una duración entre 80 y 100.**

        *Comando*

        ``` sql
        SELECT * FROM film WHERE length BETWEEN 80 and 100;
        ```

        *Salida*

        ``` sql
        +-------------+----------------------+-----------------+-------------+--------+------------------+--------+--------------------------------------------------------+---------------------+
        | film_id | title                   | description                                                                                                                    | release_year | language_id | original_language_id | rental_duration | rental_rate | length | replacement_cost | rating | special_features                                       | last_update         |
        +---------+-------------------------+--------------------------------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+--------------------------------------------------------+---------------------+
        |       1 | ACADEMY DINOSAUR        | A Epic Drama of a Feminist And a Mad Scientist who must Battle a Teacher in The Canadian Rockies                               |         2006 |           1 |                 NULL |               6 |        0.99 |     86 |            20.99 | PG     | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |      14 | ALICE FANTASIA          | A Emotional Drama of a A Shark And a Database Administrator who must Vanquish a Pioneer in Soviet Georgia                      |         2006 |           1 |                 NULL |               6 |        0.99 |     94 |            23.99 | NC-17  | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |      17 | ALONE TRIP              | A Fast-Paced Character Study of a Composer And a Dog who must Outgun a Boat in An Abandoned Fun House                          |         2006 |           1 |                 NULL |               3 |        0.99 |     82 |            14.99 | R      | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |      22 | AMISTAD MIDSUMMER       | A Emotional Character Study of a Dentist And a Crocodile who must Meet a Sumo Wrestler in California                           |         2006 |           1 |                 NULL |               6 |        2.99 |     85 |            10.99 | G      | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |      23 | ANACONDA CONFESSIONS    | A Lacklusture Display of a Dentist And a Dentist who must Fight a Girl in Australia                                            |         2006 |           1 |                 NULL |               3 |        0.99 |     92 |             9.99 | R      | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |      26 | ANNIE IDENTITY          | A Amazing Panorama of a Pastry Chef And a Boat who must Escape a Woman in An Abandoned Amusement Park                          |         2006 |           1 |                 NULL |               3 |        0.99 |     86 |            15.99 | G      | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |      28 | ANTHEM LUKE             | A Touching Panorama of a Waitress And a Woman who must Outrace a Dog in An Abandoned Amusement Park                            |         2006 |           1 |                 NULL |               5 |        4.99 |     91 |            16.99 | PG-13  | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |      30 | ANYTHING SAVANNAH       | A Epic Story of a Pastry Chef And a Woman who must Chase a Feminist in An Abandoned Fun House                                  |         2006 |           1 |                 NULL |               4 |        2.99 |     82 |            27.99 | R      | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |      31 | APACHE DIVINE           | A Awe-Inspiring Reflection of a Pastry Chef And a Teacher who must Overcome a Sumo Wrestler in A U-Boat                        |         2006 |           1 |                 NULL |               5 |        4.99 |     92 |            16.99 | NC-17  | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |      39 | ARMAGEDDON LOST         | A Fast-Paced Tale of a Boat And a Teacher who must Succumb a Composer in An Abandoned Mine Shaft                               |         2006 |           1 |                 NULL |               5 |        0.99 |     99 |            10.99 | G      | Trailers                                               | 2006-02-15 05:03:42 |
        |      45 | ATTRACTION NEWTON       | A Astounding Panorama of a Composer And a Frisbee who must Reach a Husband in Ancient Japan                                    |         2006 |           1 |                 NULL |               5 |        4.99 |     83 |            14.99 | PG-13  | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |      53 | BANG KWAI               | A Epic Drama of a Madman And a Cat who must Face a A Shark in An Abandoned Amusement Park                                      |         2006 |           1 |                 NULL |               5 |        2.99 |     87 |            25.99 | NC-17  | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |      57 | BASIC EASY              | A Stunning Epistle of a Man And a Husband who must Reach a Mad Scientist in A Jet Boat                                         |         2006 |           1 |                 NULL |               4 |        2.99 |     90 |            18.99 | PG-13  | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |      60 | BEAST HUNCHBACK         | A Awe-Inspiring Epistle of a Student And a Squirrel who must Defeat a Boy in Ancient China                                     |         2006 |           1 |                 NULL |               3 |        4.99 |     89 |            22.99 | R      | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |      65 | BEHAVIOR RUNAWAY        | A Unbelieveable Drama of a Student And a Husband who must Outrace a Sumo Wrestler in Berlin                                    |         2006 |           1 |                 NULL |               3 |        4.99 |    100 |            20.99 | PG     | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |      69 | BEVERLY OUTLAW          | A Fanciful Documentary of a Womanizer And a Boat who must Defeat a Madman in The First Manned Space Station                    |         2006 |           1 |                 NULL |               3 |        2.99 |     85 |            21.99 | R      | Trailers                                               | 2006-02-15 05:03:42 |
        |      71 | BILKO ANONYMOUS         | A Emotional Reflection of a Teacher And a Man who must Meet a Cat in The First Manned Space Station                            |         2006 |           1 |                 NULL |               3 |        4.99 |    100 |            25.99 | PG-13  | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |      72 | BILL OTHERS             | A Stunning Saga of a Mad Scientist And a Forensic Psychologist who must Challenge a Squirrel in A MySQL Convention             |         2006 |           1 |                 NULL |               6 |        2.99 |     93 |            12.99 | PG     | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |      78 | BLACKOUT PRIVATE        | A Intrepid Yarn of a Pastry Chef And a Mad Scientist who must Challenge a Secret Agent in Ancient Japan                        |         2006 |           1 |                 NULL |               7 |        2.99 |     85 |            12.99 | PG     | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |      91 | BOUND CHEAPER           | A Thrilling Panorama of a Database Administrator And a Astronaut who must Challenge a Lumberjack in A Baloon                   |         2006 |           1 |                 NULL |               5 |        0.99 |     98 |            17.99 | PG     | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     109 | BUTTERFLY CHOCOLAT      | A Fateful Story of a Girl And a Composer who must Conquer a Husband in A Shark Tank                                            |         2006 |           1 |                 NULL |               3 |        0.99 |     89 |            17.99 | G      | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     118 | CANYON STOCK            | A Thoughtful Reflection of a Waitress And a Feminist who must Escape a Squirrel in A Manhattan Penthouse                       |         2006 |           1 |                 NULL |               7 |        0.99 |     85 |            26.99 | R      | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     120 | CARIBBEAN LIBERTY       | A Fanciful Tale of a Pioneer And a Technical Writer who must Outgun a Pioneer in A Shark Tank                                  |         2006 |           1 |                 NULL |               3 |        4.99 |     92 |            16.99 | NC-17  | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     123 | CASABLANCA SUPER        | A Amazing Panorama of a Crocodile And a Forensic Psychologist who must Pursue a Secret Agent in The First Manned Space Station |         2006 |           1 |                 NULL |               6 |        4.99 |     85 |            22.99 | G      | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     140 | CHEAPER CLYDE           | A Emotional Character Study of a Pioneer And a Girl who must Discover a Dog in Ancient Japan                                   |         2006 |           1 |                 NULL |               6 |        0.99 |     87 |            23.99 | G      | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     152 | CIRCUS YOUTH            | A Thoughtful Drama of a Pastry Chef And a Dentist who must Pursue a Girl in A Baloon                                           |         2006 |           1 |                 NULL |               5 |        2.99 |     90 |            13.99 | PG-13  | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     154 | CLASH FREDDY            | A Amazing Yarn of a Composer And a Squirrel who must Escape a Astronaut in Australia                                           |         2006 |           1 |                 NULL |               6 |        2.99 |     81 |            12.99 | G      | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     162 | CLUELESS BUCKET         | A Taut Tale of a Car And a Pioneer who must Conquer a Sumo Wrestler in An Abandoned Fun House                                  |         2006 |           1 |                 NULL |               4 |        2.99 |     95 |            13.99 | R      | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     176 | CONGENIALITY QUEST      | A Touching Documentary of a Cat And a Pastry Chef who must Find a Lumberjack in A Baloon                                       |         2006 |           1 |                 NULL |               6 |        0.99 |     87 |            21.99 | PG-13  | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     184 | CORE SUIT               | A Unbelieveable Tale of a Car And a Explorer who must Confront a Boat in A Manhattan Penthouse                                 |         2006 |           1 |                 NULL |               3 |        2.99 |     92 |            24.99 | PG-13  | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     203 | DAISY MENAGERIE         | A Fast-Paced Saga of a Pastry Chef And a Monkey who must Sink a Composer in Ancient India                                      |         2006 |           1 |                 NULL |               5 |        4.99 |     84 |             9.99 | G      | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     208 | DARES PLUTO             | A Fateful Story of a Robot And a Dentist who must Defeat a Astronaut in New Orleans                                            |         2006 |           1 |                 NULL |               7 |        2.99 |     89 |            16.99 | PG-13  | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     209 | DARKNESS WAR            | A Touching Documentary of a Husband And a Hunter who must Escape a Boy in The Sahara Desert                                    |         2006 |           1 |                 NULL |               6 |        2.99 |     99 |            24.99 | NC-17  | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     221 | DELIVERANCE MULHOLLAND  | A Astounding Saga of a Monkey And a Moose who must Conquer a Butler in A Shark Tank                                            |         2006 |           1 |                 NULL |               4 |        0.99 |    100 |             9.99 | R      | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     224 | DESPERATE TRAINSPOTTING | A Epic Yarn of a Forensic Psychologist And a Teacher who must Face a Lumberjack in California                                  |         2006 |           1 |                 NULL |               7 |        4.99 |     81 |            29.99 | G      | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     227 | DETAILS PACKER          | A Epic Saga of a Waitress And a Composer who must Face a Boat in A U-Boat                                                      |         2006 |           1 |                 NULL |               4 |        4.99 |     88 |            17.99 | R      | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     229 | DEVIL DESIRE            | A Beautiful Reflection of a Monkey And a Dentist who must Face a Database Administrator in Ancient Japan                       |         2006 |           1 |                 NULL |               6 |        4.99 |     87 |            12.99 | R      | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     234 | DISTURBING SCARFACE     | A Lacklusture Display of a Crocodile And a Butler who must Overcome a Monkey in A U-Boat                                       |         2006 |           1 |                 NULL |               6 |        2.99 |     94 |            27.99 | R      | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     236 | DIVINE RESURRECTION     | A Boring Character Study of a Man And a Womanizer who must Succumb a Teacher in An Abandoned Amusement Park                    |         2006 |           1 |                 NULL |               4 |        2.99 |    100 |            19.99 | R      | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     258 | DRUMS DYNAMITE          | A Epic Display of a Crocodile And a Crocodile who must Confront a Dog in An Abandoned Amusement Park                           |         2006 |           1 |                 NULL |               6 |        0.99 |     96 |            11.99 | PG     | Trailers                                               | 2006-02-15 05:03:42 |
        |     268 | EARLY HOME              | A Amazing Panorama of a Mad Scientist And a Husband who must Meet a Woman in The Outback                                       |         2006 |           1 |                 NULL |               6 |        4.99 |     96 |            27.99 | NC-17  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     269 | EARRING INSTINCT        | A Stunning Character Study of a Dentist And a Mad Cow who must Find a Teacher in Nigeria                                       |         2006 |           1 |                 NULL |               3 |        0.99 |     98 |            22.99 | R      | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     270 | EARTH VISION            | A Stunning Drama of a Butler And a Madman who must Outrace a Womanizer in Ancient India                                        |         2006 |           1 |                 NULL |               7 |        0.99 |     85 |            29.99 | NC-17  | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     275 | EGYPT TENENBAUMS        | A Intrepid Story of a Madman And a Secret Agent who must Outrace a Astronaut in An Abandoned Amusement Park                    |         2006 |           1 |                 NULL |               3 |        0.99 |     85 |            11.99 | PG     | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     282 | ENCOUNTERS CURTAIN      | A Insightful Epistle of a Pastry Chef And a Womanizer who must Build a Boat in New Orleans                                     |         2006 |           1 |                 NULL |               5 |        0.99 |     92 |            20.99 | NC-17  | Trailers                                               | 2006-02-15 05:03:42 |
        |     283 | ENDING CROWDS           | A Unbelieveable Display of a Dentist And a Madman who must Vanquish a Squirrel in Berlin                                       |         2006 |           1 |                 NULL |               6 |        0.99 |     85 |            10.99 | NC-17  | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     295 | EXPENDABLE STALLION     | A Amazing Character Study of a Mad Cow And a Squirrel who must Discover a Hunter in A U-Boat                                   |         2006 |           1 |                 NULL |               3 |        0.99 |     97 |            14.99 | PG     | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     305 | FATAL HAUNTED           | A Beautiful Drama of a Student And a Secret Agent who must Confront a Dentist in Ancient Japan                                 |         2006 |           1 |                 NULL |               6 |        2.99 |     91 |            24.99 | PG     | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     309 | FEUD FROGMEN            | A Brilliant Reflection of a Database Administrator And a Mad Cow who must Chase a Woman in The Canadian Rockies                |         2006 |           1 |                 NULL |               6 |        0.99 |     98 |            29.99 | R      | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |     314 | FIGHT JAWBREAKER        | A Intrepid Panorama of a Womanizer And a Girl who must Escape a Girl in A Manhattan Penthouse                                  |         2006 |           1 |                 NULL |               3 |        0.99 |     91 |            13.99 | R      | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |     320 | FLAMINGOS CONNECTICUT   | A Fast-Paced Reflection of a Composer And a Composer who must Meet a Cat in The Sahara Desert                                  |         2006 |           1 |                 NULL |               4 |        4.99 |     80 |            28.99 | PG-13  | Trailers                                               | 2006-02-15 05:03:42 |
        |     322 | FLATLINERS KILLER       | A Taut Display of a Secret Agent And a Waitress who must Sink a Robot in An Abandoned Mine Shaft                               |         2006 |           1 |                 NULL |               5 |        2.99 |    100 |            29.99 | G      | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     331 | FORWARD TEMPLE          | A Astounding Display of a Forensic Psychologist And a Mad Scientist who must Challenge a Girl in New Orleans                   |         2006 |           1 |                 NULL |               6 |        2.99 |     90 |            25.99 | NC-17  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     336 | FRENCH HOLIDAY          | A Thrilling Epistle of a Dog And a Feminist who must Kill a Madman in Berlin                                                   |         2006 |           1 |                 NULL |               5 |        4.99 |     99 |            22.99 | PG     | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     341 | FROST HEAD              | A Amazing Reflection of a Lumberjack And a Cat who must Discover a Husband in A MySQL Convention                               |         2006 |           1 |                 NULL |               5 |        0.99 |     82 |            13.99 | PG     | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     342 | FUGITIVE MAGUIRE        | A Taut Epistle of a Feminist And a Sumo Wrestler who must Battle a Crocodile in Australia                                      |         2006 |           1 |                 NULL |               7 |        4.99 |     83 |            28.99 | R      | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     343 | FULL FLATLINERS         | A Beautiful Documentary of a Astronaut And a Moose who must Pursue a Monkey in A Shark Tank                                    |         2006 |           1 |                 NULL |               6 |        2.99 |     94 |            14.99 | PG     | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     348 | GANDHI KWAI             | A Thoughtful Display of a Mad Scientist And a Secret Agent who must Chase a Boat in Berlin                                     |         2006 |           1 |                 NULL |               7 |        0.99 |     86 |             9.99 | PG-13  | Trailers                                               | 2006-02-15 05:03:42 |
        |     350 | GARDEN ISLAND           | A Unbelieveable Character Study of a Womanizer And a Madman who must Reach a Man in The Outback                                |         2006 |           1 |                 NULL |               3 |        4.99 |     80 |            21.99 | G      | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     354 | GHOST GROUNDHOG         | A Brilliant Panorama of a Madman And a Composer who must Succumb a Car in Ancient India                                        |         2006 |           1 |                 NULL |               6 |        4.99 |     85 |            18.99 | G      | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |     361 | GLEAMING JAWBREAKER     | A Amazing Display of a Composer And a Forensic Psychologist who must Discover a Car in The Canadian Rockies                    |         2006 |           1 |                 NULL |               5 |        2.99 |     89 |            25.99 | NC-17  | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     366 | GOLDFINGER SENSIBILITY  | A Insightful Drama of a Mad Scientist And a Hunter who must Defeat a Pastry Chef in New Orleans                                |         2006 |           1 |                 NULL |               3 |        0.99 |     93 |            29.99 | G      | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     368 | GONE TROUBLE            | A Insightful Character Study of a Mad Cow And a Forensic Psychologist who must Conquer a A Shark in A Manhattan Penthouse      |         2006 |           1 |                 NULL |               7 |        2.99 |     84 |            20.99 | R      | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     375 | GRAIL FRANKENSTEIN      | A Unbelieveable Saga of a Teacher And a Monkey who must Fight a Girl in An Abandoned Mine Shaft                                |         2006 |           1 |                 NULL |               4 |        2.99 |     85 |            17.99 | NC-17  | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     378 | GREATEST NORTH          | A Astounding Character Study of a Secret Agent And a Robot who must Build a A Shark in Berlin                                  |         2006 |           1 |                 NULL |               5 |        2.99 |     93 |            24.99 | NC-17  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     387 | GUN BONNIE              | A Boring Display of a Sumo Wrestler And a Husband who must Build a Waitress in The Gulf of Mexico                              |         2006 |           1 |                 NULL |               7 |        0.99 |    100 |            27.99 | G      | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     390 | GUYS FALCON             | A Boring Story of a Woman And a Feminist who must Redeem a Squirrel in A U-Boat                                                |         2006 |           1 |                 NULL |               4 |        4.99 |     84 |            20.99 | R      | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     399 | HAPPINESS UNITED        | A Action-Packed Panorama of a Husband And a Feminist who must Meet a Forensic Psychologist in Ancient Japan                    |         2006 |           1 |                 NULL |               6 |        2.99 |    100 |            23.99 | G      | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     415 | HIGH ENCINO             | A Fateful Saga of a Waitress And a Hunter who must Outrace a Sumo Wrestler in Australia                                        |         2006 |           1 |                 NULL |               3 |        2.99 |     84 |            23.99 | R      | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     417 | HILLS NEIGHBORS         | A Epic Display of a Hunter And a Feminist who must Sink a Car in A U-Boat                                                      |         2006 |           1 |                 NULL |               5 |        0.99 |     93 |            29.99 | G      | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |     425 | HOLY TADPOLE            | A Action-Packed Display of a Feminist And a Pioneer who must Pursue a Dog in A Baloon Factory                                  |         2006 |           1 |                 NULL |               6 |        0.99 |     88 |            20.99 | R      | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     429 | HONEY TIES              | A Taut Story of a Waitress And a Crocodile who must Outrace a Lumberjack in A Shark Tank                                       |         2006 |           1 |                 NULL |               3 |        0.99 |     84 |            29.99 | R      | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     433 | HORN WORKING            | A Stunning Display of a Mad Scientist And a Technical Writer who must Succumb a Monkey in A Shark Tank                         |         2006 |           1 |                 NULL |               4 |        2.99 |     95 |            23.99 | PG     | Trailers                                               | 2006-02-15 05:03:42 |
        |     444 | HUSTLER PARTY           | A Emotional Reflection of a Sumo Wrestler And a Monkey who must Conquer a Robot in The Sahara Desert                           |         2006 |           1 |                 NULL |               3 |        4.99 |     83 |            22.99 | NC-17  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     445 | HYDE DOCTOR             | A Fanciful Documentary of a Boy And a Woman who must Redeem a Womanizer in A Jet Boat                                          |         2006 |           1 |                 NULL |               5 |        2.99 |    100 |            11.99 | G      | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     450 | IDOLS SNATCHERS         | A Insightful Drama of a Car And a Composer who must Fight a Man in A Monastery                                                 |         2006 |           1 |                 NULL |               5 |        2.99 |     84 |            29.99 | NC-17  | Trailers                                               | 2006-02-15 05:03:42 |
        |     468 | INVASION CYCLONE        | A Lacklusture Character Study of a Mad Scientist And a Womanizer who must Outrace a Explorer in A Monastery                    |         2006 |           1 |                 NULL |               5 |        2.99 |     97 |            12.99 | PG     | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     471 | ISLAND EXORCIST         | A Fanciful Panorama of a Technical Writer And a Boy who must Find a Dentist in An Abandoned Fun House                          |         2006 |           1 |                 NULL |               7 |        2.99 |     84 |            23.99 | NC-17  | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     480 | JEEPERS WEDDING         | A Astounding Display of a Composer And a Dog who must Kill a Pastry Chef in Soviet Georgia                                     |         2006 |           1 |                 NULL |               3 |        2.99 |     84 |            29.99 | R      | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     493 | KANE EXORCIST           | A Epic Documentary of a Composer And a Robot who must Overcome a Car in Berlin                                                 |         2006 |           1 |                 NULL |               5 |        0.99 |     92 |            18.99 | R      | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     520 | LICENSE WEEKEND         | A Insightful Story of a Man And a Husband who must Overcome a Madman in A Monastery                                            |         2006 |           1 |                 NULL |               7 |        2.99 |     91 |            28.99 | NC-17  | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     527 | LOLA AGENT              | A Astounding Tale of a Mad Scientist And a Husband who must Redeem a Database Administrator in Ancient Japan                   |         2006 |           1 |                 NULL |               4 |        4.99 |     85 |            24.99 | PG     | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     532 | LOSER HUSTLER           | A Stunning Drama of a Robot And a Feminist who must Outgun a Butler in Nigeria                                                 |         2006 |           1 |                 NULL |               5 |        4.99 |     80 |            28.99 | PG     | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     533 | LOST BIRD               | A Emotional Character Study of a Robot And a A Shark who must Defeat a Technical Writer in A Manhattan Penthouse               |         2006 |           1 |                 NULL |               4 |        2.99 |     98 |            21.99 | PG-13  | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     540 | LUCKY FLYING            | A Lacklusture Character Study of a A Shark And a Man who must Find a Forensic Psychologist in A U-Boat                         |         2006 |           1 |                 NULL |               7 |        2.99 |     97 |            10.99 | PG-13  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     546 | MADRE GABLES            | A Intrepid Panorama of a Sumo Wrestler And a Forensic Psychologist who must Discover a Moose in The First Manned Space Station |         2006 |           1 |                 NULL |               7 |        2.99 |     98 |            27.99 | PG-13  | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     567 | MEET CHOCOLATE          | A Boring Documentary of a Dentist And a Butler who must Confront a Monkey in A MySQL Convention                                |         2006 |           1 |                 NULL |               3 |        2.99 |     80 |            26.99 | G      | Trailers                                               | 2006-02-15 05:03:42 |
        |     574 | MIDNIGHT WESTWARD       | A Taut Reflection of a Husband And a A Shark who must Redeem a Pastry Chef in A Monastery                                      |         2006 |           1 |                 NULL |               3 |        0.99 |     86 |            19.99 | G      | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     595 | MOON BUNCH              | A Beautiful Tale of a Astronaut And a Mad Cow who must Challenge a Cat in A Baloon Factory                                     |         2006 |           1 |                 NULL |               7 |        0.99 |     83 |            20.99 | PG     | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     613 | MYSTIC TRUMAN           | A Epic Yarn of a Teacher And a Hunter who must Outgun a Explorer in Soviet Georgia                                             |         2006 |           1 |                 NULL |               5 |        0.99 |     92 |            19.99 | NC-17  | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     616 | NATIONAL STORY          | A Taut Epistle of a Mad Scientist And a Girl who must Escape a Monkey in California                                            |         2006 |           1 |                 NULL |               4 |        2.99 |     92 |            19.99 | NC-17  | Trailers                                               | 2006-02-15 05:03:42 |
        |     625 | NONE SPIKING            | A Boring Reflection of a Secret Agent And a Astronaut who must Face a Composer in A Manhattan Penthouse                        |         2006 |           1 |                 NULL |               3 |        0.99 |     83 |            18.99 | NC-17  | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     639 | OPPOSITE NECKLACE       | A Fateful Epistle of a Crocodile And a Moose who must Kill a Explorer in Nigeria                                               |         2006 |           1 |                 NULL |               7 |        4.99 |     92 |             9.99 | PG     | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     649 | OZ LIAISONS             | A Epic Yarn of a Mad Scientist And a Cat who must Confront a Womanizer in A Baloon Factory                                     |         2006 |           1 |                 NULL |               4 |        2.99 |     85 |            14.99 | R      | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     651 | PACKER MADIGAN          | A Epic Display of a Sumo Wrestler And a Forensic Psychologist who must Build a Woman in An Abandoned Amusement Park            |         2006 |           1 |                 NULL |               3 |        0.99 |     84 |            20.99 | PG-13  | Trailers                                               | 2006-02-15 05:03:42 |
        |     654 | PANKY SUBMARINE         | A Touching Documentary of a Dentist And a Sumo Wrestler who must Overcome a Boy in The Gulf of Mexico                          |         2006 |           1 |                 NULL |               4 |        4.99 |     93 |            19.99 | G      | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |     663 | PATIENT SISTER          | A Emotional Epistle of a Squirrel And a Robot who must Confront a Lumberjack in Soviet Georgia                                 |         2006 |           1 |                 NULL |               7 |        0.99 |     99 |            29.99 | NC-17  | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     668 | PEAK FOREVER            | A Insightful Reflection of a Boat And a Secret Agent who must Vanquish a Astronaut in An Abandoned Mine Shaft                  |         2006 |           1 |                 NULL |               7 |        4.99 |     80 |            25.99 | PG     | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |     671 | PERDITION FARGO         | A Fast-Paced Story of a Car And a Cat who must Outgun a Hunter in Berlin                                                       |         2006 |           1 |                 NULL |               7 |        4.99 |     99 |            27.99 | NC-17  | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     672 | PERFECT GROOVE          | A Thrilling Yarn of a Dog And a Dog who must Build a Husband in A Baloon                                                       |         2006 |           1 |                 NULL |               7 |        2.99 |     82 |            17.99 | PG-13  | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     674 | PET HAUNTING            | A Unbelieveable Reflection of a Explorer And a Boat who must Conquer a Woman in California                                     |         2006 |           1 |                 NULL |               3 |        0.99 |     99 |            11.99 | PG     | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     681 | PIRATES ROXANNE         | A Stunning Drama of a Woman And a Lumberjack who must Overcome a A Shark in The Canadian Rockies                               |         2006 |           1 |                 NULL |               4 |        0.99 |    100 |            20.99 | PG     | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     686 | PLUTO OLEANDER          | A Action-Packed Reflection of a Car And a Moose who must Outgun a Car in A Shark Tank                                          |         2006 |           1 |                 NULL |               5 |        4.99 |     84 |             9.99 | R      | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     694 | PREJUDICE OLEANDER      | A Epic Saga of a Boy And a Dentist who must Outrace a Madman in A U-Boat                                                       |         2006 |           1 |                 NULL |               6 |        4.99 |     98 |            15.99 | PG-13  | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     702 | PULP BEVERLY            | A Unbelieveable Display of a Dog And a Crocodile who must Outrace a Man in Nigeria                                             |         2006 |           1 |                 NULL |               4 |        2.99 |     89 |            12.99 | G      | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     703 | PUNK DIVORCE            | A Fast-Paced Tale of a Pastry Chef And a Boat who must Face a Frisbee in The Canadian Rockies                                  |         2006 |           1 |                 NULL |               6 |        4.99 |    100 |            18.99 | PG     | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     705 | PURPLE MOVIE            | A Boring Display of a Pastry Chef And a Sumo Wrestler who must Discover a Frisbee in An Abandoned Amusement Park               |         2006 |           1 |                 NULL |               4 |        2.99 |     88 |             9.99 | R      | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     712 | RAIDERS ANTITRUST       | A Amazing Drama of a Teacher And a Feminist who must Meet a Woman in The First Manned Space Station                            |         2006 |           1 |                 NULL |               4 |        0.99 |     82 |            11.99 | PG-13  | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     717 | REAR TRADING            | A Awe-Inspiring Reflection of a Forensic Psychologist And a Secret Agent who must Succumb a Pastry Chef in Soviet Georgia      |         2006 |           1 |                 NULL |               6 |        0.99 |     97 |            23.99 | NC-17  | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     723 | REIGN GENTLEMEN         | A Emotional Yarn of a Composer And a Man who must Escape a Butler in The Gulf of Mexico                                        |         2006 |           1 |                 NULL |               3 |        2.99 |     82 |            29.99 | PG-13  | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     741 | ROMAN PUNK              | A Thoughtful Panorama of a Mad Cow And a Student who must Battle a Forensic Psychologist in Berlin                             |         2006 |           1 |                 NULL |               7 |        0.99 |     81 |            28.99 | NC-17  | Trailers                                               | 2006-02-15 05:03:42 |
        |     744 | ROOTS REMEMBER          | A Brilliant Drama of a Mad Cow And a Hunter who must Escape a Hunter in Berlin                                                 |         2006 |           1 |                 NULL |               4 |        0.99 |     89 |            23.99 | PG-13  | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     755 | SABRINA MIDNIGHT        | A Emotional Story of a Squirrel And a Crocodile who must Succumb a Husband in The Sahara Desert                                |         2006 |           1 |                 NULL |               5 |        4.99 |     99 |            11.99 | PG     | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     756 | SADDLE ANTITRUST        | A Stunning Epistle of a Feminist And a A Shark who must Battle a Woman in An Abandoned Fun House                               |         2006 |           1 |                 NULL |               7 |        2.99 |     80 |            10.99 | PG-13  | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     766 | SAVANNAH TOWN           | A Awe-Inspiring Tale of a Astronaut And a Database Administrator who must Chase a Secret Agent in The Gulf of Mexico           |         2006 |           1 |                 NULL |               5 |        0.99 |     84 |            25.99 | PG-13  | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     772 | SEA VIRGIN              | A Fast-Paced Documentary of a Technical Writer And a Pastry Chef who must Escape a Moose in A U-Boat                           |         2006 |           1 |                 NULL |               4 |        2.99 |     80 |            24.99 | PG     | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     776 | SECRET GROUNDHOG        | A Astounding Story of a Cat And a Database Administrator who must Build a Technical Writer in New Orleans                      |         2006 |           1 |                 NULL |               6 |        4.99 |     90 |            11.99 | PG     | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     780 | SENSIBILITY REAR        | A Emotional Tale of a Robot And a Sumo Wrestler who must Redeem a Pastry Chef in A Baloon Factory                              |         2006 |           1 |                 NULL |               7 |        4.99 |     98 |            15.99 | PG     | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     783 | SHANE DARKNESS          | A Action-Packed Saga of a Moose And a Lumberjack who must Find a Woman in Berlin                                               |         2006 |           1 |                 NULL |               5 |        2.99 |     93 |            22.99 | PG     | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     785 | SHAWSHANK BUBBLE        | A Lacklusture Story of a Moose And a Monkey who must Confront a Butler in An Abandoned Amusement Park                          |         2006 |           1 |                 NULL |               6 |        4.99 |     80 |            20.99 | PG     | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     807 | SLEUTH ORIENT           | A Fateful Character Study of a Husband And a Dog who must Find a Feminist in Ancient India                                     |         2006 |           1 |                 NULL |               4 |        0.99 |     87 |            25.99 | NC-17  | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     808 | SLING LUKE              | A Intrepid Character Study of a Robot And a Monkey who must Reach a Secret Agent in An Abandoned Amusement Park                |         2006 |           1 |                 NULL |               5 |        0.99 |     84 |            10.99 | R      | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     837 | STAGE WORLD             | A Lacklusture Panorama of a Woman And a Frisbee who must Chase a Crocodile in A Jet Boat                                       |         2006 |           1 |                 NULL |               4 |        2.99 |     85 |            19.99 | PG     | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     846 | STING PERSONAL          | A Fanciful Drama of a Frisbee And a Dog who must Fight a Madman in A Jet Boat                                                  |         2006 |           1 |                 NULL |               3 |        4.99 |     93 |             9.99 | NC-17  | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     848 | STONE FIRE              | A Intrepid Drama of a Astronaut And a Crocodile who must Find a Boat in Soviet Georgia                                         |         2006 |           1 |                 NULL |               3 |        0.99 |     94 |            19.99 | G      | Trailers                                               | 2006-02-15 05:03:42 |
        |     860 | SUICIDES SILENCE        | A Emotional Character Study of a Car And a Girl who must Face a Composer in A U-Boat                                           |         2006 |           1 |                 NULL |               4 |        4.99 |     93 |            13.99 | G      | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     864 | SUNDANCE INVASION       | A Epic Drama of a Lumberjack And a Explorer who must Confront a Hunter in A Baloon Factory                                     |         2006 |           1 |                 NULL |               5 |        0.99 |     92 |            21.99 | NC-17  | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     876 | TARZAN VIDEOTAPE        | A Fast-Paced Display of a Lumberjack And a Mad Scientist who must Succumb a Sumo Wrestler in The Sahara Desert                 |         2006 |           1 |                 NULL |               3 |        2.99 |     91 |            11.99 | PG-13  | Trailers                                               | 2006-02-15 05:03:42 |
        |     882 | TENENBAUMS COMMAND      | A Taut Display of a Pioneer And a Man who must Reach a Girl in The Gulf of Mexico                                              |         2006 |           1 |                 NULL |               4 |        0.99 |     99 |            24.99 | PG-13  | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     884 | TERMINATOR CLUB         | A Touching Story of a Crocodile And a Girl who must Sink a Man in The Gulf of Mexico                                           |         2006 |           1 |                 NULL |               5 |        4.99 |     88 |            11.99 | R      | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     893 | TITANS JERK             | A Unbelieveable Panorama of a Feminist And a Sumo Wrestler who must Challenge a Technical Writer in Ancient China              |         2006 |           1 |                 NULL |               4 |        4.99 |     91 |            11.99 | PG     | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     910 | TREATMENT JEKYLL        | A Boring Story of a Teacher And a Student who must Outgun a Cat in An Abandoned Mine Shaft                                     |         2006 |           1 |                 NULL |               3 |        0.99 |     87 |            19.99 | PG     | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     915 | TRUMAN CRAZY            | A Thrilling Epistle of a Moose And a Boy who must Meet a Database Administrator in A Monastery                                 |         2006 |           1 |                 NULL |               7 |        4.99 |     92 |             9.99 | G      | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     916 | TURN STAR               | A Stunning Tale of a Man And a Monkey who must Chase a Student in New Orleans                                                  |         2006 |           1 |                 NULL |               3 |        2.99 |     80 |            10.99 | G      | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     919 | TYCOON GATHERING        | A Emotional Display of a Husband And a A Shark who must Succumb a Madman in A Manhattan Penthouse                              |         2006 |           1 |                 NULL |               3 |        4.99 |     82 |            17.99 | G      | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     928 | UPTOWN YOUNG            | A Fateful Documentary of a Dog And a Hunter who must Pursue a Teacher in An Abandoned Amusement Park                           |         2006 |           1 |                 NULL |               5 |        2.99 |     84 |            16.99 | PG     | Commentaries                                           | 2006-02-15 05:03:42 |
        |     937 | VARSITY TRIP            | A Action-Packed Character Study of a Astronaut And a Explorer who must Reach a Monkey in A MySQL Convention                    |         2006 |           1 |                 NULL |               7 |        2.99 |     85 |            14.99 | NC-17  | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     939 | VERTIGO NORTHWEST       | A Unbelieveable Display of a Mad Scientist And a Mad Scientist who must Outgun a Mad Cow in Ancient Japan                      |         2006 |           1 |                 NULL |               4 |        2.99 |     90 |            17.99 | R      | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     957 | WAR NOTTING             | A Boring Drama of a Teacher And a Sumo Wrestler who must Challenge a Secret Agent in The Canadian Rockies                      |         2006 |           1 |                 NULL |               7 |        4.99 |     80 |            26.99 | G      | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     959 | WARLOCK WEREWOLF        | A Astounding Yarn of a Pioneer And a Crocodile who must Defeat a A Shark in The Outback                                        |         2006 |           1 |                 NULL |               6 |        2.99 |     83 |            10.99 | G      | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     962 | WASTELAND DIVINE        | A Fanciful Story of a Database Administrator And a Womanizer who must Fight a Database Administrator in Ancient China          |         2006 |           1 |                 NULL |               7 |        2.99 |     85 |            18.99 | PG     | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     977 | WINDOW SIDE             | A Astounding Character Study of a Womanizer And a Hunter who must Escape a Robot in A Monastery                                |         2006 |           1 |                 NULL |               3 |        2.99 |     85 |            25.99 | R      | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     978 | WISDOM WORKER           | A Unbelieveable Saga of a Forensic Psychologist And a Student who must Face a Squirrel in The First Manned Space Station       |         2006 |           1 |                 NULL |               3 |        0.99 |     98 |            12.99 | R      | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     979 | WITCHES PANIC           | A Awe-Inspiring Drama of a Secret Agent And a Hunter who must Fight a Moose in Nigeria                                         |         2006 |           1 |                 NULL |               6 |        4.99 |    100 |            10.99 | NC-17  | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     986 | WONKA SEA               | A Brilliant Saga of a Boat And a Mad Scientist who must Meet a Moose in Ancient India                                          |         2006 |           1 |                 NULL |               6 |        2.99 |     85 |            24.99 | NC-17  | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     994 | WYOMING STORM           | A Awe-Inspiring Panorama of a Robot And a Boat who must Overcome a Feminist in A U-Boat                                        |         2006 |           1 |                 NULL |               6 |        4.99 |    100 |            29.99 | PG-13  | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     995 | YENTL IDAHO             | A Amazing Display of a Robot And a Astronaut who must Fight a Womanizer in Berlin                                              |         2006 |           1 |                 NULL |               5 |        4.99 |     86 |            11.99 | R      | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        +---------+-------------------------+--------------------------------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+--------------------------------------------------------+---------------------+
        ```

    - **Peliculas con un rental_rate entre 1 y 3.**

        *Comando*

        ``` sql
        SELECT * FROM film WHERE rental_rate BETWEEN 1 and 3;
        ```

        *Salida*

        ``` sql
        +---------+-----------------------------+------------------------------------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+--------------------------------------------------------+---------------------+
        | film_id | title                       | description                                                                                                                        | release_year | language_id | original_language_id | rental_duration | rental_rate | length | replacement_cost | rating | special_features                                       | last_update         |
        +---------+-----------------------------+------------------------------------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+--------------------------------------------------------+---------------------+
        |       3 | ADAPTATION HOLES            | A Astounding Reflection of a Lumberjack And a Car who must Sink a Lumberjack in A Baloon Factory                                   |         2006 |           1 |                 NULL |               7 |        2.99 |     50 |            18.99 | NC-17  | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |       4 | AFFAIR PREJUDICE            | A Fanciful Documentary of a Frisbee And a Lumberjack who must Chase a Monkey in A Shark Tank                                       |         2006 |           1 |                 NULL |               5 |        2.99 |    117 |            26.99 | G      | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |       5 | AFRICAN EGG                 | A Fast-Paced Documentary of a Pastry Chef And a Dentist who must Pursue a Forensic Psychologist in The Gulf of Mexico              |         2006 |           1 |                 NULL |               6 |        2.99 |    130 |            22.99 | G      | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |       6 | AGENT TRUMAN                | A Intrepid Panorama of a Robot And a Boy who must Escape a Sumo Wrestler in Ancient China                                          |         2006 |           1 |                 NULL |               3 |        2.99 |    169 |            17.99 | PG     | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |       9 | ALABAMA DEVIL               | A Thoughtful Panorama of a Database Administrator And a Mad Scientist who must Outgun a Mad Scientist in A Jet Boat                |         2006 |           1 |                 NULL |               3 |        2.99 |    114 |            21.99 | PG-13  | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |      15 | ALIEN CENTER                | A Brilliant Drama of a Cat And a Mad Scientist who must Battle a Feminist in A MySQL Convention                                    |         2006 |           1 |                 NULL |               5 |        2.99 |     46 |            10.99 | NC-17  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |      16 | ALLEY EVOLUTION             | A Fast-Paced Drama of a Robot And a Composer who must Battle a Astronaut in New Orleans                                            |         2006 |           1 |                 NULL |               6 |        2.99 |    180 |            23.99 | NC-17  | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |      22 | AMISTAD MIDSUMMER           | A Emotional Character Study of a Dentist And a Crocodile who must Meet a Sumo Wrestler in California                               |         2006 |           1 |                 NULL |               6 |        2.99 |     85 |            10.99 | G      | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |      24 | ANALYZE HOOSIERS            | A Thoughtful Display of a Explorer And a Pastry Chef who must Overcome a Feminist in The Sahara Desert                             |         2006 |           1 |                 NULL |               6 |        2.99 |    181 |            19.99 | R      | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |      25 | ANGELS LIFE                 | A Thoughtful Display of a Woman And a Astronaut who must Battle a Robot in Berlin                                                  |         2006 |           1 |                 NULL |               3 |        2.99 |     74 |            15.99 | G      | Trailers                                               | 2006-02-15 05:03:42 |
        |      29 | ANTITRUST TOMATOES          | A Fateful Yarn of a Womanizer And a Feminist who must Succumb a Database Administrator in Ancient India                            |         2006 |           1 |                 NULL |               5 |        2.99 |    168 |            11.99 | NC-17  | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |      30 | ANYTHING SAVANNAH           | A Epic Story of a Pastry Chef And a Woman who must Chase a Feminist in An Abandoned Fun House                                      |         2006 |           1 |                 NULL |               4 |        2.99 |     82 |            27.99 | R      | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |      33 | APOLLO TEEN                 | A Action-Packed Reflection of a Crocodile And a Explorer who must Find a Sumo Wrestler in An Abandoned Mine Shaft                  |         2006 |           1 |                 NULL |               5 |        2.99 |    153 |            15.99 | PG-13  | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |      35 | ARACHNOPHOBIA ROLLERCOASTER | A Action-Packed Reflection of a Pastry Chef And a Composer who must Discover a Mad Scientist in The First Manned Space Station     |         2006 |           1 |                 NULL |               4 |        2.99 |    147 |            24.99 | PG-13  | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |      37 | ARIZONA BANG                | A Brilliant Panorama of a Mad Scientist And a Mad Cow who must Meet a Pioneer in A Monastery                                       |         2006 |           1 |                 NULL |               3 |        2.99 |    121 |            28.99 | PG     | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |      42 | ARTIST COLDBLOODED          | A Stunning Reflection of a Robot And a Moose who must Challenge a Woman in California                                              |         2006 |           1 |                 NULL |               5 |        2.99 |    170 |            10.99 | NC-17  | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |      43 | ATLANTIS CAUSE              | A Thrilling Yarn of a Feminist And a Hunter who must Fight a Technical Writer in A Shark Tank                                      |         2006 |           1 |                 NULL |               6 |        2.99 |    170 |            15.99 | G      | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |      49 | BADMAN DAWN                 | A Emotional Panorama of a Pioneer And a Composer who must Escape a Mad Scientist in A Jet Boat                                     |         2006 |           1 |                 NULL |               6 |        2.99 |    162 |            22.99 | R      | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |      50 | BAKED CLEOPATRA             | A Stunning Drama of a Forensic Psychologist And a Husband who must Overcome a Waitress in A Monastery                              |         2006 |           1 |                 NULL |               3 |        2.99 |    182 |            20.99 | G      | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |      51 | BALLOON HOMEWARD            | A Insightful Panorama of a Forensic Psychologist And a Mad Cow who must Build a Mad Scientist in The First Manned Space Station    |         2006 |           1 |                 NULL |               5 |        2.99 |     75 |            10.99 | NC-17  | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |      53 | BANG KWAI                   | A Epic Drama of a Madman And a Cat who must Face a A Shark in An Abandoned Amusement Park                                          |         2006 |           1 |                 NULL |               5 |        2.99 |     87 |            25.99 | NC-17  | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |      55 | BARBARELLA STREETCAR        | A Awe-Inspiring Story of a Feminist And a Cat who must Conquer a Dog in A Monastery                                                |         2006 |           1 |                 NULL |               6 |        2.99 |     65 |            27.99 | G      | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |      56 | BAREFOOT MANCHURIAN         | A Intrepid Story of a Cat And a Student who must Vanquish a Girl in An Abandoned Amusement Park                                    |         2006 |           1 |                 NULL |               6 |        2.99 |    129 |            15.99 | G      | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |      57 | BASIC EASY                  | A Stunning Epistle of a Man And a Husband who must Reach a Mad Scientist in A Jet Boat                                             |         2006 |           1 |                 NULL |               4 |        2.99 |     90 |            18.99 | PG-13  | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |      58 | BEACH HEARTBREAKERS         | A Fateful Display of a Womanizer And a Mad Scientist who must Outgun a A Shark in Soviet Georgia                                   |         2006 |           1 |                 NULL |               6 |        2.99 |    122 |            16.99 | G      | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |      59 | BEAR GRACELAND              | A Astounding Saga of a Dog And a Boy who must Kill a Teacher in The First Manned Space Station                                     |         2006 |           1 |                 NULL |               4 |        2.99 |    160 |            20.99 | R      | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |      62 | BED HIGHBALL                | A Astounding Panorama of a Lumberjack And a Dog who must Redeem a Woman in An Abandoned Fun House                                  |         2006 |           1 |                 NULL |               5 |        2.99 |    106 |            23.99 | NC-17  | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |      67 | BERETS AGENT                | A Taut Saga of a Crocodile And a Boy who must Overcome a Technical Writer in Ancient China                                         |         2006 |           1 |                 NULL |               5 |        2.99 |     77 |            24.99 | PG-13  | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |      69 | BEVERLY OUTLAW              | A Fanciful Documentary of a Womanizer And a Boat who must Defeat a Madman in The First Manned Space Station                        |         2006 |           1 |                 NULL |               3 |        2.99 |     85 |            21.99 | R      | Trailers                                               | 2006-02-15 05:03:42 |
        |      72 | BILL OTHERS                 | A Stunning Saga of a Mad Scientist And a Forensic Psychologist who must Challenge a Squirrel in A MySQL Convention                 |         2006 |           1 |                 NULL |               6 |        2.99 |     93 |            12.99 | PG     | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |      73 | BINGO TALENTED              | A Touching Tale of a Girl And a Crocodile who must Discover a Waitress in Nigeria                                                  |         2006 |           1 |                 NULL |               5 |        2.99 |    150 |            22.99 | PG-13  | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |      78 | BLACKOUT PRIVATE            | A Intrepid Yarn of a Pastry Chef And a Mad Scientist who must Challenge a Secret Agent in Ancient Japan                            |         2006 |           1 |                 NULL |               7 |        2.99 |     85 |            12.99 | PG     | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |      80 | BLANKET BEVERLY             | A Emotional Documentary of a Student And a Girl who must Build a Boat in Nigeria                                                   |         2006 |           1 |                 NULL |               7 |        2.99 |    148 |            21.99 | G      | Trailers                                               | 2006-02-15 05:03:42 |
        |      83 | BLUES INSTINCT              | A Insightful Documentary of a Boat And a Composer who must Meet a Forensic Psychologist in An Abandoned Fun House                  |         2006 |           1 |                 NULL |               5 |        2.99 |     50 |            18.99 | G      | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |      94 | BRAVEHEART HUMAN            | A Insightful Story of a Dog And a Pastry Chef who must Battle a Girl in Berlin                                                     |         2006 |           1 |                 NULL |               7 |        2.99 |    176 |            14.99 | PG-13  | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |      96 | BREAKING HOME               | A Beautiful Display of a Secret Agent And a Monkey who must Battle a Sumo Wrestler in An Abandoned Mine Shaft                      |         2006 |           1 |                 NULL |               4 |        2.99 |    169 |            21.99 | PG-13  | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |      99 | BRINGING HYSTERICAL         | A Fateful Saga of a A Shark And a Technical Writer who must Find a Woman in A Jet Boat                                             |         2006 |           1 |                 NULL |               7 |        2.99 |    136 |            14.99 | PG     | Trailers                                               | 2006-02-15 05:03:42 |
        |     104 | BUGSY SONG                  | A Awe-Inspiring Character Study of a Secret Agent And a Boat who must Find a Squirrel in The First Manned Space Station            |         2006 |           1 |                 NULL |               4 |        2.99 |    119 |            17.99 | G      | Commentaries                                           | 2006-02-15 05:03:42 |
        |     106 | BULWORTH COMMANDMENTS       | A Amazing Display of a Mad Cow And a Pioneer who must Redeem a Sumo Wrestler in The Outback                                        |         2006 |           1 |                 NULL |               4 |        2.99 |     61 |            14.99 | G      | Trailers                                               | 2006-02-15 05:03:42 |
        |     107 | BUNCH MINDS                 | A Emotional Story of a Feminist And a Feminist who must Escape a Pastry Chef in A MySQL Convention                                 |         2006 |           1 |                 NULL |               4 |        2.99 |     63 |            13.99 | G      | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     115 | CAMPUS REMEMBER             | A Astounding Drama of a Crocodile And a Mad Cow who must Build a Robot in A Jet Boat                                               |         2006 |           1 |                 NULL |               5 |        2.99 |    167 |            27.99 | R      | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     116 | CANDIDATE PERDITION         | A Brilliant Epistle of a Composer And a Database Administrator who must Vanquish a Mad Scientist in The First Manned Space Station |         2006 |           1 |                 NULL |               4 |        2.99 |     70 |            10.99 | R      | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     121 | CAROL TEXAS                 | A Astounding Character Study of a Composer And a Student who must Overcome a Composer in A Monastery                               |         2006 |           1 |                 NULL |               4 |        2.99 |    151 |            15.99 | PG     | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     125 | CASSIDY WYOMING             | A Intrepid Drama of a Frisbee And a Hunter who must Kill a Secret Agent in New Orleans                                             |         2006 |           1 |                 NULL |               5 |        2.99 |     61 |            19.99 | NC-17  | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     129 | CAUSE DATE                  | A Taut Tale of a Explorer And a Pastry Chef who must Conquer a Hunter in A MySQL Convention                                        |         2006 |           1 |                 NULL |               3 |        2.99 |    179 |            16.99 | R      | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     135 | CHANCE RESURRECTION         | A Astounding Story of a Forensic Psychologist And a Forensic Psychologist who must Overcome a Moose in Ancient China               |         2006 |           1 |                 NULL |               3 |        2.99 |     70 |            22.99 | R      | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     136 | CHAPLIN LICENSE             | A Boring Drama of a Dog And a Forensic Psychologist who must Outrace a Explorer in Ancient India                                   |         2006 |           1 |                 NULL |               7 |        2.99 |    146 |            26.99 | NC-17  | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     137 | CHARADE DUFFEL              | A Action-Packed Display of a Man And a Waitress who must Build a Dog in A MySQL Convention                                         |         2006 |           1 |                 NULL |               3 |        2.99 |     66 |            21.99 | PG     | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     138 | CHARIOTS CONSPIRACY         | A Unbelieveable Epistle of a Robot And a Husband who must Chase a Robot in The First Manned Space Station                          |         2006 |           1 |                 NULL |               5 |        2.99 |     71 |            29.99 | R      | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     146 | CHITTY LOCK                 | A Boring Epistle of a Boat And a Database Administrator who must Kill a Sumo Wrestler in The First Manned Space Station            |         2006 |           1 |                 NULL |               6 |        2.99 |    107 |            24.99 | G      | Commentaries                                           | 2006-02-15 05:03:42 |
        |     148 | CHOCOLATE DUCK              | A Unbelieveable Story of a Mad Scientist And a Technical Writer who must Discover a Composer in Ancient China                      |         2006 |           1 |                 NULL |               3 |        2.99 |    132 |            13.99 | R      | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     150 | CIDER DESIRE                | A Stunning Character Study of a Composer And a Mad Cow who must Succumb a Cat in Soviet Georgia                                    |         2006 |           1 |                 NULL |               7 |        2.99 |    101 |             9.99 | PG     | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     152 | CIRCUS YOUTH                | A Thoughtful Drama of a Pastry Chef And a Dentist who must Pursue a Girl in A Baloon                                               |         2006 |           1 |                 NULL |               5 |        2.99 |     90 |            13.99 | PG-13  | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     154 | CLASH FREDDY                | A Amazing Yarn of a Composer And a Squirrel who must Escape a Astronaut in Australia                                               |         2006 |           1 |                 NULL |               6 |        2.99 |     81 |            12.99 | G      | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     158 | CLONES PINOCCHIO            | A Amazing Drama of a Car And a Robot who must Pursue a Dentist in New Orleans                                                      |         2006 |           1 |                 NULL |               6 |        2.99 |    124 |            16.99 | R      | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     162 | CLUELESS BUCKET             | A Taut Tale of a Car And a Pioneer who must Conquer a Sumo Wrestler in An Abandoned Fun House                                      |         2006 |           1 |                 NULL |               4 |        2.99 |     95 |            13.99 | R      | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     166 | COLOR PHILADELPHIA          | A Thoughtful Panorama of a Car And a Crocodile who must Sink a Monkey in The Sahara Desert                                         |         2006 |           1 |                 NULL |               6 |        2.99 |    149 |            19.99 | G      | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     169 | COMFORTS RUSH               | A Unbelieveable Panorama of a Pioneer And a Husband who must Meet a Mad Cow in An Abandoned Mine Shaft                             |         2006 |           1 |                 NULL |               3 |        2.99 |     76 |            19.99 | NC-17  | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     175 | CONFUSED CANDLES            | A Stunning Epistle of a Cat And a Forensic Psychologist who must Confront a Pioneer in A Baloon                                    |         2006 |           1 |                 NULL |               3 |        2.99 |    122 |            27.99 | PG-13  | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |     180 | CONSPIRACY SPIRIT           | A Awe-Inspiring Story of a Student And a Frisbee who must Conquer a Crocodile in An Abandoned Mine Shaft                           |         2006 |           1 |                 NULL |               4 |        2.99 |    184 |            27.99 | PG-13  | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     181 | CONTACT ANONYMOUS           | A Insightful Display of a A Shark And a Monkey who must Face a Database Administrator in Ancient India                             |         2006 |           1 |                 NULL |               7 |        2.99 |    166 |            10.99 | PG-13  | Commentaries                                           | 2006-02-15 05:03:42 |
        |     184 | CORE SUIT                   | A Unbelieveable Tale of a Car And a Explorer who must Confront a Boat in A Manhattan Penthouse                                     |         2006 |           1 |                 NULL |               3 |        2.99 |     92 |            24.99 | PG-13  | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     185 | COWBOY DOOM                 | A Astounding Drama of a Boy And a Lumberjack who must Fight a Butler in A Baloon                                                   |         2006 |           1 |                 NULL |               3 |        2.99 |    146 |            10.99 | PG     | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     187 | CRANES RESERVOIR            | A Fanciful Documentary of a Teacher And a Dog who must Outgun a Forensic Psychologist in A Baloon Factory                          |         2006 |           1 |                 NULL |               5 |        2.99 |     57 |            12.99 | NC-17  | Commentaries                                           | 2006-02-15 05:03:42 |
        |     188 | CRAZY HOME                  | A Fanciful Panorama of a Boy And a Woman who must Vanquish a Database Administrator in The Outback                                 |         2006 |           1 |                 NULL |               7 |        2.99 |    136 |            24.99 | PG     | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     193 | CROSSROADS CASUALTIES       | A Intrepid Documentary of a Sumo Wrestler And a Astronaut who must Battle a Composer in The Outback                                |         2006 |           1 |                 NULL |               5 |        2.99 |    153 |            20.99 | G      | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     197 | CRUSADE HONEY               | A Fast-Paced Reflection of a Explorer And a Butler who must Battle a Madman in An Abandoned Amusement Park                         |         2006 |           1 |                 NULL |               4 |        2.99 |    112 |            27.99 | R      | Commentaries                                           | 2006-02-15 05:03:42 |
        |     198 | CRYSTAL BREAKING            | A Fast-Paced Character Study of a Feminist And a Explorer who must Face a Pastry Chef in Ancient Japan                             |         2006 |           1 |                 NULL |               6 |        2.99 |    184 |            22.99 | NC-17  | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     199 | CUPBOARD SINNERS            | A Emotional Reflection of a Frisbee And a Boat who must Reach a Pastry Chef in An Abandoned Amusement Park                         |         2006 |           1 |                 NULL |               4 |        2.99 |     56 |            29.99 | R      | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     201 | CYCLONE FAMILY              | A Lacklusture Drama of a Student And a Monkey who must Sink a Womanizer in A MySQL Convention                                      |         2006 |           1 |                 NULL |               7 |        2.99 |    176 |            18.99 | PG     | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     208 | DARES PLUTO                 | A Fateful Story of a Robot And a Dentist who must Defeat a Astronaut in New Orleans                                                |         2006 |           1 |                 NULL |               7 |        2.99 |     89 |            16.99 | PG-13  | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     209 | DARKNESS WAR                | A Touching Documentary of a Husband And a Hunter who must Escape a Boy in The Sahara Desert                                        |         2006 |           1 |                 NULL |               6 |        2.99 |     99 |            24.99 | NC-17  | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     220 | DEER VIRGINIAN              | A Thoughtful Story of a Mad Cow And a Womanizer who must Overcome a Mad Scientist in Soviet Georgia                                |         2006 |           1 |                 NULL |               7 |        2.99 |    106 |            13.99 | NC-17  | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     223 | DESIRE ALIEN                | A Fast-Paced Tale of a Dog And a Forensic Psychologist who must Meet a Astronaut in The First Manned Space Station                 |         2006 |           1 |                 NULL |               7 |        2.99 |     76 |            24.99 | NC-17  | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     230 | DIARY PANIC                 | A Thoughtful Character Study of a Frisbee And a Mad Cow who must Outgun a Man in Ancient India                                     |         2006 |           1 |                 NULL |               7 |        2.99 |    107 |            20.99 | G      | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     231 | DINOSAUR SECRETARY          | A Action-Packed Drama of a Feminist And a Girl who must Reach a Robot in The Canadian Rockies                                      |         2006 |           1 |                 NULL |               7 |        2.99 |     63 |            27.99 | R      | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     232 | DIRTY ACE                   | A Action-Packed Character Study of a Forensic Psychologist And a Girl who must Build a Dentist in The Outback                      |         2006 |           1 |                 NULL |               7 |        2.99 |    147 |            29.99 | NC-17  | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     234 | DISTURBING SCARFACE         | A Lacklusture Display of a Crocodile And a Butler who must Overcome a Monkey in A U-Boat                                           |         2006 |           1 |                 NULL |               6 |        2.99 |     94 |            27.99 | R      | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     235 | DIVIDE MONSTER              | A Intrepid Saga of a Man And a Forensic Psychologist who must Reach a Squirrel in A Monastery                                      |         2006 |           1 |                 NULL |               6 |        2.99 |     68 |            13.99 | PG-13  | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     236 | DIVINE RESURRECTION         | A Boring Character Study of a Man And a Womanizer who must Succumb a Teacher in An Abandoned Amusement Park                        |         2006 |           1 |                 NULL |               4 |        2.99 |    100 |            19.99 | R      | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     237 | DIVORCE SHINING             | A Unbelieveable Saga of a Crocodile And a Student who must Discover a Cat in Ancient India                                         |         2006 |           1 |                 NULL |               3 |        2.99 |     47 |            21.99 | G      | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     238 | DOCTOR GRAIL                | A Insightful Drama of a Womanizer And a Waitress who must Reach a Forensic Psychologist in The Outback                             |         2006 |           1 |                 NULL |               4 |        2.99 |     57 |            29.99 | G      | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     240 | DOLLS RAGE                  | A Thrilling Display of a Pioneer And a Frisbee who must Escape a Teacher in The Outback                                            |         2006 |           1 |                 NULL |               7 |        2.99 |    120 |            10.99 | PG-13  | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     252 | DREAM PICKUP                | A Epic Display of a Car And a Composer who must Overcome a Forensic Psychologist in The Gulf of Mexico                             |         2006 |           1 |                 NULL |               6 |        2.99 |    135 |            18.99 | PG     | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     254 | DRIVER ANNIE                | A Lacklusture Character Study of a Butler And a Car who must Redeem a Boat in An Abandoned Fun House                               |         2006 |           1 |                 NULL |               4 |        2.99 |    159 |            11.99 | PG-13  | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     259 | DUCK RACER                  | A Lacklusture Yarn of a Teacher And a Squirrel who must Overcome a Dog in A Shark Tank                                             |         2006 |           1 |                 NULL |               4 |        2.99 |    116 |            15.99 | NC-17  | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     264 | DWARFS ALTER                | A Emotional Yarn of a Girl And a Dog who must Challenge a Composer in Ancient Japan                                                |         2006 |           1 |                 NULL |               6 |        2.99 |    101 |            13.99 | G      | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     274 | EGG IGBY                    | A Beautiful Documentary of a Boat And a Sumo Wrestler who must Succumb a Database Administrator in The First Manned Space Station  |         2006 |           1 |                 NULL |               4 |        2.99 |     67 |            20.99 | PG     | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     286 | ENOUGH RAGING               | A Astounding Character Study of a Boat And a Secret Agent who must Find a Mad Cow in The Sahara Desert                             |         2006 |           1 |                 NULL |               7 |        2.99 |    158 |            16.99 | NC-17  | Commentaries                                           | 2006-02-15 05:03:42 |
        |     288 | ESCAPE METROPOLIS           | A Taut Yarn of a Astronaut And a Technical Writer who must Outgun a Boat in New Orleans                                            |         2006 |           1 |                 NULL |               7 |        2.99 |    167 |            20.99 | R      | Trailers                                               | 2006-02-15 05:03:42 |
        |     293 | EXORCIST STING              | A Touching Drama of a Dog And a Sumo Wrestler who must Conquer a Mad Scientist in Berlin                                           |         2006 |           1 |                 NULL |               6 |        2.99 |    167 |            17.99 | G      | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     296 | EXPRESS LONELY              | A Boring Drama of a Astronaut And a Boat who must Face a Boat in California                                                        |         2006 |           1 |                 NULL |               5 |        2.99 |    178 |            23.99 | R      | Trailers                                               | 2006-02-15 05:03:42 |
        |     297 | EXTRAORDINARY CONQUERER     | A Stunning Story of a Dog And a Feminist who must Face a Forensic Psychologist in Berlin                                           |         2006 |           1 |                 NULL |               6 |        2.99 |    122 |            29.99 | G      | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     298 | EYES DRIVING                | A Thrilling Story of a Cat And a Waitress who must Fight a Explorer in The Outback                                                 |         2006 |           1 |                 NULL |               4 |        2.99 |    172 |            13.99 | PG-13  | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     302 | FANTASIA PARK               | A Thoughtful Documentary of a Mad Scientist And a A Shark who must Outrace a Feminist in Australia                                 |         2006 |           1 |                 NULL |               5 |        2.99 |    131 |            29.99 | G      | Commentaries                                           | 2006-02-15 05:03:42 |
        |     304 | FARGO GANDHI                | A Thrilling Reflection of a Pastry Chef And a Crocodile who must Reach a Teacher in The Outback                                    |         2006 |           1 |                 NULL |               3 |        2.99 |    130 |            28.99 | G      | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     305 | FATAL HAUNTED               | A Beautiful Drama of a Student And a Secret Agent who must Confront a Dentist in Ancient Japan                                     |         2006 |           1 |                 NULL |               6 |        2.99 |     91 |            24.99 | PG     | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     308 | FERRIS MOTHER               | A Touching Display of a Frisbee And a Frisbee who must Kill a Girl in The Gulf of Mexico                                           |         2006 |           1 |                 NULL |               3 |        2.99 |    142 |            13.99 | PG     | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     319 | FISH OPUS                   | A Touching Display of a Feminist And a Girl who must Confront a Astronaut in Australia                                             |         2006 |           1 |                 NULL |               4 |        2.99 |    125 |            22.99 | R      | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     322 | FLATLINERS KILLER           | A Taut Display of a Secret Agent And a Waitress who must Sink a Robot in An Abandoned Mine Shaft                                   |         2006 |           1 |                 NULL |               5 |        2.99 |    100 |            29.99 | G      | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     325 | FLOATS GARDEN               | A Action-Packed Epistle of a Robot And a Car who must Chase a Boat in Ancient Japan                                                |         2006 |           1 |                 NULL |               6 |        2.99 |    145 |            29.99 | PG-13  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     326 | FLYING HOOK                 | A Thrilling Display of a Mad Cow And a Dog who must Challenge a Frisbee in Nigeria                                                 |         2006 |           1 |                 NULL |               6 |        2.99 |     69 |            18.99 | NC-17  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     328 | FOREVER CANDIDATE           | A Unbelieveable Panorama of a Technical Writer And a Man who must Pursue a Frisbee in A U-Boat                                     |         2006 |           1 |                 NULL |               7 |        2.99 |    131 |            28.99 | NC-17  | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     329 | FORREST SONS                | A Thrilling Documentary of a Forensic Psychologist And a Butler who must Defeat a Explorer in A Jet Boat                           |         2006 |           1 |                 NULL |               4 |        2.99 |     63 |            15.99 | R      | Commentaries                                           | 2006-02-15 05:03:42 |
        |     331 | FORWARD TEMPLE              | A Astounding Display of a Forensic Psychologist And a Mad Scientist who must Challenge a Girl in New Orleans                       |         2006 |           1 |                 NULL |               6 |        2.99 |     90 |            25.99 | NC-17  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     333 | FREAKY POCUS                | A Fast-Paced Documentary of a Pastry Chef And a Crocodile who must Chase a Squirrel in The Gulf of Mexico                          |         2006 |           1 |                 NULL |               7 |        2.99 |    126 |            16.99 | R      | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     337 | FRIDA SLIPPER               | A Fateful Story of a Lumberjack And a Car who must Escape a Boat in An Abandoned Mine Shaft                                        |         2006 |           1 |                 NULL |               6 |        2.99 |     73 |            11.99 | R      | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     343 | FULL FLATLINERS             | A Beautiful Documentary of a Astronaut And a Moose who must Pursue a Monkey in A Shark Tank                                        |         2006 |           1 |                 NULL |               6 |        2.99 |     94 |            14.99 | PG     | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     349 | GANGS PRIDE                 | A Taut Character Study of a Woman And a A Shark who must Confront a Frisbee in Berlin                                              |         2006 |           1 |                 NULL |               4 |        2.99 |    185 |            27.99 | PG-13  | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     351 | GASLIGHT CRUSADE            | A Amazing Epistle of a Boy And a Astronaut who must Redeem a Man in The Gulf of Mexico                                             |         2006 |           1 |                 NULL |               4 |        2.99 |    106 |            10.99 | PG     | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     353 | GENTLEMEN STAGE             | A Awe-Inspiring Reflection of a Monkey And a Student who must Overcome a Dentist in The First Manned Space Station                 |         2006 |           1 |                 NULL |               6 |        2.99 |    125 |            22.99 | NC-17  | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     356 | GIANT TROOPERS              | A Fateful Display of a Feminist And a Monkey who must Vanquish a Monkey in The Canadian Rockies                                    |         2006 |           1 |                 NULL |               5 |        2.99 |    102 |            10.99 | R      | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     361 | GLEAMING JAWBREAKER         | A Amazing Display of a Composer And a Forensic Psychologist who must Discover a Car in The Canadian Rockies                        |         2006 |           1 |                 NULL |               5 |        2.99 |     89 |            25.99 | NC-17  | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     362 | GLORY TRACY                 | A Amazing Saga of a Woman And a Womanizer who must Discover a Cat in The First Manned Space Station                                |         2006 |           1 |                 NULL |               7 |        2.99 |    115 |            13.99 | PG-13  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     364 | GODFATHER DIARY             | A Stunning Saga of a Lumberjack And a Squirrel who must Chase a Car in The Outback                                                 |         2006 |           1 |                 NULL |               3 |        2.99 |     73 |            14.99 | NC-17  | Trailers                                               | 2006-02-15 05:03:42 |
        |     368 | GONE TROUBLE                | A Insightful Character Study of a Mad Cow And a Forensic Psychologist who must Conquer a A Shark in A Manhattan Penthouse          |         2006 |           1 |                 NULL |               7 |        2.99 |     84 |            20.99 | R      | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     370 | GORGEOUS BINGO              | A Action-Packed Display of a Sumo Wrestler And a Car who must Overcome a Waitress in A Baloon Factory                              |         2006 |           1 |                 NULL |               4 |        2.99 |    108 |            26.99 | R      | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     373 | GRADUATE LORD               | A Lacklusture Epistle of a Girl And a A Shark who must Meet a Mad Scientist in Ancient China                                       |         2006 |           1 |                 NULL |               7 |        2.99 |    156 |            14.99 | G      | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     375 | GRAIL FRANKENSTEIN          | A Unbelieveable Saga of a Teacher And a Monkey who must Fight a Girl in An Abandoned Mine Shaft                                    |         2006 |           1 |                 NULL |               4 |        2.99 |     85 |            17.99 | NC-17  | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     378 | GREATEST NORTH              | A Astounding Character Study of a Secret Agent And a Robot who must Build a A Shark in Berlin                                      |         2006 |           1 |                 NULL |               5 |        2.99 |     93 |            24.99 | NC-17  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     380 | GREEK EVERYONE              | A Stunning Display of a Butler And a Teacher who must Confront a A Shark in The First Manned Space Station                         |         2006 |           1 |                 NULL |               7 |        2.99 |    176 |            11.99 | PG     | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     389 | GUNFIGHTER MUSSOLINI        | A Touching Saga of a Robot And a Boy who must Kill a Man in Ancient Japan                                                          |         2006 |           1 |                 NULL |               3 |        2.99 |    127 |             9.99 | PG-13  | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     391 | HALF OUTFIELD               | A Epic Epistle of a Database Administrator And a Crocodile who must Face a Madman in A Jet Boat                                    |         2006 |           1 |                 NULL |               6 |        2.99 |    146 |            25.99 | PG-13  | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |     393 | HALLOWEEN NUTS              | A Amazing Panorama of a Forensic Psychologist And a Technical Writer who must Fight a Dentist in A U-Boat                          |         2006 |           1 |                 NULL |               6 |        2.99 |     47 |            19.99 | PG-13  | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     394 | HAMLET WISDOM               | A Touching Reflection of a Man And a Man who must Sink a Robot in The Outback                                                      |         2006 |           1 |                 NULL |               7 |        2.99 |    146 |            21.99 | R      | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     397 | HANKY OCTOBER               | A Boring Epistle of a Database Administrator And a Explorer who must Pursue a Madman in Soviet Georgia                             |         2006 |           1 |                 NULL |               5 |        2.99 |    107 |            26.99 | NC-17  | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     399 | HAPPINESS UNITED            | A Action-Packed Panorama of a Husband And a Feminist who must Meet a Forensic Psychologist in Ancient Japan                        |         2006 |           1 |                 NULL |               6 |        2.99 |    100 |            23.99 | G      | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     400 | HARDLY ROBBERS              | A Emotional Character Study of a Hunter And a Car who must Kill a Woman in Berlin                                                  |         2006 |           1 |                 NULL |               7 |        2.99 |     72 |            15.99 | R      | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     410 | HEAVEN FREEDOM              | A Intrepid Story of a Butler And a Car who must Vanquish a Man in New Orleans                                                      |         2006 |           1 |                 NULL |               7 |        2.99 |     48 |            19.99 | PG     | Commentaries                                           | 2006-02-15 05:03:42 |
        |     413 | HEDWIG ALTER                | A Action-Packed Yarn of a Womanizer And a Lumberjack who must Chase a Sumo Wrestler in A Monastery                                 |         2006 |           1 |                 NULL |               7 |        2.99 |    169 |            16.99 | NC-17  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     414 | HELLFIGHTERS SIERRA         | A Taut Reflection of a A Shark And a Dentist who must Battle a Boat in Soviet Georgia                                              |         2006 |           1 |                 NULL |               3 |        2.99 |     75 |            23.99 | PG     | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     415 | HIGH ENCINO                 | A Fateful Saga of a Waitress And a Hunter who must Outrace a Sumo Wrestler in Australia                                            |         2006 |           1 |                 NULL |               3 |        2.99 |     84 |            23.99 | R      | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     419 | HOCUS FRIDA                 | A Awe-Inspiring Tale of a Girl And a Madman who must Outgun a Student in A Shark Tank                                              |         2006 |           1 |                 NULL |               4 |        2.99 |    141 |            19.99 | G      | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     428 | HOMICIDE PEACH              | A Astounding Documentary of a Hunter And a Boy who must Confront a Boy in A MySQL Convention                                       |         2006 |           1 |                 NULL |               6 |        2.99 |    141 |            21.99 | PG-13  | Commentaries                                           | 2006-02-15 05:03:42 |
        |     431 | HOOSIERS BIRDCAGE           | A Astounding Display of a Explorer And a Boat who must Vanquish a Car in The First Manned Space Station                            |         2006 |           1 |                 NULL |               3 |        2.99 |    176 |            12.99 | G      | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     432 | HOPE TOOTSIE                | A Amazing Documentary of a Student And a Sumo Wrestler who must Outgun a A Shark in A Shark Tank                                   |         2006 |           1 |                 NULL |               4 |        2.99 |    139 |            22.99 | NC-17  | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     433 | HORN WORKING                | A Stunning Display of a Mad Scientist And a Technical Writer who must Succumb a Monkey in A Shark Tank                             |         2006 |           1 |                 NULL |               4 |        2.99 |     95 |            23.99 | PG     | Trailers                                               | 2006-02-15 05:03:42 |
        |     437 | HOUSE DYNAMITE              | A Taut Story of a Pioneer And a Squirrel who must Battle a Student in Soviet Georgia                                               |         2006 |           1 |                 NULL |               7 |        2.99 |    109 |            13.99 | R      | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     438 | HUMAN GRAFFITI              | A Beautiful Reflection of a Womanizer And a Sumo Wrestler who must Chase a Database Administrator in The Gulf of Mexico            |         2006 |           1 |                 NULL |               3 |        2.99 |     68 |            22.99 | NC-17  | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     441 | HUNTER ALTER                | A Emotional Drama of a Mad Cow And a Boat who must Redeem a Secret Agent in A Shark Tank                                           |         2006 |           1 |                 NULL |               5 |        2.99 |    125 |            21.99 | PG-13  | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     442 | HUNTING MUSKETEERS          | A Thrilling Reflection of a Pioneer And a Dentist who must Outrace a Womanizer in An Abandoned Mine Shaft                          |         2006 |           1 |                 NULL |               6 |        2.99 |     65 |            24.99 | NC-17  | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     443 | HURRICANE AFFAIR            | A Lacklusture Epistle of a Database Administrator And a Woman who must Meet a Hunter in An Abandoned Mine Shaft                    |         2006 |           1 |                 NULL |               6 |        2.99 |     49 |            11.99 | PG     | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     445 | HYDE DOCTOR                 | A Fanciful Documentary of a Boy And a Woman who must Redeem a Womanizer in A Jet Boat                                              |         2006 |           1 |                 NULL |               5 |        2.99 |    100 |            11.99 | G      | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     447 | ICE CROSSING                | A Fast-Paced Tale of a Butler And a Moose who must Overcome a Pioneer in A Manhattan Penthouse                                     |         2006 |           1 |                 NULL |               5 |        2.99 |    131 |            28.99 | R      | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     448 | IDAHO LOVE                  | A Fast-Paced Drama of a Student And a Crocodile who must Meet a Database Administrator in The Outback                              |         2006 |           1 |                 NULL |               3 |        2.99 |    172 |            25.99 | PG-13  | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |     449 | IDENTITY LOVER              | A Boring Tale of a Composer And a Mad Cow who must Defeat a Car in The Outback                                                     |         2006 |           1 |                 NULL |               4 |        2.99 |    119 |            12.99 | PG-13  | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     450 | IDOLS SNATCHERS             | A Insightful Drama of a Car And a Composer who must Fight a Man in A Monastery                                                     |         2006 |           1 |                 NULL |               5 |        2.99 |     84 |            29.99 | NC-17  | Trailers                                               | 2006-02-15 05:03:42 |
        |     453 | IMAGE PRINCESS              | A Lacklusture Panorama of a Secret Agent And a Crocodile who must Discover a Madman in The Canadian Rockies                        |         2006 |           1 |                 NULL |               3 |        2.99 |    178 |            17.99 | PG-13  | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     462 | INSIDER ARIZONA             | A Astounding Saga of a Mad Scientist And a Hunter who must Pursue a Robot in A Baloon Factory                                      |         2006 |           1 |                 NULL |               5 |        2.99 |     78 |            17.99 | NC-17  | Commentaries                                           | 2006-02-15 05:03:42 |
        |     463 | INSTINCT AIRPORT            | A Touching Documentary of a Mad Cow And a Explorer who must Confront a Butler in A Manhattan Penthouse                             |         2006 |           1 |                 NULL |               4 |        2.99 |    116 |            21.99 | PG     | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     464 | INTENTIONS EMPIRE           | A Astounding Epistle of a Cat And a Cat who must Conquer a Mad Cow in A U-Boat                                                     |         2006 |           1 |                 NULL |               3 |        2.99 |    107 |            13.99 | PG-13  | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     468 | INVASION CYCLONE            | A Lacklusture Character Study of a Mad Scientist And a Womanizer who must Outrace a Explorer in A Monastery                        |         2006 |           1 |                 NULL |               5 |        2.99 |     97 |            12.99 | PG     | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     471 | ISLAND EXORCIST             | A Fanciful Panorama of a Technical Writer And a Boy who must Find a Dentist in An Abandoned Fun House                              |         2006 |           1 |                 NULL |               7 |        2.99 |     84 |            23.99 | NC-17  | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     473 | JACKET FRISCO               | A Insightful Reflection of a Womanizer And a Husband who must Conquer a Pastry Chef in A Baloon                                    |         2006 |           1 |                 NULL |               5 |        2.99 |    181 |            16.99 | PG-13  | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     474 | JADE BUNCH                  | A Insightful Panorama of a Squirrel And a Mad Cow who must Confront a Student in The First Manned Space Station                    |         2006 |           1 |                 NULL |               6 |        2.99 |    174 |            21.99 | NC-17  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     476 | JASON TRAP                  | A Thoughtful Tale of a Woman And a A Shark who must Conquer a Dog in A Monastery                                                   |         2006 |           1 |                 NULL |               5 |        2.99 |    130 |             9.99 | NC-17  | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     478 | JAWS HARRY                  | A Thrilling Display of a Database Administrator And a Monkey who must Overcome a Dog in An Abandoned Fun House                     |         2006 |           1 |                 NULL |               4 |        2.99 |    112 |            10.99 | G      | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     480 | JEEPERS WEDDING             | A Astounding Display of a Composer And a Dog who must Kill a Pastry Chef in Soviet Georgia                                         |         2006 |           1 |                 NULL |               3 |        2.99 |     84 |            29.99 | R      | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     481 | JEKYLL FROGMEN              | A Fanciful Epistle of a Student And a Astronaut who must Kill a Waitress in A Shark Tank                                           |         2006 |           1 |                 NULL |               4 |        2.99 |     58 |            22.99 | PG     | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     483 | JERICHO MULAN               | A Amazing Yarn of a Hunter And a Butler who must Defeat a Boy in A Jet Boat                                                        |         2006 |           1 |                 NULL |               3 |        2.99 |    171 |            29.99 | NC-17  | Commentaries                                           | 2006-02-15 05:03:42 |
        |     484 | JERK PAYCHECK               | A Touching Character Study of a Pastry Chef And a Database Administrator who must Reach a A Shark in Ancient Japan                 |         2006 |           1 |                 NULL |               3 |        2.99 |    172 |            13.99 | NC-17  | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |     490 | JUMANJI BLADE               | A Intrepid Yarn of a Husband And a Womanizer who must Pursue a Mad Scientist in New Orleans                                        |         2006 |           1 |                 NULL |               4 |        2.99 |    121 |            13.99 | G      | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     495 | KENTUCKIAN GIANT            | A Stunning Yarn of a Woman And a Frisbee who must Escape a Waitress in A U-Boat                                                    |         2006 |           1 |                 NULL |               5 |        2.99 |    169 |            10.99 | PG     | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |     498 | KILLER INNOCENT             | A Fanciful Character Study of a Student And a Explorer who must Succumb a Composer in An Abandoned Mine Shaft                      |         2006 |           1 |                 NULL |               7 |        2.99 |    161 |            11.99 | R      | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     502 | KNOCK WARLOCK               | A Unbelieveable Story of a Teacher And a Boat who must Confront a Moose in A Baloon                                                |         2006 |           1 |                 NULL |               4 |        2.99 |     71 |            21.99 | PG-13  | Trailers                                               | 2006-02-15 05:03:42 |
        |     503 | KRAMER CHOCOLATE            | A Amazing Yarn of a Robot And a Pastry Chef who must Redeem a Mad Scientist in The Outback                                         |         2006 |           1 |                 NULL |               3 |        2.99 |    171 |            24.99 | R      | Trailers                                               | 2006-02-15 05:03:42 |
        |     505 | LABYRINTH LEAGUE            | A Awe-Inspiring Saga of a Composer And a Frisbee who must Succumb a Pioneer in The Sahara Desert                                   |         2006 |           1 |                 NULL |               6 |        2.99 |     46 |            24.99 | PG-13  | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     513 | LEATHERNECKS DWARFS         | A Fateful Reflection of a Dog And a Mad Cow who must Outrace a Teacher in An Abandoned Mine Shaft                                  |         2006 |           1 |                 NULL |               6 |        2.99 |    153 |            21.99 | PG-13  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     514 | LEBOWSKI SOLDIERS           | A Beautiful Epistle of a Secret Agent And a Pioneer who must Chase a Astronaut in Ancient China                                    |         2006 |           1 |                 NULL |               6 |        2.99 |     69 |            17.99 | PG-13  | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     519 | LIBERTY MAGNIFICENT         | A Boring Drama of a Student And a Cat who must Sink a Technical Writer in A Baloon                                                 |         2006 |           1 |                 NULL |               3 |        2.99 |    138 |            27.99 | G      | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     520 | LICENSE WEEKEND             | A Insightful Story of a Man And a Husband who must Overcome a Madman in A Monastery                                                |         2006 |           1 |                 NULL |               7 |        2.99 |     91 |            28.99 | NC-17  | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     522 | LIFE TWISTED                | A Thrilling Reflection of a Teacher And a Composer who must Find a Man in The First Manned Space Station                           |         2006 |           1 |                 NULL |               4 |        2.99 |    137 |             9.99 | NC-17  | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     526 | LOCK REAR                   | A Thoughtful Character Study of a Squirrel And a Technical Writer who must Outrace a Student in Ancient Japan                      |         2006 |           1 |                 NULL |               7 |        2.99 |    120 |            10.99 | R      | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     528 | LOLITA WORLD                | A Thrilling Drama of a Girl And a Robot who must Redeem a Waitress in An Abandoned Mine Shaft                                      |         2006 |           1 |                 NULL |               4 |        2.99 |    155 |            25.99 | NC-17  | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     529 | LONELY ELEPHANT             | A Intrepid Story of a Student And a Dog who must Challenge a Explorer in Soviet Georgia                                            |         2006 |           1 |                 NULL |               3 |        2.99 |     67 |            12.99 | G      | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |     530 | LORD ARIZONA                | A Action-Packed Display of a Frisbee And a Pastry Chef who must Pursue a Crocodile in A Jet Boat                                   |         2006 |           1 |                 NULL |               5 |        2.99 |    108 |            27.99 | PG-13  | Trailers                                               | 2006-02-15 05:03:42 |
        |     533 | LOST BIRD                   | A Emotional Character Study of a Robot And a A Shark who must Defeat a Technical Writer in A Manhattan Penthouse                   |         2006 |           1 |                 NULL |               4 |        2.99 |     98 |            21.99 | PG-13  | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     536 | LOVELY JINGLE               | A Fanciful Yarn of a Crocodile And a Forensic Psychologist who must Discover a Crocodile in The Outback                            |         2006 |           1 |                 NULL |               3 |        2.99 |     65 |            18.99 | PG     | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     537 | LOVER TRUMAN                | A Emotional Yarn of a Robot And a Boy who must Outgun a Technical Writer in A U-Boat                                               |         2006 |           1 |                 NULL |               3 |        2.99 |     75 |            29.99 | G      | Trailers                                               | 2006-02-15 05:03:42 |
        |     539 | LUCK OPUS                   | A Boring Display of a Moose And a Squirrel who must Outrace a Teacher in A Shark Tank                                              |         2006 |           1 |                 NULL |               7 |        2.99 |    152 |            21.99 | NC-17  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     540 | LUCKY FLYING                | A Lacklusture Character Study of a A Shark And a Man who must Find a Forensic Psychologist in A U-Boat                             |         2006 |           1 |                 NULL |               7 |        2.99 |     97 |            10.99 | PG-13  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     541 | LUKE MUMMY                  | A Taut Character Study of a Boy And a Robot who must Redeem a Mad Scientist in Ancient India                                       |         2006 |           1 |                 NULL |               5 |        2.99 |     74 |            21.99 | NC-17  | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     542 | LUST LOCK                   | A Fanciful Panorama of a Hunter And a Dentist who must Meet a Secret Agent in The Sahara Desert                                    |         2006 |           1 |                 NULL |               3 |        2.99 |     52 |            28.99 | G      | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     544 | MADISON TRAP                | A Awe-Inspiring Reflection of a Monkey And a Dentist who must Overcome a Pioneer in A U-Boat                                       |         2006 |           1 |                 NULL |               4 |        2.99 |    147 |            11.99 | R      | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     546 | MADRE GABLES                | A Intrepid Panorama of a Sumo Wrestler And a Forensic Psychologist who must Discover a Moose in The First Manned Space Station     |         2006 |           1 |                 NULL |               7 |        2.99 |     98 |            27.99 | PG-13  | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     548 | MAGNIFICENT CHITTY          | A Insightful Story of a Teacher And a Hunter who must Face a Mad Cow in California                                                 |         2006 |           1 |                 NULL |               3 |        2.99 |     53 |            27.99 | R      | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     550 | MAGUIRE APACHE              | A Fast-Paced Reflection of a Waitress And a Hunter who must Defeat a Forensic Psychologist in A Baloon                             |         2006 |           1 |                 NULL |               6 |        2.99 |     74 |            22.99 | NC-17  | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     554 | MALKOVICH PET               | A Intrepid Reflection of a Waitress And a A Shark who must Kill a Squirrel in The Outback                                          |         2006 |           1 |                 NULL |               6 |        2.99 |    159 |            22.99 | G      | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     557 | MANCHURIAN CURTAIN          | A Stunning Tale of a Mad Cow And a Boy who must Battle a Boy in Berlin                                                             |         2006 |           1 |                 NULL |               5 |        2.99 |    177 |            27.99 | PG     | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     558 | MANNEQUIN WORST             | A Astounding Saga of a Mad Cow And a Pastry Chef who must Discover a Husband in Ancient India                                      |         2006 |           1 |                 NULL |               3 |        2.99 |     71 |            18.99 | PG-13  | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     559 | MARRIED GO                  | A Fanciful Story of a Womanizer And a Dog who must Face a Forensic Psychologist in The Sahara Desert                               |         2006 |           1 |                 NULL |               7 |        2.99 |    114 |            22.99 | G      | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     561 | MASK PEACH                  | A Boring Character Study of a Student And a Robot who must Meet a Woman in California                                              |         2006 |           1 |                 NULL |               6 |        2.99 |    123 |            26.99 | NC-17  | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     564 | MASSAGE IMAGE               | A Fateful Drama of a Frisbee And a Crocodile who must Vanquish a Dog in The First Manned Space Station                             |         2006 |           1 |                 NULL |               4 |        2.99 |    161 |            11.99 | PG     | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     567 | MEET CHOCOLATE              | A Boring Documentary of a Dentist And a Butler who must Confront a Monkey in A MySQL Convention                                    |         2006 |           1 |                 NULL |               3 |        2.99 |     80 |            26.99 | G      | Trailers                                               | 2006-02-15 05:03:42 |
        |     569 | MENAGERIE RUSHMORE          | A Unbelieveable Panorama of a Composer And a Butler who must Overcome a Database Administrator in The First Manned Space Station   |         2006 |           1 |                 NULL |               7 |        2.99 |    147 |            18.99 | G      | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     571 | METAL ARMAGEDDON            | A Thrilling Display of a Lumberjack And a Crocodile who must Meet a Monkey in A Baloon Factory                                     |         2006 |           1 |                 NULL |               6 |        2.99 |    161 |            26.99 | PG-13  | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     572 | METROPOLIS COMA             | A Emotional Saga of a Database Administrator And a Pastry Chef who must Confront a Teacher in A Baloon Factory                     |         2006 |           1 |                 NULL |               4 |        2.99 |     64 |             9.99 | PG-13  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     573 | MICROCOSMOS PARADISE        | A Touching Character Study of a Boat And a Student who must Sink a A Shark in Nigeria                                              |         2006 |           1 |                 NULL |               6 |        2.99 |    105 |            22.99 | PG-13  | Commentaries                                           | 2006-02-15 05:03:42 |
        |     576 | MIGHTY LUCK                 | A Astounding Epistle of a Mad Scientist And a Pioneer who must Escape a Database Administrator in A MySQL Convention               |         2006 |           1 |                 NULL |               7 |        2.99 |    122 |            13.99 | PG     | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     582 | MIRACLE VIRTUAL             | A Touching Epistle of a Butler And a Boy who must Find a Mad Scientist in The Sahara Desert                                        |         2006 |           1 |                 NULL |               3 |        2.99 |    162 |            19.99 | PG-13  | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     584 | MIXED DOORS                 | A Taut Drama of a Womanizer And a Lumberjack who must Succumb a Pioneer in Ancient India                                           |         2006 |           1 |                 NULL |               6 |        2.99 |    180 |            26.99 | PG-13  | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     590 | MONEY HAROLD                | A Touching Tale of a Explorer And a Boat who must Defeat a Robot in Australia                                                      |         2006 |           1 |                 NULL |               3 |        2.99 |    135 |            17.99 | PG     | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     592 | MONSTER SPARTACUS           | A Fast-Paced Story of a Waitress And a Cat who must Fight a Girl in Australia                                                      |         2006 |           1 |                 NULL |               6 |        2.99 |    107 |            28.99 | PG     | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     605 | MULHOLLAND BEAST            | A Awe-Inspiring Display of a Husband And a Squirrel who must Battle a Sumo Wrestler in A Jet Boat                                  |         2006 |           1 |                 NULL |               7 |        2.99 |    157 |            13.99 | PG     | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     608 | MURDER ANTITRUST            | A Brilliant Yarn of a Car And a Database Administrator who must Escape a Boy in A MySQL Convention                                 |         2006 |           1 |                 NULL |               6 |        2.99 |    166 |            11.99 | PG     | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     609 | MUSCLE BRIGHT               | A Stunning Panorama of a Sumo Wrestler And a Husband who must Redeem a Madman in Ancient India                                     |         2006 |           1 |                 NULL |               7 |        2.99 |    185 |            23.99 | G      | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     612 | MUSSOLINI SPOILERS          | A Thrilling Display of a Boat And a Monkey who must Meet a Composer in Ancient China                                               |         2006 |           1 |                 NULL |               6 |        2.99 |    180 |            10.99 | G      | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     615 | NASH CHOCOLAT               | A Epic Reflection of a Monkey And a Mad Cow who must Kill a Forensic Psychologist in An Abandoned Mine Shaft                       |         2006 |           1 |                 NULL |               6 |        2.99 |    180 |            21.99 | PG-13  | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     616 | NATIONAL STORY              | A Taut Epistle of a Mad Scientist And a Girl who must Escape a Monkey in California                                                |         2006 |           1 |                 NULL |               4 |        2.99 |     92 |            19.99 | NC-17  | Trailers                                               | 2006-02-15 05:03:42 |
        |     620 | NEMO CAMPUS                 | A Lacklusture Reflection of a Monkey And a Squirrel who must Outrace a Womanizer in A Manhattan Penthouse                          |         2006 |           1 |                 NULL |               5 |        2.99 |    131 |            23.99 | NC-17  | Trailers                                               | 2006-02-15 05:03:42 |
        |     621 | NETWORK PEAK                | A Unbelieveable Reflection of a Butler And a Boat who must Outgun a Mad Scientist in California                                    |         2006 |           1 |                 NULL |               5 |        2.99 |     75 |            23.99 | PG-13  | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     626 | NOON PAPI                   | A Unbelieveable Character Study of a Mad Scientist And a Astronaut who must Find a Pioneer in A Manhattan Penthouse                |         2006 |           1 |                 NULL |               5 |        2.99 |     57 |            12.99 | G      | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     628 | NORTHWEST POLISH            | A Boring Character Study of a Boy And a A Shark who must Outrace a Womanizer in The Outback                                        |         2006 |           1 |                 NULL |               5 |        2.99 |    172 |            24.99 | PG     | Trailers                                               | 2006-02-15 05:03:42 |
        |     638 | OPERATION OPERATION         | A Intrepid Character Study of a Man And a Frisbee who must Overcome a Madman in Ancient China                                      |         2006 |           1 |                 NULL |               7 |        2.99 |    156 |            23.99 | G      | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |     642 | ORDER BETRAYED              | A Amazing Saga of a Dog And a A Shark who must Challenge a Cat in The Sahara Desert                                                |         2006 |           1 |                 NULL |               7 |        2.99 |    120 |            13.99 | PG-13  | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     643 | ORIENT CLOSER               | A Astounding Epistle of a Technical Writer And a Teacher who must Fight a Squirrel in The Sahara Desert                            |         2006 |           1 |                 NULL |               3 |        2.99 |    118 |            22.99 | R      | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     644 | OSCAR GOLD                  | A Insightful Tale of a Database Administrator And a Dog who must Face a Madman in Soviet Georgia                                   |         2006 |           1 |                 NULL |               7 |        2.99 |    115 |            29.99 | PG     | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     645 | OTHERS SOUP                 | A Lacklusture Documentary of a Mad Cow And a Madman who must Sink a Moose in The Gulf of Mexico                                    |         2006 |           1 |                 NULL |               7 |        2.99 |    118 |            18.99 | PG     | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     649 | OZ LIAISONS                 | A Epic Yarn of a Mad Scientist And a Cat who must Confront a Womanizer in A Baloon Factory                                         |         2006 |           1 |                 NULL |               4 |        2.99 |     85 |            14.99 | R      | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     657 | PARADISE SABRINA            | A Intrepid Yarn of a Car And a Moose who must Outrace a Crocodile in A Manhattan Penthouse                                         |         2006 |           1 |                 NULL |               5 |        2.99 |     48 |            12.99 | PG-13  | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     658 | PARIS WEEKEND               | A Intrepid Story of a Squirrel And a Crocodile who must Defeat a Monkey in The Outback                                             |         2006 |           1 |                 NULL |               7 |        2.99 |    121 |            19.99 | PG-13  | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |     660 | PARTY KNOCK                 | A Fateful Display of a Technical Writer And a Butler who must Battle a Sumo Wrestler in An Abandoned Mine Shaft                    |         2006 |           1 |                 NULL |               7 |        2.99 |    107 |            11.99 | PG     | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     664 | PATRIOT ROMAN               | A Taut Saga of a Robot And a Database Administrator who must Challenge a Astronaut in California                                   |         2006 |           1 |                 NULL |               6 |        2.99 |     65 |            12.99 | PG     | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     665 | PATTON INTERVIEW            | A Thrilling Documentary of a Composer And a Secret Agent who must Succumb a Cat in Berlin                                          |         2006 |           1 |                 NULL |               4 |        2.99 |    175 |            22.99 | PG     | Commentaries                                           | 2006-02-15 05:03:42 |
        |     667 | PEACH INNOCENT              | A Action-Packed Drama of a Monkey And a Dentist who must Chase a Butler in Berlin                                                  |         2006 |           1 |                 NULL |               3 |        2.99 |    160 |            20.99 | PG-13  | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     669 | PEARL DESTINY               | A Lacklusture Yarn of a Astronaut And a Pastry Chef who must Sink a Dog in A U-Boat                                                |         2006 |           1 |                 NULL |               3 |        2.99 |     74 |            10.99 | NC-17  | Trailers                                               | 2006-02-15 05:03:42 |
        |     672 | PERFECT GROOVE              | A Thrilling Yarn of a Dog And a Dog who must Build a Husband in A Baloon                                                           |         2006 |           1 |                 NULL |               7 |        2.99 |     82 |            17.99 | PG-13  | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     675 | PHANTOM GLORY               | A Beautiful Documentary of a Astronaut And a Crocodile who must Discover a Madman in A Monastery                                   |         2006 |           1 |                 NULL |               6 |        2.99 |     60 |            17.99 | NC-17  | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     678 | PICKUP DRIVING              | A Touching Documentary of a Husband And a Boat who must Meet a Pastry Chef in A Baloon Factory                                     |         2006 |           1 |                 NULL |               3 |        2.99 |     77 |            23.99 | G      | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |     679 | PILOT HOOSIERS              | A Awe-Inspiring Reflection of a Crocodile And a Sumo Wrestler who must Meet a Forensic Psychologist in An Abandoned Mine Shaft     |         2006 |           1 |                 NULL |               6 |        2.99 |     50 |            17.99 | PG     | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     684 | PIZZA JUMANJI               | A Epic Saga of a Cat And a Squirrel who must Outgun a Robot in A U-Boat                                                            |         2006 |           1 |                 NULL |               4 |        2.99 |    173 |            11.99 | NC-17  | Commentaries                                           | 2006-02-15 05:03:42 |
        |     689 | POLLOCK DELIVERANCE         | A Intrepid Story of a Madman And a Frisbee who must Outgun a Boat in The Sahara Desert                                             |         2006 |           1 |                 NULL |               5 |        2.99 |    137 |            14.99 | PG     | Commentaries                                           | 2006-02-15 05:03:42 |
        |     690 | POND SEATTLE                | A Stunning Drama of a Teacher And a Boat who must Battle a Feminist in Ancient China                                               |         2006 |           1 |                 NULL |               7 |        2.99 |    185 |            25.99 | PG-13  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     692 | POTLUCK MIXED               | A Beautiful Story of a Dog And a Technical Writer who must Outgun a Student in A Baloon                                            |         2006 |           1 |                 NULL |               3 |        2.99 |    179 |            10.99 | G      | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     693 | POTTER CONNECTICUT          | A Thrilling Epistle of a Frisbee And a Cat who must Fight a Technical Writer in Berlin                                             |         2006 |           1 |                 NULL |               5 |        2.99 |    115 |            16.99 | PG     | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     698 | PRINCESS GIANT              | A Thrilling Yarn of a Pastry Chef And a Monkey who must Battle a Monkey in A Shark Tank                                            |         2006 |           1 |                 NULL |               3 |        2.99 |     71 |            29.99 | NC-17  | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     700 | PRIX UNDEFEATED             | A Stunning Saga of a Mad Scientist And a Boat who must Overcome a Dentist in Ancient China                                         |         2006 |           1 |                 NULL |               4 |        2.99 |    115 |            13.99 | R      | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     701 | PSYCHO SHRUNK               | A Amazing Panorama of a Crocodile And a Explorer who must Fight a Husband in Nigeria                                               |         2006 |           1 |                 NULL |               5 |        2.99 |    155 |            11.99 | PG-13  | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     702 | PULP BEVERLY                | A Unbelieveable Display of a Dog And a Crocodile who must Outrace a Man in Nigeria                                                 |         2006 |           1 |                 NULL |               4 |        2.99 |     89 |            12.99 | G      | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     704 | PURE RUNNER                 | A Thoughtful Documentary of a Student And a Madman who must Challenge a Squirrel in A Manhattan Penthouse                          |         2006 |           1 |                 NULL |               3 |        2.99 |    121 |            25.99 | NC-17  | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     705 | PURPLE MOVIE                | A Boring Display of a Pastry Chef And a Sumo Wrestler who must Discover a Frisbee in An Abandoned Amusement Park                   |         2006 |           1 |                 NULL |               4 |        2.99 |     88 |             9.99 | R      | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     707 | QUEST MUSSOLINI             | A Fateful Drama of a Husband And a Sumo Wrestler who must Battle a Pastry Chef in A Baloon Factory                                 |         2006 |           1 |                 NULL |               5 |        2.99 |    177 |            29.99 | R      | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     709 | RACER EGG                   | A Emotional Display of a Monkey And a Waitress who must Reach a Secret Agent in California                                         |         2006 |           1 |                 NULL |               7 |        2.99 |    147 |            19.99 | NC-17  | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     714 | RANDOM GO                   | A Fateful Drama of a Frisbee And a Student who must Confront a Cat in A Shark Tank                                                 |         2006 |           1 |                 NULL |               6 |        2.99 |     73 |            29.99 | NC-17  | Trailers                                               | 2006-02-15 05:03:42 |
        |     716 | REAP UNFAITHFUL             | A Thrilling Epistle of a Composer And a Sumo Wrestler who must Challenge a Mad Cow in A MySQL Convention                           |         2006 |           1 |                 NULL |               6 |        2.99 |    136 |            26.99 | PG-13  | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     720 | REDEMPTION COMFORTS         | A Emotional Documentary of a Dentist And a Woman who must Battle a Mad Scientist in Ancient China                                  |         2006 |           1 |                 NULL |               3 |        2.99 |    179 |            20.99 | NC-17  | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     723 | REIGN GENTLEMEN             | A Emotional Yarn of a Composer And a Man who must Escape a Butler in The Gulf of Mexico                                            |         2006 |           1 |                 NULL |               3 |        2.99 |     82 |            29.99 | PG-13  | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     724 | REMEMBER DIARY              | A Insightful Tale of a Technical Writer And a Waitress who must Conquer a Monkey in Ancient India                                  |         2006 |           1 |                 NULL |               5 |        2.99 |    110 |            15.99 | R      | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     726 | RESERVOIR ADAPTATION        | A Intrepid Drama of a Teacher And a Moose who must Kill a Car in California                                                        |         2006 |           1 |                 NULL |               7 |        2.99 |     61 |            29.99 | PG-13  | Commentaries                                           | 2006-02-15 05:03:42 |
        |     729 | RIDER CADDYSHACK            | A Taut Reflection of a Monkey And a Womanizer who must Chase a Moose in Nigeria                                                    |         2006 |           1 |                 NULL |               5 |        2.99 |    177 |            28.99 | PG     | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     735 | ROBBERS JOON                | A Thoughtful Story of a Mad Scientist And a Waitress who must Confront a Forensic Psychologist in Soviet Georgia                   |         2006 |           1 |                 NULL |               7 |        2.99 |    102 |            26.99 | PG-13  | Commentaries                                           | 2006-02-15 05:03:42 |
        |     740 | ROLLERCOASTER BRINGING      | A Beautiful Drama of a Robot And a Lumberjack who must Discover a Technical Writer in A Shark Tank                                 |         2006 |           1 |                 NULL |               5 |        2.99 |    153 |            13.99 | PG-13  | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     754 | RUSHMORE MERMAID            | A Boring Story of a Woman And a Moose who must Reach a Husband in A Shark Tank                                                     |         2006 |           1 |                 NULL |               6 |        2.99 |    150 |            17.99 | PG-13  | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     756 | SADDLE ANTITRUST            | A Stunning Epistle of a Feminist And a A Shark who must Battle a Woman in An Abandoned Fun House                                   |         2006 |           1 |                 NULL |               7 |        2.99 |     80 |            10.99 | PG-13  | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     757 | SAGEBRUSH CLUELESS          | A Insightful Story of a Lumberjack And a Hunter who must Kill a Boy in Ancient Japan                                               |         2006 |           1 |                 NULL |               4 |        2.99 |    106 |            28.99 | G      | Trailers                                               | 2006-02-15 05:03:42 |
        |     758 | SAINTS BRIDE                | A Fateful Tale of a Technical Writer And a Composer who must Pursue a Explorer in The Gulf of Mexico                               |         2006 |           1 |                 NULL |               5 |        2.99 |    125 |            11.99 | G      | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     759 | SALUTE APOLLO               | A Awe-Inspiring Character Study of a Boy And a Feminist who must Sink a Crocodile in Ancient China                                 |         2006 |           1 |                 NULL |               4 |        2.99 |     73 |            29.99 | R      | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |     760 | SAMURAI LION                | A Fast-Paced Story of a Pioneer And a Astronaut who must Reach a Boat in A Baloon                                                  |         2006 |           1 |                 NULL |               5 |        2.99 |    110 |            21.99 | G      | Commentaries                                           | 2006-02-15 05:03:42 |
        |     761 | SANTA PARIS                 | A Emotional Documentary of a Moose And a Car who must Redeem a Mad Cow in A Baloon Factory                                         |         2006 |           1 |                 NULL |               7 |        2.99 |    154 |            23.99 | PG     | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     770 | SCISSORHANDS SLUMS          | A Awe-Inspiring Drama of a Girl And a Technical Writer who must Meet a Feminist in The Canadian Rockies                            |         2006 |           1 |                 NULL |               5 |        2.99 |    147 |            13.99 | G      | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     772 | SEA VIRGIN                  | A Fast-Paced Documentary of a Technical Writer And a Pastry Chef who must Escape a Moose in A U-Boat                               |         2006 |           1 |                 NULL |               4 |        2.99 |     80 |            24.99 | PG     | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     773 | SEABISCUIT PUNK             | A Insightful Saga of a Man And a Forensic Psychologist who must Discover a Mad Cow in A MySQL Convention                           |         2006 |           1 |                 NULL |               6 |        2.99 |    112 |            28.99 | NC-17  | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     774 | SEARCHERS WAIT              | A Fast-Paced Tale of a Car And a Mad Scientist who must Kill a Womanizer in Ancient Japan                                          |         2006 |           1 |                 NULL |               3 |        2.99 |    182 |            22.99 | NC-17  | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |     782 | SHAKESPEARE SADDLE          | A Fast-Paced Panorama of a Lumberjack And a Database Administrator who must Defeat a Madman in A MySQL Convention                  |         2006 |           1 |                 NULL |               6 |        2.99 |     60 |            26.99 | PG-13  | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     783 | SHANE DARKNESS              | A Action-Packed Saga of a Moose And a Lumberjack who must Find a Woman in Berlin                                                   |         2006 |           1 |                 NULL |               5 |        2.99 |     93 |            22.99 | PG     | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     784 | SHANGHAI TYCOON             | A Fast-Paced Character Study of a Crocodile And a Lumberjack who must Build a Husband in An Abandoned Fun House                    |         2006 |           1 |                 NULL |               7 |        2.99 |     47 |            20.99 | PG     | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     788 | SHIP WONDERLAND             | A Thrilling Saga of a Monkey And a Frisbee who must Escape a Explorer in The Outback                                               |         2006 |           1 |                 NULL |               5 |        2.99 |    104 |            15.99 | R      | Commentaries                                           | 2006-02-15 05:03:42 |
        |     789 | SHOCK CABIN                 | A Fateful Tale of a Mad Cow And a Crocodile who must Meet a Husband in New Orleans                                                 |         2006 |           1 |                 NULL |               7 |        2.99 |     79 |            15.99 | PG-13  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     792 | SHREK LICENSE               | A Fateful Yarn of a Secret Agent And a Feminist who must Find a Feminist in A Jet Boat                                             |         2006 |           1 |                 NULL |               7 |        2.99 |    154 |            15.99 | PG-13  | Commentaries                                           | 2006-02-15 05:03:42 |
        |     793 | SHRUNK DIVINE               | A Fateful Character Study of a Waitress And a Technical Writer who must Battle a Hunter in A Baloon                                |         2006 |           1 |                 NULL |               6 |        2.99 |    139 |            14.99 | R      | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     800 | SINNERS ATLANTIS            | A Epic Display of a Dog And a Boat who must Succumb a Mad Scientist in An Abandoned Mine Shaft                                     |         2006 |           1 |                 NULL |               7 |        2.99 |    126 |            19.99 | PG-13  | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     802 | SKY MIRACLE                 | A Epic Drama of a Mad Scientist And a Explorer who must Succumb a Waitress in An Abandoned Fun House                               |         2006 |           1 |                 NULL |               7 |        2.99 |    132 |            15.99 | PG     | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     806 | SLEEPY JAPANESE             | A Emotional Epistle of a Moose And a Composer who must Fight a Technical Writer in The Outback                                     |         2006 |           1 |                 NULL |               4 |        2.99 |    137 |            25.99 | PG     | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     811 | SMILE EARRING               | A Intrepid Drama of a Teacher And a Butler who must Build a Pastry Chef in Berlin                                                  |         2006 |           1 |                 NULL |               4 |        2.99 |     60 |            29.99 | G      | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     815 | SNATCHERS MONTEZUMA         | A Boring Epistle of a Sumo Wrestler And a Woman who must Escape a Man in The Canadian Rockies                                      |         2006 |           1 |                 NULL |               4 |        2.99 |     74 |            14.99 | PG-13  | Commentaries                                           | 2006-02-15 05:03:42 |
        |     820 | SONS INTERVIEW              | A Taut Character Study of a Explorer And a Mad Cow who must Battle a Hunter in Ancient China                                       |         2006 |           1 |                 NULL |               3 |        2.99 |    184 |            11.99 | NC-17  | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     823 | SOUTH WAIT                  | A Amazing Documentary of a Car And a Robot who must Escape a Lumberjack in An Abandoned Amusement Park                             |         2006 |           1 |                 NULL |               4 |        2.99 |    143 |            21.99 | R      | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     825 | SPEAKEASY DATE              | A Lacklusture Drama of a Forensic Psychologist And a Car who must Redeem a Man in A Manhattan Penthouse                            |         2006 |           1 |                 NULL |               6 |        2.99 |    165 |            22.99 | PG-13  | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     828 | SPIKING ELEMENT             | A Lacklusture Epistle of a Dentist And a Technical Writer who must Find a Dog in A Monastery                                       |         2006 |           1 |                 NULL |               7 |        2.99 |     79 |            12.99 | G      | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     829 | SPINAL ROCKY                | A Lacklusture Epistle of a Sumo Wrestler And a Squirrel who must Defeat a Explorer in California                                   |         2006 |           1 |                 NULL |               7 |        2.99 |    138 |            12.99 | PG-13  | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     835 | SPY MILE                    | A Thrilling Documentary of a Feminist And a Feminist who must Confront a Feminist in A Baloon                                      |         2006 |           1 |                 NULL |               6 |        2.99 |    112 |            13.99 | PG-13  | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |     836 | SQUAD FISH                  | A Fast-Paced Display of a Pastry Chef And a Dog who must Kill a Teacher in Berlin                                                  |         2006 |           1 |                 NULL |               3 |        2.99 |    136 |            14.99 | PG     | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     837 | STAGE WORLD                 | A Lacklusture Panorama of a Woman And a Frisbee who must Chase a Crocodile in A Jet Boat                                           |         2006 |           1 |                 NULL |               4 |        2.99 |     85 |            19.99 | PG     | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     841 | STAR OPERATION              | A Insightful Character Study of a Girl And a Car who must Pursue a Mad Cow in A Shark Tank                                         |         2006 |           1 |                 NULL |               5 |        2.99 |    181 |             9.99 | PG     | Commentaries                                           | 2006-02-15 05:03:42 |
        |     842 | STATE WASTELAND             | A Beautiful Display of a Cat And a Pastry Chef who must Outrace a Mad Cow in A Jet Boat                                            |         2006 |           1 |                 NULL |               4 |        2.99 |    113 |            13.99 | NC-17  | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |     847 | STOCK GLASS                 | A Boring Epistle of a Crocodile And a Lumberjack who must Outgun a Moose in Ancient China                                          |         2006 |           1 |                 NULL |               7 |        2.99 |    160 |            10.99 | PG     | Commentaries                                           | 2006-02-15 05:03:42 |
        |     857 | STRICTLY SCARFACE           | A Touching Reflection of a Crocodile And a Dog who must Chase a Hunter in An Abandoned Fun House                                   |         2006 |           1 |                 NULL |               3 |        2.99 |    144 |            24.99 | PG-13  | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     869 | SUSPECTS QUILLS             | A Emotional Epistle of a Pioneer And a Crocodile who must Battle a Man in A Manhattan Penthouse                                    |         2006 |           1 |                 NULL |               4 |        2.99 |     47 |            22.99 | PG     | Trailers                                               | 2006-02-15 05:03:42 |
        |     872 | SWEET BROTHERHOOD           | A Unbelieveable Epistle of a Sumo Wrestler And a Hunter who must Chase a Forensic Psychologist in A Baloon                         |         2006 |           1 |                 NULL |               3 |        2.99 |    185 |            27.99 | R      | Deleted Scenes                                         | 2006-02-15 05:03:42 |
        |     874 | TADPOLE PARK                | A Beautiful Tale of a Frisbee And a Moose who must Vanquish a Dog in An Abandoned Amusement Park                                   |         2006 |           1 |                 NULL |               6 |        2.99 |    155 |            13.99 | PG     | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     876 | TARZAN VIDEOTAPE            | A Fast-Paced Display of a Lumberjack And a Mad Scientist who must Succumb a Sumo Wrestler in The Sahara Desert                     |         2006 |           1 |                 NULL |               3 |        2.99 |     91 |            11.99 | PG-13  | Trailers                                               | 2006-02-15 05:03:42 |
        |     880 | TELEMARK HEARTBREAKERS      | A Action-Packed Panorama of a Technical Writer And a Man who must Build a Forensic Psychologist in A Manhattan Penthouse           |         2006 |           1 |                 NULL |               6 |        2.99 |    152 |             9.99 | PG-13  | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |     895 | TOMORROW HUSTLER            | A Thoughtful Story of a Moose And a Husband who must Face a Secret Agent in The Sahara Desert                                      |         2006 |           1 |                 NULL |               3 |        2.99 |    142 |            21.99 | R      | Commentaries                                           | 2006-02-15 05:03:42 |
        |     900 | TOWN ARK                    | A Awe-Inspiring Documentary of a Moose And a Madman who must Meet a Dog in An Abandoned Mine Shaft                                 |         2006 |           1 |                 NULL |               6 |        2.99 |    136 |            17.99 | R      | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     912 | TROJAN TOMORROW             | A Astounding Panorama of a Husband And a Sumo Wrestler who must Pursue a Boat in Ancient India                                     |         2006 |           1 |                 NULL |               3 |        2.99 |     52 |             9.99 | PG     | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     914 | TROUBLE DATE                | A Lacklusture Panorama of a Forensic Psychologist And a Woman who must Kill a Explorer in Ancient Japan                            |         2006 |           1 |                 NULL |               6 |        2.99 |     61 |            13.99 | PG     | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     916 | TURN STAR                   | A Stunning Tale of a Man And a Monkey who must Chase a Student in New Orleans                                                      |         2006 |           1 |                 NULL |               3 |        2.99 |     80 |            10.99 | G      | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     917 | TUXEDO MILE                 | A Boring Drama of a Man And a Forensic Psychologist who must Face a Frisbee in Ancient India                                       |         2006 |           1 |                 NULL |               3 |        2.99 |    152 |            24.99 | R      | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |     921 | UNCUT SUICIDES              | A Intrepid Yarn of a Explorer And a Pastry Chef who must Pursue a Mad Cow in A U-Boat                                              |         2006 |           1 |                 NULL |               7 |        2.99 |    172 |            29.99 | PG-13  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     923 | UNFAITHFUL KILL             | A Taut Documentary of a Waitress And a Mad Scientist who must Battle a Technical Writer in New Orleans                             |         2006 |           1 |                 NULL |               7 |        2.99 |     78 |            12.99 | R      | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     926 | UNTOUCHABLES SUNRISE        | A Amazing Documentary of a Woman And a Astronaut who must Outrace a Teacher in An Abandoned Fun House                              |         2006 |           1 |                 NULL |               5 |        2.99 |    120 |            11.99 | NC-17  | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |     927 | UPRISING UPTOWN             | A Fanciful Reflection of a Boy And a Butler who must Pursue a Woman in Berlin                                                      |         2006 |           1 |                 NULL |               6 |        2.99 |    174 |            16.99 | NC-17  | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     928 | UPTOWN YOUNG                | A Fateful Documentary of a Dog And a Hunter who must Pursue a Teacher in An Abandoned Amusement Park                               |         2006 |           1 |                 NULL |               5 |        2.99 |     84 |            16.99 | PG     | Commentaries                                           | 2006-02-15 05:03:42 |
        |     930 | VACATION BOONDOCK           | A Fanciful Character Study of a Secret Agent And a Mad Scientist who must Reach a Teacher in Australia                             |         2006 |           1 |                 NULL |               4 |        2.99 |    145 |            23.99 | R      | Commentaries                                           | 2006-02-15 05:03:42 |
        |     936 | VANISHING ROCKY             | A Brilliant Reflection of a Man And a Woman who must Conquer a Pioneer in A MySQL Convention                                       |         2006 |           1 |                 NULL |               3 |        2.99 |    123 |            21.99 | NC-17  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     937 | VARSITY TRIP                | A Action-Packed Character Study of a Astronaut And a Explorer who must Reach a Monkey in A MySQL Convention                        |         2006 |           1 |                 NULL |               7 |        2.99 |     85 |            14.99 | NC-17  | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |     939 | VERTIGO NORTHWEST           | A Unbelieveable Display of a Mad Scientist And a Mad Scientist who must Outgun a Mad Cow in Ancient Japan                          |         2006 |           1 |                 NULL |               4 |        2.99 |     90 |            17.99 | R      | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     952 | WAGON JAWS                  | A Intrepid Drama of a Moose And a Boat who must Kill a Explorer in A Manhattan Penthouse                                           |         2006 |           1 |                 NULL |               7 |        2.99 |    152 |            17.99 | PG     | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     958 | WARDROBE PHANTOM            | A Action-Packed Display of a Mad Cow And a Astronaut who must Kill a Car in Ancient India                                          |         2006 |           1 |                 NULL |               6 |        2.99 |    178 |            19.99 | G      | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     959 | WARLOCK WEREWOLF            | A Astounding Yarn of a Pioneer And a Crocodile who must Defeat a A Shark in The Outback                                            |         2006 |           1 |                 NULL |               6 |        2.99 |     83 |            10.99 | G      | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     960 | WARS PLUTO                  | A Taut Reflection of a Teacher And a Database Administrator who must Chase a Madman in The Sahara Desert                           |         2006 |           1 |                 NULL |               5 |        2.99 |    128 |            15.99 | G      | Commentaries,Behind the Scenes                         | 2006-02-15 05:03:42 |
        |     962 | WASTELAND DIVINE            | A Fanciful Story of a Database Administrator And a Womanizer who must Fight a Database Administrator in Ancient China              |         2006 |           1 |                 NULL |               7 |        2.99 |     85 |            18.99 | PG     | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |     967 | WEEKEND PERSONAL            | A Fast-Paced Documentary of a Car And a Butler who must Find a Frisbee in A Jet Boat                                               |         2006 |           1 |                 NULL |               5 |        2.99 |    134 |            26.99 | R      | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |     975 | WILLOW TRACY                | A Brilliant Panorama of a Boat And a Astronaut who must Challenge a Teacher in A Manhattan Penthouse                               |         2006 |           1 |                 NULL |               6 |        2.99 |    137 |            22.99 | R      | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     977 | WINDOW SIDE                 | A Astounding Character Study of a Womanizer And a Hunter who must Escape a Robot in A Monastery                                    |         2006 |           1 |                 NULL |               3 |        2.99 |     85 |            25.99 | R      | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     983 | WON DARES                   | A Unbelieveable Documentary of a Teacher And a Monkey who must Defeat a Explorer in A U-Boat                                       |         2006 |           1 |                 NULL |               7 |        2.99 |    105 |            18.99 | PG     | Behind the Scenes                                      | 2006-02-15 05:03:42 |
        |     984 | WONDERFUL DROP              | A Boring Panorama of a Woman And a Madman who must Overcome a Butler in A U-Boat                                                   |         2006 |           1 |                 NULL |               3 |        2.99 |    126 |            20.99 | NC-17  | Commentaries                                           | 2006-02-15 05:03:42 |
        |     986 | WONKA SEA                   | A Brilliant Saga of a Boat And a Mad Scientist who must Meet a Moose in Ancient India                                              |         2006 |           1 |                 NULL |               6 |        2.99 |     85 |            24.99 | NC-17  | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |     987 | WORDS HUNTER                | A Action-Packed Reflection of a Composer And a Mad Scientist who must Face a Pioneer in A MySQL Convention                         |         2006 |           1 |                 NULL |               3 |        2.99 |    116 |            13.99 | PG     | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |     988 | WORKER TARZAN               | A Action-Packed Yarn of a Secret Agent And a Technical Writer who must Battle a Sumo Wrestler in The First Manned Space Station    |         2006 |           1 |                 NULL |               7 |        2.99 |    139 |            26.99 | R      | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |     991 | WORST BANGER                | A Thrilling Drama of a Madman And a Dentist who must Conquer a Boy in The Outback                                                  |         2006 |           1 |                 NULL |               4 |        2.99 |    185 |            26.99 | PG     | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |     993 | WRONG BEHAVIOR              | A Emotional Saga of a Crocodile And a Sumo Wrestler who must Discover a Mad Cow in New Orleans                                     |         2006 |           1 |                 NULL |               6 |        2.99 |    178 |            10.99 | PG-13  | Trailers,Behind the Scenes                             | 2006-02-15 05:03:42 |
        |     999 | ZOOLANDER FICTION           | A Fateful Reflection of a Waitress And a Boat who must Discover a Sumo Wrestler in Ancient China                                   |         2006 |           1 |                 NULL |               5 |        2.99 |    101 |            28.99 | R      | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        +---------+-----------------------------+------------------------------------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+--------------------------------------------------------+---------------------+

        ```
    - **Películas con un titulo de más de 12 letras.**

        *Comando*

        ``` sql
        SELECT * FROM film WHERE LENGTH(title) > 12 LIMIT 10;
        ```

        *Salida*

        ``` sql
        +---------+------------------+---------------------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+----------------------------------+---------------------+
        | film_id | title            | description                                                                                                         | release_year | language_id | original_language_id | rental_duration | rental_rate | length | replacement_cost | rating | special_features                 | last_update         |
        +---------+------------------+---------------------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+----------------------------------+---------------------+
        |       1 | ACADEMY DINOSAUR | A Epic Drama of a Feminist And a Mad Scientist who must Battle a Teacher in The Canadian Rockies                    |         2006 |           1 |                 NULL |               6 |        0.99 |     86 |            20.99 | PG     | Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |       2 | ACE GOLDFINGER   | A Astounding Epistle of a Database Administrator And a Explorer who must Find a Car in Ancient China                |         2006 |           1 |                 NULL |               3 |        4.99 |     48 |            12.99 | G      | Trailers,Deleted Scenes          | 2006-02-15 05:03:42 |
        |       3 | ADAPTATION HOLES | A Astounding Reflection of a Lumberjack And a Car who must Sink a Lumberjack in A Baloon Factory                    |         2006 |           1 |                 NULL |               7 |        2.99 |     50 |            18.99 | NC-17  | Trailers,Deleted Scenes          | 2006-02-15 05:03:42 |
        |       4 | AFFAIR PREJUDICE | A Fanciful Documentary of a Frisbee And a Lumberjack who must Chase a Monkey in A Shark Tank                        |         2006 |           1 |                 NULL |               5 |        2.99 |    117 |            26.99 | G      | Commentaries,Behind the Scenes   | 2006-02-15 05:03:42 |
        |       7 | AIRPLANE SIERRA  | A Touching Saga of a Hunter And a Butler who must Discover a Butler in A Jet Boat                                   |         2006 |           1 |                 NULL |               6 |        4.99 |     62 |            28.99 | PG-13  | Trailers,Deleted Scenes          | 2006-02-15 05:03:42 |
        |       8 | AIRPORT POLLOCK  | A Epic Tale of a Moose And a Girl who must Confront a Monkey in Ancient India                                       |         2006 |           1 |                 NULL |               6 |        4.99 |     54 |            15.99 | R      | Trailers                         | 2006-02-15 05:03:42 |
        |       9 | ALABAMA DEVIL    | A Thoughtful Panorama of a Database Administrator And a Mad Scientist who must Outgun a Mad Scientist in A Jet Boat |         2006 |           1 |                 NULL |               3 |        2.99 |    114 |            21.99 | PG-13  | Trailers,Deleted Scenes          | 2006-02-15 05:03:42 |
        |      10 | ALADDIN CALENDAR | A Action-Packed Tale of a Man And a Lumberjack who must Reach a Feminist in Ancient China                           |         2006 |           1 |                 NULL |               6 |        4.99 |     63 |            24.99 | NC-17  | Trailers,Deleted Scenes          | 2006-02-15 05:03:42 |
        |      11 | ALAMO VIDEOTAPE  | A Boring Epistle of a Butler And a Cat who must Fight a Pastry Chef in A MySQL Convention                           |         2006 |           1 |                 NULL |               6 |        0.99 |    126 |            16.99 | G      | Commentaries,Behind the Scenes   | 2006-02-15 05:03:42 |
        |      12 | ALASKA PHANTOM   | A Fanciful Saga of a Hunter And a Pastry Chef who must Vanquish a Boy in Australia                                  |         2006 |           1 |                 NULL |               6 |        0.99 |    136 |            22.99 | PG     | Commentaries,Deleted Scenes      | 2006-02-15 05:03:42 |
        +---------+------------------+---------------------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+----------------------------------+---------------------+
        ```

    - **Peliculas con un rating de PG o G.**

        *Comando*

        ``` sql
        SELECT * FROM film WHERE rating = "PG" or "G" LIMIT 10;
        ```

        *Salida*

        ``` sql
        +---------+----------------------+--------------------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+-----------------------------------------------+---------------------+
        | film_id | title                | description                                                                                                        | release_year | language_id | original_language_id | rental_duration | rental_rate | length | replacement_cost | rating | special_features                              | last_update         |
        +---------+----------------------+--------------------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+-----------------------------------------------+---------------------+
        |       1 | ACADEMY DINOSAUR     | A Epic Drama of a Feminist And a Mad Scientist who must Battle a Teacher in The Canadian Rockies                   |         2006 |           1 |                 NULL |               6 |        0.99 |     86 |            20.99 | PG     | Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |       6 | AGENT TRUMAN         | A Intrepid Panorama of a Robot And a Boy who must Escape a Sumo Wrestler in Ancient China                          |         2006 |           1 |                 NULL |               3 |        2.99 |    169 |            17.99 | PG     | Deleted Scenes                                | 2006-02-15 05:03:42 |
        |      12 | ALASKA PHANTOM       | A Fanciful Saga of a Hunter And a Pastry Chef who must Vanquish a Boy in Australia                                 |         2006 |           1 |                 NULL |               6 |        0.99 |    136 |            22.99 | PG     | Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |      13 | ALI FOREVER          | A Action-Packed Drama of a Dentist And a Crocodile who must Battle a Feminist in The Canadian Rockies              |         2006 |           1 |                 NULL |               4 |        4.99 |    150 |            21.99 | PG     | Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |      19 | AMADEUS HOLY         | A Emotional Display of a Pioneer And a Technical Writer who must Battle a Man in A Baloon                          |         2006 |           1 |                 NULL |               6 |        0.99 |    113 |            20.99 | PG     | Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |      37 | ARIZONA BANG         | A Brilliant Panorama of a Mad Scientist And a Mad Cow who must Meet a Pioneer in A Monastery                       |         2006 |           1 |                 NULL |               3 |        2.99 |    121 |            28.99 | PG     | Trailers,Deleted Scenes                       | 2006-02-15 05:03:42 |
        |      41 | ARSENIC INDEPENDENCE | A Fanciful Documentary of a Mad Cow And a Womanizer who must Find a Dentist in Berlin                              |         2006 |           1 |                 NULL |               4 |        0.99 |    137 |            17.99 | PG     | Trailers,Deleted Scenes,Behind the Scenes     | 2006-02-15 05:03:42 |
        |      63 | BEDAZZLED MARRIED    | A Astounding Character Study of a Madman And a Robot who must Meet a Mad Scientist in An Abandoned Fun House       |         2006 |           1 |                 NULL |               6 |        0.99 |     73 |            21.99 | PG     | Trailers,Deleted Scenes,Behind the Scenes     | 2006-02-15 05:03:42 |
        |      65 | BEHAVIOR RUNAWAY     | A Unbelieveable Drama of a Student And a Husband who must Outrace a Sumo Wrestler in Berlin                        |         2006 |           1 |                 NULL |               3 |        4.99 |    100 |            20.99 | PG     | Trailers,Deleted Scenes,Behind the Scenes     | 2006-02-15 05:03:42 |
        |      72 | BILL OTHERS          | A Stunning Saga of a Mad Scientist And a Forensic Psychologist who must Challenge a Squirrel in A MySQL Convention |         2006 |           1 |                 NULL |               6 |        2.99 |     93 |            12.99 | PG     | Trailers,Commentaries                         | 2006-02-15 05:03:42 |
        +---------+----------------------+--------------------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+-----------------------------------------------+---------------------+

        ```

    - **Peliculas que no tengan un rating de NC-17.**

        *Comando*

        ``` sql
        SELECT * FROM film WHERE rating = "NC-17" LIMIT 10;
        ```

        *Salida*

        ``` sql
        +---------+--------------------+----------------------------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+--------------------------------------------------------+---------------------+
        | film_id | title              | description                                                                                                                | release_year | language_id | original_language_id | rental_duration | rental_rate | length | replacement_cost | rating | special_features                                       | last_update         |
        +---------+--------------------+----------------------------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+--------------------------------------------------------+---------------------+
        |       3 | ADAPTATION HOLES   | A Astounding Reflection of a Lumberjack And a Car who must Sink a Lumberjack in A Baloon Factory                           |         2006 |           1 |                 NULL |               7 |        2.99 |     50 |            18.99 | NC-17  | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |      10 | ALADDIN CALENDAR   | A Action-Packed Tale of a Man And a Lumberjack who must Reach a Feminist in Ancient China                                  |         2006 |           1 |                 NULL |               6 |        4.99 |     63 |            24.99 | NC-17  | Trailers,Deleted Scenes                                | 2006-02-15 05:03:42 |
        |      14 | ALICE FANTASIA     | A Emotional Drama of a A Shark And a Database Administrator who must Vanquish a Pioneer in Soviet Georgia                  |         2006 |           1 |                 NULL |               6 |        0.99 |     94 |            23.99 | NC-17  | Trailers,Deleted Scenes,Behind the Scenes              | 2006-02-15 05:03:42 |
        |      15 | ALIEN CENTER       | A Brilliant Drama of a Cat And a Mad Scientist who must Battle a Feminist in A MySQL Convention                            |         2006 |           1 |                 NULL |               5 |        2.99 |     46 |            10.99 | NC-17  | Trailers,Commentaries,Behind the Scenes                | 2006-02-15 05:03:42 |
        |      16 | ALLEY EVOLUTION    | A Fast-Paced Drama of a Robot And a Composer who must Battle a Astronaut in New Orleans                                    |         2006 |           1 |                 NULL |               6 |        2.99 |    180 |            23.99 | NC-17  | Trailers,Commentaries                                  | 2006-02-15 05:03:42 |
        |      27 | ANONYMOUS HUMAN    | A Amazing Reflection of a Database Administrator And a Astronaut who must Outrace a Database Administrator in A Shark Tank |         2006 |           1 |                 NULL |               7 |        0.99 |    179 |            12.99 | NC-17  | Deleted Scenes,Behind the Scenes                       | 2006-02-15 05:03:42 |
        |      29 | ANTITRUST TOMATOES | A Fateful Yarn of a Womanizer And a Feminist who must Succumb a Database Administrator in Ancient India                    |         2006 |           1 |                 NULL |               5 |        2.99 |    168 |            11.99 | NC-17  | Trailers,Commentaries,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |      31 | APACHE DIVINE      | A Awe-Inspiring Reflection of a Pastry Chef And a Teacher who must Overcome a Sumo Wrestler in A U-Boat                    |         2006 |           1 |                 NULL |               5 |        4.99 |     92 |            16.99 | NC-17  | Commentaries,Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |      34 | ARABIA DOGMA       | A Touching Epistle of a Madman And a Mad Cow who must Defeat a Student in Nigeria                                          |         2006 |           1 |                 NULL |               6 |        0.99 |     62 |            29.99 | NC-17  | Commentaries,Deleted Scenes                            | 2006-02-15 05:03:42 |
        |      38 | ARK RIDGEMONT      | A Beautiful Yarn of a Pioneer And a Monkey who must Pursue a Explorer in The Sahara Desert                                 |         2006 |           1 |                 NULL |               6 |        0.99 |     68 |            25.99 | NC-17  | Trailers,Commentaries,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        +---------+--------------------+----------------------------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+--------------------------------------------------------+---------------------+
        ```

    - **Peliculas con un rating PG y duracion de más de 120.**

        *Comando*

        ``` sql
        SELECT * FROM film WHERE rating = "PG" and length > 120 LIMIT 10;
        ```

        *Salida*

        ``` sql
        +---------+----------------------+-------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+-------------------------------------------+---------------------+
        | film_id | title                | description                                                                                           | release_year | language_id | original_language_id | rental_duration | rental_rate | length | replacement_cost | rating | special_features                          | last_update         |
        +---------+----------------------+-------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+-------------------------------------------+---------------------+
        |       6 | AGENT TRUMAN         | A Intrepid Panorama of a Robot And a Boy who must Escape a Sumo Wrestler in Ancient China             |         2006 |           1 |                 NULL |               3 |        2.99 |    169 |            17.99 | PG     | Deleted Scenes                            | 2006-02-15 05:03:42 |
        |      12 | ALASKA PHANTOM       | A Fanciful Saga of a Hunter And a Pastry Chef who must Vanquish a Boy in Australia                    |         2006 |           1 |                 NULL |               6 |        0.99 |    136 |            22.99 | PG     | Commentaries,Deleted Scenes               | 2006-02-15 05:03:42 |
        |      13 | ALI FOREVER          | A Action-Packed Drama of a Dentist And a Crocodile who must Battle a Feminist in The Canadian Rockies |         2006 |           1 |                 NULL |               4 |        4.99 |    150 |            21.99 | PG     | Deleted Scenes,Behind the Scenes          | 2006-02-15 05:03:42 |
        |      37 | ARIZONA BANG         | A Brilliant Panorama of a Mad Scientist And a Mad Cow who must Meet a Pioneer in A Monastery          |         2006 |           1 |                 NULL |               3 |        2.99 |    121 |            28.99 | PG     | Trailers,Deleted Scenes                   | 2006-02-15 05:03:42 |
        |      41 | ARSENIC INDEPENDENCE | A Fanciful Documentary of a Mad Cow And a Womanizer who must Find a Dentist in Berlin                 |         2006 |           1 |                 NULL |               4 |        0.99 |    137 |            17.99 | PG     | Trailers,Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        |      74 | BIRCH ANTITRUST      | A Fanciful Panorama of a Husband And a Pioneer who must Outgun a Dog in A Baloon                      |         2006 |           1 |                 NULL |               4 |        4.99 |    162 |            18.99 | PG     | Trailers,Commentaries,Deleted Scenes      | 2006-02-15 05:03:42 |
        |      88 | BORN SPINAL          | A Touching Epistle of a Frisbee And a Husband who must Pursue a Student in Nigeria                    |         2006 |           1 |                 NULL |               7 |        4.99 |    179 |            17.99 | PG     | Trailers,Commentaries,Deleted Scenes      | 2006-02-15 05:03:42 |
        |      93 | BRANNIGAN SUNRISE    | A Amazing Epistle of a Moose And a Crocodile who must Outrace a Dog in Berlin                         |         2006 |           1 |                 NULL |               4 |        4.99 |    121 |            27.99 | PG     | Trailers                                  | 2006-02-15 05:03:42 |
        |      99 | BRINGING HYSTERICAL  | A Fateful Saga of a A Shark And a Technical Writer who must Find a Woman in A Jet Boat                |         2006 |           1 |                 NULL |               7 |        2.99 |    136 |            14.99 | PG     | Trailers                                  | 2006-02-15 05:03:42 |
        |     103 | BUCKET BROTHERHOOD   | A Amazing Display of a Girl And a Womanizer who must Succumb a Lumberjack in A Baloon Factory         |         2006 |           1 |                 NULL |               7 |        4.99 |    133 |            27.99 | PG     | Commentaries,Deleted Scenes               | 2006-02-15 05:03:42 |
        +---------+----------------------+-------------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+-------------------------------------------+---------------------+
        ```

    - **¿Cuantos actores hay?**

        *Comando*

        ``` sql
        SELECT count(*) as Total_actores FROM film_actor;
        ```

        *Salida*

        ``` sql
        +---------------+
        | Total_actores |
        +---------------+
        |          5462 |
        +---------------+
        ```

    - **¿Cuántas ciudades tiene el country Spain?**

        *Comando*

        ``` sql
        SELECT count(ci.city) as Total_ciudades_Spain FROM city AS ci JOIN country AS co ON ci.country_id = co.country_id WHERE co.country = "Spain";
        ```

        *Salida*

        ``` sql
        +----------------------+
        | Total_ciudades_Spain |
        +----------------------+
        |                    5 |
        +----------------------+
        ```

    - **¿Cuántos countries hay que empiezan por a?**

        *Comando*

        ``` sql
        SELECT count(*) AS total_ciudades_a FROM country WHERE country REGEXP "^a";
        ```

        *Salida*

        ``` sql
        +------------------+
        | total_ciudades_a |
        +------------------+
        |               10 |
        +------------------+
        ```

    - **Media de duración de peliculas con PG.**

        *Comando*

        ``` sql
        SELECT avg(length) AS media_duracion FROM film WHERE rating = "PG";
        ```

        *Salida*

        ``` sql
        +----------------+
        | media_duracion |
        +----------------+
        |       112.0052 |
        +----------------+
        ```

    - **Suma de rental_rate de todas las peliculas.**

        *Comando*

        ``` sql
        SELECT sum(rental_rate) total_rentas_peliculas FROM film;
        ```

        *Salida*

        ``` sql
        +------------------------+
        | total_rentas_peliculas |
        +------------------------+
        |                2980.00 |
        +------------------------+
        ```

    - **Pelicula con mayor duración.**

        *Comando*

        ``` sql
        SELECT * FROM film ORDER BY length DESC LIMIT 1;
        ```

        *Salida*

        ``` sql
        +---------+---------------+------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+----------------------------------+---------------------+
        | film_id | title         | description                                                                        | release_year | language_id | original_language_id | rental_duration | rental_rate | length | replacement_cost | rating | special_features                 | last_update         |
        +---------+---------------+------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+----------------------------------+---------------------+
        |     141 | CHICAGO NORTH | A Fateful Yarn of a Mad Cow And a Waitress who must Battle a Student in California |         2006 |           1 |                 NULL |               6 |        4.99 |    185 |            11.99 | PG-13  | Deleted Scenes,Behind the Scenes | 2006-02-15 05:03:42 |
        +---------+---------------+------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+----------------------------------+---------------------+
        ```

    - **Película con menor duración.**

        *Comando*

        ``` sql
        SELECT * FROM film ORDER BY length ASC LIMIT 1;
        ```

        *Salida*

        ``` sql
        +---------+--------------+-------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+-----------------------------------------+---------------------+
        | film_id | title        | description                                                                                     | release_year | language_id | original_language_id | rental_duration | rental_rate | length | replacement_cost | rating | special_features                        | last_update         |
        +---------+--------------+-------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+-----------------------------------------+---------------------+
        |      15 | ALIEN CENTER | A Brilliant Drama of a Cat And a Mad Scientist who must Battle a Feminist in A MySQL Convention |         2006 |           1 |                 NULL |               5 |        2.99 |     46 |            10.99 | NC-17  | Trailers,Commentaries,Behind the Scenes | 2006-02-15 05:03:42 |
        +---------+--------------+-------------------------------------------------------------------------------------------------+--------------+-------------+----------------------+-----------------+-------------+--------+------------------+--------+-----------------------------------------+---------------------+
        ```

    - **Mostrar las ciudades del country Spain (multitabla).**

        *Comando*

        ``` sql
        SELECT ci.* FROM city AS ci JOIN country AS co on ci.country_id = co.country_id WHERE co.country = "Spain"; 
        ```

        *Salida*

        ``` sql
        +---------+-------------------------+------------+---------------------+
        | city_id | city                    | country_id | last_update         |
        +---------+-------------------------+------------+---------------------+
        |       1 | A Coruña (La Coruña)    |         87 | 2006-02-15 04:45:25 |
        |     146 | Donostia-San Sebastián  |         87 | 2006-02-15 04:45:25 |
        |     181 | Gijón                   |         87 | 2006-02-15 04:45:25 |
        |     388 | Ourense (Orense)        |         87 | 2006-02-15 04:45:25 |
        |     459 | Santiago de Compostela  |         87 | 2006-02-15 04:45:25 |
        +---------+-------------------------+------------+---------------------+
        ```

    - **Mostrar el nombre de la película y el nombre de los actores.**

        *Comando*

        ``` sql
        SELECT fi.title, CONCAT(act.first_name, ' ', act.last_name) AS actores FROM film AS fi JOIN film_actor AS fi_act ON fi.film_id = fi_act.film_id JOIN actor AS act ON fi_act.actor_id = act.actor_id LIMIT 10;
        ```

        *Salida*

        ``` sql
        +-----------------------+------------------+
        | title                 | actores          |
        +-----------------------+------------------+
        | ACADEMY DINOSAUR      | PENELOPE GUINESS |
        | ANACONDA CONFESSIONS  | PENELOPE GUINESS |
        | ANGELS LIFE           | PENELOPE GUINESS |
        | BULWORTH COMMANDMENTS | PENELOPE GUINESS |
        | CHEAPER CLYDE         | PENELOPE GUINESS |
        | COLOR PHILADELPHIA    | PENELOPE GUINESS |
        | ELEPHANT TROJAN       | PENELOPE GUINESS |
        | GLEAMING JAWBREAKER   | PENELOPE GUINESS |
        | HUMAN GRAFFITI        | PENELOPE GUINESS |
        | KING EVOLUTION        | PENELOPE GUINESS |
        +-----------------------+------------------+
        ```

    - **Mostrar el nombre de la película y el de sus categorías.**

        *Comando*

        ``` sql
        SELECT fi.title, cat.name AS categorias FROM film AS fi JOIN film_category AS fi_cat ON fi.film_id = fi_cat.film_id JOIN category AS cat ON fi_cat.category_id = cat.category_id LIMIT 10; 
        ```

        *Salida*

        ``` sql
        +---------------------+------------+
        | title               | categorias |
        +---------------------+------------+
        | AMADEUS HOLY        | Action     |
        | AMERICAN CIRCUS     | Action     |
        | ANTITRUST TOMATOES  | Action     |
        | ARK RIDGEMONT       | Action     |
        | BAREFOOT MANCHURIAN | Action     |
        | BERETS AGENT        | Action     |
        | BRIDE INTRIGUE      | Action     |
        | BULL SHAWSHANK      | Action     |
        | CADDYSHACK JEDI     | Action     |
        | CAMPUS REMEMBER     | Action     |
        +---------------------+------------+
        ```

    - **Mostrar el country, la ciudad y dirección de cada miembro del staff.**

        *Comando*

        ``` sql

        ```

        *Salida*

        ``` sql

        ```

    - **Mostrar el country, la ciudad y dirección de cada customer.**

        *Comando*

        ``` sql
        SELECT co.country, ci.city, cust.address FROM customer AS cust JOIN address ON customer.address_id = address.address_id JOIN city AS ci ON address.city_id = ci.city_id JOIN country AS co ON ci.country_id = co.country_id;
        ```

        *Salida*

        ``` sql

        ```
    - **Numero de películas de cada rating**

        *Comando*

        ``` sql
        SELECT rating, COUNT(*) AS cantidad FROM film GROUP BY rating;
        ```

        *Salida*

        ``` sql
        +--------+----------+
        | rating | cantidad |
        +--------+----------+
        | PG     |      194 |
        | G      |      178 |
        | NC-17  |      210 |
        | PG-13  |      223 |
        | R      |      195 |
        +--------+----------+
        ```

    - **Cuantas películas ha realizado el actor ED CHASE.**

        *Comando*

        ``` sql
        SELECT COUNT(*) AS cantidad_películas FROM film AS fi JOIN film_actor AS fi_act ON fi.film_id = fi_act.film_id JOIN actor AS act ON fi_act.actor_id = act.actor_id WHERE act.first_name = 'ED' AND act.last_name = 'CHASE';
        ```

        *Salida*

        ``` sql
        +---------------------+
        | cantidad_películas  |
        +---------------------+
        |                  22 |
        +---------------------+
        ```

    - **Media de duración de las películas cada categoría.**

        *Comando*

        ``` sql
        SELECT cat.name, AVG(fi.length) AS duracion_media FROM film AS fi JOIN film_category AS fi_cat ON fi.film_id = fi_cat.film_id JOIN category AS cat ON fi_cat.category_id = cat.category_id GROUP BY cat.name;
        ```

        *Salida*

        ``` sql
        +-------------+----------------+
        | name        | duracion_media |
        +-------------+----------------+
        | Action      |       111.6094 |
        | Animation   |       111.0152 |
        | Children    |       109.8000 |
        | Classics    |       111.6667 |
        | Comedy      |       115.8276 |
        | Documentary |       108.7500 |
        | Drama       |       120.8387 |
        | Family      |       114.7826 |
        | Foreign     |       121.6986 |
        | Games       |       127.8361 |
        | Horror      |       112.4821 |
        | Music       |       113.6471 |
        | New         |       111.1270 |
        | Sci-Fi      |       108.1967 |
        | Sports      |       128.2027 |
        | Travel      |       113.3158 |
        +-------------+----------------+
        ```

    - **A continuación se muestran algunas de las vistas que se han utilizado en la base de datos Sakila.**

    ``` sql
        --
    -- View structure for view `customer_list`
    --

    CREATE VIEW customer_list AS
    SELECT 
    cu.customer_id AS ID, 
        CONCAT(cu.first_name, _utf8mb4' ', cu.last_name) AS name, 
        a.address AS address, 
        a.postal_code AS `zip code`,
    a.phone AS phone, 
        city.city AS city, 
        country.country AS country, 
        IF(cu.active, _utf8mb4'active',_utf8mb4'') AS notes, 
        cu.store_id AS SID
    FROM 
    customer AS cu JOIN address AS a 
        ON cu.address_id = a.address_id 
        JOIN city 
        ON a.city_id = city.city_id
    JOIN country 
        ON city.country_id = country.country_id;
    --
    -- View structure for view `film_list`
    --

    CREATE VIEW film_list AS
    SELECT 
    film.film_id AS FID, 
        film.title AS title, 
        film.description AS description, 
        category.name AS category, 
        film.rental_rate AS price,
    film.length AS length, 
        film.rating AS rating, 
        GROUP_CONCAT(CONCAT(actor.first_name, _utf8mb4' ', actor.last_name) SEPARATOR ', ') AS actors
    FROM 
    category LEFT JOIN film_category 
        ON category.category_id = film_category.category_id 
        LEFT JOIN film 
        ON film_category.film_id = film.film_id
    JOIN film_actor 
        ON film.film_id = film_actor.film_id
    JOIN actor 
        ON film_actor.actor_id = actor.actor_id
    GROUP BY film.film_id, category.name;
    ```

    - **Muestra el resultado de la consulta de las vistas que se proporcionan**

    - **Crea 5 vistas sobre la BBDD, y realiza la consulta, para mostrar los resultados. Las vistas deben tener 3 o más tablas de la BBDD**

    *Comando*

    ``` sql
    CREATE VIEW customer_rental_info AS
    SELECT c.first_name AS customer_first_name, c.last_name AS customer_last_name,
        f.title AS film_title, r.rental_date AS rental_date, r.return_date AS return_date
    FROM rental r
    JOIN customer c ON r.customer_id = c.customer_id
    JOIN inventory i ON r.inventory_id = i.inventory_id
    JOIN film f ON i.film_id = f.film_id;
    ```

    *Salida*

    ``` sql

    ```

    *Comando*

    ``` sql
    CREATE VIEW film_actor_category AS
    SELECT f.title AS film_title, GROUP_CONCAT(CONCAT(a.first_name, ' ', a.last_name) SEPARATOR ', ') AS actors,
        c.name AS category
    FROM film f
    JOIN film_actor fa ON f.film_id = fa.film_id
    JOIN actor a ON fa.actor_id = a.actor_id
    JOIN film_category fc ON f.film_id = fc.film_id
    JOIN category c ON fc.category_id = c.category_id
    GROUP BY f.film_id, c.name;
    ```

    *Salida*

    ``` sql

    ```
    
    *Comando*

    ``` sql
    CREATE VIEW staff_customer_address AS
    SELECT s.first_name AS staff_first_name, s.last_name AS staff_last_name,
        c.first_name AS customer_first_name, c.last_name AS customer_last_name,
        a.address AS customer_address, a.district AS customer_district,
        ci.city AS customer_city, co.country AS customer_country
    FROM staff s
    JOIN address a ON s.address_id = a.address_id
    JOIN city ci ON a.city_id = ci.city_id
    JOIN country co ON ci.country_id = co.country_id
    JOIN customer c ON c.store_id = s.store_id;
    ```

    *Salida*

    ``` sql

    ```
    
    *Comando*

    ``` sql
    CREATE VIEW rental_film_category AS
    SELECT r.rental_id, f.title AS film_title, c.name AS category
    FROM rental r
    JOIN inventory i ON r.inventory_id = i.inventory_id
    JOIN film f ON i.film_id = f.film_id
    JOIN film_category fc ON f.film_id = fc.film_id
    JOIN category c ON fc.category_id = c.category_id;
    ```

    *Salida*

    ``` sql

    ```
    
    *Comando*

    ``` sql
    CREATE VIEW inventory_store AS
    SELECT i.inventory_id, f.title AS film_title, s.store_id, s.manager_staff_id
    FROM inventory i
    JOIN film f ON i.film_id = f.film_id
    JOIN store s ON i.store_id = s.store_id;
    ```

    *Salida*

    ``` sql

    ```




