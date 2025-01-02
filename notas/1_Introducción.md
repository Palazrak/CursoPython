# 1. Introducción a Python

Muchas veces queremos saltar directo a crear nuestro primer programa, o a hacer cosas que apantayen mucho a nuestros conocidos, pero es importante entender qué es lo que está pasando de fondo para usar correctamente esta herramienta. Conocer un poquito del "detrás de cámara" de Python nos ayudará mucho a entender cómo funciona, cuándo debe usarse y cómo debe usarse para evitarnos problemas en el futuro.

## 1.1. Qué es Python

Traduciendo la definición oficial de python, que se encuentra en el siguiente [link](https://www.python.org/doc/essays/blurb/):

> Python es un lenguaje de programación de alto nivel, orientado a objetos e interpretado con semántica dinámica

Desglocemos de forma muy general qué significa esto (no entraré en mucho detalle porque no es el objetivo del curso, pero si te interesa, considera buscar en internet).

- Que sea un lenguaje de programacion de alto nivel significa que en lugar de usar ceros y unos (que es lo que la máquina entiende), se usan palabras y símbolos lógicos y significativos.
- Que sea orientado a objetos significa que puedes crear clases y objetos con atributos y métodos propios.
- Que sea interpretado significa que es leído y ejecutado línea por línea por un "intérprete", en lugar de ser compilado directamente en código máquina
- Que tenga semántica dinámica significa que sus objetos son dinámicos. El lenguaje te permite asignar variables en una forma que te hace mas sentido a tí que a la computadora.

El intérprete de Python es un programa escrito en otro lenguaje de programación, comúnmente **C**. Esto significa que, cuando ejecutas un programa en Python:

1. El intérprete lee tu código
2. Lo traduce a un formato intermedio llamado bytecode
3. Ese bytecode es procesado por una "máquina virtual" (Python Virtual Machine, PVM), que ejecuta las instrucciones

## 1.2. Cuándo usar Python

Python es un lenguaje de programación de propósito general y con una sintaxis muy sencilla. Esto lo hace muy facil de aprender para cualquier persona, y al ser un lenguaje de programación tan usado, hay mucho material de apoyo repartido en la web. Sin embargo, que sea tan accesible para las personas, tiene su costo a nivel máquina.

Esto quiere decir que, dado que Python hace muchas cosas por el usuario (como alocar memoria, manejo de variables, etc), y dado que es interpretado, normalmente Python es mas lento y más pesado computacionalmente que otros lenguajes de programación. Eso se puede volver en un problema cuando estamos manejando grandes volúmenes de datos, pero en general, cuando hablamos de usos menos especializados, esos defectos no suelen afectar mucho.

Python tiene su propia "filosofía", llamada el **Zen de Python**, que a la vez fija las convenciones que se siguen al escribir código en Python. Por si te da curiosidad, lo incluiré aquí debajo:

> Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.[c]
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than right now.[d]
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea – let's do more of those!

## 1.3. Instalación de Python (Conda)

Para instalar Python, en este curso sugeriré instalar directamente `Anaconda`. La razón principal es que es mucho más fácil de usar y más intuitivo para usuarios no especializados. Sin embargo, es importante reconocer que instalar Anaconda es bastante pesado, y normalmente sugeriría instalar `miniconda`.

### 1.3.1. Qué es Conda y por qué es importante

Cuando instalas Python directamente en tu computadora, el sistema de gestion de paquetes *default* es `pip` (preferred installer program). `pip` es una herramienta que permite instalar y gestionar bibliotecas y dependencias adicionales que no existen por default en Python (como NumPy, Pandas, etc). El problema es que, si instalas dependencias directamente en el Python del sistema, podría haber conflictos entre dependencias y Python podría dejar de funcionar. En sistemas operativos como Windows no es tan grave, pero en sistemas operativos como IOS, que usan Python para manejar operaciones del sistema operativo, eso puede ser fatal.

Conda es una herramienta para crear **ambientes virtuales** en tu Python. Imagina que cada ambiente virtual es una cajita, donde en cada cajita están los paquetes y dependencias que necesitas para cada proyecto. Eso hace que no afectes el Python del sistema, y que cualquier error de manejo de dependencias pueda ser tratable (cambiando las versiones, eliminando y creando otro ambiente virtual, etc).

### 1.3.2. Otras alternativas a Conda

Si se desea no usar Conda (porque los ambientes virtuales son más pesados), otras alternativas para crear ambientes virtuales son `pyenv` o directamente crear un ambiente virtual en tu carpeta actual usando `venv`. Conda tiene un mejor manejo de dependencias, y hay algunos casos de uso en donde se recomienda directamente usar Conda (por ejemplo, en aplicaciones de Machine Learning que usen paquetes y versiones muy especificos). Además, Conda es un poco más amigable al evitarte tener que interactuar con la terminal.

### 1.3.3. Instalando Conda

Para instalar Anaconda, se seguirá el tutorial oficial de su página web: [Link](https://docs.anaconda.com/anaconda/install/). En esa misma página aparece como instalar miniconda en lugar de anaconda.
