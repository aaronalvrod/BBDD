# Simulacro 1º Examen 2º Trimestre

### Tablas

**Tabla Pokemon:**

``` sql
┌────┬────────────┬─────────┬───────┐
│ id │   nombre   │ id_tipo │ nivel │
├────┼────────────┼─────────┼───────┤
│ 1  │ Bulbasaur  │ 3       │ 10    │
│ 2  │ Charmander │ 2       │ 12    │
│ 3  │ Squirtle   │ 1       │ 8     │
│ 4  │ Pikachu    │ 4       │ 15    │
│ 5  │ Geodude    │ 5       │ 11    │
│ 6  │ Vaporeon   │ 1       │ 25    │
│ 7  │ Flareon    │ 2       │ 27    │
│ 8  │ Ivysaur    │ 3       │ 18    │
│ 9  │ Jolteon    │ 4       │ 22    │
│ 10 │ Cubone     │ 5       │ 14    │
│ 11 │ Gyarados   │ 1       │ 30    │
│ 12 │ Arcanine   │ 2       │ 35    │
│ 13 │ Exeggutor  │ 3       │ 40    │
│ 14 │ Raichu     │ 4       │ 38    │
│ 15 │ Sandslash  │ 5       │ 33    │
│ 16 │ Venusaur   │ 3       │ 45    │
│ 17 │ Charizard  │ 2       │ 50    │
│ 18 │ Blastoise  │ 1       │ 55    │
│ 19 │ Electabuzz │ 4       │ 48    │
│ 20 │ Rhydon     │ 5       │ 52    │
│ 21 │ Dragonite  │ 2       │ 60    │
│ 22 │ Flareon    │ 2       │ 65    │
│ 23 │ Venusaur   │ 3       │ 70    │
│ 24 │ Zapdos     │ 4       │ 75    │
│ 25 │ Rhydon     │ 5       │ 80    │
└────┴────────────┴─────────┴───────┘
```
**Tabla Tipo:**

``` sql
┌────┬───────────┐
│ id │  nombre   │
├────┼───────────┤
│ 1  │ Agua      │
│ 2  │ Fuego     │
│ 3  │ Planta    │
│ 4  │ Eléctrico │
│ 5  │ Tierra    │
└────┴───────────┘
```

---

- **Actualizar el nivel de Bulbasaur.**

Consulta:

``` sql 
UPDATE pokemon SET nivel = 15 WHERE nombre = 'Bulbasaur';
```

Resultado

``` sql
┌────┬───────────┬─────────┬───────┐
│ id │  nombre   │ id_tipo │ nivel │
├────┼───────────┼─────────┼───────┤
│ 1  │ Bulbasaur │ 3       │ 15    │
└────┴───────────┴─────────┴───────┘
```

- **Cambiar el tipo de Pikachu a 'Eléctrico/Rojo'.**

Consulta:

``` sql
UPDATE pokemon SET id_tipo = (SELECT id_tipo FROM tipo WHERE nombre = 'Eléctrico/Rojo') WHERE nombre = 'Pikachu';'; 
```

Resultado: 

- **Incremetar el nivel de todos los Pokémon de tipo Agua.**

Consulta:

``` sql
UPDATE pokemon SET nivel = nivel + 5 WHERE id_tipo = (SELECT id_tipo FROM tipo WHERE nombre = 'Agua');
```

Resultado:

``` sql
┌────┬────────────┬─────────┬───────┐
│ id │   nombre   │ id_tipo │ nivel │
├────┼────────────┼─────────┼───────┤
│ 1  │ Bulbasaur  │ 3       │ 20    │
│ 2  │ Charmander │ 2       │ 17    │
│ 3  │ Squirtle   │ 1       │ 13    │
│ 4  │ Pikachu    │         │ 15    │
│ 5  │ Geodude    │ 5       │ 16    │
│ 6  │ Vaporeon   │ 1       │ 30    │
│ 7  │ Flareon    │ 2       │ 32    │
│ 8  │ Ivysaur    │ 3       │ 23    │
│ 9  │ Jolteon    │ 4       │ 27    │
│ 10 │ Cubone     │ 5       │ 19    │
│ 11 │ Gyarados   │ 1       │ 35    │
│ 12 │ Arcanine   │ 2       │ 40    │
│ 13 │ Exeggutor  │ 3       │ 45    │
│ 14 │ Raichu     │ 4       │ 43    │
│ 15 │ Sandslash  │ 5       │ 38    │
│ 16 │ Venusaur   │ 3       │ 50    │
│ 17 │ Charizard  │ 2       │ 55    │
│ 18 │ Blastoise  │ 1       │ 60    │
│ 19 │ Electabuzz │ 4       │ 53    │
│ 20 │ Rhydon     │ 5       │ 57    │
│ 21 │ Dragonite  │ 2       │ 65    │
│ 22 │ Flareon    │ 2       │ 70    │
│ 23 │ Venusaur   │ 3       │ 75    │
│ 24 │ Zapdos     │ 4       │ 80    │
│ 25 │ Rhydon     │ 5       │ 85    │
└────┴────────────┴─────────┴───────┘
```

- **Eliminar a Jyn de la lista de Pokémon.**

Consulta: 

``` sql
DELETE FROM pokemon WHERE nombre = 'Jynx';
```

Resultado

``` sql
┌────┬────────────┬─────────┬───────┐
│ id │   nombre   │ id_tipo │ nivel │
├────┼────────────┼─────────┼───────┤
│ 1  │ Bulbasaur  │ 3       │ 20    │
│ 2  │ Charmander │ 2       │ 17    │
│ 3  │ Squirtle   │ 1       │ 13    │
│ 4  │ Pikachu    │         │ 15    │
│ 5  │ Geodude    │ 5       │ 16    │
│ 6  │ Vaporeon   │ 1       │ 30    │
│ 7  │ Flareon    │ 2       │ 32    │
│ 8  │ Ivysaur    │ 3       │ 23    │
│ 9  │ Jolteon    │ 4       │ 27    │
│ 10 │ Cubone     │ 5       │ 19    │
│ 11 │ Gyarados   │ 1       │ 35    │
│ 12 │ Arcanine   │ 2       │ 40    │
│ 13 │ Exeggutor  │ 3       │ 45    │
│ 14 │ Raichu     │ 4       │ 43    │
│ 15 │ Sandslash  │ 5       │ 38    │
│ 16 │ Venusaur   │ 3       │ 50    │
│ 17 │ Charizard  │ 2       │ 55    │
│ 18 │ Blastoise  │ 1       │ 60    │
│ 19 │ Electabuzz │ 4       │ 53    │
│ 20 │ Rhydon     │ 5       │ 57    │
│ 21 │ Dragonite  │ 2       │ 65    │
│ 22 │ Flareon    │ 2       │ 70    │
│ 23 │ Venusaur   │ 3       │ 75    │
│ 24 │ Zapdos     │ 4       │ 80    │
│ 25 │ Rhydon     │ 5       │ 85    │
└────┴────────────┴─────────┴───────┘
```

- **Eliminar el tipo 'Hielo' de la lista.**

Consulta:

``` sql
DELETE FROM tipo WHERE nombre = 'Hielo';.
```

Resultado:

``` sql
┌────┬───────────┐
│ id │  nombre   │
├────┼───────────┤
│ 1  │ Agua      │
│ 2  │ Fuego     │
│ 3  │ Planta    │
│ 4  │ Eléctrico │
│ 5  │ Tierra    │
└────┴───────────┘
```

- **Obtener todos los pokemon.**

Consulta:

``` sql
SELECT * FROM pokemon;
```

Resultado:

``` sql
┌────┬────────────┬─────────┬───────┐
│ id │   nombre   │ id_tipo │ nivel │
├────┼────────────┼─────────┼───────┤
│ 1  │ Bulbasaur  │ 3       │ 20    │
│ 2  │ Charmander │ 2       │ 17    │
│ 3  │ Squirtle   │ 1       │ 13    │
│ 4  │ Pikachu    │         │ 15    │
│ 5  │ Geodude    │ 5       │ 16    │
│ 6  │ Vaporeon   │ 1       │ 30    │
│ 7  │ Flareon    │ 2       │ 32    │
│ 8  │ Ivysaur    │ 3       │ 23    │
│ 9  │ Jolteon    │ 4       │ 27    │
│ 10 │ Cubone     │ 5       │ 19    │
│ 11 │ Gyarados   │ 1       │ 35    │
│ 12 │ Arcanine   │ 2       │ 40    │
│ 13 │ Exeggutor  │ 3       │ 45    │
│ 14 │ Raichu     │ 4       │ 43    │
│ 15 │ Sandslash  │ 5       │ 38    │
│ 16 │ Venusaur   │ 3       │ 50    │
│ 17 │ Charizard  │ 2       │ 55    │
│ 18 │ Blastoise  │ 1       │ 60    │
│ 19 │ Electabuzz │ 4       │ 53    │
│ 20 │ Rhydon     │ 5       │ 57    │
│ 21 │ Dragonite  │ 2       │ 65    │
│ 22 │ Flareon    │ 2       │ 70    │
│ 23 │ Venusaur   │ 3       │ 75    │
│ 24 │ Zapdos     │ 4       │ 80    │
│ 25 │ Rhydon     │ 5       │ 85    │
└────┴────────────┴─────────┴───────┘
```

- **Obtener el nombre y nivel de los Pokémon de tipo Fuego.**

Consulta:

``` sql
SELECT nombre, nivel FROM pokemon WHERE id_tipo = (SELECT id_tipo FROM tipo WHERE nombre = 'Fuego');
```

Restultado:

``` sql
┌────────────┬───────┐
│   nombre   │ nivel │
├────────────┼───────┤
│ Bulbasaur  │ 20    │
│ Charmander │ 17    │
│ Squirtle   │ 13    │
│ Geodude    │ 16    │
│ Vaporeon   │ 30    │
│ Flareon    │ 32    │
│ Ivysaur    │ 23    │
│ Jolteon    │ 27    │
│ Cubone     │ 19    │
│ Gyarados   │ 35    │
│ Arcanine   │ 40    │
│ Exeggutor  │ 45    │
│ Raichu     │ 43    │
│ Sandslash  │ 38    │
│ Venusaur   │ 50    │
│ Charizard  │ 55    │
│ Blastoise  │ 60    │
│ Electabuzz │ 53    │
│ Rhydon     │ 57    │
│ Dragonite  │ 65    │
│ Flareon    │ 70    │
│ Venusaur   │ 75    │
│ Zapdos     │ 80    │
│ Rhydon     │ 85    │
└────────────┴───────┘
```

- **Obtener el nombre de los Pokémon que tienen un nivel superior a 30.**

Consulta:

``` sql
SELECT nombre FROM pokemon where nivel > 30;
```

Resultado:

``` sql
┌────────────┐
│   nombre   │
├────────────┤
│ Flareon    │
│ Gyarados   │
│ Arcanine   │
│ Exeggutor  │
│ Raichu     │
│ Sandslash  │
│ Venusaur   │
│ Charizard  │
│ Blastoise  │
│ Electabuzz │
│ Rhydon     │
│ Dragonite  │
│ Flareon    │
│ Venusaur   │
│ Zapdos     │
│ Rhydon     │
└────────────┘
```

- **Obtener el nombre de los Pokémon ordenados por nivel de forma descendente.**

Consulta:

``` sql
SELECT nombre FROM pokemon ORDER BY nivel DESC;
```

Resultado:

``` sql
┌────────────┐
│   nombre   │
├────────────┤
│ Rhydon     │
│ Zapdos     │
│ Venusaur   │
│ Flareon    │
│ Dragonite  │
│ Blastoise  │
│ Rhydon     │
│ Charizard  │
│ Electabuzz │
│ Venusaur   │
│ Exeggutor  │
│ Raichu     │
│ Arcanine   │
│ Sandslash  │
│ Gyarados   │
│ Flareon    │
│ Vaporeon   │
│ Jolteon    │
│ Ivysaur    │
│ Bulbasaur  │
│ Cubone     │
│ Charmander │
│ Geodude    │
│ Pikachu    │
│ Squirtle   │
└────────────┘
```

- **Obtener la información completa de un Pokémon específico. Selecciona el que desees.**

Consulta:

``` sql
SELECT * FROM pokemon WHERE nombre = 'Charizard';
```

Resultado:

``` sql
┌────┬───────────┬─────────┬───────┐
│ id │  nombre   │ id_tipo │ nivel │
├────┼───────────┼─────────┼───────┤
│ 17 │ Charizard │ 2       │ 55    │
└────┴───────────┴─────────┴───────┘
```

- **Obtener el promedio de niveles de todos los Pokémon.**

Consulta:

``` sql
SELECT AVG(nivel) AS Promedio_niveles FROM pokemon;
```

Resultado:

``` sql
┌──────────────────┐
│ Promedio_niveles │
├──────────────────┤
│ 42.52            │
└──────────────────┘
```

- **Obtener el nombre del Pokémon de mayor nivel.**

Consulta:

```sql
SELECT nombre FROM pokemon ORDER BY nivel LIMIT 1;
```

Resultado:

``` sql
┌──────────┐
│  nombre  │
├──────────┤
│ Squirtle │
└──────────┘
```

- **Actualizar el nombre de Bulbasaur a 'Bulbasaur NV.15'.**

Consulta:

``` sql
UPDATE pokemon SET nombre = 'Bulbasaur Nv.15' WHERE nombre = 'Bulbasaur';
```

Resultado:

``` sql
┌────┬─────────────────┬─────────┬───────┐
│ id │     nombre      │ id_tipo │ nivel │
├────┼─────────────────┼─────────┼───────┤
│ 1  │ Bulbasaur Nv.15 │ 3       │ 20    │
│ 2  │ Charmander      │ 2       │ 17    │
│ 3  │ Squirtle        │ 1       │ 13    │
│ 4  │ Pikachu         │         │ 15    │
│ 5  │ Geodude         │ 5       │ 16    │
│ 6  │ Vaporeon        │ 1       │ 30    │
│ 7  │ Flareon         │ 2       │ 32    │
│ 8  │ Ivysaur         │ 3       │ 23    │
│ 9  │ Jolteon         │ 4       │ 27    │
│ 10 │ Cubone          │ 5       │ 19    │
│ 11 │ Gyarados        │ 1       │ 35    │
│ 12 │ Arcanine        │ 2       │ 40    │
│ 13 │ Exeggutor       │ 3       │ 45    │
│ 14 │ Raichu          │ 4       │ 43    │
│ 15 │ Sandslash       │ 5       │ 38    │
│ 16 │ Venusaur        │ 3       │ 50    │
│ 17 │ Charizard       │ 2       │ 55    │
│ 18 │ Blastoise       │ 1       │ 60    │
│ 19 │ Electabuzz      │ 4       │ 53    │
│ 20 │ Rhydon          │ 5       │ 57    │
│ 21 │ Dragonite       │ 2       │ 65    │
│ 22 │ Flareon         │ 2       │ 70    │
│ 23 │ Venusaur        │ 3       │ 75    │
│ 24 │ Zapdos          │ 4       │ 80    │
│ 25 │ Rhydon          │ 5       │ 85    │
└────┴─────────────────┴─────────┴───────┘
```

- **Obtener los Pokémon cuyo nivel es igual a 50.**

Consulta:

```sql
SELECT * FROM pokemon WHERE nivel = 50;
```

Resultado:

```sql
┌────┬──────────┬─────────┬───────┐
│ id │  nombre  │ id_tipo │ nivel │
├────┼──────────┼─────────┼───────┤
│ 16 │ Venusaur │ 3       │ 50    │
└────┴──────────┴─────────┴───────┘
```

