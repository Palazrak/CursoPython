# 2. Python Básico

En esta sección se aprenderán los elementos que considero más básicos de Python. Con estas herramientas, se pueden hacer problemas bastante complejos de forma legible y eficiente. No incluí en esta sección a las Clases y Funciones solo para no abrumar entrando de lleno con Programación Orientada a Objetos.

En esta sección se planea implementar tanto las notas de la sección como ejercicios de código. Estos ejercicios podrán abrirse en Google Colab o podrían trabajarse en la computadora en caso de tener Jupyter o VSCode.

## 2.1. Variables y manejo de memoria

Pensémoslo de la forma mas sencilla posible. Al programar, nosotros asignamos nombres a objetos para que sea más fácil para nosotros trabajar con esos objetos. Un objeto puede ser muchas cosas: una instancia de una clase, un tipo primitivo, una estructura de datos, etc. (Más adelante entraremos en detalles de todas las palabras nuevas que acabo de utilizar).

Al nosotros asignarle un nombre a un objeto, estamos creando una **variable**. Esta variable va a almacenarse en la memoria de la computadora (Python lo hace automáticamente por nosotros). Por ejemplo, si yo tomo el siguiente codigo:

```python
a = 0
b = "Hola"
```

Lo que estoy haciendo es crear variables `a` y `b` y almacenar en memoria los valores `0` y `"hola"` respectivamente. Esto nos va a permitir que, si nosotros queremos hacer operaciones sobre esas variables, podamos solo hacer referencias a esos nombres, sin tener que indicarle a la computadora a qué espacios de la memoria acceder para hacer las operaciones.

## 2.2. Tipos de datos primitivos en Python

Python tiene un pequeño conjunto de tipos de datos primitivos para manejar datos numéricos, cadenas de caracteres, valores booleanos y fechas. Normalmente a estos tipos de datos se les llama `escalares` (ignorando la noción de "escalar" en álgebra lineal).

Los principales tipos escalares son:

| Tipo de dato | Descripción                    |
| ------------- | ------------------------------ |
| `bytes`      | Valores binarios sin procesar       |
| `int`   | Enteros de precisión arbitraria     |
| `float`      | Valores de punto flotante de doble precisión      |
| `bool`   | Valores booleanos `True` o `False`    |
| `str`      | Cadena de caracteres       |
| `None`   | Valor "nulo" en Python     |

### 2.2.1. Datos numéricos

Para los datos numéricos, están definidas las siguientes operaciones:

| Operación | Descripción                    |
| ------------- | ------------------------------ |
| a + b      | Suma de `a` y `b`       |
| a - b      | Diferencia de `a` y `b` (resta a `b` de `a`)       |
| a * b      | Multiplica `a` por `b`      |
| a / b   | Divide `a` entre `b`    |
| a // b      | División entera de `a` entre `b` (quita los decimales)       |
| a ** b   | Elevar `a` a la `b` (operador potencia)     |
| a == b      | Arroja `True` si `a` es igual a `b`       |
| a != b      | Arroja `True` si `a` es diferente a `b` |
| a < b, a <= b            | Arroja `True` si `a` es menor (menor o igual) a `b`      |
| a > b, a >= b   | Arroja `True` si `a` es mayor (mayor o igual) a `b`|
| a `is` b      | Arroja `True` si `a` y `b` están referenciados al mismo objeto|
| a `is not` b   | Arroja `True` si `a` y `b` no están referenciados al mismo objeto |

También están definidas operaciones "bitwise", como AND (`a & b`), OR (`a | b`) y XOR (`a ^ b`).

### 2.2.2. Datos booleanos

Para valores booleanos, están definidas las siguientes operaciones

| Operación | Descripción                    |
| ------------- | ------------------------------ |
| a == b      | Arroja `True` si `a` es igual a `b`       |
| a != b      | Arroja `True` si `a` es diferente a `b` |
| a `is` b      | Arroja `True` si `a` y `b` están referenciados al mismo objeto|
| a `is not` b   | Arroja `True` si `a` y `b` no están referenciados al mismo objeto |

También están definidas operaciones lógicas AND (`a & b`), OR (`a | b`) y XOR (`a ^ b`).

### 2.2.3. Datos String

En otros lenguajes de programación, como en Java, el tipo de dato primitivo es un `char` (es decir, únicamente un caracter). En Python no existe el tipo de dato `char`, y existe únicamente la cadena de caracteres `str`. Sin embargo, con estas cadenas de caracteres podemos hacer muchas cosas, por ejemplo:

- Separar la cadena en varias partes a partir de cierta posición o caracter
- Quitar los espacios en blanco
- Pasar todo a mayúsculas o minúsculas
- Preguntar si la cadena contiene cierto caracter o secuencia de caracteres

Otra maravilla que tienen los strings en Python es el uso de `f strings`. Esto es una forma de crear mensajes con cierto formato pero que durante la ejecución puede variar según el estado actual de las variables. Por ejemplo:

```python

nombre = "Juan"
apellido = "Escutia"
print(f{"¡Hola, {nombre} {apellido}!"})
```

> ¡Hola, Juan Escutia!

## 2.3. User inputs

En muchas ocasiones, necesitamos que el usuario nos de información relevante para poder ejecutar un programa. Por ejemplo, si estamos desarrollando una aplicación y necesitamos el nombre del usuario, es necesario indicarle a Python que queremos recibir esa información de forma externa. La forma en la que hacemos esto es con el siguiente comando:

```python
nombre = input("Ingrese el nombre")
```

Lo que está haciendo el código anterior es que está imprimiendo en la terminal el mensaje "ingrese el nombre" y permite que el usuario teclee cualquier cosa. Al dar `enter`, lo que haya ingresado el usuario se guardará en la variable `nombre`, con la que después podrás trabajar.

Es importante notar que, como mencioné, así como está el código, el usuario podría ingresar cualquier cosa: un número, una frase que no sea un nombre o incluso no ingresar nada. Todo esto será necesario manejarlo correctamente utilizando if statements. Además, cualquier input del usuario será considerado como String por default. Si estás ingresando un número, puedes cambiarle el tipo después.

```python
numero = input("Dame un número")
numero = int(numero)
```

## 2.4. Condiciones lógicas e "if statements"

Las condiciones lógicas y los if statements son una parte esencial de cualquier lenguaje de programación, incluido Python. Nos permiten tomar decisiones en el código basándonos en ciertos criterios, haciendo que el programa sea dinámico y pueda reaccionar a diferentes situaciones.

### 2.4.1. Condiciones lógicas

Las condiciones lógicas son expresiones que se evalúan como True (verdadero) o False (falso). Estas expresiones se construyen utilizando operadores lógicos y relacionales.

| Operadores Relacionales | Descripción                    |
| ------------- | ------------------------------ |
|  == (igual) | Verifica si dos valores son iguales |
| != (diferente)     | Verifica si dos valores son diferentes|
| > (mayor que)      | Verifica si el primer valor es mayor que el otro |
| >= (mayor o igual que)      | Verifica si el primer valor es mayor o igual que el otro |
| < (menor que)      | Verifica si el primer valor es menor que el otro |
| <= (menor o igual que)      | Verifica si el primer valor es menor o igual que el otro |

| Operadores Lógicos | Descripción                    |
| ------------- | ------------------------------ |
|  `and` | Devuelve True si ambas condiciones son verdaderas |
| `or`   | Devuelve True si al menos una condición es verdadera|
| `not`    | Invierte el valor lógico |

### 2.4.2. If statements

Los "if statements" son estructuras que permiten que el programa tome decisiones basadas en condiciones lógicas. En Python, se usa la palabra reservada `if` para definirlos.

La sintaxis básica es:

```python
if condición:
    # Código a ejecutar si la condición es verdadera
```

Por ejemplo, supongamos que se le solicita al usuario ingresar su edad para detemrinar si es mayor de edad o no. Un ejemplo de uso de un if simple es:

```python
if edad >= 18:
    print("Eres mayor de edad")
```

Es muy importante notar que, para que el intérprete de Python ejecute correctamente el código, debe haber una sangría para denotar qué cae dentro de cada if. Esta sangría se acostumbra a hacer con un tab sencillo, mientras que otras personas lo hacen con 4 espacios. Lo importante es que **no se pueden mezclar tabs y espacios**, así que elige solo uno.

Como extensiones de los "if statements", también se tienen las palabras reservadas `elif` y `else`. Esto es importante cuando nuestro proceso se separe dependiendo de si la condición es verdadera o falsa. Por ejemplo, si yo quiero ver cuál es el número más alto entre dos opciones para posteriormente imprimirlo, es necesario el uso de `if` y de `else` para contemplar completamente todos los casos posibles.

```python
# Suponiendo que ya están definidos valores `a` y `b`
if a > b:
    print(a)
else:
    print(b) 
```

Por último, hablemos de las diferencias entre `elif` y `else`. `elif` se usa para comprobar condiciones adicionales si la condición inicial del if no se cumple. Es útil cuando tienes múltiples caminos posibles. Por otro lado, `else` se usa como una opción por defecto si todas las condiciones anteriores son falsas. Es como un "cajón de seguridad" que asegura que siempre haya un resultado.

Aquí un pequeño ejemplo que incorpora el uso de `if`, `elif` y `else` para imprimir mensajes distintos dependiendo del intervalo en el que caiga cierto valor:

```python
# Suponiendo una variable "nota" que represente una calificación:
if nota >= 90:
    print("Excelente")
elif nota >= 70:
    print("Aprobado")
elif nota >= 50:
    print("Necesita mejorar")
else:
    print("Reprobado")
```

## 2.5. Estructuras de datos nativas de Python

### 2.5.1. Listas

### 2.5.2. Tuplas

### 2.5.3. Conjuntos

### 2.5.4. Diccionarios

## 2.6. Ciclos "for" y "while"

## 2.7. Lectura de archivos
