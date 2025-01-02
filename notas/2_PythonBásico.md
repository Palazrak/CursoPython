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

## 2.2. Tipos de datos nativos en Python

Python tiene un pequeño conjunto de tipos de datos nativos para manejar datos numéricos, cadenas de caracteres, valores booleanos y fechas. Normalmente a estos tipos de datos se les llama `escalares` (ignorando la noción de "escalar" en álgebra lineal).

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

Es importante notar que, como mencioné, así como está el código, el usuario podría ingresar cualquier cosa: un número, una frase que no sea un nombre o incluso no ingresar nada. Todo esto será necesario manejarlo correctamente utilizando if statements

## 2.4. Condiciones lógicas e "if statements"

## 2.5. Estructuras de datos nativas de Python

### 2.5.1. Listas

### 2.5.2. Tuplas

### 2.5.3. Conjuntos

### 2.5.4. Diccionarios

## 2.6. Ciclos "for" y "while"
