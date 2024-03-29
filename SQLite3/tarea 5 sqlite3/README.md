# Trabajo con expresiones regulares

### Tablas

**Tabla Autor**

``` sql
┌────┬─────────────────┐
│ id │     nombre      │
├────┼─────────────────┤
│ 1  │ J.K. Rowling    │
│ 2  │ Stephen King    │
│ 3  │ George Orwell   │
│ 4  │ Jane Austen     │
│ 5  │ Agatha Christie │
└────┴─────────────────┘
```

**Tabla Libro**

``` sql
┌────────┬───────────────────────────────────┬──────────┬─────────────────────────────────────────────┬────────┐
│ codigo │              titulo               │ autor_id │                  editorial                  │ precio │
├────────┼───────────────────────────────────┼──────────┼─────────────────────────────────────────────┼────────┤
│ 1      │ The Great Gatsby                  │ 6        │ Charles Scribner's Sons                     │ 20.99  │
│ 2      │ To Kill a Mockingbird             │ 7        │ J.B. Lippincott & Co.                       │ 15.95  │
│ 3      │ The Catcher in the Rye            │ 8        │ Little, Brown and Company                   │ 18.75  │
│ 4      │ One Hundred Years of Solitude     │ 9        │ Harper & Row                                │ 22.5   │
│ 5      │ Brave New World                   │ 3        │ Chatto & Windus                             │ 17.99  │
│ 6      │ The Hobbit                        │ 10       │ George Allen & Unwin                        │ 24.99  │
│ 7      │ The Lord of the Rings             │ 10       │ George Allen & Unwin                        │ 35.5   │
│ 8      │ The Chronicles of Narnia          │ 11       │ Geoffrey Bles                               │ 28.99  │
│ 9      │ The Odyssey                       │ 12       │ Homer                                       │ 14.95  │
│ 10     │ The Iliad                         │ 12       │ Homer                                       │ 14.95  │
│ 11     │ Moby-Dick                         │ 13       │ Harper & Brothers                           │ 19.99  │
│ 12     │ The Road                          │ 14       │ Alfred A. Knopf                             │ 16.75  │
│ 13     │ The Grapes of Wrath               │ 15       │ The Viking Press                            │ 21.5   │
│ 14     │ Wuthering Heights                 │ 16       │ Emily Brontë                                │ 12.99  │
│ 15     │ The Old Man and the Sea           │ 17       │ Charles Scribner's Sons                     │ 18.95  │
│ 16     │ The Count of Monte Cristo         │ 18       │ Pétion                                      │ 27.99  │
│ 17     │ The Picture of Dorian Gray        │ 19       │ Ward, Lock, and Company                     │ 14.5   │
│ 18     │ The Adventures of Sherlock Holmes │ 20       │ George Newnes                               │ 16.99  │
│ 19     │ Frankenstein                      │ 21       │ Lackington, Hughes, Harding, Mavor, & Jones │ 13.25  │
│ 20     │ Alice's Adventures in Wonderland  │ 22       │ Macmillan                                   │ 11.5   │
│ 21     │ The Prince                        │ 23       │ Niccolò Machiavelli                         │ 10.99  │
│ 22     │ Don Quixote                       │ 24       │ Francisco de Robles                         │ 26.75  │
│ 23     │ The Divine Comedy                 │ 25       │ Dante Alighieri                             │ 20.5   │
│ 24     │ Anna Karenina                     │ 26       │ The Russian Messenger                       │ 23.99  │
│ 25     │ Les Misérables                    │ 27       │ A. Lacroix, Verboeckhoven & Cie.            │ 29.75  │
│ 26     │ The Jungle Book                   │ 28       │ Macmillan Publishers                        │ 14.99  │
│ 27     │ The Wind in the Willows           │ 29       │ Methuen & Co.                               │ 17.5   │
│ 28     │ War and Peace                     │ 26       │ The Russian Messenger                       │ 33.25  │
│ 29     │ Crime and Punishment              │ 30       │ The Russian Messenger                       │ 19.99  │
└────────┴───────────────────────────────────┴──────────┴─────────────────────────────────────────────┴────────┘
```

### Consultas


-- **Selección de libros cuyo título comienza con "H".**

Consulta:

``` sql
SELECT * FROM libro WHERE titulo = 'H%';
```

Resultado

``` sql
Ninguno porque ningún titulo comienza por H.
```

-- **Libros escritos por autores cuyos nombres terminan con "ing".**

Consulta:

``` sql
SELECT * FROM libro WHERE autor_id IN (SELECT id FROM autor WHERE nombre LIKE '%ing');
```

Resultado:

``` sql

```

-- **Libros con títulos que contienen la palabra "and" en cualquier posición.**

Consulta:

``` sql
SELECT * FROM libro WHERE titulo LIKE '%and%';
```

Resultado:

``` sql
┌────────┬──────────────────────────────────┬──────────┬─────────────────────────┬────────┐
│ codigo │              titulo              │ autor_id │        editorial        │ precio │
├────────┼──────────────────────────────────┼──────────┼─────────────────────────┼────────┤
│ 15     │ The Old Man and the Sea          │ 17       │ Charles Scribner's Sons │ 18.95  │
│ 20     │ Alice's Adventures in Wonderland │ 22       │ Macmillan               │ 11.5   │
│ 28     │ War and Peace                    │ 26       │ The Russian Messenger   │ 33.25  │
│ 29     │ Crime and Punishment             │ 30       │ The Russian Messenger   │ 19.99  │
└────────┴──────────────────────────────────┴──────────┴─────────────────────────┴────────┘
```

-- **Libros cuyo título comienza con una vocal.**

Consulta:

``` sql
SELECT * FROM libro WHERE titulo LIKE 'a%' OR 'e%' OR 'i%' OR 'u%';
```

Resultado:

``` sql
┌────────┬──────────────────────────────────┬──────────┬───────────────────────┬────────┐
│ codigo │              titulo              │ autor_id │       editorial       │ precio │
├────────┼──────────────────────────────────┼──────────┼───────────────────────┼────────┤
│ 20     │ Alice's Adventures in Wonderland │ 22       │ Macmillan             │ 11.5   │
│ 24     │ Anna Karenina                    │ 26       │ The Russian Messenger │ 23.99  │
└────────┴──────────────────────────────────┴──────────┴───────────────────────┴────────┘
```

-- **Libros cuyo autor tiene al menos una vocal repetida.**

Consulta:

``` sql
SELECT * FROM libro WHERE autor_id IN (SELECT id FROM autor WHERE nombre REGEXP '[aeiouAEIOU].*[aeiouAEIOU]');
```

Resultado:

``` sql
┌────────┬─────────────────┬──────────┬─────────────────┬────────┐
│ codigo │     titulo      │ autor_id │    editorial    │ precio │
├────────┼─────────────────┼──────────┼─────────────────┼────────┤
│ 5      │ Brave New World │ 3        │ Chatto & Windus │ 17.99  │
└────────┴─────────────────┴──────────┴─────────────────┴────────┘
```

-- **Libros con precios que tienen dos dígitos decimales exactos.**

Consulta:

``` sql
SELECT * FROM libro WHERE precio REGEXP '\.[0-9]{2}$';
```

Resultado:

``` sql
┌────────┬───────────────────────────────────┬──────────┬─────────────────────────────────────────────┬────────┐
│ codigo │              titulo               │ autor_id │                  editorial                  │ precio │
├────────┼───────────────────────────────────┼──────────┼─────────────────────────────────────────────┼────────┤
│ 1      │ The Great Gatsby                  │ 6        │ Charles Scribner's Sons                     │ 20.99  │
│ 2      │ To Kill a Mockingbird             │ 7        │ J.B. Lippincott & Co.                       │ 15.95  │
│ 3      │ The Catcher in the Rye            │ 8        │ Little, Brown and Company                   │ 18.75  │
│ 5      │ Brave New World                   │ 3        │ Chatto & Windus                             │ 17.99  │
│ 6      │ The Hobbit                        │ 10       │ George Allen & Unwin                        │ 24.99  │
│ 8      │ The Chronicles of Narnia          │ 11       │ Geoffrey Bles                               │ 28.99  │
│ 9      │ The Odyssey                       │ 12       │ Homer                                       │ 14.95  │
│ 10     │ The Iliad                         │ 12       │ Homer                                       │ 14.95  │
│ 11     │ Moby-Dick                         │ 13       │ Harper & Brothers                           │ 19.99  │
│ 12     │ The Road                          │ 14       │ Alfred A. Knopf                             │ 16.75  │
│ 14     │ Wuthering Heights                 │ 16       │ Emily Brontë                                │ 12.99  │
│ 15     │ The Old Man and the Sea           │ 17       │ Charles Scribner's Sons                     │ 18.95  │
│ 16     │ The Count of Monte Cristo         │ 18       │ Pétion                                      │ 27.99  │
│ 18     │ The Adventures of Sherlock Holmes │ 20       │ George Newnes                               │ 16.99  │
│ 19     │ Frankenstein                      │ 21       │ Lackington, Hughes, Harding, Mavor, & Jones │ 13.25  │
│ 21     │ The Prince                        │ 23       │ Niccolò Machiavelli                         │ 10.99  │
│ 22     │ Don Quixote                       │ 24       │ Francisco de Robles                         │ 26.75  │
│ 24     │ Anna Karenina                     │ 26       │ The Russian Messenger                       │ 23.99  │
│ 25     │ Les Misérables                    │ 27       │ A. Lacroix, Verboeckhoven & Cie.            │ 29.75  │
│ 26     │ The Jungle Book                   │ 28       │ Macmillan Publishers                        │ 14.99  │
│ 28     │ War and Peace                     │ 26       │ The Russian Messenger                       │ 33.25  │
│ 29     │ Crime and Punishment              │ 30       │ The Russian Messenger                       │ 19.99  │
└────────┴───────────────────────────────────┴──────────┴─────────────────────────────────────────────┴────────┘
```

-- **Libros cuyos títulos tienen al menos tres palabras.**

Consulta:

``` sql
SELECT * FROM libro WHERE titulo LIKE '% % %';
```

Resultado:

``` sql
┌────────┬───────────────────────────────────┬──────────┬───────────────────────────┬────────┐
│ codigo │              titulo               │ autor_id │         editorial         │ precio │
├────────┼───────────────────────────────────┼──────────┼───────────────────────────┼────────┤
│ 1      │ The Great Gatsby                  │ 6        │ Charles Scribner's Sons   │ 20.99  │
│ 2      │ To Kill a Mockingbird             │ 7        │ J.B. Lippincott & Co.     │ 15.95  │
│ 3      │ The Catcher in the Rye            │ 8        │ Little, Brown and Company │ 18.75  │
│ 4      │ One Hundred Years of Solitude     │ 9        │ Harper & Row              │ 22.5   │
│ 5      │ Brave New World                   │ 3        │ Chatto & Windus           │ 17.99  │
│ 7      │ The Lord of the Rings             │ 10       │ George Allen & Unwin      │ 35.5   │
│ 8      │ The Chronicles of Narnia          │ 11       │ Geoffrey Bles             │ 28.99  │
│ 13     │ The Grapes of Wrath               │ 15       │ The Viking Press          │ 21.5   │
│ 15     │ The Old Man and the Sea           │ 17       │ Charles Scribner's Sons   │ 18.95  │
│ 16     │ The Count of Monte Cristo         │ 18       │ Pétion                    │ 27.99  │
│ 17     │ The Picture of Dorian Gray        │ 19       │ Ward, Lock, and Company   │ 14.5   │
│ 18     │ The Adventures of Sherlock Holmes │ 20       │ George Newnes             │ 16.99  │
│ 20     │ Alice's Adventures in Wonderland  │ 22       │ Macmillan                 │ 11.5   │
│ 23     │ The Divine Comedy                 │ 25       │ Dante Alighieri           │ 20.5   │
│ 26     │ The Jungle Book                   │ 28       │ Macmillan Publishers      │ 14.99  │
│ 27     │ The Wind in the Willows           │ 29       │ Methuen & Co.             │ 17.5   │
│ 28     │ War and Peace                     │ 26       │ The Russian Messenger     │ 33.25  │
│ 29     │ Crime and Punishment              │ 30       │ The Russian Messenger     │ 19.99  │
└────────┴───────────────────────────────────┴──────────┴───────────────────────────┴────────┘

```

-- **Obtener todos los autores cuyo nombre empieza con la letra "A":**

Consulta:

``` sql
SELECT * FROM autor WHERE nombre LIKE 'A%';
```

Resultado:

``` sql
┌────┬─────────────────┐
│ id │     nombre      │
├────┼─────────────────┤
│ 5  │ Agatha Christie │
└────┴─────────────────┘

```

-- **Seleccionar los libros cuyo título contiene la palabra "SQL":**

Consulta:

``` sql
SELECT * FROM libro WHERE titulo LIKE '%SQL%';
```

Resultado:

``` sql
No hay resultado porque ningun título contiene la palabra SQL.
```

-- **Obtener todos los autores cuyo nombre termina con "ez":**

Consulta:

``` sql
SELECT * FROM autor WHERE nombre LIKE '%ez';
```

Resultado:

``` sql
No hay resultado porque ninguno de los nombres de los autores termina por 'ez'.
```

-- **Obtener todos los autores cuyo nombre tiene al menos 5 caracteres:**

Consulta:

``` sql
SELECT * FROM autor WHERE LENGTH(nombre) >= 5;
```

Resultado:

``` sql
┌────┬─────────────────┐
│ id │     nombre      │
├────┼─────────────────┤
│ 1  │ J.K. Rowling    │
│ 2  │ Stephen King    │
│ 3  │ George Orwell   │
│ 4  │ Jane Austen     │
│ 5  │ Agatha Christie │
└────┴─────────────────┘
```

-- **Seleccionar los libros cuya editorial es diferente de "EditorialX":**

Consulta:

``` sql
SELECT * FROM libro WHERE editorial != 'EditorialX';
```

Resultado:

``` sql
┌────────┬───────────────────────────────────┬──────────┬─────────────────────────────────────────────┬────────┐
│ codigo │              titulo               │ autor_id │                  editorial                  │ precio │
├────────┼───────────────────────────────────┼──────────┼─────────────────────────────────────────────┼────────┤
│ 1      │ The Great Gatsby                  │ 6        │ Charles Scribner's Sons                     │ 20.99  │
│ 2      │ To Kill a Mockingbird             │ 7        │ J.B. Lippincott & Co.                       │ 15.95  │
│ 3      │ The Catcher in the Rye            │ 8        │ Little, Brown and Company                   │ 18.75  │
│ 4      │ One Hundred Years of Solitude     │ 9        │ Harper & Row                                │ 22.5   │
│ 5      │ Brave New World                   │ 3        │ Chatto & Windus                             │ 17.99  │
│ 6      │ The Hobbit                        │ 10       │ George Allen & Unwin                        │ 24.99  │
│ 7      │ The Lord of the Rings             │ 10       │ George Allen & Unwin                        │ 35.5   │
│ 8      │ The Chronicles of Narnia          │ 11       │ Geoffrey Bles                               │ 28.99  │
│ 9      │ The Odyssey                       │ 12       │ Homer                                       │ 14.95  │
│ 10     │ The Iliad                         │ 12       │ Homer                                       │ 14.95  │
│ 11     │ Moby-Dick                         │ 13       │ Harper & Brothers                           │ 19.99  │
│ 12     │ The Road                          │ 14       │ Alfred A. Knopf                             │ 16.75  │
│ 13     │ The Grapes of Wrath               │ 15       │ The Viking Press                            │ 21.5   │
│ 14     │ Wuthering Heights                 │ 16       │ Emily Brontë                                │ 12.99  │
│ 15     │ The Old Man and the Sea           │ 17       │ Charles Scribner's Sons                     │ 18.95  │
│ 16     │ The Count of Monte Cristo         │ 18       │ Pétion                                      │ 27.99  │
│ 17     │ The Picture of Dorian Gray        │ 19       │ Ward, Lock, and Company                     │ 14.5   │
│ 18     │ The Adventures of Sherlock Holmes │ 20       │ George Newnes                               │ 16.99  │
│ 19     │ Frankenstein                      │ 21       │ Lackington, Hughes, Harding, Mavor, & Jones │ 13.25  │
│ 20     │ Alice's Adventures in Wonderland  │ 22       │ Macmillan                                   │ 11.5   │
│ 21     │ The Prince                        │ 23       │ Niccolò Machiavelli                         │ 10.99  │
│ 22     │ Don Quixote                       │ 24       │ Francisco de Robles                         │ 26.75  │
│ 23     │ The Divine Comedy                 │ 25       │ Dante Alighieri                             │ 20.5   │
│ 24     │ Anna Karenina                     │ 26       │ The Russian Messenger                       │ 23.99  │
│ 25     │ Les Misérables                    │ 27       │ A. Lacroix, Verboeckhoven & Cie.            │ 29.75  │
│ 26     │ The Jungle Book                   │ 28       │ Macmillan Publishers                        │ 14.99  │
│ 27     │ The Wind in the Willows           │ 29       │ Methuen & Co.                               │ 17.5   │
│ 28     │ War and Peace                     │ 26       │ The Russian Messenger                       │ 33.25  │
│ 29     │ Crime and Punishment              │ 30       │ The Russian Messenger                       │ 19.99  │
└────────┴───────────────────────────────────┴──────────┴─────────────────────────────────────────────┴────────┘
```

-- **Obtener todos los autores cuyo nombre contiene al menos una vocal:**

Consulta:

``` sql
SELECT * FROM autor WHERE nombre REGEXP '[aeiouAEIOU]+';
```

Resultado:

``` sql
┌────┬─────────────────┐
│ id │     nombre      │
├────┼─────────────────┤
│ 1  │ J.K. Rowling    │
│ 2  │ Stephen King    │
│ 3  │ George Orwell   │
│ 4  │ Jane Austen     │
│ 5  │ Agatha Christie │
└────┴─────────────────┘
```

-- **Seleccionar los libros cuyo título comienza con una letra mayúscula:**

Consulta:

``` sql
SELECT * FROM libro WHERE titulo REGEXP '^[A-Z]';
```

Resultado:

``` sql
┌────────┬───────────────────────────────────┬──────────┬─────────────────────────────────────────────┬────────┐
│ codigo │              titulo               │ autor_id │                  editorial                  │ precio │
├────────┼───────────────────────────────────┼──────────┼─────────────────────────────────────────────┼────────┤
│ 1      │ The Great Gatsby                  │ 6        │ Charles Scribner's Sons                     │ 20.99  │
│ 2      │ To Kill a Mockingbird             │ 7        │ J.B. Lippincott & Co.                       │ 15.95  │
│ 3      │ The Catcher in the Rye            │ 8        │ Little, Brown and Company                   │ 18.75  │
│ 4      │ One Hundred Years of Solitude     │ 9        │ Harper & Row                                │ 22.5   │
│ 5      │ Brave New World                   │ 3        │ Chatto & Windus                             │ 17.99  │
│ 6      │ The Hobbit                        │ 10       │ George Allen & Unwin                        │ 24.99  │
│ 7      │ The Lord of the Rings             │ 10       │ George Allen & Unwin                        │ 35.5   │
│ 8      │ The Chronicles of Narnia          │ 11       │ Geoffrey Bles                               │ 28.99  │
│ 9      │ The Odyssey                       │ 12       │ Homer                                       │ 14.95  │
│ 10     │ The Iliad                         │ 12       │ Homer                                       │ 14.95  │
│ 11     │ Moby-Dick                         │ 13       │ Harper & Brothers                           │ 19.99  │
│ 12     │ The Road                          │ 14       │ Alfred A. Knopf                             │ 16.75  │
│ 13     │ The Grapes of Wrath               │ 15       │ The Viking Press                            │ 21.5   │
│ 14     │ Wuthering Heights                 │ 16       │ Emily Brontë                                │ 12.99  │
│ 15     │ The Old Man and the Sea           │ 17       │ Charles Scribner's Sons                     │ 18.95  │
│ 16     │ The Count of Monte Cristo         │ 18       │ Pétion                                      │ 27.99  │
│ 17     │ The Picture of Dorian Gray        │ 19       │ Ward, Lock, and Company                     │ 14.5   │
│ 18     │ The Adventures of Sherlock Holmes │ 20       │ George Newnes                               │ 16.99  │
│ 19     │ Frankenstein                      │ 21       │ Lackington, Hughes, Harding, Mavor, & Jones │ 13.25  │
│ 20     │ Alice's Adventures in Wonderland  │ 22       │ Macmillan                                   │ 11.5   │
│ 21     │ The Prince                        │ 23       │ Niccolò Machiavelli                         │ 10.99  │
│ 22     │ Don Quixote                       │ 24       │ Francisco de Robles                         │ 26.75  │
│ 23     │ The Divine Comedy                 │ 25       │ Dante Alighieri                             │ 20.5   │
│ 24     │ Anna Karenina                     │ 26       │ The Russian Messenger                       │ 23.99  │
│ 25     │ Les Misérables                    │ 27       │ A. Lacroix, Verboeckhoven & Cie.            │ 29.75  │
│ 26     │ The Jungle Book                   │ 28       │ Macmillan Publishers                        │ 14.99  │
│ 27     │ The Wind in the Willows           │ 29       │ Methuen & Co.                               │ 17.5   │
│ 28     │ War and Peace                     │ 26       │ The Russian Messenger                       │ 33.25  │
│ 29     │ Crime and Punishment              │ 30       │ The Russian Messenger                       │ 19.99  │
└────────┴───────────────────────────────────┴──────────┴─────────────────────────────────────────────┴────────┘
```

-- **Obtener todos los autores cuyo nombre no contiene la letra "r":**

Consulta:

``` sql
SELECT * FROM autor WHERE nombre NOT REGEXP '[rR]';
```

Resultado:

``` sql
┌────┬──────────────┐
│ id │    nombre    │
├────┼──────────────┤
│ 2  │ Stephen King │
│ 4  │ Jane Austen  │
└────┴──────────────┘
```

-- **Seleccionar los libros cuya editorial empieza con la letra "P":**

Consulta:

``` sql
SELECT * FROM libro WHERE editorial REGEXP '^P';
```

Resultado:

``` sql
┌────────┬───────────────────────────┬──────────┬───────────┬────────┐
│ codigo │          titulo           │ autor_id │ editorial │ precio │
├────────┼───────────────────────────┼──────────┼───────────┼────────┤
│ 16     │ The Count of Monte Cristo │ 18       │ Pétion    │ 27.99  │
└────────┴───────────────────────────┴──────────┴───────────┴────────┘
```

-- **Obtener todos los autores cuyo nombre tiene exactamente 6 caracteres:**

Consulta:

``` sql
SELECT * FROM autor WHERE length(nombre) = 6;
```

Resultado:

``` sql

```

-- **Seleccionar los libros cuyo título contiene al menos un número:**

Consulta:

``` sql
SELECT * FROM libro WHERE titulo REGEXP '\d';
```

Resultado:

``` sql
No hay resultado porque ningun titulo contiene ningun número
```

-- **Obtener todos los autores cuyo nombre inicia con una vocal:**

Consulta:

``` sql
SELECT * FROM autor WHERE nombre REGEXP '^[aeiouAEIOU]';
```

Resultado:

``` sql
┌────┬─────────────────┐
│ id │     nombre      │
├────┼─────────────────┤
│ 5  │ Agatha Christie │
└────┴─────────────────┘
```

-- **Obtener todos los autores cuyo nombre no contiene espacios en blanco:**

Consulta:

``` sql
SELECT * FROM autor WHERE nombre NOT REGEXP '\s';
```

Resultado:

``` sql
No hay resultado porque todos los nombre contiene espacios
```

-- **Seleccionar los libros cuyo título termina con una vocal:**

Consulta:

``` sql
SELECT * FROM libro WHERE titulo REGEXP '[aeiouAEIOU]$';
```

Resultado:

``` sql
┌────────┬───────────────────────────────┬──────────┬───────────────────────────┬────────┐
│ codigo │            titulo             │ autor_id │         editorial         │ precio │
├────────┼───────────────────────────────┼──────────┼───────────────────────────┼────────┤
│ 3      │ The Catcher in the Rye        │ 8        │ Little, Brown and Company │ 18.75  │
│ 4      │ One Hundred Years of Solitude │ 9        │ Harper & Row              │ 22.5   │
│ 8      │ The Chronicles of Narnia      │ 11       │ Geoffrey Bles             │ 28.99  │
│ 15     │ The Old Man and the Sea       │ 17       │ Charles Scribner's Sons   │ 18.95  │
│ 16     │ The Count of Monte Cristo     │ 18       │ Pétion                    │ 27.99  │
│ 21     │ The Prince                    │ 23       │ Niccolò Machiavelli       │ 10.99  │
│ 22     │ Don Quixote                   │ 24       │ Francisco de Robles       │ 26.75  │
│ 24     │ Anna Karenina                 │ 26       │ The Russian Messenger     │ 23.99  │
│ 28     │ War and Peace                 │ 26       │ The Russian Messenger     │ 33.25  │
└────────┴───────────────────────────────┴──────────┴───────────────────────────┴────────┘
```

-- **Obtener todos los autores cuyo nombre contiene la secuencia "er":**

Consulta:

``` sql
SELECT * FROM autor WHERE nombre REGEXP 'er';
```

Resultado:

``` sql
No hay resultado porque ninguno contiene la secuencia 'er'.
```

-- **Seleccionar los libros cuyo título empieza con la palabra "The":**

Consulta:

``` sql
SELECT * FROM libro WHERE titulo REGEXP '^The\b';
```

Resultado:

``` sql
┌────────┬───────────────────────────────────┬──────────┬───────────────────────────┬────────┐
│ codigo │              titulo               │ autor_id │
editorial         │ precio │
├────────┼───────────────────────────────────┼──────────┼───────────────────────────┼────────┤
│ 1      │ The Great Gatsby                  │ 6        │ Charles Scribner's Sons   │ 20.99  │
│ 3      │ The Catcher in the Rye            │ 8        │ Little, Brown and Company │ 18.75  │
│ 6      │ The Hobbit                        │ 10       │ George Allen & Unwin      │ 24.99  │
│ 7      │ The Lord of the Rings             │ 10       │ George Allen & Unwin      │ 35.5   │
│ 8      │ The Chronicles of Narnia          │ 11       │ Geoffrey Bles             │ 28.99  │
│ 9      │ The Odyssey                       │ 12       │ Homer                     │ 14.95  │
│ 10     │ The Iliad                         │ 12       │ Homer                     │ 14.95  │
│ 12     │ The Road                          │ 14       │ Alfred A. Knopf           │ 16.75  │
│ 13     │ The Grapes of Wrath               │ 15       │ The Viking Press          │ 21.5   │
│ 15     │ The Old Man and the Sea           │ 17       │ Charles Scribner's Sons   │ 18.95  │
│ 16     │ The Count of Monte Cristo         │ 18       │ Pétion                    │ 27.99  │
│ 17     │ The Picture of Dorian Gray        │ 19       │ Ward, Lock, and Company   │ 14.5   │
│ 18     │ The Adventures of Sherlock Holmes │ 20       │ George Newnes             │ 16.99  │
│ 21     │ The Prince                        │ 23       │ Niccolò Machiavelli       │ 10.99  │
│ 23     │ The Divine Comedy                 │ 25       │ Dante Alighieri           │ 20.5   │
│ 26     │ The Jungle Book                   │ 28       │ Macmillan Publishers      │ 14.99  │
│ 27     │ The Wind in the Willows           │ 29       │ Methuen & Co.             │ 17.5   │
└────────┴───────────────────────────────────┴──────────┴───────────────────────────┴────────┘
```

-- **Obtener todos los autores cuyo nombre tiene al menos una letra mayúscula:**

Consulta:

``` sql
SELECT * FROM autor WHERE nombre REGEXP '[A-Z]';
```

Resultado:

``` sql
┌────┬─────────────────┐
│ id │     nombre      │
├────┼─────────────────┤
│ 1  │ J.K. Rowling    │
│ 2  │ Stephen King    │
│ 3  │ George Orwell   │
│ 4  │ Jane Austen     │
│ 5  │ Agatha Christie │
└────┴─────────────────┘
```

-- **Seleccionar los libros cuyo precio es un número decimal con exactamente dos decimales:**

Consulta:

``` sql
SELECT * FROM libro WHERE precio REGEXP '^\d+\.\d{2}$';
```

Resultado:

``` sql
┌────────┬───────────────────────────────────┬──────────┬─────────────────────────────────────────────┬────────┐
│ codigo │              titulo               │ autor_id │
         editorial                  │ precio │
├────────┼───────────────────────────────────┼──────────┼─────────────────────────────────────────────┼────────┤
│ 1      │ The Great Gatsby                  │ 6        │ Charles Scribner's Sons                     │ 20.99  │
│ 2      │ To Kill a Mockingbird             │ 7        │ J.B. Lippincott & Co.                       │ 15.95  │
│ 3      │ The Catcher in the Rye            │ 8        │ Little, Brown and Company                   │ 18.75  │
│ 5      │ Brave New World                   │ 3        │ Chatto & Windus                             │ 17.99  │
│ 6      │ The Hobbit                        │ 10       │ George Allen & Unwin                        │ 24.99  │
│ 8      │ The Chronicles of Narnia          │ 11       │ Geoffrey Bles                               │ 28.99  │
│ 9      │ The Odyssey                       │ 12       │ Homer                                       │ 14.95  │
│ 10     │ The Iliad                         │ 12       │ Homer                                       │ 14.95  │
│ 11     │ Moby-Dick                         │ 13       │ Harper & Brothers                           │ 19.99  │
│ 12     │ The Road                          │ 14       │ Alfred A. Knopf                             │ 16.75  │
│ 14     │ Wuthering Heights                 │ 16       │ Emily Brontë                                │ 12.99  │
│ 15     │ The Old Man and the Sea           │ 17       │ Charles Scribner's Sons                     │ 18.95  │
│ 16     │ The Count of Monte Cristo         │ 18       │ Pétion                                      │ 27.99  │
│ 18     │ The Adventures of Sherlock Holmes │ 20       │ George Newnes                               │ 16.99  │
│ 19     │ Frankenstein                      │ 21       │ Lackington, Hughes, Harding, Mavor, & Jones │ 13.25  │
│ 21     │ The Prince                        │ 23       │ Niccolò Machiavelli                         │ 10.99  │
│ 22     │ Don Quixote                       │ 24       │ Francisco de Robles                         │ 26.75  │
│ 24     │ Anna Karenina                     │ 26       │ The Russian Messenger                       │ 23.99  │
│ 25     │ Les Misérables                    │ 27       │ A. Lacroix, Verboeckhoven & Cie.            │ 29.75  │
│ 26     │ The Jungle Book                   │ 28       │ Macmillan Publishers                        │ 14.99  │
│ 28     │ War and Peace                     │ 26       │ The Russian Messenger                       │ 33.25  │
│ 29     │ Crime and Punishment              │ 30       │ The Russian Messenger                       │ 19.99  │
└────────┴───────────────────────────────────┴──────────┴─────────────────────────────────────────────┴────────┘
```

-- **Obtener todos los autores cuyo nombre no contiene números:**

Consulta:

``` sql
SELECT * FROM autor WHERE nombre NOT REGEXP '\d';
```

Resultado:

``` sql
No hay resultado porque ningun nombre de los autores contiene números.
```

-- **Seleccionar los libros cuyo título contiene al menos tres vocales:**

Consulta:

``` sql
SELECT * FROM libro WHERE titulo REGEXP '(.*[aeiouAEIOU]){3,}';
```

Resultado:

``` sql
┌────────┬───────────────────────────────────┬──────────┬─────────────────────────────────────────────┬────────┐
│ codigo │              titulo               │ autor_id │
         editorial                  │ precio │
├────────┼───────────────────────────────────┼──────────┼─────────────────────────────────────────────┼────────┤
│ 1      │ The Great Gatsby                  │ 6        │ Charles Scribner's Sons                     │ 20.99  │
│ 2      │ To Kill a Mockingbird             │ 7        │ J.B. Lippincott & Co.                       │ 15.95  │
│ 3      │ The Catcher in the Rye            │ 8        │ Little, Brown and Company                   │ 18.75  │
│ 4      │ One Hundred Years of Solitude     │ 9        │ Harper & Row                                │ 22.5   │
│ 5      │ Brave New World                   │ 3        │ Chatto & Windus                             │ 17.99  │
│ 6      │ The Hobbit                        │ 10       │ George Allen & Unwin                        │ 24.99  │
│ 7      │ The Lord of the Rings             │ 10       │ George Allen & Unwin                        │ 35.5   │
│ 8      │ The Chronicles of Narnia          │ 11       │ Geoffrey Bles                               │ 28.99  │
│ 9      │ The Odyssey                       │ 12       │ Homer                                       │ 14.95  │
│ 10     │ The Iliad                         │ 12       │ Homer                                       │ 14.95  │
│ 12     │ The Road                          │ 14       │ Alfred A. Knopf                             │ 16.75  │
│ 13     │ The Grapes of Wrath               │ 15       │ The Viking Press                            │ 21.5   │
│ 14     │ Wuthering Heights                 │ 16       │ Emily Brontë                                │ 12.99  │
│ 15     │ The Old Man and the Sea           │ 17       │ Charles Scribner's Sons                     │ 18.95  │
│ 16     │ The Count of Monte Cristo         │ 18       │ Pétion                                      │ 27.99  │
│ 17     │ The Picture of Dorian Gray        │ 19       │ Ward, Lock, and Company                     │ 14.5   │
│ 18     │ The Adventures of Sherlock Holmes │ 20       │ George Newnes                               │ 16.99  │
│ 19     │ Frankenstein                      │ 21       │ Lackington, Hughes, Harding, Mavor, & Jones │ 13.25  │
│ 20     │ Alice's Adventures in Wonderland  │ 22       │ Macmillan                                   │ 11.5   │
│ 21     │ The Prince                        │ 23       │ Niccolò Machiavelli                         │ 10.99  │
│ 22     │ Don Quixote                       │ 24       │ Francisco de Robles                         │ 26.75  │
│ 23     │ The Divine Comedy                 │ 25       │ Dante Alighieri                             │ 20.5   │
│ 24     │ Anna Karenina                     │ 26       │ The Russian Messenger                       │ 23.99  │
│ 25     │ Les Misérables                    │ 27       │ A. Lacroix, Verboeckhoven & Cie.            │ 29.75  │
│ 26     │ The Jungle Book                   │ 28       │ Macmillan Publishers                        │ 14.99  │
│ 27     │ The Wind in the Willows           │ 29       │ Methuen & Co.                               │ 17.5   │
│ 28     │ War and Peace                     │ 26       │ The Russian Messenger                       │ 33.25  │
│ 29     │ Crime and Punishment              │ 30       │ The Russian Messenger                       │ 19.99  │
└────────┴───────────────────────────────────┴──────────┴─────────────────────────────────────────────┴────────┘
```

-- **Obtener todos los autores cuyo nombre inicia con una consonante:**

Consulta:

``` sql
SELECT * FROM autor WHERE nombre REGEXP '^[^aeiouAEIOU]';
```

Resultado:

``` sql
┌────┬───────────────┐
│ id │    nombre     │
├────┼───────────────┤
│ 1  │ J.K. Rowling  │
│ 2  │ Stephen King  │
│ 3  │ George Orwell │
│ 4  │ Jane Austen   │
└────┴───────────────┘
```

-- **Seleccionar los libros cuyo título no contiene la palabra "Science":**

Consulta:

``` sql
SELECT * FROM libro WHERE titulo NOT REGEXP 'Science';
```

Resultado:

``` sql
┌────────┬───────────────────────────────────┬──────────┬─────────────────────────────────────────────┬────────┐
│ codigo │              titulo               │ autor_id │
         editorial                  │ precio │
├────────┼───────────────────────────────────┼──────────┼─────────────────────────────────────────────┼────────┤
│ 1      │ The Great Gatsby                  │ 6        │ Charles Scribner's Sons                     │ 20.99  │
│ 2      │ To Kill a Mockingbird             │ 7        │ J.B. Lippincott & Co.                       │ 15.95  │
│ 3      │ The Catcher in the Rye            │ 8        │ Little, Brown and Company                   │ 18.75  │
│ 4      │ One Hundred Years of Solitude     │ 9        │ Harper & Row                                │ 22.5   │
│ 5      │ Brave New World                   │ 3        │ Chatto & Windus                             │ 17.99  │
│ 6      │ The Hobbit                        │ 10       │ George Allen & Unwin                        │ 24.99  │
│ 7      │ The Lord of the Rings             │ 10       │ George Allen & Unwin                        │ 35.5   │
│ 8      │ The Chronicles of Narnia          │ 11       │ Geoffrey Bles                               │ 28.99  │
│ 9      │ The Odyssey                       │ 12       │ Homer                                       │ 14.95  │
│ 10     │ The Iliad                         │ 12       │ Homer                                       │ 14.95  │
│ 11     │ Moby-Dick                         │ 13       │ Harper & Brothers                           │ 19.99  │
│ 12     │ The Road                          │ 14       │ Alfred A. Knopf                             │ 16.75  │
│ 13     │ The Grapes of Wrath               │ 15       │ The Viking Press                            │ 21.5   │
│ 14     │ Wuthering Heights                 │ 16       │ Emily Brontë                                │ 12.99  │
│ 15     │ The Old Man and the Sea           │ 17       │ Charles Scribner's Sons                     │ 18.95  │
│ 16     │ The Count of Monte Cristo         │ 18       │ Pétion                                      │ 27.99  │
│ 17     │ The Picture of Dorian Gray        │ 19       │ Ward, Lock, and Company                     │ 14.5   │
│ 18     │ The Adventures of Sherlock Holmes │ 20       │ George Newnes                               │ 16.99  │
│ 19     │ Frankenstein                      │ 21       │ Lackington, Hughes, Harding, Mavor, & Jones │ 13.25  │
│ 20     │ Alice's Adventures in Wonderland  │ 22       │ Macmillan                                   │ 11.5   │
│ 21     │ The Prince                        │ 23       │ Niccolò Machiavelli                         │ 10.99  │
│ 22     │ Don Quixote                       │ 24       │ Francisco de Robles                         │ 26.75  │
│ 23     │ The Divine Comedy                 │ 25       │ Dante Alighieri                             │ 20.5   │
│ 24     │ Anna Karenina                     │ 26       │ The Russian Messenger                       │ 23.99  │
│ 25     │ Les Misérables                    │ 27       │ A. Lacroix, Verboeckhoven & Cie.            │ 29.75  │
│ 26     │ The Jungle Book                   │ 28       │ Macmillan Publishers                        │ 14.99  │
│ 27     │ The Wind in the Willows           │ 29       │ Methuen & Co.                               │ 17.5   │
│ 28     │ War and Peace                     │ 26       │ The Russian Messenger                       │ 33.25  │
│ 29     │ Crime and Punishment              │ 30       │ The Russian Messenger                       │ 19.99  │
└────────┴───────────────────────────────────┴──────────┴─────────────────────────────────────────────┴────────┘
```

-- **Obtener todos los autores cuyo nombre empieza con "M" o termina con "n":**

Consulta:

``` sql
SELECT * FROM autor WHERE nombre LIKE 'M%' OR nombre LIKE '%n';
```

Resultado:

``` sql
┌────┬─────────────┐
│ id │   nombre    │
├────┼─────────────┤
│ 4  │ Jane Austen │
└────┴─────────────┘
```

-- **Obtener todos los autores cuyo nombre no contiene caracteres especiales:**

Consulta:

``` sql
SELECT * FROM autor WHERE nombre REGEXP '^[a-zA-Z0-9]+$';
```

Resultado:

``` sql
No hay resultado porque ningun autor contiene caracteres especiales
```
