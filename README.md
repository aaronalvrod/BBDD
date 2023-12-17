# Primeros pasos en SQL

### ¿Que es SQLite3?

- SQLite3 es un sistema de gestión de base de datos relacional que se caracteriza por ser un motor de base de datos incorporado, ligero y de código abierto. A diferencia de otros sistemas de gestión de base de datos como MySQL, SQLite3 no funciona como un servidor independiente, sino que se implementa como una biblioteca que se vincula directamente con la  aplicación.

![SQLite3 logo](https://github.com/aaronalvrod/BBDD./assets/147527842/66e6aecb-6d3f-4a2c-b845-6059ccd59596)


---
### *Descripción*

- En esta practica se creara y manipulara una base de datos en SQLite3 desde la linea de comandos.

---

### Paso 1: Crear una tabla con un campo de cada tipo

1. Primeramente abriremos la terminal y pondremos en ella el siguiente comando:

```
sqlite3 tarea1.db
```

2. Luego tendremos que crear una tabla con los siguientes campos:

- `id` (tipo INTEGER, clave primaria)
- `texto` (tipo TEXT)
- `entero` (tipo INTEGER)
- `decimal` (tipo REAL)
- `fecha` (tipo DATE)
- `booleano` (tipo BOOLEAN)

Para crear esta tabla procederemos a escribir lo siguiente en la linea de comando:

```
CREATE TABLE ejemplos (
id INTEGER NOT NULL PRIMARY KEY AUTOINCREMENT,
texto TEXT NOT NULL,
entero INTEGER NOT NULL,
decimal REAL NOT NULL,
fecha DATE NOT NULL,
booleano BOOLEAN NOT NULL );
```
---

### Paso 2: Insertar 50 entradas

- Para añadir entradas a nuestra tabla utilizaremos el siguiente comando:

    ```
    insert into ejemplos (text, entero, decimal, fecha, booleano) 
    values ( 'Ejemplo1', '25', '10.5', '2022-05-15', '0' );
    ```


Dentro del `insert into ejemplos` se puede apreciar que no esta el campo id que fue el que definimos como `PRIMARY KEY`, esto es porque lo definimos como `AUTOINCREMENT` que hace que cada entrada a la tabla vaya incrementando el id y no haga falta ponerlo a mano.

Tenemos que añadir 50 entradas a nuestra tabla, con el comando que aparece arriba tendremos que repetir 50 veces la misma secuencia pero con los datos que nos suministran.

Como ejemplo vamos a insertar las dos primeras filas, para insertalas seria tal que asi:

```
insert into ejemplos ( text, entero, decimal, fecha, booleano )
values ( 'Ejemplo1', '25', '10.5', '2022-05-15', '0' );
```

```
insert into ejemplos ( text, entero, decimal, fecha, booleano )
values ( 'Ejemplo2', '63', '45.7', '2022-06-22', '1' );
``` 

Como resultado la tabla deberia de quedar asi:

```
+----+-----------+--------+---------+------------+----------+
| id |   texto   | entero | decimal |   fecha    | booleano |
+----+-----------+--------+---------+------------+----------+
| 1  | Ejemplo1  | 25     | 10.5    | 2022-05-15 | 0        |
| 2  | Ejemplo2  | 63     | 45.7    | 2022-06-22 | 1        |
| 3  | Ejemplo3  | 12     | 30.0    | 2022-07-10 | 0        |
| 4  | Ejemplo4  | 78     | 75.2    | 2022-08-05 | 1        |
| 5  | Ejemplo5  | 42     | 18.9    | 2022-09-12 | 0        |
| 6  | Ejemplo6  | 55     | 60.3    | 2022-10-08 | 1        |
| 7  | Ejemplo7  | 10     | 40.1    | 2022-11-17 | 0        |
| 8  | Ejemplo8  | 87     | 22.6    | 2022-12-03 | 1        |
| 9  | Ejemplo9  | 31     | 55.0    | 2023-01-20 | 0        |
| 10 | Ejemplo10 | 68     | 90.4    | 2023-02-14 | 1        |
| 11 | Ejemplo11 | 15     | 12.8    | 2023-03-22 | 0        |
| 12 | Ejemplo12 | 72     | 48.6    | 2023-04-09 | 1        |
| 13 | Ejemplo13 | 22     | 33.7    | 2023-05-01 | 0        |
| 14 | Ejemplo14 | 93     | 70.2    | 2023-06-18 | 1        |
| 15 | Ejemplo15 | 37     | 15.4    | 2023-07-05 | 0        |
| 16 | Ejemplo16 | 81     | 82.9    | 2023-08-11 | 1        |
| 17 | Ejemplo17 | 45     | 28.3    | 2023-09-27 | 0        |
| 18 | Ejemplo18 | 60     | 50.6    | 2023-10-15 | 1        |
| 19 | Ejemplo19 | 5      | 8.7     | 2023-11-22 | 0        |
| 20 | Ejemplo20 | 76     | 65.1    | 2023-12-08 | 1        |
| 21 | Ejemplo21 | 33     | 20.3    | 2024-01-14 | 0        |
| 22 | Ejemplo22 | 70     | 55.8    | 2024-02-29 | 1        |
| 23 | Ejemplo23 | 13     | 42.7    | 2024-03-18 | 0        |
| 24 | Ejemplo24 | 89     | 78.4    | 2024-04-25 | 1        |
| 25 | Ejemplo25 | 49     | 15.9    | 2024-05-12 | 0        |
| 26 | Ejemplo26 | 62     | 60.7    | 2024-06-20 | 1        |
| 27 | Ejemplo27 | 8      | 35.2    | 2024-07-07 | 0        |
| 28 | Ejemplo28 | 95     | 25.6    | 2024-08-23 | 1        |
| 29 | Ejemplo29 | 27     | 50.0    | 2024-09-10 | 0        |
| 30 | Ejemplo30 | 74     | 85.3    | 2024-10-05 | 1        |
| 31 | Ejemplo31 | 18     | 11.8    | 2024-11-12 | 0        |
| 32 | Ejemplo32 | 83     | 47.6    | 2024-12-28 | 1        |
| 33 | Ejemplo33 | 38     | 32.7    | 2025-01-15 | 0        |
| 34 | Ejemplo34 | 101    | 70.2    | 2025-02-01 | 1        |
| 35 | Ejemplo35 | 52     | 18.4    | 2025-03-20 | 0        |
| 36 | Ejemplo36 | 67     | 83.9    | 2025-04-06 | 1        |
| 37 | Ejemplo37 | 43     | 28.3    | 2025-05-13 | 0        |
| 38 | Ejemplo38 | 58     | 50.6    | 2025-06-30 | 1        |
| 39 | Ejemplo39 | 9      | 8.7     | 2025-07-17 | 0        |
| 40 | Ejemplo40 | 82     | 65.1    | 2025-08-23 | 1        |
| 41 | Ejemplo41 | 26     | 20.3    | 2025-09-09 | 0        |
| 42 | Ejemplo42 | 73     | 55.8    | 2025-10-26 | 1        |
| 43 | Ejemplo43 | 14     | 42.7    | 2025-11-13 | 0        |
| 44 | Ejemplo44 | 90     | 78.4    | 2025-12-30 | 1        |
| 45 | Ejemplo45 | 50     | 15.9    | 2026-01-16 | 0        |
| 46 | Ejemplo46 | 63     | 60.7    | 2026-02-03 | 1        |
| 47 | Ejemplo47 | 7      | 35.2    | 2026-03-22 | 0        |
| 48 | Ejemplo48 | 96     | 25.6    | 2026-04-08 | 1        |
| 49 | Ejemplo49 | 28     | 50.0    | 2026-05-25 | 0        |
| 50 | Ejemplo50 | 75     | 85.3    | 2026-06-11 | 1        |
+----+-----------+--------+---------+------------+----------+
```
---

### Paso 3: Realizar 5 consultas de datos

1. Obtén todas las entradas de la tabla ejemplos.

- Para obtener todas las entradas de la tabla ejemplos haremos uso de la sentencia `SELECT`

```
select * from ejemplos;
```

Para seleccionar todos los elementos de la tabla hacemos uso del *

Al ejecutar esta sentencia nos aparecera la tabla de antes.

2. Obtén las entradas con el campo entero mayor a 50.

- Para obtener las entradas de entero mayor a 50 hacemos uso de la siguiente sentencia:

```
select * from ejemplos
where decimal > 50;
```

Para localizar entradas concretas usaremos el `where`

Una vez usemos el comando anterior nos aparecera en pantalla todos los campos decimales mayores a 50.

``` 
+----+-----------+--------+---------+------------+----------+
| id |   texto   | entero | decimal |   fecha    | booleano |
+----+-----------+--------+---------+------------+----------+
| 4  | Ejemplo4  | 78     | 75.2    | 2022-08-05 | 1        |
| 6  | Ejemplo6  | 55     | 60.3    | 2022-10-08 | 1        |
| 9  | Ejemplo9  | 31     | 55.0    | 2023-01-20 | 0        |
| 10 | Ejemplo10 | 68     | 90.4    | 2023-02-14 | 1        |
| 14 | Ejemplo14 | 93     | 70.2    | 2023-06-18 | 1        |
| 16 | Ejemplo16 | 81     | 82.9    | 2023-08-11 | 1        |
| 18 | Ejemplo18 | 60     | 50.6    | 2023-10-15 | 1        |
| 20 | Ejemplo20 | 76     | 65.1    | 2023-12-08 | 1        |
| 22 | Ejemplo22 | 70     | 55.8    | 2024-02-29 | 1        |
| 24 | Ejemplo24 | 89     | 78.4    | 2024-04-25 | 1        |
| 26 | Ejemplo26 | 62     | 60.7    | 2024-06-20 | 1        |
| 30 | Ejemplo30 | 74     | 85.3    | 2024-10-05 | 1        |
| 34 | Ejemplo34 | 101    | 70.2    | 2025-02-01 | 1        |
| 36 | Ejemplo36 | 67     | 83.9    | 2025-04-06 | 1        |
| 38 | Ejemplo38 | 58     | 50.6    | 2025-06-30 | 1        |
| 40 | Ejemplo40 | 82     | 65.1    | 2025-08-23 | 1        |
| 42 | Ejemplo42 | 73     | 55.8    | 2025-10-26 | 1        |
| 44 | Ejemplo44 | 90     | 78.4    | 2025-12-30 | 1        |
| 46 | Ejemplo46 | 63     | 60.7    | 2026-02-03 | 1        |
| 50 | Ejemplo50 | 75     | 85.3    | 2026-06-11 | 1        |
+----+-----------+--------+---------+------------+----------+
```

---

### Paso 4: Realizar 3 eliminaciones y 3 modificaciones.

1. Elimina las entradas donde el campo `booleano` es igual a `true`.

- Para eleminar campos de nuestra tabla, hacemos uso del `DELETE` de la siguiente manera:

```
delete from ejemplos
where booleano = 1;
```

Nos quedara este resultado:

```
+----+-----------+--------+---------+------------+----------+
| id |   texto   | entero | decimal |   fecha    | booleano |
+----+-----------+--------+---------+------------+----------+
| 1  | Ejemplo1  | 25     | 10.5    | 2022-05-15 | 0        |
| 3  | Ejemplo3  | 12     | 30.0    | 2022-07-10 | 0        |
| 5  | Ejemplo5  | 42     | 18.9    | 2022-09-12 | 0        |
| 7  | Ejemplo7  | 10     | 40.1    | 2022-11-17 | 0        |
| 9  | Ejemplo9  | 31     | 55.0    | 2023-01-20 | 0        |
| 11 | Ejemplo11 | 15     | 12.8    | 2023-03-22 | 0        |
| 13 | Ejemplo13 | 22     | 33.7    | 2023-05-01 | 0        |
| 15 | Ejemplo15 | 37     | 15.4    | 2023-07-05 | 0        |
| 17 | Ejemplo17 | 45     | 28.3    | 2023-09-27 | 0        |
| 19 | Ejemplo19 | 5      | 8.7     | 2023-11-22 | 0        |
| 21 | Ejemplo21 | 33     | 20.3    | 2024-01-14 | 0        |
| 23 | Ejemplo23 | 13     | 42.7    | 2024-03-18 | 0        |
| 25 | Ejemplo25 | 49     | 15.9    | 2024-05-12 | 0        |
| 27 | Ejemplo27 | 8      | 35.2    | 2024-07-07 | 0        |
| 29 | Ejemplo29 | 27     | 50.0    | 2024-09-10 | 0        |
| 31 | Ejemplo31 | 18     | 11.8    | 2024-11-12 | 0        |
| 33 | Ejemplo33 | 38     | 32.7    | 2025-01-15 | 0        |
| 35 | Ejemplo35 | 52     | 18.4    | 2025-03-20 | 0        |
| 37 | Ejemplo37 | 43     | 28.3    | 2025-05-13 | 0        |
| 39 | Ejemplo39 | 9      | 8.7     | 2025-07-17 | 0        |
| 41 | Ejemplo41 | 26     | 20.3    | 2025-09-09 | 0        |
| 43 | Ejemplo43 | 14     | 42.7    | 2025-11-13 | 0        |
| 45 | Ejemplo45 | 50     | 15.9    | 2026-01-16 | 0        |
| 47 | Ejemplo47 | 7      | 35.2    | 2026-03-22 | 0        |
| 49 | Ejemplo49 | 28     | 50.0    | 2026-05-25 | 0        |
+----+-----------+--------+---------+------------+----------+
```

2. Modifica el campo `texto` de las entradas donde el campo `entero` es menos a 30 y establece el texto como "Modificado".

- Para modificar el campo `texto` utilizaremos el siguiente comando:

```
set entero = 'modificado'
where entero < 30;
```

```
+----+-----------+------------+---------+------------+----------+
| id |   texto   |   entero   | decimal |   fecha    | booleano |
+----+-----------+------------+---------+------------+----------+
| 1  | Ejemplo1  | modificado | 10.5    | 2022-05-15 | 0        |
| 3  | Ejemplo3  | modificado | 30.0    | 2022-07-10 | 0        |
| 5  | Ejemplo5  | 42         | 18.9    | 2022-09-12 | 0        |
| 7  | Ejemplo7  | modificado | 40.1    | 2022-11-17 | 0        |
| 9  | Ejemplo9  | 31         | 55.0    | 2023-01-20 | 0        |
| 11 | Ejemplo11 | modificado | 12.8    | 2023-03-22 | 0        |
| 13 | Ejemplo13 | modificado | 33.7    | 2023-05-01 | 0        |
| 15 | Ejemplo15 | 37         | 15.4    | 2023-07-05 | 0        |
| 17 | Ejemplo17 | 45         | 28.3    | 2023-09-27 | 0        |
| 19 | Ejemplo19 | modificado | 8.7     | 2023-11-22 | 0        |
| 21 | Ejemplo21 | 33         | 20.3    | 2024-01-14 | 0        |
| 23 | Ejemplo23 | modificado | 42.7    | 2024-03-18 | 0        |
| 25 | Ejemplo25 | 49         | 15.9    | 2024-05-12 | 0        |
| 27 | Ejemplo27 | modificado | 35.2    | 2024-07-07 | 0        |
| 29 | Ejemplo29 | modificado | 50.0    | 2024-09-10 | 0        |
| 31 | Ejemplo31 | modificado | 11.8    | 2024-11-12 | 0        |
| 33 | Ejemplo33 | 38         | 32.7    | 2025-01-15 | 0        |
| 35 | Ejemplo35 | 52         | 18.4    | 2025-03-20 | 0        |
| 37 | Ejemplo37 | 43         | 28.3    | 2025-05-13 | 0        |
| 39 | Ejemplo39 | modificado | 8.7     | 2025-07-17 | 0        |
| 41 | Ejemplo41 | modificado | 20.3    | 2025-09-09 | 0        |
| 43 | Ejemplo43 | modificado | 42.7    | 2025-11-13 | 0        |
| 45 | Ejemplo45 | 50         | 15.9    | 2026-01-16 | 0        |
| 47 | Ejemplo47 | modificado | 35.2    | 2026-03-22 | 0        |
| 49 | Ejemplo49 | modificado | 50.0    | 2026-05-25 | 0        |
+----+-----------+------------+---------+------------+----------+
``` 

3. Elimina las entradas donde el campo `entero` es igual a 50.

- Para eliminar las entradas del campo entero igual a 50 utilizaremos:

```
delete from ejemplos
where entero = 50;
```

```
+----+-----------+------------+---------+------------+----------+
| id |   texto   |   entero   | decimal |   fecha    | booleano |
+----+-----------+------------+---------+------------+----------+
| 1  | Ejemplo1  | modificado | 10.5    | 2022-05-15 | 0        |
| 3  | Ejemplo3  | modificado | 30.0    | 2022-07-10 | 0        |
| 5  | Ejemplo5  | 42         | 18.9    | 2022-09-12 | 0        |
| 7  | Ejemplo7  | modificado | 40.1    | 2022-11-17 | 0        |
| 9  | Ejemplo9  | 31         | 55.0    | 2023-01-20 | 0        |
| 11 | Ejemplo11 | modificado | 12.8    | 2023-03-22 | 0        |
| 13 | Ejemplo13 | modificado | 33.7    | 2023-05-01 | 0        |
| 15 | Ejemplo15 | 37         | 15.4    | 2023-07-05 | 0        |
| 17 | Ejemplo17 | 45         | 28.3    | 2023-09-27 | 0        |
| 19 | Ejemplo19 | modificado | 8.7     | 2023-11-22 | 0        |
| 21 | Ejemplo21 | 33         | 20.3    | 2024-01-14 | 0        |
| 23 | Ejemplo23 | modificado | 42.7    | 2024-03-18 | 0        |
| 25 | Ejemplo25 | 49         | 15.9    | 2024-05-12 | 0        |
| 27 | Ejemplo27 | modificado | 35.2    | 2024-07-07 | 0        |
| 29 | Ejemplo29 | modificado | 50.0    | 2024-09-10 | 0        |
| 31 | Ejemplo31 | modificado | 11.8    | 2024-11-12 | 0        |
| 33 | Ejemplo33 | 38         | 32.7    | 2025-01-15 | 0        |
| 35 | Ejemplo35 | 52         | 18.4    | 2025-03-20 | 0        |
| 37 | Ejemplo37 | 43         | 28.3    | 2025-05-13 | 0        |
| 39 | Ejemplo39 | modificado | 8.7     | 2025-07-17 | 0        |
| 41 | Ejemplo41 | modificado | 20.3    | 2025-09-09 | 0        |
| 43 | Ejemplo43 | modificado | 42.7    | 2025-11-13 | 0        |
| 47 | Ejemplo47 | modificado | 35.2    | 2026-03-22 | 0        |
| 49 | Ejemplo49 | modificado | 50.0    | 2026-05-25 | 0        |
+----+-----------+------------+---------+------------+----------+
```

4. Incrementar en 10 el valor del campo `entero` para las entradas donde el campo `booleano` es igual a `false`.

- Para incremente en 10 el valor del campo `entero` utilizaremos lo siguiente:

```
set entero = entero + 10
where booleano = 0;
```

El resultado seria

```
+----+-----------+--------+---------+------------+----------+
| id |   texto   | entero | decimal |   fecha    | booleano |
+----+-----------+--------+---------+------------+----------+
| 1  | Ejemplo1  | 10     | 10.5    | 2022-05-15 | 0        |
| 3  | Ejemplo3  | 10     | 30.0    | 2022-07-10 | 0        |
| 5  | Ejemplo5  | 52     | 18.9    | 2022-09-12 | 0        |
| 7  | Ejemplo7  | 10     | 40.1    | 2022-11-17 | 0        |
| 9  | Ejemplo9  | 41     | 55.0    | 2023-01-20 | 0        |
| 11 | Ejemplo11 | 10     | 12.8    | 2023-03-22 | 0        |
| 13 | Ejemplo13 | 10     | 33.7    | 2023-05-01 | 0        |
| 15 | Ejemplo15 | 47     | 15.4    | 2023-07-05 | 0        |
| 17 | Ejemplo17 | 55     | 28.3    | 2023-09-27 | 0        |
| 19 | Ejemplo19 | 10     | 8.7     | 2023-11-22 | 0        |
| 21 | Ejemplo21 | 43     | 20.3    | 2024-01-14 | 0        |
| 23 | Ejemplo23 | 10     | 42.7    | 2024-03-18 | 0        |
| 25 | Ejemplo25 | 59     | 15.9    | 2024-05-12 | 0        |
| 27 | Ejemplo27 | 10     | 35.2    | 2024-07-07 | 0        |
| 29 | Ejemplo29 | 10     | 50.0    | 2024-09-10 | 0        |
| 31 | Ejemplo31 | 10     | 11.8    | 2024-11-12 | 0        |
| 33 | Ejemplo33 | 48     | 32.7    | 2025-01-15 | 0        |
| 35 | Ejemplo35 | 62     | 18.4    | 2025-03-20 | 0        |
| 37 | Ejemplo37 | 53     | 28.3    | 2025-05-13 | 0        |
| 39 | Ejemplo39 | 10     | 8.7     | 2025-07-17 | 0        |
| 41 | Ejemplo41 | 10     | 20.3    | 2025-09-09 | 0        |
| 43 | Ejemplo43 | 10     | 42.7    | 2025-11-13 | 0        |
| 47 | Ejemplo47 | 10     | 35.2    | 2026-03-22 | 0        |
| 49 | Ejemplo49 | 10     | 50.0    | 2026-05-25 | 0        |
+----+-----------+--------+---------+------------+----------+
```

5. Elimina las entradas donde el campo `decimal` es menor a 50.

- Para eliminar las entradas donde el campo `decimal` es menor a 50 utilizaremos lo siguiente:

```
delete from ejemplos
where decimal < 50;
```

```
+----+-----------+--------+---------+------------+----------+
| id |   texto   | entero | decimal |   fecha    | booleano |
+----+-----------+--------+---------+------------+----------+
| 9  | Ejemplo9  | 41     | 55.0    | 2023-01-20 | 0        |
| 29 | Ejemplo29 | 10     | 50.0    | 2024-09-10 | 0        |
| 49 | Ejemplo49 | 10     | 50.0    | 2026-05-25 | 0        |
+----+-----------+--------+---------+------------+----------+
```

6. Actualiza el campo `fecha` de todas las entradas a la fecha actual.

- Para actualizar el campo `fecha` de todas las entradas a la fecha actual utilizaremos lo siguiente:

```
update ejemplo
set fecha = date('now');
```

```
+----+-----------+--------+---------+------------+----------+
| id |   texto   | entero | decimal |   fecha    | booleano |
+----+-----------+--------+---------+------------+----------+
| 9  | Ejemplo9  | 41     | 55.0    | 2023-12-16 | 0        |
| 29 | Ejemplo29 | 10     | 50.0    | 2023-12-16 | 0        |
| 49 | Ejemplo49 | 10     | 50.0    | 2023-12-16 | 0        |
+----+-----------+--------+---------+------------+----------+
```
