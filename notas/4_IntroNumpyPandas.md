# 4. Introducción a NumPy y Pandas

## 4.1. NumPy

### 4.1.1. Introducción a NumPy

NumPy (Numerical Python) es una biblioteca fundamental para la computación científica en Python. Fue creada para ofrecer una manera eficiente y rápida de trabajar con datos numéricos, permitiendo operaciones complejas en grandes volúmenes de datos. Las operaciones con listas nativas de Python son lentas cuando se manejan grandes volúmenes de datos, ya que Python no está optimizado para cálculos numéricos a bajo nivel, mientras que **NumPy utiliza C internamente**, lo que lo hace mucho más rápido y eficiente en términos de memoria.

Además, NumPy permite realizar operaciones matemáticas en todos los elementos de un arreglo sin necesidad de usar ciclos explícitos, lo que se conoce como **computación vectorizada**. Esto simplifica el código y mejora el rendimiento, además de proporcionar funciones optimizadas para trabajar con matrices, álgebra lineal, transformadas de Fourier, estadística, entre otros.

### 4.1.2. Arreglos en NumPy

Un **arreglo** (array) es una estructura de datos muy común en programación. Básicamente (y con palabras un poco a la ligera), son espacios en blanco que dejas en la memoria para llenarlos de lo que tu quieras. Su estructura rígida hace que debas tener cuidado con el manejo de la memoria, para evitar tener problemas como querer insertar un elemento en un arreglo cuando ya está lleno.

Para crear arreglos en NumPy, hay varias formas de hacerlo. Por ejemplo, puedes crear un arreglo a partir de una lista:

```python
import numpy as np
lista = [1, 2, 3, 4]
arreglo = np.array(lista)
print(arreglo)  # Salida: [1 2 3 4]
```

También se puede crear un arreglo directamente usando el paquete de NumPy con alguno de los siguientes métodos:

- **np.zeros(shape)**: Arreglo lleno de ceros
- **np.ones(shape)**: Arreglo lleno de unos
- **np.arange(start, stop, step)**: Similar a range, pero devuelve un arreglo
- **np.linspace(start, stop, num)**: Divide el rango en num partes iguales

También es posible crear arreglos con números generados aleatoriamente:

- **np.random.rand(size)**: Genera números aleatorios entre 0 y 1
- **np.random.randint(low, high, size)**: Genera enteros aleatorios en un rango
- **np.random.randn(size)**: Genera números aleatorios siguiendo una distribución normal estándar
- **np.random.normal(loc, scale, size)**: Genera números aleatorios siguiendo una distribución normal personalizada (con media y desviación estándar especificadas)
- **np.random.uniform(low, high, size)**: Genera números aleatorios en un rango con distribución uniforme
- **np.random.poisson(lam, size)**: Genera números aleatorios de una distribución de Poisson
- **np.random.binomial(n, p, size)**: Genera números aleatorios de una distribución binomial
- **np.random.exponential(scale, size)**: Genera números aleatorios de una distribución exponencial

Para asegurar reproducibilidad al ejecutar un código que trabaja con numeros generados de forma pseudoaleatoria, se utiliza una **semilla**. En el caso de NumPy, la forma de fijar una semilla es con el comando `np.random.seed()`, donde dentro de los paréntesis se ingresa un número entero.

### 4.1.3. Computación Vectorizada

Computación vectorizada significa realizar operaciones matemáticas en un arreglo completo (o en múltiples arreglos) sin usar ciclos explícitos. Esto es mucho más rápido que iterar manualmente con un ciclo `for`.

Un ejemplo de lo anterior es el siguiente: supongamos que, en una lista clásica, deseamos elevar cada uno de los elementos de la lista al cuadrado. La única forma de realizar esto es con un ciclo `for`, y el código sería parecido al siguiente:

```python
lista = [1, 2, 3, 4]

# Usando un ciclo
resultado = [x ** 2 for x in lista]
print(resultado)  # Salida: [1, 4, 9, 16]
```

En cambio, usando computación vectorizada, el codigo se reduce a:

```python
import numpy as np
arreglo = np.array([1, 2, 3, 4])

# Computación vectorizada
resultado = arreglo ** 2
print(resultado)  # Salida: [ 1  4  9 16]

```

Quizá al trabajar con poca cantidad de elementos, la ganancia en tiempo de ejecución no es mucha; sin embargo, al comenzar a trabajar con grandes volúmenes de datos, trabajar con computación vectorizada puede hacer que el tiempo de ejecución se vea significativamente reducido. Además, se prefiere usar computación vectorizada sobre listas clásicas cuando deseemos hacer cálculos matemáticos complejos e incluso para escribir código más claro y "limpio".
