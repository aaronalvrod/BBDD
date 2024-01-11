# Creación de la Base de Datos

![SQLite3 logo](https://github.com/aaronalvrod/BBDD./assets/147527842/66e6aecb-6d3f-4a2c-b845-6059ccd59596)

## Objetivo

Practicar la creación y manipulación de una base de datos SQLite3 desde la línea de comandos.

## Pasos

## Paso 1: Crear una tabla con un campo de cada tipo.

1. **Utilizamos la terminal o línea de comandos, abrimos SQLite3 y creamos una base de datos llamada ``tarea2.db``**

```sqlite3 tarea2.db```

2. **Dentro de SQLite3, creamos las siguientes tablas:**

**Tabla Propietarios:**

```
CREATE TABLE propietarios (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    nombre TEXT NOT NULL,
    apellido TEXT NOT NULL,
    dni TEXT UNIQUE NOT NULL );
```

**Tabla Vehiculos:**

```
CREATE TABLE Vehiculos (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    marca TEXT NOT NULL,
    modelo TEXT NOT NULL,
    anio INTEGER NOT NULL,
    id_propietario INTEGER,
    FOREIGN KEY (id_propietario) REFERENCES Propietarios(id) );
```

## Paso 2: Insertar las entradas de las tablas.

A continuación realizaremos las inserciones de las entradas de ambas tablas, la de propietario y la de vehiculos.

**Tabla Propietarios:**

```
INSERT INTO Propietarios (nombre, apellido, dni) VALUES
    ('Juan', 'Perez', '12345678A'),
    ('Maria', 'Lopez', '87654321B'),
    ('Carlos', 'Ruiz', '11111111C'),
    ('Laura', 'Gomez', '22222222D'),
    ('Pedro', 'Martinez', '33333333E'),
    ('Ana', 'Fernandez', '44444444F'),
    ('Diego', 'Sanchez', '55555555G'),
    ('Sofia', 'Torres', '66666666H'),
    ('Javier', 'Leon', '77777777I'),
    ('Lucia', 'Castillo', '88888888J'),
    ('Luis', 'Gonzalez', '99999999K'),
    ('Marta', 'Diaz', '10101010L'),
    ('Victor', 'Vargas', '11111112M'),
    ('Elena', 'Castro', '12121212N'),
    ('Roberto', 'Blanco', '13131313O'),
    ('Natalia', 'Paredes', '14141414P'),
    ('Fernando', 'Herrera', '15151515Q'),
    ('Clara', 'Soto', '16161616R'),
    ('Sergio', 'Mendoza', '17171717S'),
    ('Patricia', 'Navarro', '18181818T');
```

**Tabla Vehiculos:**

```
INSERT INTO Vehiculos (marca, modelo, anio, id_propietario) VALUES
    ('Ford', 'Fiesta', 2019, 1),
    ('Toyota', 'Corolla', 2018, 2),
    ('Nissan', 'Sentra', 2020, 3),
    ('Chevrolet', 'Spark', 2017, 4),
    ('Honda', 'Civic', 2016, 5),
    ('Ford', 'Mustang', 2021, 6),
    ('Toyota', 'RAV4', 2019, 7),
    ('Volkswagen', 'Golf', 2020, 8),
    ('Honda', 'CR-V', 2018, 9),
    ('Nissan', 'Altima', 2017, 10),
    ('Chevrolet', 'Malibu', 2019, 11),
    ('Toyota', 'Camry', 2020, 12),
    ('Honda', 'Accord', 2018, 13),
    ('Ford', 'Explorer', 2021, 14),
    ('Nissan', 'Rogue', 2017, 15),
    ('Volkswagen', 'Jetta', 2019, 16),
    ('Chevrolet', 'Equinox', 2018, 17),
    ('Toyota', 'Highlander', 2020, 18),
    ('Honda', 'Odyssey', 2016, 19),
    ('Nissan', 'Murano', 2019, 20);
```

## Paso 3: Realizar las siguientes 10 consultas de datos.

- **Seleccionar todos los propietarios.**

`SELECT * FROM propietarios;`

Al darle enter a este comando nos aparecera la siguiente tabla

``` sql
+----+----------+-----------+-----------+
| id |  nombre  | apellido  |    dni    |
+----+----------+-----------+-----------+
| 1  | Juan     | Perez     | 12345678A |
| 2  | Maria    | Lopez     | 87654321B |
| 3  | Carlos   | Ruiz      | 11111111C |
| 4  | Laura    | Gomez     | 22222222D |
| 5  | Pedro    | Martinez  | 33333333E |
| 6  | Ana      | Fernandez | 44444444F |
| 7  | Diego    | Sanchez   | 55555555G |
| 8  | Sofia    | Torres    | 66666666H |
| 9  | Javier   | Leon      | 77777777I |
| 10 | Lucia    | Castillo  | 88888888J |
| 11 | Luis     | Gonzalez  | 99999999K |
| 12 | Marta    | Diaz      | 10101010L |
| 13 | Victor   | Vargas    | 11111112M |
| 14 | Elena    | Castro    | 12121212N |
| 15 | Roberto  | Blanco    | 13131313O |
| 16 | Natalia  | Paredes   | 14141414P |
| 17 | Fernando | Herrera   | 15151515Q |
| 18 | Clara    | Soto      | 16161616R |
| 19 | Sergio   | Mendoza   | 17171717S |
| 20 | Patricia | Navarro   | 18181818T |
+----+----------+-----------+-----------+
```

- **Listar todos los vehículos.**

`SELECT * FROM vehiculos;`

Al darle entar a este comando nos aparecera la siguiente tabla

``` sql
+----+------------+------------+------+----------------+
| id |   marca    |   modelo   | anio | id_propietario |
+----+------------+------------+------+----------------+
| 1  | Ford       | Fiesta     | 2019 | 1              |
| 2  | Toyota     | Corolla    | 2018 | 2              |
| 3  | Nissan     | Sentra     | 2020 | 3              |
| 4  | Chevrolet  | Spark      | 2017 | 4              |
| 5  | Honda      | Civic      | 2016 | 5              |
| 6  | Ford       | Mustang    | 2021 | 6              |
| 7  | Toyota     | RAV4       | 2019 | 7              |
| 8  | Volkswagen | Golf       | 2020 | 8              |
| 9  | Honda      | CR-V       | 2018 | 9              |
| 10 | Nissan     | Altima     | 2017 | 10             |
| 11 | Chevrolet  | Malibu     | 2019 | 11             |
| 12 | Toyota     | Camry      | 2020 | 12             |
| 13 | Honda      | Accord     | 2018 | 13             |
| 14 | Ford       | Explorer   | 2021 | 14             |
| 15 | Nissan     | Rogue      | 2017 | 15             |
| 16 | Volkswagen | Jetta      | 2019 | 16             |
| 17 | Chevrolet  | Equinox    | 2018 | 17             |
| 18 | Toyota     | Highlander | 2020 | 18             |
| 19 | Honda      | Odyssey    | 2016 | 19             |
| 20 | Nissan     | Murano     | 2019 | 20             |
+----+------------+------------+------+----------------+
``` 

- **Seleccionar solo los nombres y apellidos de los propietarios.**

`SELECT nombre, apellido FROM propietarios;`

Al darle enter a este comando nos aparecera la siguiente tabla

``` sql
+----------+-----------+
|  nombre  | apellido  |
+----------+-----------+
| Juan     | Perez     |
| Maria    | Lopez     |
| Carlos   | Ruiz      |
| Laura    | Gomez     |
| Pedro    | Martinez  |
| Ana      | Fernandez |
| Diego    | Sanchez   |
| Sofia    | Torres    |
| Javier   | Leon      |
| Lucia    | Castillo  |
| Luis     | Gonzalez  |
| Marta    | Diaz      |
| Victor   | Vargas    |
| Elena    | Castro    |
| Roberto  | Blanco    |
| Natalia  | Paredes   |
| Fernando | Herrera   |
| Clara    | Soto      |
| Sergio   | Mendoza   |
| Patricia | Navarro   |
+----------+-----------+
```

- **Listar todas las marcas y modelos de los vehículos.**

`SELECT marca. modelo FROM vehiculos`

Al darle enter a este comando nos aparecera la siguiente tabla

``` sql
+------------+------------+
|   marca    |   modelo   |
+------------+------------+
| Ford       | Fiesta     |
| Toyota     | Corolla    |
| Nissan     | Sentra     |
| Chevrolet  | Spark      |
| Honda      | Civic      |
| Ford       | Mustang    |
| Toyota     | RAV4       |
| Volkswagen | Golf       |
| Honda      | CR-V       |
| Nissan     | Altima     |
| Chevrolet  | Malibu     |
| Toyota     | Camry      |
| Honda      | Accord     |
| Ford       | Explorer   |
| Nissan     | Rogue      |
| Volkswagen | Jetta      |
| Chevrolet  | Equinox    |
| Toyota     | Highlander |
| Honda      | Odyssey    |
| Nissan     | Murano     |
+------------+------------+
```

- **Seleccionar solo los propietarios con apellido "Perez".**

`SELECT * FROM vehiculos WHERE apellido = "Perez";`

Al darle enter a este comando nos aparecera la siguiente tabla

``` sql
+----+--------+----------+-----------+
| id | nombre | apellido |    dni    |
+----+--------+----------+-----------+
| 1  | Juan   | Perez    | 12345678A |
+----+--------+----------+-----------+
```

- **Listar todos los vehículos con año 2019.**

`SELECT * FROM vehiculos where anio = 2019;`

Al darle enter a este comando nos aparecera la siguiente tabla

``` sql
+----+------------+--------+------+----------------+
| id |   marca    | modelo | anio | id_propietario |
+----+------------+--------+------+----------------+
| 1  | Ford       | Fiesta | 2019 | 1              |
| 7  | Toyota     | RAV4   | 2019 | 7              |
| 11 | Chevrolet  | Malibu | 2019 | 11             |
| 16 | Volkswagen | Jetta  | 2019 | 16             |
| 20 | Nissan     | Murano | 2019 | 20             |
+----+------------+--------+------+----------------+
```

- **Seleccionar propietarios que tienen vehículos de la marca "Toyota":**

`
SELECT Propietarios.* FROM Propietarios
JOIN Vehiculos ON Propietarios.id = Vehiculos.id_propietario
WHERE Vehiculos.marca = 'Toyota';
`

Al darle enter a este comando nos aparecera la siguiente tabla

``` sql
+----+--------+----------+-----------+
| id | nombre | apellido |    dni    |
+----+--------+----------+-----------+
| 2  | Maria  | Lopez    | 87654321B |
| 7  | Diego  | Sanchez  | 55555555G |
| 12 | Marta  | Diaz     | 10101010L |
| 18 | Clara  | Soto     | 16161616R |
+----+--------+----------+-----------+
```

- **Listar vehículos con marca "Ford" y modelo "Fiesta":**

`SELECT * FROM Vehiculos WHERE marca = 'Ford' AND modelo = 'Fiesta';`

Al darle enter a este comando nos aparecera la siguiente tabla

``` sql
+----+-------+--------+------+----------------+
| id | marca | modelo | anio | id_propietario |
+----+-------+--------+------+----------------+
| 1  | Ford  | Fiesta | 2019 | 1              |
+----+-------+--------+------+----------------+
```

- **Seleccionar propietarios con DNI"12345678A".**

`SELECT * FROM Propietarios WHERE dni = '12345678A';`

Al darle enter a este comando nos aparecera la siguiente tabla

``` sql
+----+--------+----------+-----------+
| id | nombre | apellido |    dni    |
+----+--------+----------+-----------+
| 1  | Juan   | Perez    | 12345678A |
+----+--------+----------+-----------+
```

- **Listar vehículos que pertenecen al propietario con ID 5.**

`SELECT * FROM Vehiculos WHERE id_propietario = 5;`
 
Al darle enter a este comando nos aparecera la siguiente tabla

``` sql
+----+-------+--------+------+----------------+
| id | marca | modelo | anio | id_propietario |
+----+-------+--------+------+----------------+
| 5  | Honda | Civic  | 2016 | 5              |
+----+-------+--------+------+----------------+
```

## Paso 4: Realizar los siguientes updates:

- Actualizar el nombre de un propietario con DNI "12345678A"

`UPDATE Propietarios SET nombre = 'NuevoNombre' WHERE dni = '12345678A';`

- Modificar el año de un vehículo con ID 3 a 2022.

`UPDATE Vehiculos SET anio = 2022 WHERE id = 3;`

- Cambiar el modelo de todos los vehículos Nissan a "Micra".

`UPDATE Vehiculos SET modelo = 'Micra' WHERE marca = 'Nissan';`

- Actualizar el apellido de un propietario con ID 7 a "Gomez".

`UPDATE Propietarios SET apellido = 'Gomez' WHERE id = 7;`

- Modificar la marca de un vehículo con modelo "Fiesta" a "Renault".

`UPDATE Vehiculos SET marca = 'Renault' WHERE modelo = 'Fiesta';`

El resultado de realizar estos updates es.

Tabla Propietarios: 

``` sql
+----+-------------+-----------+-----------+
| id |   nombre    | apellido  |    dni    |
+----+-------------+-----------+-----------+
| 1  | NuevoNombre | Perez     | 12345678A |
| 2  | Maria       | Lopez     | 87654321B |
| 3  | Carlos      | Ruiz      | 11111111C |
| 4  | Laura       | Gomez     | 22222222D |
| 5  | Pedro       | Martinez  | 33333333E |
| 6  | Ana         | Fernandez | 44444444F |
| 7  | Diego       | Gomez     | 55555555G |
| 8  | Sofia       | Torres    | 66666666H |
| 9  | Javier      | Leon      | 77777777I |
| 10 | Lucia       | Castillo  | 88888888J |
| 11 | Luis        | Gonzalez  | 99999999K |
| 12 | Marta       | Diaz      | 10101010L |
| 13 | Victor      | Vargas    | 11111112M |
| 14 | Elena       | Castro    | 12121212N |
| 15 | Roberto     | Blanco    | 13131313O |
| 16 | Natalia     | Paredes   | 14141414P |
| 17 | Fernando    | Herrera   | 15151515Q |
| 18 | Clara       | Soto      | 16161616R |
| 19 | Sergio      | Mendoza   | 17171717S |
| 20 | Patricia    | Navarro   | 18181818T |
+----+-------------+-----------+-----------+
```

Tabla Vehiculos: 
``` sql
+----+------------+------------+------+----------------+
| id |   marca    |   modelo   | anio | id_propietario |
+----+------------+------------+------+----------------+
| 1  | Renault    | Fiesta     | 2019 | 1              |
| 2  | Toyota     | Corolla    | 2018 | 2              |
| 3  | Nissan     | Micra      | 2022 | 3              |
| 4  | Chevrolet  | Spark      | 2017 | 4              |
| 5  | Honda      | Civic      | 2016 | 5              |
| 6  | Ford       | Mustang    | 2021 | 6              |
| 7  | Toyota     | RAV4       | 2019 | 7              |
| 8  | Volkswagen | Golf       | 2020 | 8              |
| 9  | Honda      | CR-V       | 2018 | 9              |
| 10 | Nissan     | Micra      | 2017 | 10             |
| 11 | Chevrolet  | Malibu     | 2019 | 11             |
| 12 | Toyota     | Camry      | 2020 | 12             |
| 13 | Honda      | Accord     | 2018 | 13             |
| 14 | Ford       | Explorer   | 2021 | 14             |
| 15 | Nissan     | Micra      | 2017 | 15             |
| 16 | Volkswagen | Jetta      | 2019 | 16             |
| 17 | Chevrolet  | Equinox    | 2018 | 17             |
| 18 | Toyota     | Highlander | 2020 | 18             |
| 19 | Honda      | Odyssey    | 2016 | 19             |
| 20 | Nissan     | Micra      | 2019 | 20             |
+----+------------+------------+------+----------------+
```


