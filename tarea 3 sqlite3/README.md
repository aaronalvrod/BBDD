# Trabajo con funciones en BBDD

### ¿Que es SQLite3?

- SQLite3 es un sistema de gestión de base de datos relacional que se caracteriza por ser un motor de base de datos incorporado, ligero y de código abierto. A diferencia de otros sistemas de gestión de base de datos como MySQL, SQLite3 no funciona como un servidor independiente, sino que se implementa como una biblioteca que se vincula directamente con la  aplicación.

![SQLite3 logo](https://github.com/aaronalvrod/BBDD./assets/147527842/66e6aecb-6d3f-4a2c-b845-6059ccd59596)

---

# Pasos

# Paso 1: Creación de la BBDD

Primero creamos el fichero `empleados-dump.sql`

``` sql
vi empleados-dump.sql
```

Una vez dentro del fichero copiaremos el siguiente CREATE TABLE y los INSERT de la tabla empleados

``` sql
CREATE TABLE empleados (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    nombre TEXT,
    salario REAL,
    departamento TEXT
);

INSERT INTO empleados (nombre, salario, departamento) VALUES ('Juan', 50000, 'Ventas');
INSERT INTO empleados (nombre, salario, departamento) VALUES ('María', 60000, 'TI');
INSERT INTO empleados (nombre, salario, departamento) VALUES ('Carlos', 55000, 'Ventas');
INSERT INTO empleados (nombre, salario, departamento) VALUES ('Ana', 48000, 'Recursos Humanos');
INSERT INTO empleados (nombre, salario, departamento) VALUES ('Pedro', 70000, 'TI');
INSERT INTO empleados (nombre, salario, departamento) VALUES ('Laura', 52000, 'Ventas');
INSERT INTO empleados (nombre, salario, departamento) VALUES ('Javier', 48000, 'Recursos Humanos');
INSERT INTO empleados (nombre, salario, departamento) VALUES ('Carmen', 65000, 'TI');
INSERT INTO empleados (nombre, salario, departamento) VALUES ('Miguel', 51000, 'Ventas');
INSERT INTO empleados (nombre, salario, departamento) VALUES ('Elena', 55000, 'Recursos Humanos');
INSERT INTO empleados (nombre, salario, departamento) VALUES ('Diego', 72000, 'TI');
INSERT INTO empleados (nombre, salario, departamento) VALUES ('Sofía', 49000, 'Ventas');
INSERT INTO empleados (nombre, salario, departamento) VALUES ('Andrés', 60000, 'Recursos Humanos');
INSERT INTO empleados (nombre, salario, departamento) VALUES ('Isabel', 53000, 'TI');
INSERT INTO empleados (nombre, salario, departamento) VALUES ('Raúl', 68000, 'Ventas');
INSERT INTO empleados (nombre, salario, departamento) VALUES ('Patricia', 47000, 'Recursos Humanos');
INSERT INTO empleados (nombre, salario, departamento) VALUES ('Alejandro', 71000, 'TI');
INSERT INTO empleados (nombre, salario, departamento) VALUES ('Natalia', 54000, 'Ventas');
INSERT INTO empleados (nombre, salario, departamento) VALUES ('Roberto', 49000, 'Recursos Humanos');
INSERT INTO empleados (nombre, salario, departamento) VALUES ('Beatriz', 63000, 'TI');
```

Seguidamente de este paso crearemos el fichero de la base de datos

```sqlite3 tarea3.db```

Una vez creado el fichero de la base de datos accederemos a el y leeremos el archivo en el cual insertamos el CREATE TABLE y los INSERT de la tabla empleados.

```.read empleados-dump.sql```

Despues de realizar este paso veremos a ver si nos a leido la tabla correctamente.

Para ver si tenemos la tabla - `.tables` 

Para verificar que todos los datos han sido leidos - `select * from empleados;`

Una vez realizados estos pasos podremos observar la siguiente tabla

``` sql
┌────┬───────────┬─────────┬──────────────────┐
│ id │  nombre   │ salario │   departamento   │
├────┼───────────┼─────────┼──────────────────┤
│ 1  │ Juan      │ 50000.0 │ Ventas           │
│ 2  │ María     │ 60000.0 │ TI               │
│ 3  │ Carlos    │ 55000.0 │ Ventas           │
│ 4  │ Ana       │ 48000.0 │ Recursos Humanos │
│ 5  │ Pedro     │ 70000.0 │ TI               │
│ 6  │ Laura     │ 52000.0 │ Ventas           │
│ 7  │ Javier    │ 48000.0 │ Recursos Humanos │
│ 8  │ Carmen    │ 65000.0 │ TI               │
│ 9  │ Miguel    │ 51000.0 │ Ventas           │
│ 10 │ Elena     │ 55000.0 │ Recursos Humanos │
│ 11 │ Diego     │ 72000.0 │ TI               │
│ 12 │ Sofía     │ 49000.0 │ Ventas           │
│ 13 │ Andrés    │ 60000.0 │ Recursos Humanos │
│ 14 │ Isabel    │ 53000.0 │ TI               │
│ 15 │ Raúl      │ 68000.0 │ Ventas           │
│ 16 │ Patricia  │ 47000.0 │ Recursos Humanos │
│ 17 │ Alejandro │ 71000.0 │ TI               │
│ 18 │ Natalia   │ 54000.0 │ Ventas           │
│ 19 │ Roberto   │ 49000.0 │ Recursos Humanos │
│ 20 │ Beatriz   │ 63000.0 │ TI               │
└────┴───────────┴─────────┴──────────────────┘
```

### Paso 2: Lectura del fichero