# Tarea 1

En este ejercicio, vamos a trabajar en la creación de una base de datos simple utilizando MySQL. Esta base de datos estará diseñada para administrar información de usuarios y productos. Una vez que hayamos creado la base de datos y las tablas necesarias, vamos a implementar procedimientos almacenados y funciones para realizar operaciones comunes sobre estos datos.

**1.** *Crea la bbdd. Utilizaremos comandos SQL para crear una base de datos llamada "SimpleDB" que contendrá dos tablas: "Users" para almacenar información de usuarios y "Products" para almacenar información de productos.*

``` sql
CREATE DATABASE IF NOT EXISTS SimpleDB;

USE SimpleDB;

CREATE TABLE IF NOT EXISTS Users (
    UserID INT AUTO_INCREMENT PRIMARY KEY,
    UserName VARCHAR(50) NOT NULL,
    Email VARCHAR(100) NOT NULL
);

CREATE TABLE IF NOT EXISTS Products (
    ProductID INT AUTO_INCREMENT PRIMARY KEY,
    ProductName VARCHAR(100) NOT NULL,
    Price DECIMAL(10, 2) NOT NULL
);
```

**2.** *Realiza la inserción de algunos datos de prueba.*

``` sql

INSERT INTO Users (UserName, Email) VALUES ('Juan', 'juan@example.com');
INSERT INTO Users (UserName, Email) VALUES ('María', 'maria@example.com');
INSERT INTO Users (UserName, Email) VALUES ('Pedro', 'pedro@example.com');

INSERT INTO Products (ProductName, Price) VALUES ('Producto 1', 10.99);
INSERT INTO Products (ProductName, Price) VALUES ('Producto 2', 20.50);
INSERT INTO Products (ProductName, Price) VALUES ('Producto 3', 15.75);
```

>__Nota__:_Realizar la inserción de al menos_ ___3 elementos___ _más en cada tabla_.


``` sql
INSERT INTO Users (UserName, Email) VALUES ("Pepe","pepe@gmail.com");
INSERT INTO Users (UserName, Email) VALUES ("Lola","lola@gmail.com");
INSERT INTO Users (UserName, Email) VALUES ("Mariano","Mariano@gmail.com");
INSERT INTO Products (ProductName, Price) VALUES ("Producto 4",25.00);
INSERT INTO Products (ProductName, Price) VALUES ("Producto 5",30.00);
INSERT INTO Products (ProductName, Price) VALUES ("Producto 6",35.00);
``` 

**3.** *Crea procedimientos almacenados para realizar operaciones como insertar un nuevo usuario, actualizar el nombre de un usuario, etc*

- Procedimiento para insertar un nuevo usuario.

``` sql
DELIMITER $$
DROP PROCEDURE IF EXISTS insert_user$$
CREATE PROCEDURE insert_user(IN Username VARCHAR(50), IN email VARCHAR(50))
BEGIN
INSERT INTO Users (UserName, Email) VALUES (Username, email);
END
$$
DELIMITER ;
```

``` sql
CALL insert_user("Gonzalo", "gonza@gmail.com");
CALL insert_user("Carlos", "carlos@gmail.com");
CALL insert_user("Oscar", "oscar@gmail.com");
```

``` sql
+--------+----------+-------------------+
| UserID | UserName | Email             |
+--------+----------+-------------------+
|      1 | Juan     | juan@example.com  |
|      2 | María    | maria@example.com |
|      3 | Pedro    | pedro@example.com |
|      4 | Juan     | juan@example.com  |
|      5 | María    | maria@example.com |
|      6 | Pedro    | pedro@example.com |
|      7 | Pepe     | pepe@gmail.com    |
|      8 | Lola     | lola@gmail.com    |
|      9 | Mariano  | Mariano@gmail.com |
|     10 | Gonzalo  | gonza@gmail.com   |
|     11 | Carlos   | carlos@gmail.com  |
|     12 | Oscar    | oscar@gmail.com   |
+--------+----------+-------------------+
```

- Procedimiento para actualizar el nombre de un usuario.

``` sql
DELIMITER $$
DROP PROCEDURE IF EXISTS update_user$$
CREATE PROCEDURE update_user(IN Userid INT(3), IN NewUser VARCHAR(50))
BEGIN
UPDATE Users
SET UserName = NewUser
WHERE UserID = Userid;
END $$
DELIMITER ;
```

``` sql
CALL update_user("Gonzalo", "Alberto");
CALL update_user("Lola", "Maria");
CALL update_user("Oscar", "Nicolas");
```

``` sql
+--------+----------+-------------------+
| UserID | UserName | Email             |
+--------+----------+-------------------+
|      1 | Oscar    | juan@example.com  |
|      2 | Oscar    | maria@example.com |
|      3 | Oscar    | pedro@example.com |
|      4 | Oscar    | juan@example.com  |
|      5 | Oscar    | maria@example.com |
|      6 | Oscar    | pedro@example.com |
|      7 | Oscar    | pepe@gmail.com    |
|      8 | Oscar    | lola@gmail.com    |
|      9 | Oscar    | Mariano@gmail.com |
|     10 | Oscar    | gonza@gmail.com   |
|     11 | Oscar    | carlos@gmail.com  |
|     12 | Oscar    | oscar@gmail.com   |
+--------+----------+-------------------+
```

>__Nota__:_Realizar la invocación y la verificación de que han funcionado correctamente_.

**4.** - *Implementa funciones para realizar cálculos o consultas:*

- Función para calcular el precio total de un conjunto de productos.

``` sql
DELIMITER $$
DROP FUNCTION IF EXISTS calc_precio_total$$
CREATE FUNCTION calc_preio_total()
```

- Función para contar el número de usuarios.
