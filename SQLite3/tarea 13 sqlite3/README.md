# Repasando consultas III

# Tablas

**Tabla** *alumno_se_matricula_asignatura*

``` sql
┌───────────┬───────────────┬──────────────────┐
│ id_alumno │ id_asignatura │ id_curso_escolar │
├───────────┼───────────────┼──────────────────┤
│ 1         │ 1             │ 1                │
│ 1         │ 2             │ 1                │
│ 1         │ 3             │ 1                │
│ 2         │ 1             │ 1                │
│ 2         │ 2             │ 1                │
│ 2         │ 3             │ 1                │
│ 4         │ 1             │ 1                │
│ 4         │ 2             │ 1                │
│ 4         │ 3             │ 1                │
│ 24        │ 1             │ 5                │
│ 24        │ 2             │ 5                │
│ 24        │ 3             │ 5                │
│ 24        │ 4             │ 5                │
│ 24        │ 5             │ 5                │
│ 24        │ 6             │ 5                │
│ 24        │ 7             │ 5                │
│ 24        │ 8             │ 5                │
│ 24        │ 9             │ 5                │
│ 24        │ 10            │ 5                │
│ 23        │ 1             │ 5                │
│ 23        │ 2             │ 5                │
│ 23        │ 3             │ 5                │
│ 23        │ 4             │ 5                │
│ 23        │ 5             │ 5                │
│ 23        │ 6             │ 5                │
│ 23        │ 7             │ 5                │
│ 23        │ 8             │ 5                │
│ 23        │ 9             │ 5                │
│ 23        │ 10            │ 5                │
│ 19        │ 1             │ 5                │
│ 19        │ 2             │ 5                │
│ 19        │ 3             │ 5                │
│ 19        │ 4             │ 5                │
│ 19        │ 5             │ 5                │
│ 19        │ 6             │ 5                │
│ 19        │ 7             │ 5                │
│ 19        │ 8             │ 5                │
│ 19        │ 9             │ 5                │
│ 19        │ 10            │ 5                │
└───────────┴───────────────┴──────────────────┘
``` 

**Tabla** *asignatura*

``` sql
┌────┬────────────────────────────────────────────────────────────────────────┬──────────┬─────────────┬───────┬──────────────┬─────────────┬──────────┐
│ id │                                 nombre                                 │ creditos │    tipo     │ curso │ cuatrimestre │ id_profesor │ id_grado │
├────┼────────────────────────────────────────────────────────────────────────┼──────────┼─────────────┼───────┼──────────────┼─────────────┼──────────┤
│ 1  │ Álgegra lineal y matemática discreta                                   │ 6.0      │ básica      │ 1     │ 1            │ 3           │ 4        │
│ 2  │ Cálculo                                                                │ 6.0      │ básica      │ 1     │ 1            │ 14          │ 4        │
│ 3  │ Física para informática                                                │ 6.0      │ básica      │ 1     │ 1            │ 3           │ 4        │
│ 4  │ Introducción a la programación                                         │ 6.0      │ básica      │ 1     │ 1            │ 14          │ 4        │
│ 5  │ Organización y gestión de empresas                                     │ 6.0      │ básica      │ 1     │ 1            │ 3           │ 4        │
│ 6  │ Estadística                                                            │ 6.0      │ básica      │ 1     │ 2            │ 14          │ 4        │
│ 7  │ Estructura y tecnología de computadores                                │ 6.0      │ básica      │ 1     │ 2            │ 3           │ 4        │
│ 8  │ Fundamentos de electrónica                                             │ 6.0      │ básica      │ 1     │ 2            │ 14          │ 4        │
│ 9  │ Lógica y algorítmica                                                   │ 6.0      │ básica      │ 1     │ 2            │ 3           │ 4        │
│ 10 │ Metodología de la programación                                         │ 6.0      │ básica      │ 1     │ 2            │ 14          │ 4        │
│ 11 │ Arquitectura de Computadores                                           │ 6.0      │ básica      │ 2     │ 1            │ 3           │ 4        │
│ 12 │ Estructura de Datos y Algoritmos I                                     │ 6.0      │ obligatoria │ 2     │ 1            │ 3           │ 4        │
│ 13 │ Ingeniería del Software                                                │ 6.0      │ obligatoria │ 2     │ 1            │ 14          │ 4        │
│ 14 │ Sistemas Inteligentes                                                  │ 6.0      │ obligatoria │ 2     │ 1            │ 3           │ 4        │
│ 15 │ Sistemas Operativos                                                    │ 6.0      │ obligatoria │ 2     │ 1            │ 14          │ 4        │
│ 16 │ Bases de Datos                                                         │ 6.0      │ básica      │ 2     │ 2            │ 14          │ 4        │
│ 17 │ Estructura de Datos y Algoritmos II                                    │ 6.0      │ obligatoria │ 2     │ 2            │ 14          │ 4        │
│ 18 │ Fundamentos de Redes de Computadores                                   │ 6.0      │ obligatoria │ 2     │ 2            │ 3           │ 4        │
│ 19 │ Planificación y Gestión de Proyectos Informáticos                      │ 6.0      │ obligatoria │ 2     │ 2            │ 3           │ 4        │
│ 20 │ Programación de Servicios Software                                     │ 6.0      │ obligatoria │ 2     │ 2            │ 14          │ 4        │
│ 21 │ Desarrollo de interfaces de usuario                                    │ 6.0      │ obligatoria │ 3     │ 1            │ 14          │ 4        │
│ 22 │ Ingeniería de Requisitos                                               │ 6.0      │ optativa    │ 3     │ 1            │             │ 4        │
│ 23 │ Integración de las Tecnologías de la Información en las Organizaciones │ 6.0      │ optativa    │ 3     │ 1            │             │ 4        │
│ 24 │ Modelado y Diseño del Software 1                                       │ 6.0      │ optativa    │ 3     │ 1            │             │ 4        │
│ 25 │ Multiprocesadores                                                      │ 6.0      │ optativa    │ 3     │ 1            │             │ 4        │
│ 26 │ Seguridad y cumplimiento normativo                                     │ 6.0      │ optativa    │ 3     │ 1            │             │ 4        │
│ 27 │ Sistema de Información para las Organizaciones                         │ 6.0      │ optativa    │ 3     │ 1            │             │ 4        │
│ 28 │ Tecnologías web                                                        │ 6.0      │ optativa    │ 3     │ 1            │             │ 4        │
│ 29 │ Teoría de códigos y criptografía                                       │ 6.0      │ optativa    │ 3     │ 1            │             │ 4        │
│ 30 │ Administración de bases de datos                                       │ 6.0      │ optativa    │ 3     │ 2            │             │ 4        │
│ 31 │ Herramientas y Métodos de Ingeniería del Software                      │ 6.0      │ optativa    │ 3     │ 2            │             │ 4        │
│ 32 │ Informática industrial y robótica                                      │ 6.0      │ optativa    │ 3     │ 2            │             │ 4        │
│ 33 │ Ingeniería de Sistemas de Información                                  │ 6.0      │ optativa    │ 3     │ 2            │             │ 4        │
│ 34 │ Modelado y Diseño del Software 2                                       │ 6.0      │ optativa    │ 3     │ 2            │             │ 4        │
│ 35 │ Negocio Electrónico                                                    │ 6.0      │ optativa    │ 3     │ 2            │             │ 4        │
│ 36 │ Periféricos e interfaces                                               │ 6.0      │ optativa    │ 3     │ 2            │             │ 4        │
│ 37 │ Sistemas de tiempo real                                                │ 6.0      │ optativa    │ 3     │ 2            │             │ 4        │
│ 38 │ Tecnologías de acceso a red                                            │ 6.0      │ optativa    │ 3     │ 2            │             │ 4        │
│ 39 │ Tratamiento digital de imágenes                                        │ 6.0      │ optativa    │ 3     │ 2            │             │ 4        │
│ 40 │ Administración de redes y sistemas operativos                          │ 6.0      │ optativa    │ 4     │ 1            │             │ 4        │
│ 41 │ Almacenes de Datos                                                     │ 6.0      │ optativa    │ 4     │ 1            │             │ 4        │
│ 42 │ Fiabilidad y Gestión de Riesgos                                        │ 6.0      │ optativa    │ 4     │ 1            │             │ 4        │
│ 43 │ Líneas de Productos Software                                           │ 6.0      │ optativa    │ 4     │ 1            │             │ 4        │
│ 44 │ Procesos de Ingeniería del Software 1                                  │ 6.0      │ optativa    │ 4     │ 1            │             │ 4        │
│ 45 │ Tecnologías multimedia                                                 │ 6.0      │ optativa    │ 4     │ 1            │             │ 4        │
│ 46 │ Análisis y planificación de las TI                                     │ 6.0      │ optativa    │ 4     │ 2            │             │ 4        │
│ 47 │ Desarrollo Rápido de Aplicaciones                                      │ 6.0      │ optativa    │ 4     │ 2            │             │ 4        │
│ 48 │ Gestión de la Calidad y de la Innovación Tecnológica                   │ 6.0      │ optativa    │ 4     │ 2            │             │ 4        │
│ 49 │ Inteligencia del Negocio                                               │ 6.0      │ optativa    │ 4     │ 2            │             │ 4        │
│ 50 │ Procesos de Ingeniería del Software 2                                  │ 6.0      │ optativa    │ 4     │ 2            │             │ 4        │
│ 51 │ Seguridad Informática                                                  │ 6.0      │ optativa    │ 4     │ 2            │             │ 4        │
│ 52 │ Biologia celular                                                       │ 6.0      │ básica      │ 1     │ 1            │             │ 7        │
│ 53 │ Física                                                                 │ 6.0      │ básica      │ 1     │ 1            │             │ 7        │
│ 54 │ Matemáticas I                                                          │ 6.0      │ básica      │ 1     │ 1            │             │ 7        │
│ 55 │ Química general                                                        │ 6.0      │ básica      │ 1     │ 1            │             │ 7        │
│ 56 │ Química orgánica                                                       │ 6.0      │ básica      │ 1     │ 1            │             │ 7        │
│ 57 │ Biología vegetal y animal                                              │ 6.0      │ básica      │ 1     │ 2            │             │ 7        │
│ 58 │ Bioquímica                                                             │ 6.0      │ básica      │ 1     │ 2            │             │ 7        │
│ 59 │ Genética                                                               │ 6.0      │ básica      │ 1     │ 2            │             │ 7        │
│ 60 │ Matemáticas II                                                         │ 6.0      │ básica      │ 1     │ 2            │             │ 7        │
│ 61 │ Microbiología                                                          │ 6.0      │ básica      │ 1     │ 2            │             │ 7        │
│ 62 │ Botánica agrícola                                                      │ 6.0      │ obligatoria │ 2     │ 1            │             │ 7        │
│ 63 │ Fisiología vegetal                                                     │ 6.0      │ obligatoria │ 2     │ 1            │             │ 7        │
│ 64 │ Genética molecular                                                     │ 6.0      │ obligatoria │ 2     │ 1            │             │ 7        │
│ 65 │ Ingeniería bioquímica                                                  │ 6.0      │ obligatoria │ 2     │ 1            │             │ 7        │
│ 66 │ Termodinámica y cinética química aplicada                              │ 6.0      │ obligatoria │ 2     │ 1            │             │ 7        │
│ 67 │ Biorreactores                                                          │ 6.0      │ obligatoria │ 2     │ 2            │             │ 7        │
│ 68 │ Biotecnología microbiana                                               │ 6.0      │ obligatoria │ 2     │ 2            │             │ 7        │
│ 69 │ Ingeniería genética                                                    │ 6.0      │ obligatoria │ 2     │ 2            │             │ 7        │
│ 70 │ Inmunología                                                            │ 6.0      │ obligatoria │ 2     │ 2            │             │ 7        │
│ 71 │ Virología                                                              │ 6.0      │ obligatoria │ 2     │ 2            │             │ 7        │
│ 72 │ Bases moleculares del desarrollo vegetal                               │ 4.5      │ obligatoria │ 3     │ 1            │             │ 7        │
│ 73 │ Fisiología animal                                                      │ 4.5      │ obligatoria │ 3     │ 1            │             │ 7        │
│ 74 │ Metabolismo y biosíntesis de biomoléculas                              │ 6.0      │ obligatoria │ 3     │ 1            │             │ 7        │
│ 75 │ Operaciones de separación                                              │ 6.0      │ obligatoria │ 3     │ 1            │             │ 7        │
│ 76 │ Patología molecular de plantas                                         │ 4.5      │ obligatoria │ 3     │ 1            │             │ 7        │
│ 77 │ Técnicas instrumentales básicas                                        │ 4.5      │ obligatoria │ 3     │ 1            │             │ 7        │
│ 78 │ Bioinformática                                                         │ 4.5      │ obligatoria │ 3     │ 2            │             │ 7        │
│ 79 │ Biotecnología de los productos hortofrutículas                         │ 4.5      │ obligatoria │ 3     │ 2            │             │ 7        │
│ 80 │ Biotecnología vegetal                                                  │ 6.0      │ obligatoria │ 3     │ 2            │             │ 7        │
│ 81 │ Genómica y proteómica                                                  │ 4.5      │ obligatoria │ 3     │ 2            │             │ 7        │
│ 82 │ Procesos biotecnológicos                                               │ 6.0      │ obligatoria │ 3     │ 2            │             │ 7        │
│ 83 │ Técnicas instrumentales avanzadas                                      │ 4.5      │ obligatoria │ 3     │ 2            │             │ 7        │
└────┴────────────────────────────────────────────────────────────────────────┴──────────┴─────────────┴───────┴──────────────┴─────────────┴──────────┘
```

**Tabla** *curso_escolar*

``` sql
┌────┬─────────────┬──────────┐
│ id │ anyo_inicio │ anyo_fin │
├────┼─────────────┼──────────┤
│ 1  │ 2014        │ 2015     │
│ 2  │ 2015        │ 2016     │
│ 3  │ 2016        │ 2017     │
│ 4  │ 2017        │ 2018     │
│ 5  │ 2018        │ 2019     │
└────┴─────────────┴──────────┘
```

**Tabla** *departamento*

``` sql
┌────┬─────────────────────┐
│ id │       nombre        │
├────┼─────────────────────┤
│ 1  │ Informática         │
│ 2  │ Matemáticas         │
│ 3  │ Economía y Empresa  │
│ 4  │ Educación           │
│ 5  │ Agronomía           │
│ 6  │ Química y Física    │
│ 7  │ Filología           │
│ 8  │ Derecho             │
│ 9  │ Biología y Geología │
└────┴─────────────────────┘
```

**Tabla** *grado*

``` sql
┌────┬────────────────────────────────────────────────────────┐
│ id │                         nombre                         │
├────┼────────────────────────────────────────────────────────┤
│ 1  │ Grado en Ingeniería Agrícola (Plan 2015)               │
│ 2  │ Grado en Ingeniería Eléctrica (Plan 2014)              │
│ 3  │ Grado en Ingeniería Electrónica Industrial (Plan 2010) │
│ 4  │ Grado en Ingeniería Informática (Plan 2015)            │
│ 5  │ Grado en Ingeniería Mecánica (Plan 2010)               │
│ 6  │ Grado en Ingeniería Química Industrial (Plan 2010)     │
│ 7  │ Grado en Biotecnología (Plan 2015)                     │
│ 8  │ Grado en Ciencias Ambientales (Plan 2009)              │
│ 9  │ Grado en Matemáticas (Plan 2010)                       │
│ 10 │ Grado en Química (Plan 2009)                           │
└────┴────────────────────────────────────────────────────────┘
```

**Tabla** *persona*

``` sql
┌────┬───────────┬───────────┬────────────┬────────────┬─────────┬───────────────────────────┬───────────┬──────────────────┬──────┬──────────┐
│ id │    nif    │  nombre   │ apellido1  │ apellido2  │ ciudad  │         direccion         │ telefono  │ fecha_nacimiento │ sexo │   tipo   │
├────┼───────────┼───────────┼────────────┼────────────┼─────────┼───────────────────────────┼───────────┼──────────────────┼──────┼──────────┤
│ 1  │ 26902806M │ Salvador  │ Sánchez    │ Pérez      │ Almería │ C/ Real del barrio alto   │ 950254837 │ 1991/03/28       │ H    │ alumno   │
│ 2  │ 89542419S │ Juan      │ Saez       │ Vega       │ Almería │ C/ Mercurio               │ 618253876 │ 1992/08/08       │ H    │ alumno   │
│ 3  │ 11105554G │ Zoe       │ Ramirez    │ Gea        │ Almería │ C/ Marte                  │ 618223876 │ 1979/08/19       │ M    │ profesor │
│ 4  │ 17105885A │ Pedro     │ Heller     │ Pagac      │ Almería │ C/ Estrella fugaz         │           │ 2000/10/05       │ H    │ alumno   │
│ 5  │ 38223286T │ David     │ Schmidt    │ Fisher     │ Almería │ C/ Venus                  │ 678516294 │ 1978/01/19       │ H    │ profesor │
│ 6  │ 04233869Y │ José      │ Koss       │ Bayer      │ Almería │ C/ Júpiter                │ 628349590 │ 1998/01/28       │ H    │ alumno   │
│ 7  │ 97258166K │ Ismael    │ Strosin    │ Turcotte   │ Almería │ C/ Neptuno                │           │ 1999/05/24       │ H    │ alumno   │
│ 8  │ 79503962T │ Cristina  │ Lemke      │ Rutherford │ Almería │ C/ Saturno                │ 669162534 │ 1977/08/21       │ M    │ profesor │
│ 9  │ 82842571K │ Ramón     │ Herzog     │ Tremblay   │ Almería │ C/ Urano                  │ 626351429 │ 1996/11/21       │ H    │ alumno   │
│ 10 │ 61142000L │ Esther    │ Spencer    │ Lakin      │ Almería │ C/ Plutón                 │           │ 1977/05/19       │ M    │ profesor │
│ 11 │ 46900725E │ Daniel    │ Herman     │ Pacocha    │ Almería │ C/ Andarax                │ 679837625 │ 1997/04/26       │ H    │ alumno   │
│ 12 │ 85366986W │ Carmen    │ Streich    │ Hirthe     │ Almería │ C/ Almanzora              │           │ 1971-04-29       │ M    │ profesor │
│ 13 │ 73571384L │ Alfredo   │ Stiedemann │ Morissette │ Almería │ C/ Guadalquivir           │ 950896725 │ 1980/02/01       │ H    │ profesor │
│ 14 │ 82937751G │ Manolo    │ Hamill     │ Kozey      │ Almería │ C/ Duero                  │ 950263514 │ 1977/01/02       │ H    │ profesor │
│ 15 │ 80502866Z │ Alejandro │ Kohler     │ Schoen     │ Almería │ C/ Tajo                   │ 668726354 │ 1980/03/14       │ H    │ profesor │
│ 16 │ 10485008K │ Antonio   │ Fahey      │ Considine  │ Almería │ C/ Sierra de los Filabres │           │ 1982/03/18       │ H    │ profesor │
│ 17 │ 85869555K │ Guillermo │ Ruecker    │ Upton      │ Almería │ C/ Sierra de Gádor        │           │ 1973/05/05       │ H    │ profesor │
│ 18 │ 04326833G │ Micaela   │ Monahan    │ Murray     │ Almería │ C/ Veleta                 │ 662765413 │ 1976/02/25       │ H    │ profesor │
│ 19 │ 11578526G │ Inma      │ Lakin      │ Yundt      │ Almería │ C/ Picos de Europa        │ 678652431 │ 1998/09/01       │ M    │ alumno   │
│ 20 │ 79221403L │ Francesca │ Schowalter │ Muller     │ Almería │ C/ Quinto pino            │           │ 1980/10/31       │ H    │ profesor │
│ 21 │ 79089577Y │ Juan      │ Gutiérrez  │ López      │ Almería │ C/ Los pinos              │ 678652431 │ 1998/01/01       │ H    │ alumno   │
│ 22 │ 41491230N │ Antonio   │ Domínguez  │ Guerrero   │ Almería │ C/ Cabo de Gata           │ 626652498 │ 1999/02/11       │ H    │ alumno   │
│ 23 │ 64753215G │ Irene     │ Hernández  │ Martínez   │ Almería │ C/ Zapillo                │ 628452384 │ 1996/03/12       │ M    │ alumno   │
│ 24 │ 85135690V │ Sonia     │ Gea        │ Ruiz       │ Almería │ C/ Mercurio               │ 678812017 │ 1995/04/13       │ M    │ alumno   │
└────┴───────────┴───────────┴────────────┴────────────┴─────────┴───────────────────────────┴───────────┴──────────────────┴──────┴──────────┘
```

**Tabla** *profesor*

``` sql
┌─────────────┬─────────────────┐
│ id_profesor │ id_departamento │
├─────────────┼─────────────────┤
│ 3           │ 1               │
│ 5           │ 2               │
│ 8           │ 3               │
│ 10          │ 4               │
│ 12          │ 4               │
│ 13          │ 6               │
│ 14          │ 1               │
│ 15          │ 2               │
│ 16          │ 3               │
│ 17          │ 4               │
│ 18          │ 5               │
│ 20          │ 6               │
└─────────────┴─────────────────┘
```

# Consultas

## Consultas multitabla (Join)

1. **Devuelve un listado con el primer apellido, segundo apellido y el nombre de todos los alumnos. El listado deberá estar ordenado alfabéticamente de menor a mayor por el primer apellido, segundo apellido y nombre.**

*Consulta*

``` sql
SELECT apellido1, apellido2, nombre FROM persona WHERE tipo = "alumno" ORDER BY apellido1, apellido2, nombre ASC;
```

*Respuesta*

``` sql
┌───────────┬───────────┬──────────┐
│ apellido1 │ apellido2 │  nombre  │
├───────────┼───────────┼──────────┤
│ Domínguez │ Guerrero  │ Antonio  │
│ Gea       │ Ruiz      │ Sonia    │
│ Gutiérrez │ López     │ Juan     │
│ Heller    │ Pagac     │ Pedro    │
│ Herman    │ Pacocha   │ Daniel   │
│ Hernández │ Martínez  │ Irene    │
│ Herzog    │ Tremblay  │ Ramón    │
│ Koss      │ Bayer     │ José     │
│ Lakin     │ Yundt     │ Inma     │
│ Saez      │ Vega      │ Juan     │
│ Strosin   │ Turcotte  │ Ismael   │
│ Sánchez   │ Pérez     │ Salvador │
└───────────┴───────────┴──────────┘
```

2. **Averigua el nombre y los dos apellidos de los alumnos que no han dado de alta su número de teléfono en la base de datos.**

*Consulta*

``` sql
SELECT nombre, apellido1, apelido2, nombre FROM persona WHERE telefono IS NULL;
```

*Respuesta*

``` sql
┌───────────┬────────────┬───────────┐
│  nombre   │ apellido1  │ apellido2 │
├───────────┼────────────┼───────────┤
│ Pedro     │ Heller     │ Pagac     │
│ Ismael    │ Strosin    │ Turcotte  │
│ Esther    │ Spencer    │ Lakin     │
│ Carmen    │ Streich    │ Hirthe    │
│ Antonio   │ Fahey      │ Considine │
│ Guillermo │ Ruecker    │ Upton     │
│ Francesca │ Schowalter │ Muller    │
└───────────┴────────────┴───────────┘
```

3. **Devuelve el listado de los alumnos que nacieron en 1999.**

*Consulta*

``` sql
SELECT * FROM persona WHERE fecha_nacimiento REGEXP "^1999";
```

*Respuesta*

``` sql
┌────┬───────────┬─────────┬───────────┬───────────┬─────────┬─────────────────┬───────────┬──────────────────┬──────┬────────┐
│ id │    nif    │ nombre  │ apellido1 │ apellido2 │ ciudad  │    direccion    │ telefono  │ fecha_nacimiento │ sexo │  tipo  │
├────┼───────────┼─────────┼───────────┼───────────┼─────────┼─────────────────┼───────────┼──────────────────┼──────┼────────┤
│ 7  │ 97258166K │ Ismael  │ Strosin   │ Turcotte  │ Almería │ C/ Neptuno      │           │ 1999/05/24       │ H    │ alumno │
│ 22 │ 41491230N │ Antonio │ Domínguez │ Guerrero  │ Almería │ C/ Cabo de Gata │ 626652498 │ 1999/02/11       │ H    │ alumno │
└────┴───────────┴─────────┴───────────┴───────────┴─────────┴─────────────────┴───────────┴──────────────────┴──────┴────────┘
```

4. **Devuelve el listado de profesores que no han dado de alta su número de teléfono en la base de datos y además su nif termina en K.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

5. **Devuelve el listado de las asignaturas que se imparten en el primer cuatrimestre, en el tercer curso del grado que tiene el identificador 7.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

## Consultas multitabla (Join)

1. **Devuelve un listado con los datos de todas las alumnas que se han matriculado alguna vez en el Grado en Ingeniería Informática (Plan 2015).**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

2. **Devuelve un listado con todas las asignaturas ofertadas en el Grado en Ingeniería Informática (Plan 2015).**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

3. **Devuelve un listado de los profesores junto con el nombre del departamento al que están vinculados. El listado debe devolver cuatro columnas, primer apellido, segundo apellido, nombre y nombre del departamento. El resultado estará ordenado alfabéticamente de menor a mayor por los apellidos y el nombre.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

4. **Devuelve un listado con el nombre de las asignaturas, año de inicio y año de fin del curso escolar del alumno con nif 26902806M.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

5. **Devuelve un listado con el nombre de todos los departamentos que tienen profesores que imparten alguna asignatura en el Grado en Ingeniería Informática (Plan 2015).**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

6. **Devuelve un listado con todos los alumnos que se han matriculado en alguna asignatura durante el curso escolar 2018/2019.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

## Consultas multitabla (Where)

1. **Devuelve un listado con los nombres de todos los profesores y los departamentos que tienen vinculados. El listado también debe mostrar aquellos profesores que no tienen ningún departamento asociado. El listado debe devolver cuatro columnas, nombre del departamento, primer apellido, segundo apellido y nombre del profesor. El resultado estará ordenado alfabéticamente de menor a mayor por el nombre del departamento, apellidos y el nombre.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

2. **Devuelve un listado con los profesores que no están asociados a un departamento.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

3. **Devuelve un listado con los departamentos que no tienen profesores asociados.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

4. **Devuelve un listado con los profesores que no imparten ninguna asignatura.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

5. **Devuelve un listado con las asignaturas que no tienen un profesor asignado.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

6. **Devuelve un listado con todos los departamentos que tienen alguna asignatura que no se haya impartido en ningún curso escolar. El resultado debe mostrar el nombre del departamento y el nombre de la asignatura que no se haya impartido nunca.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

## Consultas resúmen (Funciones)

1. **Devuelve el número total de alumnas que hay.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

2. **Calcula cuántos alumnos nacieron en 1999.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

3. **Calcula cuántos profesores hay en cada departamento. El resultado sólo debe mostrar dos columnas, una con el nombre del departamento y otra con el número de profesores que hay en ese departamento. El resultado sólo debe incluir los departamentos que tienen profesores asociados y deberá estar ordenado de mayor a menor por el número de profesores.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

4. **Devuelve un listado con todos los departamentos y el número de profesores que hay en cada uno de ellos. Tenga en cuenta que pueden existir departamentos que no tienen profesores asociados. Estos departamentos también tienen que aparecer en el listado.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

5. **Devuelve un listado con el nombre de todos los grados existentes en la base de datos y el número de asignaturas que tiene cada uno. Tenga en cuenta que pueden existir grados que no tienen asignaturas asociadas. Estos grados también tienen que aparecer en el listado. El resultado deberá estar ordenado de mayor a menor por el número de asignaturas.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

6. **Devuelve un listado con el nombre de todos los grados existentes en la base de datos y el número de asignaturas que tiene cada uno, de los grados que tengan más de 40 asignaturas asociadas.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

7. **Devuelve un listado que muestre el nombre de los grados y la suma del número total de créditos que hay para cada tipo de asignatura. El resultado debe tener tres columnas: nombre del grado, tipo de asignatura y la suma de los créditos de todas las asignaturas que hay de ese tipo. Ordene el resultado de mayor a menor por el número total de crédidos.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

8. **Devuelve un listado que muestre cuántos alumnos se han matriculado de alguna asignatura en cada uno de los cursos escolares. El resultado deberá mostrar dos columnas, una columna con el año de inicio del curso escolar y otra con el número de alumnos matriculados.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

9. **Devuelve un listado con el número de asignaturas que imparte cada profesor. El listado debe tener en cuenta aquellos profesores que no imparten ninguna asignatura. El resultado mostrará cinco columnas: id, nombre, primer apellido, segundo apellido y número de asignaturas. El resultado estará ordenado de mayor a menor por el número de asignaturas.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

## Subconsultas

1. **Devuelve todos los datos del alumno más joven.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

2. **Devuelve un listado con los profesores que no están asociados a un departamento.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

3. **Devuelve un listado con los departamentos que no tienen profesores asociados.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

4. **Devuelve un listado con los profesores que tienen un departamento asociado y que no imparten ninguna asignatura.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

5. **Devuelve un listado con las asignaturas que no tienen un profesor asignado.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

6. **Devuelve un listado con todos los departamentos que no han impartido asignaturas en ningún curso escolar.**

*Consulta*

``` sql

```

*Respuesta*

``` sql

```

