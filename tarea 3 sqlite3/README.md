# Trabajo con funciones en BBDD

### ¿Que es SQLite3?

- SQLite3 es un sistema de gestión de base de datos relacional que se caracteriza por ser un motor de base de datos incorporado, ligero y de código abierto. A diferencia de otros sistemas de gestión de base de datos como MySQL, SQLite3 no funciona como un servidor independiente, sino que se implementa como una biblioteca que se vincula directamente con la  aplicación.

![SQLite3 logo](https://github.com/aaronalvrod/BBDD./assets/147527842/66e6aecb-6d3f-4a2c-b845-6059ccd59596)

---

# Pasos

### Paso 1: Creación de la BBDD

Primero creamos el fichero `empleados-dump.sql`

``` sql
vi empleados-dump.sql
```

### Paso 2: Lectura del fichero sql.

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

``` sql
sqlite3 tarea3.db
```

Una vez creado el fichero de la base de datos accederemos a el y leeremos el archivo en el cual insertamos el CREATE TABLE y los INSERT de la tabla empleados.

``` sql
.read empleados-dump.sql
```

Despues de realizar este paso veremos a ver si nos a leido la tabla correctamente.

Para ver si tenemos la tabla - `.tables` 

Para verificar que todos los datos han sido leidos - `SELECT * FROM empleados;`

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

### Paso 3: Realización de consultas

En este paso realizaremos las siguientes consultas.

- **Funciones UPPER y LOWER:**

    - Mostrar el nombre de todos los empleados en mayúscula.

```sql
 SELECT UPPER(nombre) AS nombre_mayusculas, LOWER(nombre) AS nombre_minusculas FROM empleados;
  ```
**Resultado**

``` sql
┌───────────────────┬───────────────────┐
│ nombre_mayusculas │ nombre_minusculas │
├───────────────────┼───────────────────┤
│ JUAN              │ juan              │
│ MARíA             │ maría             │
│ CARLOS            │ carlos            │
│ ANA               │ ana               │
│ PEDRO             │ pedro             │
│ LAURA             │ laura             │
│ JAVIER            │ javier            │
│ CARMEN            │ carmen            │
│ MIGUEL            │ miguel            │
│ ELENA             │ elena             │
│ DIEGO             │ diego             │
│ SOFíA             │ sofía             │
│ ANDRéS            │ andrés            │
│ ISABEL            │ isabel            │
│ RAúL              │ raúl              │
│ PATRICIA          │ patricia          │
│ ALEJANDRO         │ alejandro         │
│ NATALIA           │ natalia           │
│ ROBERTO           │ roberto           │
│ BEATRIZ           │ beatriz           │
└───────────────────┴───────────────────┘
```

- **Funciones Numéricas:**

    - Calcular el valor absoluto del salario de todos los empleados.

``` sql
SELECT salario, ABS(salario) AS valor_absoluto_salario FROM empleados;
```
**Resultado**

``` sql
┌─────────┬────────────────────────┐
│ salario │ valor_absoluto_salario │
├─────────┼────────────────────────┤
│ 50000.0 │ 50000.0                │
│ 60000.0 │ 60000.0                │
│ 55000.0 │ 55000.0                │
│ 48000.0 │ 48000.0                │
│ 70000.0 │ 70000.0                │
│ 52000.0 │ 52000.0                │
│ 48000.0 │ 48000.0                │
│ 65000.0 │ 65000.0                │
│ 51000.0 │ 51000.0                │
│ 55000.0 │ 55000.0                │
│ 72000.0 │ 72000.0                │
│ 49000.0 │ 49000.0                │
│ 60000.0 │ 60000.0                │
│ 53000.0 │ 53000.0                │
│ 68000.0 │ 68000.0                │
│ 47000.0 │ 47000.0                │
│ 71000.0 │ 71000.0                │
│ 54000.0 │ 54000.0                │
│ 49000.0 │ 49000.0                │
│ 63000.0 │ 63000.0                │
└─────────┴────────────────────────┘
```

- **Funciones de Fecha y Hora:**

    - Muestra la fecha actual.

``` sql
SELECT CURRENT_DATE AS fecha_actual FROM empleados LIMIT 1;
```

**Resultado**

``` sql
┌──────────────┐
│ fecha_actual │
├──────────────┤
│ 2024-01-17   │
└──────────────┘
```

- **Funciones de Agragación:**

    - Calcula el promedio de salarios de todos los empleados.
    - Convierte la cadena '123' a un valor entero.

``` sql
SELECT AVG(salario) AS salario_promedio FROM empleados;
```

**Resultado calcular el promedio**

``` sql
┌──────────────────┐
│ salario_promedio │
├──────────────────┤
│ 57000.0          │
└──────────────────┘
```
``` sql
SELECT CAST('123' AS INTEGER);
```

**Resultado convertir cadena '123' a valor entero**



- **Funciones de Manipulación de Cadenas:**

    - Concatena el nombre y el departamento de cada empleado.

    ``` sql
    SELECT nombre || ' - ' || departamento AS nombre_departamento FROM empleados;
    ```

- **Funciones de Manipulación de Cadenas (CONCAT_WS):**

    - Concatena el nombre y el departamento de cada empleado con un guion como separador.

    ``` sql
    SELECT CONCAT_WS(' - ', nombre, departamento) AS nombre_departamento FROM empleados;
    ```

- **Funciones de control de Flujo (CASE):**

    - Categoriza a los empleados según sus salarios.

    ``` sql
    SELECT nombre CASE WHEN salario < 50000 THEN 'Bajo' WHEN salario >= 50000 AND salario < 60000 THEN 'Medio' ELSE END AS categoria_salario FROM empleados;
    ```

- **Funciones de Agragación (SUM):**

    - Calcula la suma total de salarios de todos los empleados.

    ``` sql
    SELECT SUM(salario) FROM empleados;
    ```

- **Funciones Numéricas (ROUND):**

    - Redondea el salario de todos los empleados a dos decimales.

    ``` sql
    SELECT ROUND(salario, 2) FROM empleados;
    ```

- **Funciones de Manipulación de Cadenas (LENGTH)**

    - Muestra la longitud de cada nombre de empleado.

    ``` sql
    SELECT nombre, LENGHT(nombre) AS longitud_nombre FROM empleados;
    ```

- **Funciones de Manipulación de Cadenas (LENGHT):**

    - Muestra la longitud de cada nombre de empleado.

    ``` sql
    SELECT nombre, LENGHT(nombre) AS longitud_nombre FROM empleados;
    ```

- **Funciones de Agregación (COUNT):**

    - Cuenta el número total de empleados en cada departamento.

    ``` sql
    SELECT departamento, COUNT(*) AS num_empleados FROM empleados GROUP BY departamento;
    ```

- **Funciones de Fecha y Hora (CURRENT_TIME):**

    - Muestra la hora actual.

    ``` sql
    SELECT CURRENT_DATE;
    ```

- **Funciones de Conversión (CAST):**

    - Convierte el salario a un valor de punto flotante.

    ``` sql
    SELECT nombre, CAST(salario AS REAL) AS salario_flotante FROM empleados;    
    ```

- **Funciones de Manipulación de Cadenas (SUBSTR):**

    - Muestra los primeros tres caracteres de cada nombre de empleado.

    ``` sql
    SELECT nombre, SUBSTR(nombre, 1, 3) AS primeros_tres_caracteres FROM empleados;
    ```

- **Order By and Like**

    - Empleados en el departamento de 'Ventas' con salarios superiores a 52000

    ``` sql
    SELECT * FROM empleados WHERE departamento = 'Ventas' AND salario > 52000 ORDER BY salario DESC;
    ```

    - Empleados cuyos nombres contienen la letra 'a' y tienen salarios ordenados de manera ascendente.

    ``` sql
    SELECT * FROM empleados WHERE nombre LIKE '%a%' ORDER BY salario ASC;
    ```

    - Empleados en el departamento 'Recursos Humanos' con salarios entre 45000 y 55000.

    ``` sql
    SELECT * FROM empleados WHERE departamento = 'Recursos Humanos' AND salario BETWEEN 45000 AND 55000;
    ```

    - Empleados con salarios en orden descendente, limitando a los primeros 5 resultados.

    ``` sql
    SELECT * FROM empleados ORDER BY salario DESC LIMIT 5;
    ```

    - Empleados cuyos nombres comienzan con 'M' o 'N' y tienen salarios superiores a 50000.

    ``` sql
    SELECT * FROM empleados WHERE (nombre LIKE 'M%' OR nombre LIKE 'N%') AND salario > 50000;
    ```

    - Empleados en el departamento 'TI' o 'Ventas' ordenados alfabéticamente por nombre.

    ``` sql
    SELECT * FROM empleados WHERE departamento IN ('TI', 'Ventas') ORDER BY nombre ASC;
    ```

    - Empleados con salarios únicos (eliminando duplicados) en orden ascendente.

    ``` sql
    SELECT DISTINCT nombre, salario, departamento FROM empleados ORDER BY salario ASC;
    ```

    - Empleados cuyos nombres terminan con 'o' o 'a' y están en el departamento 'Ventas'.

    ``` sql
    SELECT * FROM empleados WHERE (nombre LIKE '%o' OR nombre LIKE '%a') AND departamento = 'Ventas';
    ```

    - Empleados con salarios fuera del rango de 55000 a 70000, ordenados por departamento.

    ``` sql
    SELECT * FROM empleados WHERE salario < 55000 OR salario > 70000 ORDER BY departamento;
    ```

    - Empleados en el departamento 'Recursos Humanos' con nombres que no contienen la letra 'e'.

    ``` sql
    SELECT * FROM empleados WHERE departamento = 'Recursos Humanos' AND nombre NOT LIKE '%e%';
    ```

    