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

## 4.2. Pandas

### 4.2.1. Introducción a Pandas

**Pandas** es una biblioteca de Python diseñada para el análisis y manipulación de datos. Es una herramienta poderosa y flexible que permite trabajar fácilmente con datos tabulares y estructurados. Pandas se basa en NumPy, lo que la hace rápida y eficiente, y es ampliamente utilizada en ciencia de datos, análisis de datos y aprendizaje automático.

Pandas fue creado específicamente para facilitar en análisis de datos tabulares (como tablas de excel o tablas en bases de datos relacionales) ofreciendo funciones para filtrar, agrupar, pivotar y limpiar datos, entre otras. Puede leer y escribir datos desde múltiples formatos (csv, excel, json, etc.) y ofrece operaciones rápidas y optimizadas para datos grandes, aprovechando las capacidades de NumPy.

### 4.2.2. Principales estructuras de datos en Pandas

#### 4.2.2.1. Series

Una **Serie** es una estructura de datos unidimensional que puede contener elementos de cualquier tipo (números, cadenas, etc.); es similar a una lista o un arreglo de NumPy, con la diferencia de que tiene un **índice** asociado a cada elemento. 

```python
import pandas as pd

# Crear una Serie desde una lista
serie = pd.Series([10, 20, 30, 40])
print(serie)
# Salida:
# 0    10
# 1    20
# 2    30
# 3    40
# dtype: int64
```

Su principal ventaja es que los índices pemriten acceder directamente a los elementos y, a diferencia de los arreglos y las listas, las series pueden tener un **índice personalizado**, como un String.

```python
serie = pd.Series([10, 20, 30], index=["a", "b", "c"])
print(serie["b"])  # Salida: 20

```

#### 4.2.2.2. DataFrames

Un **DataFrame** es una estructura de datos **bidimensional** (tabla) con filas y columnas. Cada columna es una **Serie**, y todas las columnas comparten el mismo índice de filas.

```python
# Crear un DataFrame desde un diccionario
datos = {
    "Nombre": ["Ana", "Luis", "Carlos"],
    "Edad": [25, 30, 35],
    "Ciudad": ["Madrid", "Barcelona", "Sevilla"]
}
df = pd.DataFrame(datos)
print(df)
# Salida:
#    Nombre  Edad      Ciudad
# 0     Ana    25      Madrid
# 1    Luis    30  Barcelona
# 2  Carlos    35     Sevilla

```

Las características claves de los DataFrames son:

- Puedes acceder a columnas como Series:
  
```python
print(df["Nombre"])  # Salida: Serie con nombres
```

- Permite realizar operaciones por filas o columnas:
  
```python
print(df["Edad"].mean())  # Promedio de las edades

```

### 4.2.3. Principales métodos y funcionalidades de Pandas

1. Importar y exportar datos

   - Leer archivos desde diferentes formatos:
  
    ```python
    df = pd.read_csv("archivo.csv")  # Leer un archivo CSV
    df = pd.read_excel("archivo.xlsx")  # Leer un archivo Excel
    ```

   - Exportar datos:

    ```python
    df.to_csv("archivo.csv", index=False)  # Guardar como CSV
    df.to_excel("archivo.xlsx", index=False)  # Guardar como Excel
    ```

2. Selección y acceso a datos

    - Selección de columnas:
  
    ```python
    df["Edad"]  # Seleccionar una columna
    df[["Nombre", "Edad"]]  # Seleccionar múltiples columnas
    ```

   - Selección de filas: Por índice con `.loc` o por posición con `.iloc`

    ```python
    print(df.loc[1])  # Fila con índice 1
    print(df.iloc[0])  # Primera fila
    ```

3. Filtrado de datos

    ```python
    mayores = df[df["Edad"] > 30]
    print(mayores)
    ```

4. Operaciones básicas:

    - Estadisticas descriptivas:
  
    ```python
    print(df.describe())  # Resumen estadístico
    print(df["Edad"].sum())  # Suma de una columna
    ```

   - Modificar valores:

    ```python
    df["Edad"] = df["Edad"] + 1  # Incrementar edades
    ```

5. Manejo de datos faltantes

    - Identificar valores faltantes:
  
    ```python
    print(df.isnull())  # Ver valores nulos
    ```

   - Rellenar o eliminar datos faltantes:

    ```python
    df.fillna(0, inplace=True)  # Rellenar valores nulos con 0
    df.dropna(inplace=True)  # Eliminar filas con valores nulos
    ```

6. Agrupación y operaciones avanzadas

    - Agrupar datos:
  
    ```python
    df.groupby("Ciudad")["Edad"].mean()  # Promedio de edad por ciudad
    ```

   - Rellenar o eliminar datos faltantes:

    ```python
    tabla_pivote = df.pivot_table(values="Edad", index="Ciudad")
    ```
