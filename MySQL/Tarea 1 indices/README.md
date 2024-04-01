<div align="center">

# Tarea 1: Trabajo con índices
<img src="indices.jpeg"/>
</div>
<br>

### Un instituto de enseñanza guarda los siguientes datos de sus alumnos:

    número de inscripción, comienza desde 1 cada año,
    año de inscripción,
    nombre del alumno,
    documento del alumno,
    domicilio,
    ciudad,
    provincia,
    clave primaria: número de inscripto y año de inscripción.


**Se pide:**

**Elimine la tabla "alumno" si existe.**

*Comando*

``` sql
DROP TABLE IF EXISTS alumno;
```

*Salida*

``` sql

```

**Cree la tabla definiendo una clave primaria compuesta (año de inscripción y número de inscripción).**

*Comando*

``` sql
CREATE TABLE alumno (
    numero_inscripcion INT,
    ano_inscripcion INT,
    nombre VARCHAR(50),
    documento VARCHAR(20),
    domicilio VARCHAR(100),
    ciudad VARCHAR(50),
    provincia VARCHAR(50),
    PRIMARY KEY (ano_inscripcion, numero_inscripcion)
);
```

*Salida*

``` sql

```

**Define los siguientes indices:**

- **Un índice único por el campo "documento" y un índice común por ciudad y provincia.**

Nota:Muestra el comando y la salida. Justifica el tipo de indice en un comentario.

*Comando*

``` sql
CREATE UNIQUE INDEX idx_documento ON alumno (documento);
```
``` sql
CREATE INDEX idx_ciudad_provincia ON alumno (ciudad, provincia);
```

*Salida*

``` sql

```

``` sql

```

- **Vea los índices de la tabla.**

Nota:Muestra el comando y la salida "show index".

*Comando*

``` sql
SHOW INDEX FROM alumno;
```

*Salida*

``` sql

```

**Intente ingresar un alumno con clave primaria repetida.**

Nota:Muestra el comando y la salida.


*Comando*

``` sql
INSERT INTO alumno (numero_inscripcion, ano_inscripcion, nombre, documento, domicilio, ciudad, provincia) VALUES (1, 2024, 'Juan Perez', '12345678', 'Calle 123', 'Ciudad A', 'Provincia X');
```

*Salida*

``` sql

```

**Intente ingresar un alumno con documento repetido.**

Nota:Muestra el comando y la salida.

*Comando*

``` sql
INSERT INTO alumno (numero_inscripcion, ano_inscripcion, nombre, documento, domicilio, ciudad, provincia) VALUES (2, 2024, 'Maria Lopez', '12345678', 'Calle 456', 'Ciudad B', 'Provincia Y');
```

*Salida*

``` sql

```

**Ingrese varios alumnos de la misma ciudad y provincia.**

Nota:Muestra el comando y la salida.

*Comando*

``` sql
INSERT INTO alumno (numero_inscripcion, ano_inscripcion, nombre, documento, domicilio, ciudad, provincia) VALUES 
(3, 2024, 'Pedro Ramirez', '87654321', 'Calle 789', 'Ciudad A', 'Provincia X'),
(4, 2024, 'Ana Martinez', '98765432', 'Calle 012', 'Ciudad A', 'Provincia X');
```

*Salida*

``` sql

```

**Elimina los indices creados, y muestra que ya no se encuentran.**

Nota:Muestra el comando y la salida.

*Comando*

``` sql
DROP INDEX idx_documento ON alumno;
```
``` sql
DROP INDEX idx_ciudad_provincia ON alumno;
```
``` sql
SHOW INDEX FROM alumno;
```

*Salida*

``` sql

```
``` sql

```
``` sql

```