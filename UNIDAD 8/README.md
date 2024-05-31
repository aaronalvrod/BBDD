<div align="justify">

# Funciones en MySQL para generar Aleatoriedad

Generar datos aleatorios en MySQL puede ser útil para pruebas, demostraciones o simulaciones.

- __RAND()__. Esta función devuelve un valor de punto flotante aleatorio entre 0 y 1. Se puede usar para generar valores aleatorios en general.

```sql
SELECT RAND(); -- Genera un número aleatorio entre 0 y 1
-- Ejemplo de salida: 0.712345
```

- __RAND(N)__. Similar a RAND(), pero toma una semilla N como argumento para generar números pseudo-aleatorios.

```sql
SELECT RAND(1); -- Genera un número aleatorio basado en la semilla 1
-- Ejemplo de salida: 0.659217
```

- __RAND() con ORDER BY__. Si necesitas una lista de filas en un orden aleatorio, puedes usar RAND() junto con ORDER BY.

```sql
SELECT * FROM tabla ORDER BY RAND();
-- SELECT * FROM tabla ORDER BY RAND(); -- Ejemplo de salida: Filas de la tabla en un orden aleatorio
```

- __FLOOR(RAND() * (max - min + 1)) + min__. Esta fórmula te permite generar un número entero aleatorio dentro de un rango específico.

```sql
SELECT FLOOR(RAND() * (100 - 1 + 1)) + 1; -- Genera un número aleatorio entre 1 y 100
-- Ejemplo de salida: 42
```

- __UUID()__. Esta función genera un identificador único universal (UUID) en formato hexadecimal.

```sql
SELECT UUID(); -- Genera un UUID único
-- Ejemplo de salida: 123e4567-e89b-12d3-a456-426614174000
```

- __CONCAT() con RAND()__. Puedes usar CONCAT() junto con RAND() para generar datos aleatorios combinando valores.

```sql
SELECT CONCAT('Usuario', RAND()); -- Genera un nombre de usuario aleatorio
-- Ejemplo de salida: Usuario0.123456
```

- __SUBSTRING_INDEX(UUID(), '-', -1)__. Esta expresión toma el UUID generado por UUID() y extrae la última parte, que es la parte aleatoria. Esto puede ser útil si necesitas solo la parte aleatoria de un UUID.

```sql
SELECT SUBSTRING_INDEX(UUID(), '-', -1); -- Extrae la parte aleatoria de un UUID
-- Ejemplo de salida: 426614174000
```

</div>

<div align="justify">

# Cursores en MySQL

___En base de datos un Cursor es un mecanismo el cual nos permite procesar fila por fila el resultado de una consulta___.

>SQL es un lenguaje orientado a conjuntos. Si nosotros deseamos alterar ciertos elementos en nuestra colección tendremos que hacerlo mediante condicione. Única y exclusivamente los elementos que cumpla con dichas condiciones podrán ser alterados. ___Con los cursores podremos trabajar con cada uno de los elementos (filas) de nuestra consulta sin tener que obtener nuevos conjuntos. Esto nos permitirá ser mucho más flexibles al momento de manipular la información___.

Para nosotros poder hacer uso de un cursor será necesario seguir los siguientes pasos:

- Crear un cursor a partir de una sentencia SQL.
- Apertura del cursor.
- Acceso a datos.
- Cierre del cursor.

## Declaración del Cursor

Donde definimos el nombre del cursor y la consulta SQL SELECT que va a devolver el conjunto de resultados.

```sql
DECLARE nome_cursor CURSOR FOR 
   sentencia_SELECT;
```

> - _Indicar que para salir del bucle vamos a 'capturar' una excepción de 'no hay más datos'_. La definición de dicha captura tienen que ir después de __DECLARE__.
> - La declaración del cursor tiene que ir después de la declaración de las variables y condiciones.
> - En la sentencia __SELECT__ seleccionaremos las columnas que queremos guardar 'por cada fila' al recorrer el cursor.
> - Dentro de un __procedimiento, trigger o función__ podemos tener varios cursores, __pero todos ellos deben de tener un nombre diferente__.

### Apertira del Cursor

Para poder procesar la información que viene en el SELECT.

```sql
OPEN nombre_cursor;
```

### Lectura del Cursor

Esto se realiza con la orden __FETCH__ que permite guardar la información de una fila en variables locales y pasa a la siguiente fila del conjunto de resultados. La lectura va en un bucle que se ejecuta hasta que se terminan de leer todas las filas.

```sql
FETCH nombre_cursor INTO variable1[,variable2,...];
```

> - En la parte INTO deben ir tantas variables como columnas tengamos en la sentencia SELECT.
> - Cada variable guardará el dato de la columna que venga en el SELECT, de tal forma que la primera variable guardará el dato de la primera columna, la segunda variable, el dato de la segunda columna y así sucesivamente
> - Cada variable debe estar definida con el mismo tipo de dato que la columna a la que está asociada.


### Cierre del Cursos

Para liberar de la memoria el cursor creado.

```sql
CLOSE nombre_cursor;
```

> ___(IMP)Un cursor es un recurso de programación que nos ofrecen casi todos los gestores de bases de datos relacional y consiste en la posibilidad de recorrer fila a fila un conjunto de resultados provenientes de una sentencia SELECT.___
> ___La ventaja que tiene el uso de cursores es que vamos a poder guardar en variables locales cada fila de resultados y manejar esa información como queramos (para realizar otras consultas, operaciones de INSERT, UPDATE o DELETE).___

Un cursor tiene las siguientes características:

- __Son de sólo lectura__: Sólo sirven para leer datos. Es decir, sólo podremos declarar un cursor para leer los datos que provienen de una consulta SELECT y nunca podremos modificar los datos de la tabla a través del cursor.
- __De acceso secuencial__: La información que va a procesar el cursor (_el resultado de un_ ___SELECT___) es secuencial. Vamos a recorrer fila a fila desde la primera a la última de forma secuencial, una detrás de otra y no podremos saltar a una fila cualquiera de forma directa, tendremos que pasar por todas las anteriores.
- Puede crearse dentro de un ___procedimiento, función o trigger___.

## Ejemplo.

_1.-Crear un stored procedure el cual incremente en 10 el número de páginas de cada libro (tabla libros). En consola debemos visualizar el título, el anterior número de páginas y el actual número de páginas de cada libro_.

Bien, este ejemplo nos permitirá comprender de una mejor manera el uso de cursores.

Veamos como pudiese quedar nuestro stored procedure.

```sql
DELIMITER //

DROP PROCEDURE IF EXISTS facilito_procedure//
CREATE PROCEDURE facilito_procedure()
BEGIN

  DECLARE var_id INTEGER;
  DECLARE var_paginas INTEGER;
  DECLARE var_titulo VARCHAR(255);
  DECLARE var_final INTEGER DEFAULT 0;

  DECLARE cursor1 CURSOR FOR SELECT libro_id, titulo, paginas FROM libros;

  DECLARE CONTINUE HANDLER FOR NOT FOUND SET var_final = 1;

  OPEN cursor1;

  bucle: LOOP

    FETCH cursor1 INTO var_id, var_titulo, var_paginas;

    IF var_final = 1 THEN
      LEAVE bucle;
    END IF;

    UPDATE libros SET paginas = var_paginas + 10 WHERE libro_id = var_id;

    SELECT
      var_titulo AS  'titulo',
      var_paginas AS 'Anterior',
      paginas AS 'Incremento'
      FROM libros WHERE libro_id = var_id;


  END LOOP bucle;
  CLOSE cursor1;

END//
DELIMITER ;
```

Dentro del stored procedure lo primero que hacemos es declarar todas las variables que usaremos. En este caso como trabajaremos con el título y el número de páginas de cada libro declaró tres nuevas variables: __var_id, var_paginas, var_titulo__.

Para tener un control sobre la iteración de cada uno de los elementos en la consulta declaró una cuarta variable llamada __var_final__, cuyo valor comienza en 0.

Una vez hemos declarado todas las variables procedemos a crear nuestro cursor. ___El cursor se creará a partir de una consulta SQL___. En este caso la consulta no es demasiado compleja, sin embargo, _si así lo deseamos podemos crear un cursos a partir de una consulta con joins, order, group etc.._.

Con la sentencia

```sql
DECLARE CONTINUE HANDLER FOR NOT FOUND SET var_final = 1;
```

>Indicamos que una vez todos los elementos (filas) dentro de nuestro cursor hayan sido iterados la variable var_final tomará un nuevo valor, de 0 a 1.

Para comenzar la iteración de los elementos será necesario abrir el cursor.

```sql
OPEN cursor1;
```

La iteración la logramos utilizando un __Loop__, el cual será controlado a partir de la variable __var_final__.

```sql
    IF var_final = 1 THEN
            --Si ya no existen más elementos finalizamos el ciclo.
      LEAVE bucle;
    END IF;
```

Al nosotros usar la cláusula Fetch obtenemos el elemento (fila) actual de nuestra consulta y avanzamos al siguiente elemento.

En este caso como en nuestra consulta hemos obtenido 3 columnas (id, titulo, páginas) asignamos el valor de cada una de las columnas a nuestras variables. Es importante mencionar que los valores podrán ser asignados únicamente a variables del mismo tipo, no podremos asignar un varchar a una variable de tipo integer.

El orden es importante.

```sql
FETCH cursor1 INTO var_id, var_titulo, var_paginas;
````

Una vez hemos realizado todas las tareas correspondientes y se han iterado todos los elementos (filas) el siguiente paso será cerrar el cursor.

```sql
close cursor1
```

Para ejecutar nuestro stored prcedure ejecutaremos la siguiente sentencia.

```sql
call facilito_procedure();
```

</div>

<div align="justify">

# Funciones en MySQL

Como se ha explicado, [los procedimientos](procedimientos.md) permiten tener funcionalidades del lado de la __BBDD__ (MySQL) en lugar de de procesar los datos con algún lenguaje del lado del servidor, como __PHP/Java/etc__ .Tiene la ventaja de que viaja menos información de la base de datos al servidor web, con el consiguiente aumento del rendimiento y que estas funciones harán que podamos atacar la base de datos desde cualquier otro lenguaje __.NET/Python__, como  sin tener que volver a procesar los datos otra vez.

MySQL tiene muchas funciones que podemos usar en nuestro procedimientos almacenados y consultas, pero en ocasiones podemos necesitar crear nuestras propias funciones para hacer cosas más especializadas…

Vamos a ver cómo crear funciones en MySQL:

### Sintaxis

```sql
CREATE
    [DEFINER = { user | CURRENT_USER }]
    FUNCTION sp_name ([func_parameter[,...]])
    RETURNS type
    [characteristic ...] routine_body

func_parameter:
    param_name type

type:
    Any valid MySQL data type

characteristic:
    COMMENT 'string'
  | LANGUAGE SQL
  | [NOT] DETERMINISTIC
  | { CONTAINS SQL | NO SQL | READS SQL DATA | MODIFIES SQL DATA }
  | SQL SECURITY { DEFINER | INVOKER }

routine_body:
    Valid SQL routine statement
```

### Características de la función

Después de la definición del tipo de dato que devolverá la función con la palabra reservada RETURNS, tenemos que indicar las características de la función. Las opciones disponibles son las siguientes:

- __DETERMINISTIC__: Indica que la función siempre devuelve el mismo resultado cuando se utilizan los mismos parámetros de entrada.
- __NOT DETERMINISTIC__: Indica que la función no siempre devuelve el mismo resultado, aunque se utilicen los mismos parámetros de entrada. Esta es la opción que se selecciona por defecto cuando no se indica una característica de forma explícita.
- __CONTAINS SQL__: Indica que la función contiene sentencias SQL, pero no contiene sentencias de manipulación de datos. Algunos ejemplos de sentencias SQL que pueden aparecer en este caso son operaciones con variables _(Ej: SET @x = 1)_ o uso de funciones de MySQL _(Ej: SELECT NOW();)_ entre otras. Pero en ningún caso aparecerán sentencias de escritura o lectura de datos.
- __NO SQL__: Indica que la función no contiene sentencias SQL.
- __READS SQL DATA__: Indica que la función no modifica los datos de la base de datos y que contiene sentencias de lectura de datos, como la sentencia SELECT.
- __MODIFIES SQL DATA__: Indica que la función sí modifica los datos de la base de datos y que contiene sentencias como _INSERT, UPDATE o DELETE_.

Para poder crear una función en MySQL es necesario indicar al menos una de estas tres características:
- DETERMINISTIC
- NO SQL
- READS SQL DATA

Si no se indica al menos una de estas características obtendremos el siguiente mensaje de error.

```sql
ERROR 1418 (HY000): This function has none of DETERMINISTIC, NO SQL,
or READS SQL DATA in its declaration and binary logging is enabled
(you *might* want to use the less safe log_bin_trust_function_creators variable)
```

Es posible configurar el valor de la varible global log_bin_trust_function_creators a 1, para indicar a MySQL que queremos eliminar la restricción de indicar alguna de las características anteriores cuando definimos una función almacenada. Esta variable está configurada con el valor 0 por defecto y para poder modificarla es necesario contar con el privilegio SUPER.

```sql
SET GLOBAL log_bin_trust_function_creators = 1;
```

En lugar de configurar la variable global en tiempo de ejecución, es posible modificarla en el archivo de configuración de MySQL.


Puede encontrar más información en la [documentación oficial de MySQL](https://dev.mysql.com/doc/refman/8.0/en/create-procedure.html).

__Un ejemplo__:


```sql
DELIMITER //

CREATE FUCNTION holaMundo() RETURNS VARCHAR(20)
BEGIN
    RETURN ‘HolaMundo!!’;
END
//
```

Para comprobar que funciona lanzamos el siguiente comando en la consola de MySQL :

```sql
Select holaMundo();
```

El resultado será similar al siguiente:

```sql
mysql> select holaMundo()//

+--------------+
| holaMundo()  |
+--------------+
| Hola Mundo!! |
+--------------+
1 row in set (0.00 sec)
```

Para borrar una función que hayamos creado debemos lanzar el siguiente comando:

```sql
DROP FUNCTION IF EXISTS holaMundo
```

## Uso de las variables en funciones:

Las variables en las funciones se usan de igual manera que en los [procedimientos almacenados](procedimientos.md), se declaran con la sentencia __DECLARE__, y se asignan valores con la sentencia __SET__.

```sql
DELIMITER //

CREATE FUNCTION holaMundo() RETURNS VARCHAR(30)
BEGIN
  DECLARE salida VARCHAR(30) DEFAULT 'Hola mundo';
;
  SET salida = ‘Hola mundo con variables’;
  RETURN salida;
END
//
```

Esta variable es de ámbito local, y será destruida una vez finalice la función. Cabe destacar el uso de la sentencia __DEFAULT__ en conjunto con DECLARE, que asigna un valor por defecto al declarar la variable.

> __Nota__: Realiza el siguiente ejercicio. Crea la función, previa eliminación si existe, y realiza la llamada. ¿Qué resultado obtienes?

## Uso de parámetros en funciones:

```sql
DELIMITER // -- se crea el delimitador
DROP FUNCTION IF EXISTS holaMundo//

CREATE FUNCTION holaMundo(entrada VARCHAR(20)) RETURNS VARCHAR(20)
BEGIN
  DECLARE salida VARCHAR(20);
  SET salida = entrada;
  RETURN salida;
END

//-- se cierra el delimitador
```
Ahora hemos creado una función que devuelve el mismo valor que le pasamos como parámetro.

Si tecleamos :

```sql
mysql> select holaMundo("que buen profesor tengo ;)")//
+---------------------------+
| holaMundo("que buen profesor tengo ;)") |
+---------------------------+
| que buen profesor tengo ;)             |
+---------------------------+
1 row in set (0.00 sec)
```

> __Nota__: Obtenemos como resultado lo mismo que le hemos pasado como párametro.

Vamos a crear una función que acepte un __dividendo__ y un __divisor__ y haga una división sin usar el operador división:

```sql
delimiter // -- comienzo del delimitador
DROP FUNCTION IF EXISTS divide//
create function divide(dividendo int,divisor int) returns int
begin
    declare aux int; -- declaracion de la variable aux
    declare contador int;-- declaracion de la variable contador
    declare resto int; -- declaracion de la variable resto
    set contador = 0;
    set aux = 0;
    while (aux + divisor) <= dividendo do
        set aux = aux + divisor ;
        set contador = contador + 1;
    end while;
    set resto = dividendo - aux ;
    return contador;
end
// -- finalizacion del delimitador
```

> __Nota__: Como podemos observar podemos hacer uso de las mismas estructuras que se han descrito en [los procedimientos](procedimientos.md).

Simplemente llamaríamos a la función así:

```sql
SELECT divide(20,2)
```

Lo que devolvería __10__.

## Documentación y ejemplos
- [Ejemplos funciones](https://www.mysqltutorial.org/mysql-stored-function/).
- [Funciones en MySql](https://dev.mysql.com/doc/refman/8.0/en/create-procedure.html).


</div>

<div align="justify">

# Procedimientos en MySQL

En esta unidad vamos a estudiar los procedimientos que son objetos que contienen código SQL y se almacenan asociados a una base de datos. El resumen sería:

- __Procedimiento almacenado__: Es un objeto que se crea con la sentencia __CREATE PROCEDURE__ y se invoca con la sentencia __CALL__. Un procedimiento puede tener cero o muchos parámetros de entrada y cero o muchos parámetros de salida.

## Procedimientos

Un procedimiento almacenado es un __conjunto de instrucciones SQL__ que se almacena asociado a una base de datos. Es un objeto que se crea con la sentencia CREATE PROCEDURE y se invoca con la sentencia __CALL__. Un procedimiento puede tener ___cero o muchos parámetros de entrada___ y ___cero o muchos parámetros de salida___.

### Sintaxis

```sql
CREATE
    [DEFINER = { user | CURRENT_USER }]
    PROCEDURE sp_name ([proc_parameter[,...]])
    [characteristic ...] routine_body

proc_parameter:
    [ IN | OUT | INOUT ] param_name type

func_parameter:
    param_name type

type:
    Any valid MySQL data type

characteristic:
    COMMENT 'string'
  | LANGUAGE SQL
  | [NOT] DETERMINISTIC
  | { CONTAINS SQL | NO SQL | READS SQL DATA | MODIFIES SQL DATA }
  | SQL SECURITY { DEFINER | INVOKER }

routine_body:
    Valid SQL routine statement
```

Nota > Puede encontrar más información en la [documentación oficial de MySQL](https://dev.mysql.com/doc/refman/8.0/en/create-procedure.html).

### DELIMITER

Para definir un procedimiento almacenado es necesario modificar temporalmente el carácter separador que se utiliza para delimitar las sentencias SQL.

El carácter separador que se utiliza por defecto en SQL es el punto y coma __(;)__. En los ejemplos que vamos a realizar en esta unidad vamos a utilizar los caracteres __$$__ para delimitar las instrucciones SQL, __pero es posible utilizar cualquier otro carácter__.

__Ejemplo__:

En este ejemplo estamos configurando los caracteres __$$__ como los separadores entre las sentencias SQL.

```sql
DELIMITER $$ -- comienzo del delimitador
```

__Ejemplo__:

En este ejemplo volvemos a configurar que el carácter separador es el punto y coma.

```sql
DELIMITER ;  -- comienzo del delimitador
```

### Uniendo Todo

Si unimos todo lo visto hasta ahora tendríamos:

```sql
DELIMITER // -- comienzo del delimitador
CREATE PROCEDURE nombre_procedimiento
BEGIN
  /* CODIGO EN SQL A EJECUTAR */
END //  -- fin del delimitador
```

Un ejemplo simple de un procedimiento:

```sql
DELIMITER // -- comienzo del delimitador
CREATE PROCEDURE total_paises
BEGIN
  SELECT COUNT(*)
  FROM pais
END // -- fin del delimitador
```

### Parámetros de entrada, salida y entrada/salida

En los procedimientos almacenados podemos tener parámetros.

```sql
DELIMITER // -- comienzo del delimitador
CREATE PROCEDURE nombre_procedimiento ( TIPOPARAMETRO parametro1 TIPOVALOR, ...)
BEGIN
  /* CODIGO EN SQL A EJECUTAR */
END // -- fin del delimitador
```

Exisen tres tipos de parámetros:

- __Entrada__: Se indican poniendo la palabra reservada __IN__ delante del nombre del parámetro. ___Estos parámetros no pueden cambiar su valor dentro del procedimiento, es decir, cuando el procedimiento finalice estos parámetros tendrán el mismo valor que tenían cuando se hizo la llamada al procedimiento___. En programación sería equivalente al _paso por valor de un parámetro_.
- __Salida__: Se indican poniendo la palabra reservada __OUT__ delante del nombre del parametro. Estos parámetros cambian su valor dentro del procedimiento. Cuando se hace la llamada al procedimiento empiezan con un valor inicial y cuando finaliza la ejecución del procedimiento pueden terminar con otro valor diferente. En programación sería equivalente al paso por referencia de un parámetro.
- __Entrada/Salida__: Es una combinación de los tipos __IN y OUT__. Estos parámetros se indican poniendo la palabra reservada IN/OUT delante del nombre del parámetro.

__Ejemplo__:

_En este ejemplo, se muestra la cabecera de un procedimiento llamado___ __listar_productos__ _que sólo tiene el parámetro gama que es de entrada (IN)_.

```sql
CREATE PROCEDURE listar_productos(IN gama VARCHAR(50))
```

__Ejemplo__:

_Aquí se muestra la cabecera de un procedimiento llamado_ ___contar_productos___ _que tiene el parámetro gama de entrada (IN) y el parámetro total de salida (OUT)_.

```sql
CREATE PROCEDURE contar_productos(IN gama VARCHAR(50), OUT total INT UNSIGNED)
```

__Ejemplo de un procedimiento con parámetros de entrada___

_Escriba un procedimiento llamado_ ___listar_productos___ _que reciba como entrada el nombre de la gama y muestre un listado de todos los productos que existen dentro de esa gama. Este procedimiento no devuelve ningún parámetro de salida, lo que hace es mostrar el listado de los productos_.

```sql
DELIMITER $$ -- comienzo del delimitador
DROP PROCEDURE IF EXISTS listar_productos$$ -- eliminamos el procedimiento si existiera
CREATE PROCEDURE listar_productos(IN gama VARCHAR(50))
BEGIN
  SELECT *
  FROM producto
  WHERE producto.gama = gama;
END
$$ -- fin del delimitador
```

El ejemplo anterior sería:

```sql
DELIMITER // -- comienzo del delimitador
CREATE PROCEDURE total_paises_nombrados_como
(IN palabra CHAR(20))
BEGIN
  SELECT COUNT(*) FROM pais
  WHERE nombre LIKE palabra;
END // -- fin del delimitador
```

### Llamada de procedimientos con CALL

Para hacer la llamada a un procedimiento almacenado se utiliza la palabra reservada __CALL__.

__Ejemplo__:

```sql
DELIMITER // -- comienzo del delimitador
CREATE PROCEDURE total_paises_nombrados_como
(IN palabra CHAR(20))
BEGIN
  SELECT COUNT(*) FROM pais
  WHERE nombre LIKE palabra;
END // -- fin del delimitador


CALL total_paises_nombrados_como('españa');
/* devolvería el resultado de la consulta */
```

### Ejemplos de procedimientos con parámetros de salida

__Ejemplo__:

_Escriba un procedimiento llamado_ ___contar_productos___ _que reciba como entrada el nombre de la gama y devuelva el número de productos que existen dentro de esa gama. Resuelva el ejercicio de dos formas distintas, utilizando SET y SELECT ... INTO._

__Solución 1. Utilizando SET__

```sql
DELIMITER $$ -- comienzo del delimitador
DROP PROCEDURE IF EXISTS contar_productos$$
CREATE PROCEDURE contar_productos(IN gama VARCHAR(50), OUT total INT UNSIGNED)
BEGIN
  SET total = ( -- Estamos asignando a la variable total el resultado
    SELECT COUNT(*) 
    FROM producto 
    WHERE producto.gama = gama);
END

$$ -- fin del delimitador

DELIMITER ; -- comienzo del delimitador
CALL contar_productos('Herramientas', @total);
SELECT @total;-- fin del delimitador
```

__Solución 2. Utilizando SELECT ... INTO__

```sql
DELIMITER $$
DROP PROCEDURE IF EXISTS contar_productos$$
CREATE PROCEDURE contar_productos(IN gama VARCHAR(50), OUT total INT UNSIGNED)
BEGIN
  SELECT COUNT(*) 
  INTO total -- almacenamos el valor del count en la variables total
  FROM producto 
  WHERE producto.gama = gama;
END
$$ -- fin del delimitador

DELIMITER ; -- comienzo del delimitador
CALL contar_productos('Herramientas', @total);
SELECT @total; -- fin del delimitador
```

__Ejemplo:__

_Escribe un procedimiento que se llame_ ___calcular_max_min_media__, _que reciba como parámetro de entrada el nombre de la gama de un producto y devuelva como salida tres parámetros. El precio máximo, el precio mínimo y la media de los productos que existen en esa gama. Resuelva el ejercicio de dos formas distintas, utilizando_ ___SET y SELECT ... INTO___.

__Solucioń 1. Utilizando SET__

```sql
DELIMITER $$ -- comienzo del delimitador
DROP PROCEDURE IF EXISTS calcular_max_min_media$$
CREATE PROCEDURE calcular_max_min_media(
  IN gama VARCHAR(50),
    OUT maximo DECIMAL(15, 2),
        OUT minimo DECIMAL(15, 2),
            OUT media DECIMAL(15, 2)
)
BEGIN
  SET maximo = (
    SELECT MAX(precio_venta)
    FROM producto
        WHERE producto.gama = gama);
  
  SET minimo = (
    SELECT MIN(precio_venta)
    FROM producto
        WHERE producto.gama = gama);
  
  SET media = (
    SELECT AVG(precio_venta)
    FROM producto
        WHERE producto.gama = gama);
END
$$ -- fin del delimitador

DELIMITER ; -- comienzo del delimitador
CALL calcular_max_min_media('Herramientas', @maximo, @minimo, @media);
SELECT @maximo, @minimo, @media; -- fin del delimitador
```

__Solucioń 2. Utilizando SELECT ... INTO__

```sql
DELIMITER $$ -- comienzo del delimitador
DROP PROCEDURE IF EXISTS calcular_max_min_media$$
CREATE PROCEDURE calcular_max_min_media(
  IN gama VARCHAR(50),
    OUT maximo DECIMAL(15, 2),
        OUT minimo DECIMAL(15, 2),
            OUT media DECIMAL(15, 2)
)
BEGIN
  SELECT 
    MAX(precio_venta),
    MIN(precio_venta),
    AVG(precio_venta)
    FROM producto
  WHERE producto.gama = gama
    INTO maximo, minimo, media;
END
$$ -- fin del delimitador

DELIMITER ; -- comienzo del delimitador
CALL calcular_max_min_media('Herramientas', @maximo, @minimo, @media);
SELECT @maximo, @minimo, @media; -- obtenemos los valores de las variables obtenidas
```
## Variables Locales

Dependiendo de la complejidad de un procedimiento almacenado, MySQL nos brinda la posibilidad de definir variables para almacenar valores temporales y efectuar operaciones con los mismos.

Utilizamos la palabra clave ___'declare'___ seguida del nombre de la variable, el tipo de dato que almacena y el valor por defecto que almacena:

```sql
declare [nombre de la variable] [tipo de dato] default [valor por defecto];
```

Una variable que no define la sección del 'default' almacena por defecto null.

Un ejemplo de definir una variable:

```sql
declare total int default 100;
```

Confeccionemos un procedimiento almacenado que reciba dos enteros, defina una variable local que almacene la suma de dichos valores y seguidamente ejecute el comando select para recuperar el contenido de dicha variable local:

```sql
drop procedure if exists pa_sumar;

delimiter //
create procedure pa_sumar(
  in v1 int,
  in v2 int)
begin
  declare suma int;
  set suma=v1+v2;
  select suma;  
end //
delimiter ;

call pa_sumar(4,5);
```

Para modificar una variable utilizamos la palabra clave set:

```sql
  set suma=v1+v2;
```

## Sentencia IF

Como cualquier otro lenguaje procedimental el gestor de base de datos MySQL dispone la estructura condicional if para tomar decisiones dentro de un procedimiento almacenado.

La sintaxis de la estructura condicional if simple es:

```sql
if [condición] then
   [instrucciones]
end if;
```

La sintaxis de la estructura condicional if compuesta es:

```sql
if [condición] then
   [instrucciones]
else
   [instrucciones]
end if;
```

La sintaxis de la estructura condicional if anidada es:

```sql
if [condición] then
   [instrucciones]
elseif [condición] then
   [instrucciones]
elseif [condición] then
   [instrucciones]
elseif [condición] then
   [instrucciones]
......
else
   [instrucciones]
end if;
```

Confeccionaremos un procedimiento almacenado que muestre el mayor de 2 enteros que le pasamos como parámetro:

```sql
drop procedure if exists pa_mayor;

delimiter //
create procedure pa_mayor(
  in valor1 int,
  in valor2 int)
begin
  if valor1>valor2 then
    select valor1;
  else
    select valor2;
  end if;
end //
delimiter ;

call pa_mayor(20, 400);
```

Podemos utilizar operadores lógicos en una condición de un if, crearemos un nuevo procedimiento almacenado que muestre el mayor de 3 enteros:

```sql
drop procedure if exists pa_mayor3;

delimiter //
create procedure pa_mayor3(
  in valor1 int,
  in valor2 int,
  in valor3 int)
begin
  if valor1>valor2 and valor1>valor3 then
    select valor1;
  elseif valor2>valor3 then
    select valor2;
  else
    select valor3;
  end if;
end //
delimiter ;

call pa_mayor3(200, 40, 4000);
```

## Sentencia CASE

Otra estructura condicional disponible en MySQL es la estructura ___'case'___.

Se utiliza cuando hay múltiples condiciones y remplaza a la estructuras ___if/elseif___.

Hay dos variantes con la estructura case. Veamos la primera:

```sql
case [variable] 
  when [valor1] then
    [instrucciones1]
  when [valor2] then
    [instrucciones2]
  when [valor3] then
    [instrucciones3]
  ....
  else
    [instrucciones]
end case;
```

La estructura case simple analiza el contenido de una variable y lo compara con una serie de valores posibles, en caso que coincida con alguno de ellos ejecuta el bloque de instrucciones respectivo. _Dispone de una sección else que se ejecuta cuando la variable analizada no coincide con los valores indicados en los_ ___when___.

```sql
delimiter //
create procedure ejemploProcedimiento (in p1 int)
    begin
        declare var int ;
        set var = p1 +2 ;
        case var
            when 2 then insert into lista values (66666);
            when 3 then insert into lista values (4545665);
            else insert into lista values (77777777);
        end case;
    end;
//
```

## Estructuras Repetitivas (while)

Hemos visto en los conceptos anteriores las instrucciones de MySQL que nos permiten definir estructuras condicionales dentro de los procedimientos almacenados. Ahora veremos que comandos disponemos para repetir bloques de instrucciones.

La primer estructura repetitiva que disponemos y es común a la mayoría de los lenguajes de programación es el 'while'.

while
La sintaxis es la siguiente:

```sql
while [condición] do
  [instrucciones]
end while;
```

El ___bloque de instrucciones encerrado entre while y end while se repite mientras la condición se verifique verdadera___.

## Llamar a otro procedimiento desde un procedimiento existente

_Un procedimiento almacenado puede llamar a otro procedimiento almacenado_. El procedimiento que es invocado por otro debe existir cuando creamos el procedimiento que lo llama. Es decir, _si un procedimiento_ ___A___ _llama a otro procedimiento_ ___B___, _B debe existir al crear A_.

Creamos un procedimiento almacenado que reciba 2 números enteros y nos retorne el producto de los mismos:

```sql
drop procedure if exists pa_multiplicar;
 
delimiter // 
create procedure pa_multiplicar(
  in numero1 int,
  in numero2 int,
  out producto int)
begin
  set producto=numero1*numero2;
end // 
delimiter ;


call pa_multiplicar(20,3,@resu);

select @resu;
```

Hasta ahora hemos planteado un procedimiento almacenado y su llamada para ver si su algoritmo genera el resultado deseado.

Ahora crearemos un segundo procedimiento almacenado que nos retorne el factorial de un número que llamará al procedimiento __pa_multiplicar__:

```sql
drop procedure if exists pa_multiplicar;
 
delimiter // 
create procedure pa_multiplicar(
  in numero1 int,
  in numero2 int,
  out producto int)
begin
  set producto=numero1*numero2;
end // 
delimiter ;


drop procedure if exists pa_factorial;

delimiter // 
create procedure pa_factorial(
  in numero int,
  out resultado int)
begin  
  declare num int;
  set resultado=1;
  set num=numero;
  while num>1 do
     call pa_multiplicar(resultado,num,resultado);
     set num=num-1;
  end while;
end //    
delimiter ;

call pa_factorial(5, @resu);
select @resu;
```

El procedimiento almacenado ___pa_factorial___ en su algoritmo llama al procedimiento ___pa_multiplicar___.

## Recursividad

En MySQL podemos codificar procedimientos almacenados que se llamen en forma recursiva como ocurre en otros lenguajes de programación.

Es una característica que hay que usar con cuidado ya que puede afectar la eficiencia de nuestros algoritmos. Por defecto MySQL tiene desactiva la posibilidad de hacer llamadas recursivas.

Para activar la posibilidad de hacer llamadas recursivas debemos modificar la variable del sistema ___max_sp_recursion_depth__ indicando la cantidad de llamadas recursivas posibles:

```sql
SET @@session.max_sp_recursion_depth = 10; 
```

</div>

<div align="justify">

# Trigers en MySQL

<div align="center">
<img src="https://dinahosting.com/blog/upload/2022/04/triggers.jpg" width="500px"/>
</div>

Con la ayuda de los __triggers__ en __MySQL__ podemos conseguir automatizar acciones sin necesidad de desarrollar lógica en otros lenguajes.

___Un trigger o disparador___ es una _regla que se asocia a una tabla_. Mediante esta __regla__, _se ejecutan una serie de instrucciones cuando se producen ciertos eventos sobre una tabla_. Los eventos son: __INSERT, UPDATE o DELETE__.

_Para poder realizar triggers es necesario que tengas permisos para ejecutar esas consultas_. Además, es necesario tener una base de datos MySQL con una versión superior a la __5.0.2__.

_Las posibilidades de modificar información gracias a los triggers son infinitas_. Gracias a ellos podrás mantener tu base de datos actualizada y al día, sin preocuparte por nada más.

### Creación de triggers

Para poder realizar triggers y automatizar acciones, _necesitamos una base de datos MySQL y una tabla sobre la que realizar consultas_. Si ya poseemos esto, lo primero que necesitamos hacer es definirlo. Para ello escogemos un __nombre para identificarlo__, de manera que luego podamos borrar o buscar el trigger en nuestra base de datos. _Antes de la instrucción_ ___CREATE___ _es imprescindible declarar un_ __delimitador__.

```sql
DELIMITER $$
CREATE TRIGER nombre_trigger
```

El siguiente paso a realizar es definir cuando se va a ejecutar. Las posibilidades son __AFTER(después) o BEFORE(antes)__ (orden). Recuerda que las órdenes que aceptan triggers son __INSERT, DELETE y UPDATE__.

```sql
DELIMITER $$
CREATE TRIGGER nombre_trigger
AFTER INSERT ON nombre_tabla
```

Ahora deberíamos indicar la estructura del trigger, es decir, en donde se van a aplicar los cambios que queramos, en nuestro caso lo vamos a hacer para todas las filas __(FOR EACH ROW)__

```sql
DELIMITER $$
CREATE TRIGGER nombre_trigger
AFTER INSERT ON nombre_tabla
FOR EACH ROW
```

Por último, introducimos entre __BEGIN y END__ las líneas de código SQL que queremos ejecutar. También es necesario que cierres el delimitador definido al comienzo.

```sql
DELIMITER $$
CREATE TRIGGER nombre_trigger
AFTER INSERT ON nombre_tabla
FOR EACH ROW
BEGIN
//Instrucciones SQL
END;$$
```

>__Nota__:_Con este código, a partir de ahora, después de ejecutar un_ ___INSERT___ _en_ ___nombre_tabla___ _se ejecutarán las instrucciones declaradas dentro del_ ___BEGIN___.

Recuerda que puedes eliminar un trigger haciendo uso de la sentencia DROP TRIGGER.

```sql
DROP TRIGGER nombre_trigger;
````
## Instrucciones a emplear dentro de los triggers

Habitualmente lo que se introduce dentro de los disparadores son instrucciones condicionales, en otras palabras secuencias que se ejecutarán si se da un caso concreto, aunque no es obligatorio. Para poder manejar estas instrucciones condicionales tenemos las variables __OLD__ y __NEW__.

### Variable NEW

___NEW___ almacena el valor que aporta la consulta a la base de datos. Con esta variable podemos acceder a los datos introducidos. Con ___NEW.nombre_columna___ se _almacenará la información con el nuevo valor que tendrá ese registro modificado_ (desde un ___UPDATE___ o ___INSERT___) en la tabla. Los trigger relacionados con ___DELETE___ no tendrán disponible la variable ___NEW___.

### Variable OLD

___OLD___ a diferencia de ___NEW___, almacena el valor de las columnas que van a ser __borradas o eliminadas__. Al igual que pasa con ___NEW, OLD___ no está disponible en todas las instrucciones, más concretamente el valor no se puede recuperar cuando la instrucción es un ___INSERT___.

### Ejemplos de triggers
#### Comprobación de datos

Imaginemos que tenemos una tabla clientes en la que almacenamos su edad. Para evitar problemas en el tratamiento de los datos, queremos evitar que se introduzcan edades negativas. Podríamos hacer algo parecido a:

```sql
DELIMITER $$

CREATE TRIGGER comprobar_edad
AFTER INSERT ON cliente
FOR EACH ROW 
BEGIN
    IF NEW.edad<0
      THEN SET NEW.edad = 0;
    END IF; 
END; $$
````

Con este sencillo trigger evitaremos que en nuestra base de datos se puedan guardar edades menores a cero, de manera que podríamos omitir esta comprobación en desarrollos que hiciésemos con estos datos.

#### Realización de un histórico de productos

En este ejemplo no emplearemos una sentencia condicional. Imaginemos que tenemos una tienda online. Quizás nos interese tener una tabla en la que guardamos todos los productos que hemos tenido en nuestro catálogo en algún momento. Podríamos introducir los datos dentro del histórico siempre que introdujésemos un nuevo producto. Sin embargo, ___¿No sería más sencillo automatizar un histórico de los productos?___. Gracias a los trigger podremos realizarlo sin tener que ejecutar dos instrucciones separadas.

```sql
DELIMITER $$
CREATE TRIGGER trigger_producto_historico 
AFTER INSERT ON producto
FOR EACH ROW
BEGIN 
   INSERT INTO producto_historico(id, descripcion, precio)
   VALUES (NEW.id, NEW.descripcion, NEW.precio, CURDATE());
END; $$
```

De esta forma, cada vez que incluyamos un producto nuevo, este también se añadirá a la tabla __producto_historico__, y aunque posteriormente borremos el artículo de la tabla producto, este seguirá existiendo en __producto_historico__.

A través de los ejemplos que hemos visto, hemos descubierto que _gracias a los disparadores o triggers podemos automatizar acciones fácilmente con MySQL y mantener nuestra base de datos actualizada_. Trabajar con bases de datos es una tarea delicada, por ello. Si quieres más información sobre los Triggers y su funcionamiento, recuerda que tienes a mano la documentación de MySQL.

### Algunos ejemplos

En la base de datos __Sakila__ podemos encontrar los siguientes ejemplos:

#### Sobre la tabla actor

```sql
CREATE TRIGGER actor_trigger_ai AFTER INSERT ON actor
 BEGIN
  UPDATE actor SET last_update = DATETIME('NOW')  WHERE rowid = new.rowid;
 END
;
 
CREATE TRIGGER actor_trigger_au AFTER UPDATE ON actor
 BEGIN
  UPDATE actor SET last_update = DATETIME('NOW')  WHERE rowid = new.rowid;
 END
;
```

#### Sobre la tabla country

```sql
CREATE TRIGGER country_trigger_ai AFTER INSERT ON country
 BEGIN
  UPDATE country SET last_update = DATETIME('NOW')  WHERE rowid = new.rowid;
 END
;
 
CREATE TRIGGER country_trigger_au AFTER UPDATE ON country
 BEGIN
  UPDATE country SET last_update = DATETIME('NOW')  WHERE rowid = new.rowid;
 END
;
```

#### Sobre la tabla city

```sql
CREATE TRIGGER city_trigger_ai AFTER INSERT ON city
 BEGIN
  UPDATE city SET last_update = DATETIME('NOW')  WHERE rowid = new.rowid;
 END
;
 
CREATE TRIGGER city_trigger_au AFTER UPDATE ON city
 BEGIN
  UPDATE city SET last_update = DATETIME('NOW')  WHERE rowid = new.rowid;
 END
;
```

## Referencias.

- [Documentación Trigers](https://dev.mysql.com/doc/refman/8.0/en/triggers.html).
- [Visualizar Trigers](https://dev.mysql.com/doc/refman/8.0/en/show-triggers.html).


- [Ejemplos Trigers Sakila](https://dev.mysql.com/doc/sakila/en/sakila-structure-triggers.html
).

- [Ejemplos Trigers](https://dev.mysql.com/doc/refman/8.0/en/trigger-syntax.html
).

</div>

 <div align="justify">

# Lo Básico en Programación SQL

SQL (Structured Query Language) es un lenguaje de programación utilizado para interactuar con bases de datos relacionales. Aunque principalmente se utiliza para consultar y manipular datos, también proporciona características de programación para realizar tareas más complejas.

## 1. Declaración de Variables

Puedes declarar variables en SQL para almacenar valores temporales que se utilizan en tus consultas y procedimientos almacenados.

```sql
DECLARE @nombre_de_variable tipo_de_dato;
SET @nombre_de_variable = valor;
```

Además podemos asignar el valor a una o más variables como resultado de una consulta.

```sql
SELECT campo1, campo2, . . . INTO variable1, variable2, . . . 
FROM nombre_tabla WHERE . . .
```

Por último también podemos definir un valor por defecto a una variable:

```sql
DECLARE nombre_variable tipo_variable [DEFAULT valor];
```

## 2. Estructuras de Control de Flujo

### Condicionales (IF-ELSE)

Los condicionales __IF-ELSE__ se utilizan para ejecutar bloques de código dependiendo de una condición.

```sql
IF condición THEN
    sentencias;
ELSE
    sentencias;] . . .
END IF;
```

Un ejemplo más complejo:

```sql
IF condicion THEN
    sentencias;
[ELSEIF condicion2 THEN
    sentencias;] . . .
[ELSE 
    sentencias;]
END IF
```

### Case

```sql
CASE variable
    WHEN valor1 THEN
        sentencias;
    [WHEN valor2 THEN
        sentencias;] . . .
    [ELSE 
        sentencias;]
END CASE
 
CASE
    WHEN condicion THEN
        sentencias;
    [WHEN condicion2 THEN
        sentencias;] . . .
    [ELSE 
        sentencias;]
END CASE
```

### LOOP

Los bucles LOOP no incoporan condición de salida, sino que debe ser implementada utilizando la instrucción LEAVE

```sql
[etiqueta_inicio:] LOOP
    sentencias;
END LOOP [etiqueta_fin]
```

### LEAVE

Se utiliza para romper la ejecución de cualquier instrucción de control de flujo que se haya etiquetado, normalmente bucles __LOOP__.

```sql
LEAVE etiqueta;
```

### ITERATE

Sólo puede aparecer en instrucciones de bucle __({LOOP, REPEAT y WHILE)__. 
Indica que el bucle debe volver a ejecutarse

```sql
ITERATE etiqueta;
Sentencia REPEAT
[etiqueta_inicio:] REPEAT
    sentencias;
UNTIL condicion
END REPEAT [etiqueta_fin]
Sentencia WHILE
[etiqueta_inicio:] WHILE condicion DO
    sentencias;
END WHILE [etiqueta_fin]
```

## 3. Manejo de Errres

SQL proporciona opciones para manejar errores que pueden ocurrir durante la ejecución de consultas y procedimientos almacenados.

### Captura de Errores

Puedes utilizar bloques __TRY-CATCH__ para capturar y manejar errores.

```sql
BEGIN TRY
    -- Código que puede generar errores
END TRY
BEGIN CATCH
    -- Manejo de errores
END CATCH;
```

### Lanzamiento de Errores

Puedes lanzar errores manualmente utilizando la instrucción __THROW__.

```sql
IF condición THEN
    THROW 50000, 'Mensaje de error personalizado', 1;
END IF;

```

 </div>