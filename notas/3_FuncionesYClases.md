# 3. Funciones y Clases

En este módulo, exploraremos dos conceptos fundamentales en Python y la programación en general: funciones y clases. Estos conceptos no solo simplifican el desarrollo de software, sino que también permiten crear programas más estructurados, reutilizables y fáciles de mantener.

## 3.1. Funciones

Una **función** es un bloque de código reutilizable que realiza una tarea específica. En Python, las funciones permiten:

- Dividir un programa en partes más pequeñas y manejables
- Reutilizar código
- Construir programas modulares, que son más fáciles de leer y depurar

En Python, para definir una función, se utiliza la palabra reservada `def`, seguida del nombre que se le dará a la función y de los argumentos que recibirá la función (variables que se dan a la función para poder trabajar con ellas). La sintaxis más sencilla para definir una funcion es:

```python
def funcion(argumento):
    # Aquí se escribe el código
```

Un ejemplo muy sencillo de una función para sumar cualesquiera dos números es:

```python
def sumar(a,b):
    return a + b
```

Para utilizar la función que definimos, podemos hacerlo de la siguiente forma:

```python
sumar(3,4)
```

También existe la opción de tener valores por defecto, lo cual podría ser útil para garantizar que el método funcione de la forma esperada incluso aunque no se reciba toda la información:

```python
def sumar(a,b = 5):
    return a + b
```

> Así, incluso aunque no se reciba explicitamente el valor de b, basta con recibir el valor de "a" para hacer la operación correpsondiente.

## 3.2. Programación Orientada a Objetos y Clases

Las clases son un componente fundamental de la Programación Orientada a Objetos (POO), un paradigma de programación que organiza el código en torno a "objetos" que combinan datos (atributos) y comportamiento (métodos).

Según el paradigma de la Programación Orientada a Objetos, cada objeto tiene un **estado**, representado por sus **atributos** (las variables que describen el estado o las propiedades del objeto), y un **comportamiento**, representado por los **métodos** (funciones que definen el comportamiento) que contiene.

Los principios fundamentales de la Programación Orientada a Objetos son:

1. **Encapsulación**: Agrupa datos y métodos que operan sobre esos datos en una sola unidad (clase).
2. **Abstracción**: Permite enfocarse en los aspectos relevantes del objeto, ocultando detalles innecesarios.
3. **Herencia**: Permite que una clase (hija) derive de otra clase (padre), reutilizando atributos y métodos.
4. **Polimorfismo**: Permite que un mismo método se comporte de manera diferente según el contexto.

Podemos ver también a una clase es como un plano o molde para crear objetos. **Cada objeto es una instancia de una clase**.

Para crear una clase en Python, siempre es necesario comenzar con un método `__init__`, al cuál se le conoce como **constructor**; éste método nos permite crear un objeto y asignarle sus atributos. Cada método contenido dentro de una clase debe comenzar recibiendo como argumento al `self`.

Un ejemplo de cómo crear una clase en Python es la siguiente:

```python
class Persona:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad
    
    def saludar(self):
        return f"Hola, mi nombre es {self.nombre} y tengo {self.edad} años."
```

Ahora, si desearamos crear a un objeto de tipo `Persona` y usar sus métodos, lo haríamos de la siguiente forma:

```python
# Creamos a un objeto tipo persona
persona1 = Persona("Luis", 30)

# Utilizamos el método "saludar" e imprimimos el resultado
print(persona1.saludar())
```
