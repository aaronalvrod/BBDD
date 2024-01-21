# Trabajo con funciones en BBDD

### ¿Que es SQLite3?

- SQLite3 es un sistema de gestión de base de datos relacional que se caracteriza por ser un motor de base de datos incorporado, ligero y de código abierto. A diferencia de otros sistemas de gestión de base de datos como MySQL, SQLite3 no funciona como un servidor independiente, sino que se implementa como una biblioteca que se vincula directamente con la  aplicación.

![SQLite3 logo](https://github.com/aaronalvrod/BBDD./assets/147527842/66e6aecb-6d3f-4a2c-b845-6059ccd59596)

---

## Pasos

### Paso 1: Creación de la BBDD

Primeramente creamos el fichero supermercado-dump.sql

Seguidamente copiamos los CREATE TABLE de las tablas productos y ventas y ademas los INSERT de ambas tablas.

``` sql
CREATE TABLE productos (
    id INTEGER PRIMARY KEY,
    nombre TEXT,
    categoria TEXT,
    precio REAL
);

CREATE TABLE ventas (
    id INTEGER PRIMARY KEY,
    id_producto INTEGER,
    cantidad INTEGER,
    fecha DATE,
    FOREIGN KEY (id_producto) REFERENCES productos(id)
);

INSERT INTO productos (id, nombre, categoria, precio) VALUES 
    (1, 'Arroz', 'Alimentos', 2.5),
    (2, 'Leche', 'Lácteos', 1.8),
    (3, 'Pan', 'Panadería', 1.2),
    (4, 'Manzanas', 'Frutas', 3.0),
    (5, 'Pollo', 'Carnes', 5.5),
    (6, 'Huevos', 'Lácteos', 1.0),
    (7, 'Yogurt', 'Lácteos', 2.0),
    (8, 'Tomates', 'Verduras', 2.2),
    (9, 'Queso', 'Lácteos', 4.0),
    (10, 'Cereal', 'Desayuno', 3.5),
    (11, 'Papel Higiénico', 'Hogar', 1.5),
    (12, 'Cepillo de Dientes', 'Higiene', 2.0),
    (13, 'Detergente', 'Limpieza', 2.8),
    (14, 'Galletas', 'Snacks', 1.7),
    (15, 'Aceite de Oliva', 'Cocina', 4.5),
    (16, 'Café', 'Bebidas', 5.0),
    (17, 'Sopa enlatada', 'Conservas', 2.3),
    (18, 'Jabón de Baño', 'Higiene', 1.2),
    (19, 'Botellas de Agua', 'Bebidas', 1.0),
    (20, 'Cerveza', 'Bebidas', 3.8);

INSERT INTO ventas (id_producto, cantidad, fecha) VALUES 
    (1, 5, '2024-01-17'),
    (2, 3, '2024-01-17'),
    (4, 2, '2024-01-17'),
    (5, 1, '2024-01-17'),
    (6, 10, '2024-01-18'),
    (8, 4, '2024-01-18'),
    (10, 2, '2024-01-18'),
    (14, 7, '2024-01-19'),
    (16, 3, '2024-01-19'),
    (18, 6, '2024-01-20');
```
### Paso 2: Lectura del fichero sql.

En este paso crearemos el fichero de la base de datos que se llamara `tarea4.db`

``` sql
sqlite3 tarea4.db
```

Una vez tengamos el fichero creado leeremos el archivo en el cual copiamos los CREATE TABLE y los INSERT de ambas tablas.

``` sql
.read supermercado-dump.sql
```
### Paso 3: Responde a las siguientes cuestiones.

- **Realiza el diagrama ER de la BBDD supermercado**

- **Realiza el diagrama MR de la BBDD supermercado**

- **Indica si la BBDD esta normalizada hasta la 3ª forma normal, justificando la respuesta**

    - 1º F.N.: Cumple la primera forma normal, ya que todas las columnas contienen valores atómicos, y no hay conjuntos ni listas de valores

    - 2º F.N.: Cumple la segunda forma normal, ya que no hay dependencias parciales en ninguna de las tablas. Casa atributo no clave depende completamente de la clave primaria

    - 3º F.N.: Cumple la tercera forma norma, ya que no hay dependencias transitivas, lo que significa que ningún atributo no clave depende de otro atributo no clave.

### Paso 4: Responde a las siguientes cuestiones.

- **Monstrar todos los productos de la categoría "Bebidas"**

``` sql
SELECT * FROM productos WHERE categoria="Bebidas";
```

**Resultado**

``` sql
┌────┬──────────────────┬───────────┬────────┐
│ id │      nombre      │ categoria │ precio │
├────┼──────────────────┼───────────┼────────┤
│ 16 │ Café             │ Bebidas   │ 5.0    │
│ 19 │ Botellas de Agua │ Bebidas   │ 1.0    │
│ 20 │ Cerveza          │ Bebidas   │ 3.8    │
└────┴──────────────────┴───────────┴────────┘
```

- **Listar los productos ordenados por precio de forma descendente.**

``` sql
SELECT * FROM productos ORDER BY precio DESC;
```

**Resultado**

``` sql
┌────┬────────────────────┬───────────┬────────┐
│ id │       nombre       │ categoria │ precio │
├────┼────────────────────┼───────────┼────────┤
│ 5  │ Pollo              │ Carnes    │ 5.5    │
│ 16 │ Café               │ Bebidas   │ 5.0    │
│ 15 │ Aceite de Oliva    │ Cocina    │ 4.5    │
│ 9  │ Queso              │ Lácteos   │ 4.0    │
│ 20 │ Cerveza            │ Bebidas   │ 3.8    │
│ 10 │ Cereal             │ Desayuno  │ 3.5    │
│ 4  │ Manzanas           │ Frutas    │ 3.0    │
│ 13 │ Detergente         │ Limpieza  │ 2.8    │
│ 1  │ Arroz              │ Alimentos │ 2.5    │
│ 17 │ Sopa enlatada      │ Conservas │ 2.3    │
│ 8  │ Tomates            │ Verduras  │ 2.2    │
│ 7  │ Yogurt             │ Lácteos   │ 2.0    │
│ 12 │ Cepillo de Dientes │ Higiene   │ 2.0    │
│ 2  │ Leche              │ Lácteos   │ 1.8    │
│ 14 │ Galletas           │ Snacks    │ 1.7    │
│ 11 │ Papel Higiénico    │ Hogar     │ 1.5    │
│ 3  │ Pan                │ Panadería │ 1.2    │
│ 18 │ Jabón de Baño      │ Higiene   │ 1.2    │
│ 6  │ Huevos             │ Lácteos   │ 1.0    │
│ 19 │ Botellas de Agua   │ Bebidas   │ 1.0    │
└────┴────────────────────┴───────────┴────────┘
```

- **Calcular el precio total de todos los productos en la tabla "productos".**

``` sql
SELECT SUM(precio) AS precio_total FROM productos;
```

**Resultado**

``` sql
┌──────────────┐
│ precio_total │
├──────────────┤
│ 52.5         │
└──────────────┘
```

- **Encontrar los productos con un nombre que contenga la letra 'a'.**

``` sql
SELECT * FROM productos WHERE nombre LIKE '%a%';
```

**Resultado**

``` sql
┌────┬──────────────────┬───────────┬────────┐
│ id │      nombre      │ categoria │ precio │
├────┼──────────────────┼───────────┼────────┤
│ 1  │ Arroz            │ Alimentos │ 2.5    │
│ 3  │ Pan              │ Panadería │ 1.2    │
│ 4  │ Manzanas         │ Frutas    │ 3.0    │
│ 8  │ Tomates          │ Verduras  │ 2.2    │
│ 10 │ Cereal           │ Desayuno  │ 3.5    │
│ 11 │ Papel Higiénico  │ Hogar     │ 1.5    │
│ 14 │ Galletas         │ Snacks    │ 1.7    │
│ 15 │ Aceite de Oliva  │ Cocina    │ 4.5    │
│ 16 │ Café             │ Bebidas   │ 5.0    │
│ 17 │ Sopa enlatada    │ Conservas │ 2.3    │
│ 18 │ Jabón de Baño    │ Higiene   │ 1.2    │
│ 19 │ Botellas de Agua │ Bebidas   │ 1.0    │
│ 20 │ Cerveza          │ Bebidas   │ 3.8    │
└────┴──────────────────┴───────────┴────────┘
```

- **Obtener la cantidad total de productos vendidos en todas las fechas.**

``` sql
SELECT SUM(cantidad) as cantidad_total_productos
FROM Ventas;
```

**Resultado**

``` sql
┌──────────────────────────┐
│ cantidad_total_productos │
├──────────────────────────┤
│ 43                       │
└──────────────────────────┘
```

- **Encontrar el producto más caro en cada categoría.**

``` sql
SELECT
  categoria,
  nombre AS producto_mas_caro,
  precio AS precio_mas_caro
FROM
  Productos P
WHERE
  precio = (SELECT MAX(precio) FROM Productos WHERE categoria = P.categoria);
```

**Resultado**

``` sql
┌───────────┬────────────────────┬─────────────────┐
│ categoria │ producto_mas_caro  │ precio_mas_caro │
├───────────┼────────────────────┼─────────────────┤
│ Alimentos │ Arroz              │ 2.5             │
│ Panadería │ Pan                │ 1.2             │
│ Frutas    │ Manzanas           │ 3.0             │
│ Carnes    │ Pollo              │ 5.5             │
│ Verduras  │ Tomates            │ 2.2             │
│ Lácteos   │ Queso              │ 4.0             │
│ Desayuno  │ Cereal             │ 3.5             │
│ Hogar     │ Papel Higiénico    │ 1.5             │
│ Higiene   │ Cepillo de Dientes │ 2.0             │
│ Limpieza  │ Detergente         │ 2.8             │
│ Snacks    │ Galletas           │ 1.7             │
│ Cocina    │ Aceite de Oliva    │ 4.5             │
│ Bebidas   │ Café               │ 5.0             │
│ Conservas │ Sopa enlatada      │ 2.3             │
└───────────┴────────────────────┴─────────────────┘
```

- **Listar los productos que no han sido vendidos.**

``` sql
SELECT
  productos.*
FROM
  productos
LEFT JOIN
  ventas ON productos.id = ventas.id_producto
WHERE
  ventas.id_producto IS NULL;
```

**Resultado**

``` sql
┌────┬────────────────────┬───────────┬────────┐
│ id │       nombre       │ categoria │ precio │
├────┼────────────────────┼───────────┼────────┤
│ 3  │ Pan                │ Panadería │ 1.2    │
│ 7  │ Yogurt             │ Lácteos   │ 2.0    │
│ 9  │ Queso              │ Lácteos   │ 4.0    │
│ 11 │ Papel Higiénico    │ Hogar     │ 1.5    │
│ 12 │ Cepillo de Dientes │ Higiene   │ 2.0    │
│ 13 │ Detergente         │ Limpieza  │ 2.8    │
│ 15 │ Aceite de Oliva    │ Cocina    │ 4.5    │
│ 17 │ Sopa enlatada      │ Conservas │ 2.3    │
│ 19 │ Botellas de Agua   │ Bebidas   │ 1.0    │
│ 20 │ Cerveza            │ Bebidas   │ 3.8    │
└────┴────────────────────┴───────────┴────────┘
```

- **Calcular el precio promedio de los productos en la categoría "Snacks".**

``` sql
SELECT AVG(precio) AS precio_promedio_snacks
FROM productos
WHERE categoria = 'Snacks';
```

**Resultado**

``` sql
┌────────────────────────┐
│ precio_promedio_snacks │
├────────────────────────┤
│ 1.7                    │
└────────────────────────┘
```

- **Mostrar la fecha y la cantidad de ventas para cada producto.**

``` sql
SELECT
  productos.*,
  ventas.fecha,
  COUNT(ventas.id) AS cantidad_ventas
FROM
  productos
JOIN
  ventas ON productos.id = ventas.id_producto
GROUP BY
  productos.id, ventas.fecha;
```

**Resultado**

``` sql
┌────┬───────────────┬───────────┬────────┬────────────┬─────────────────┐
│ id │    nombre     │ categoria │ precio │   fecha    │ cantidad_ventas │
├────┼───────────────┼───────────┼────────┼────────────┼─────────────────┤
│ 1  │ Arroz         │ Alimentos │ 2.5    │ 2024-01-17 │ 1               │
│ 2  │ Leche         │ Lácteos   │ 1.8    │ 2024-01-17 │ 1               │
│ 4  │ Manzanas      │ Frutas    │ 3.0    │ 2024-01-17 │ 1               │
│ 5  │ Pollo         │ Carnes    │ 5.5    │ 2024-01-17 │ 1               │
│ 6  │ Huevos        │ Lácteos   │ 1.0    │ 2024-01-18 │ 1               │
│ 8  │ Tomates       │ Verduras  │ 2.2    │ 2024-01-18 │ 1               │
│ 10 │ Cereal        │ Desayuno  │ 3.5    │ 2024-01-18 │ 1               │
│ 14 │ Galletas      │ Snacks    │ 1.7    │ 2024-01-19 │ 1               │
│ 16 │ Café          │ Bebidas   │ 5.0    │ 2024-01-19 │ 1               │
│ 18 │ Jabón de Baño │ Higiene   │ 1.2    │ 2024-01-20 │ 1               │
└────┴───────────────┴───────────┴────────┴────────────┴─────────────────┘
```

- **Encontrar los productos que tienen un precio menor o igual a 2.**

``` sql
SELECT *
FROM productos
WHERE precio <= 2;
```

**Resultado**

``` sql
┌────┬────────────────────┬───────────┬────────┐
│ id │       nombre       │ categoria │ precio │
├────┼────────────────────┼───────────┼────────┤
│ 2  │ Leche              │ Lácteos   │ 1.8    │
│ 3  │ Pan                │ Panadería │ 1.2    │
│ 6  │ Huevos             │ Lácteos   │ 1.0    │
│ 7  │ Yogurt             │ Lácteos   │ 2.0    │
│ 11 │ Papel Higiénico    │ Hogar     │ 1.5    │
│ 12 │ Cepillo de Dientes │ Higiene   │ 2.0    │
│ 14 │ Galletas           │ Snacks    │ 1.7    │
│ 18 │ Jabón de Baño      │ Higiene   │ 1.2    │
│ 19 │ Botellas de Agua   │ Bebidas   │ 1.0    │
└────┴────────────────────┴───────────┴────────┘
```

- **Calcular la cantidad total de ventas para cada fecha.**

``` sql
SELECT
  fecha,
  COUNT(id) AS cantidad_total_ventas
FROM
  ventas
GROUP BY
  fecha;
```

**Resultado**

``` sql
┌────────────┬───────────────────────┐
│   fecha    │ cantidad_total_ventas │
├────────────┼───────────────────────┤
│ 2024-01-17 │ 4                     │
│ 2024-01-18 │ 3                     │
│ 2024-01-19 │ 2                     │
│ 2024-01-20 │ 1                     │
└────────────┴───────────────────────┘
```

- **Listar los productos cuyo nombre comienza con la letra 'P'.**

``` sql
SELECT *
FROM productos
WHERE nombre LIKE 'P%';
```

**Resultado**

``` sql
┌────┬─────────────────┬───────────┬────────┐
│ id │     nombre      │ categoria │ precio │
├────┼─────────────────┼───────────┼────────┤
│ 3  │ Pan             │ Panadería │ 1.2    │
│ 5  │ Pollo           │ Carnes    │ 5.5    │
│ 11 │ Papel Higiénico │ Hogar     │ 1.5    │
└────┴─────────────────┴───────────┴────────┘
```

- **Obtener el producto más vendido en términos de cantidad.**

``` sql
SELECT
  productos.*,
  SUM(ventas.cantidad) AS cantidad_total_vendida
FROM
  productos
JOIN
  ventas ON productos.id = ventas.id_producto
GROUP BY
  productos.id
ORDER BY
  cantidad_total_vendida DESC
LIMIT 1;
```

**Resultado**

``` sql
┌────┬────────┬───────────┬────────┬────────────────────────┐
│ id │ nombre │ categoria │ precio │ cantidad_total_vendida │
├────┼────────┼───────────┼────────┼────────────────────────┤
│ 6  │ Huevos │ Lácteos   │ 1.0    │ 10                     │
└────┴────────┴───────────┴────────┴────────────────────────┘
```

- **Mostrar los productos que fueron vendidos en la fecha '2024-01-18'.**

``` sql
SELECT
  productos.*,
  ventas.fecha,
  ventas.cantidad
FROM
  productos
JOIN
  ventas ON productos.id = ventas.id_producto
WHERE
  ventas.fecha = '2024-01-18';
```

**Resultado**

``` sql
┌────┬─────────┬───────────┬────────┬────────────┬──────────┐
│ id │ nombre  │ categoria │ precio │   fecha    │ cantidad │
├────┼─────────┼───────────┼────────┼────────────┼──────────┤
│ 6  │ Huevos  │ Lácteos   │ 1.0    │ 2024-01-18 │ 10       │
│ 8  │ Tomates │ Verduras  │ 2.2    │ 2024-01-18 │ 4        │
│ 10 │ Cereal  │ Desayuno  │ 3.5    │ 2024-01-18 │ 2        │
└────┴─────────┴───────────┴────────┴────────────┴──────────┘
```

- **Calcular el total de ventas para cada producto.**

``` sql
SELECT
  productos.*,
  SUM(ventas.cantidad) AS total_ventas
FROM
  productos
LEFT JOIN
  ventas ON productos.id = ventas.id_producto
GROUP BY
  productos.id;
```

**Resultado**

``` sql
┌────┬────────────────────┬───────────┬────────┬──────────────┐
│ id │       nombre       │ categoria │ precio │ total_ventas │
├────┼────────────────────┼───────────┼────────┼──────────────┤
│ 1  │ Arroz              │ Alimentos │ 2.5    │ 5            │
│ 2  │ Leche              │ Lácteos   │ 1.8    │ 3            │
│ 3  │ Pan                │ Panadería │ 1.2    │              │
│ 4  │ Manzanas           │ Frutas    │ 3.0    │ 2            │
│ 5  │ Pollo              │ Carnes    │ 5.5    │ 1            │
│ 6  │ Huevos             │ Lácteos   │ 1.0    │ 10           │
│ 7  │ Yogurt             │ Lácteos   │ 2.0    │              │
│ 8  │ Tomates            │ Verduras  │ 2.2    │ 4            │
│ 9  │ Queso              │ Lácteos   │ 4.0    │              │
│ 10 │ Cereal             │ Desayuno  │ 3.5    │ 2            │
│ 11 │ Papel Higiénico    │ Hogar     │ 1.5    │              │
│ 12 │ Cepillo de Dientes │ Higiene   │ 2.0    │              │
│ 13 │ Detergente         │ Limpieza  │ 2.8    │              │
│ 14 │ Galletas           │ Snacks    │ 1.7    │ 7            │
│ 15 │ Aceite de Oliva    │ Cocina    │ 4.5    │              │
│ 16 │ Café               │ Bebidas   │ 5.0    │ 3            │
│ 17 │ Sopa enlatada      │ Conservas │ 2.3    │              │
│ 18 │ Jabón de Baño      │ Higiene   │ 1.2    │ 6            │
│ 19 │ Botellas de Agua   │ Bebidas   │ 1.0    │              │
│ 20 │ Cerveza            │ Bebidas   │ 3.8    │              │
└────┴────────────────────┴───────────┴────────┴──────────────┘
```

- **Encontrar los productos con un precio entre 3 y 4.**

``` sql
SELECT *
FROM productos
WHERE precio BETWEEN 3 AND 4;
```

**Resultado**

``` sql
┌────┬──────────┬───────────┬────────┐
│ id │  nombre  │ categoria │ precio │
├────┼──────────┼───────────┼────────┤
│ 4  │ Manzanas │ Frutas    │ 3.0    │
│ 9  │ Queso    │ Lácteos   │ 4.0    │
│ 10 │ Cereal   │ Desayuno  │ 3.5    │
│ 20 │ Cerveza  │ Bebidas   │ 3.8    │
└────┴──────────┴───────────┴────────┘
```

- **Listar los productos y sus categorías ordenados alfabéticamente por categoría.**

``` sql
SELECT
  nombre AS producto,
  categoria
FROM
  productos
ORDER BY
  categoria ASC, nombre ASC;
```

**Resultado**

``` sql
┌────────────────────┬───────────┐
│      producto      │ categoria │
├────────────────────┼───────────┤
│ Arroz              │ Alimentos │
│ Botellas de Agua   │ Bebidas   │
│ Café               │ Bebidas   │
│ Cerveza            │ Bebidas   │
│ Pollo              │ Carnes    │
│ Aceite de Oliva    │ Cocina    │
│ Sopa enlatada      │ Conservas │
│ Cereal             │ Desayuno  │
│ Manzanas           │ Frutas    │
│ Cepillo de Dientes │ Higiene   │
│ Jabón de Baño      │ Higiene   │
│ Papel Higiénico    │ Hogar     │
│ Detergente         │ Limpieza  │
│ Huevos             │ Lácteos   │
│ Leche              │ Lácteos   │
│ Queso              │ Lácteos   │
│ Yogurt             │ Lácteos   │
│ Pan                │ Panadería │
│ Galletas           │ Snacks    │
│ Tomates            │ Verduras  │
└────────────────────┴───────────┘
```

- **Calcular el precio total de los productos vendidos en la fecha '2024-01-19'.**

``` sql
SELECT
  SUM(productos.precio * ventas.cantidad) AS precio_total
FROM
  productos
JOIN
  ventas ON productos.id = ventas.id_producto
WHERE
  ventas.fecha = '2024-01-19';
```

**Resultado**

``` sql
┌──────────────┐
│ precio_total │
├──────────────┤
│ 26.9         │
└──────────────┘
```

- **Mostrar los productos que no pertenecen a la categoría "Higiene".**

``` sql
SELECT *
FROM productos
WHERE categoria <> 'Higiene';
```

**Resultado**

``` sql
┌────┬──────────────────┬───────────┬────────┐
│ id │      nombre      │ categoria │ precio │
├────┼──────────────────┼───────────┼────────┤
│ 1  │ Arroz            │ Alimentos │ 2.5    │
│ 2  │ Leche            │ Lácteos   │ 1.8    │
│ 3  │ Pan              │ Panadería │ 1.2    │
│ 4  │ Manzanas         │ Frutas    │ 3.0    │
│ 5  │ Pollo            │ Carnes    │ 5.5    │
│ 6  │ Huevos           │ Lácteos   │ 1.0    │
│ 7  │ Yogurt           │ Lácteos   │ 2.0    │
│ 8  │ Tomates          │ Verduras  │ 2.2    │
│ 9  │ Queso            │ Lácteos   │ 4.0    │
│ 10 │ Cereal           │ Desayuno  │ 3.5    │
│ 11 │ Papel Higiénico  │ Hogar     │ 1.5    │
│ 13 │ Detergente       │ Limpieza  │ 2.8    │
│ 14 │ Galletas         │ Snacks    │ 1.7    │
│ 15 │ Aceite de Oliva  │ Cocina    │ 4.5    │
│ 16 │ Café             │ Bebidas   │ 5.0    │
│ 17 │ Sopa enlatada    │ Conservas │ 2.3    │
│ 19 │ Botellas de Agua │ Bebidas   │ 1.0    │
│ 20 │ Cerveza          │ Bebidas   │ 3.8    │
└────┴──────────────────┴───────────┴────────┘
```

- **Encontrar la cantidad total de productos en cada categoría.**

``` sql
SELECT
  categoria,
  COUNT(*) AS cantidad_total
FROM
  productos
GROUP BY
  categoria;
```

**Resultado**

``` sql
┌───────────┬────────────────┐
│ categoria │ cantidad_total │
├───────────┼────────────────┤
│ Alimentos │ 1              │
│ Bebidas   │ 3              │
│ Carnes    │ 1              │
│ Cocina    │ 1              │
│ Conservas │ 1              │
│ Desayuno  │ 1              │
│ Frutas    │ 1              │
│ Higiene   │ 2              │
│ Hogar     │ 1              │
│ Limpieza  │ 1              │
│ Lácteos   │ 4              │
│ Panadería │ 1              │
│ Snacks    │ 1              │
│ Verduras  │ 1              │
└───────────┴────────────────┘
```

- **Calcular el precio total de los productos vendidos en cada fecha.**

``` sql
SELECT
  ventas.fecha,
  SUM(productos.precio * ventas.cantidad) AS precio_total
FROM
  ventas
JOIN
  productos ON ventas.id_producto = productos.id
GROUP BY
  ventas.fecha;
```

**Resultado**

``` sql
┌────────────┬──────────────┐
│   fecha    │ precio_total │
├────────────┼──────────────┤
│ 2024-01-17 │ 29.4         │
│ 2024-01-18 │ 25.8         │
│ 2024-01-19 │ 26.9         │
│ 2024-01-20 │ 7.2          │
└────────────┴──────────────┘
```

- **Mostrar los productos con un nombre que termina con la letra 'o'.**

``` sql
SELECT *
FROM productos
WHERE nombre LIKE '%o';
```

**Resultado**

``` sql 
┌────┬─────────────────┬───────────┬────────┐
│ id │     nombre      │ categoria │ precio │
├────┼─────────────────┼───────────┼────────┤
│ 5  │ Pollo           │ Carnes    │ 5.5    │
│ 9  │ Queso           │ Lácteos   │ 4.0    │
│ 11 │ Papel Higiénico │ Hogar     │ 1.5    │
│ 18 │ Jabón de Baño   │ Higiene   │ 1.2    │
└────┴─────────────────┴───────────┴────────┘
```

- **Listar los productos cuya categoría comienza con la letra 'L'.**

``` sql
SELECT *
FROM productos
WHERE categoria LIKE 'L%';
```

**Resultado**

``` sql
┌────┬────────────┬───────────┬────────┐
│ id │   nombre   │ categoria │ precio │
├────┼────────────┼───────────┼────────┤
│ 2  │ Leche      │ Lácteos   │ 1.8    │
│ 6  │ Huevos     │ Lácteos   │ 1.0    │
│ 7  │ Yogurt     │ Lácteos   │ 2.0    │
│ 9  │ Queso      │ Lácteos   │ 4.0    │
│ 13 │ Detergente │ Limpieza  │ 2.8    │
└────┴────────────┴───────────┴────────┘
```

- **Calcular el total de ventas para cada producto en la fecha '2024-01-17'.**

``` sql
SELECT
  productos.*,
  COALESCE(SUM(ventas.cantidad), 0) AS total_ventas
FROM
  productos
LEFT JOIN
  ventas ON productos.id = ventas.id_producto AND ventas.fecha = '2024-01-17'
GROUP BY
  productos.id;
```

**Resultado**

``` sql
┌────┬────────────────────┬───────────┬────────┬──────────────┐
│ id │       nombre       │ categoria │ precio │ total_ventas │
├────┼────────────────────┼───────────┼────────┼──────────────┤
│ 1  │ Arroz              │ Alimentos │ 2.5    │ 5            │
│ 2  │ Leche              │ Lácteos   │ 1.8    │ 3            │
│ 3  │ Pan                │ Panadería │ 1.2    │ 0            │
│ 4  │ Manzanas           │ Frutas    │ 3.0    │ 2            │
│ 5  │ Pollo              │ Carnes    │ 5.5    │ 1            │
│ 6  │ Huevos             │ Lácteos   │ 1.0    │ 0            │
│ 7  │ Yogurt             │ Lácteos   │ 2.0    │ 0            │
│ 8  │ Tomates            │ Verduras  │ 2.2    │ 0            │
│ 9  │ Queso              │ Lácteos   │ 4.0    │ 0            │
│ 10 │ Cereal             │ Desayuno  │ 3.5    │ 0            │
│ 11 │ Papel Higiénico    │ Hogar     │ 1.5    │ 0            │
│ 12 │ Cepillo de Dientes │ Higiene   │ 2.0    │ 0            │
│ 13 │ Detergente         │ Limpieza  │ 2.8    │ 0            │
│ 14 │ Galletas           │ Snacks    │ 1.7    │ 0            │
│ 15 │ Aceite de Oliva    │ Cocina    │ 4.5    │ 0            │
│ 16 │ Café               │ Bebidas   │ 5.0    │ 0            │
│ 17 │ Sopa enlatada      │ Conservas │ 2.3    │ 0            │
│ 18 │ Jabón de Baño      │ Higiene   │ 1.2    │ 0            │
│ 19 │ Botellas de Agua   │ Bebidas   │ 1.0    │ 0            │
│ 20 │ Cerveza            │ Bebidas   │ 3.8    │ 0            │
└────┴────────────────────┴───────────┴────────┴──────────────┘
```

- **Mostrar los productos cuyo nombre tiene al menos 5 caracteres.**

``` sql
SELECT *
FROM productos
WHERE LENGTH(nombre) >= 5;
```

**Resultado**

``` sql
┌────┬────────────────────┬───────────┬────────┐
│ id │       nombre       │ categoria │ precio │
├────┼────────────────────┼───────────┼────────┤
│ 1  │ Arroz              │ Alimentos │ 2.5    │
│ 2  │ Leche              │ Lácteos   │ 1.8    │
│ 4  │ Manzanas           │ Frutas    │ 3.0    │
│ 5  │ Pollo              │ Carnes    │ 5.5    │
│ 6  │ Huevos             │ Lácteos   │ 1.0    │
│ 7  │ Yogurt             │ Lácteos   │ 2.0    │
│ 8  │ Tomates            │ Verduras  │ 2.2    │
│ 9  │ Queso              │ Lácteos   │ 4.0    │
│ 10 │ Cereal             │ Desayuno  │ 3.5    │
│ 11 │ Papel Higiénico    │ Hogar     │ 1.5    │
│ 12 │ Cepillo de Dientes │ Higiene   │ 2.0    │
│ 13 │ Detergente         │ Limpieza  │ 2.8    │
│ 14 │ Galletas           │ Snacks    │ 1.7    │
│ 15 │ Aceite de Oliva    │ Cocina    │ 4.5    │
│ 17 │ Sopa enlatada      │ Conservas │ 2.3    │
│ 18 │ Jabón de Baño      │ Higiene   │ 1.2    │
│ 19 │ Botellas de Agua   │ Bebidas   │ 1.0    │
│ 20 │ Cerveza            │ Bebidas   │ 3.8    │
└────┴────────────────────┴───────────┴────────┘
```
