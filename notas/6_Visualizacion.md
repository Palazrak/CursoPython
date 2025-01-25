# 6. Visualización de datos usando Matplotlib y Seaborn

**Matplotlib** es una biblioteca de Python utilizada para crear gráficos y visualizaciones de datos. Es una de las herramientas más populares en ciencia de datos y análisis porque proporciona una forma sencilla y flexible de representar datos en gráficos bidimensionales. Suele usarse a través de su submódulo `pyplot`, que simplifica la creación de gráficos.

La sintaxis general para hacer una gráfica es la siguiente:

```python
# Importamos la libreria
import matplotlib.plt as plt

# Creamos un objeto "Figure"
fig = plt.figure()

# Creamos una subgráfica que se visualiza sobre la figura
ax = fig.add_subplot()

# Suponiendo que ya tienes una coleccion `datos`
ax.plot(datos)
```

Los principales argumentos para personalizar tu gráfica son los siguientes:

|Argumento|Descripción|
|---------|-----------|
|`label`|Texto que se usa para describir una serie o línea en la leyenda de la gráfica. Se asigna con `ax.legend()` para mostrarla|
|`ax`|Objeto de tipo `Axes` donde se dibuja la gráfica. Permite controlar en qué gráfico específico se muestra cuando hay múltiples subgráficas|
|`style`|Estilo de la línea o gráfico, como color, tipo de línea o marcador. Por ejemplo, "r--" (línea roja discontinua)|
|`alpha`|Nivel de transparencia del gráfico. Va de 0 (completamente transparente) a 1 (completamente opaco)|
|`kind`|Tipo de gráfico que se quiere generar (aplicable en pandas o seaborn). Puede ser "area", "bar", "barh", "density", "kde", "line" o "pie"|
|`figsize`|Tamaño de la figura en pulgadas. Se define como una tupla `(ancho, alto)`|
|`logx`|Si es `True`, establece una escala logarítmica en el eje X. Útil para representar datos distribuidos exponencialmente|
|`logy`|Si es `True`, establece una escala logarítmica en el eje Y|
|`title`|Texto que aparece como el título de la gráfica. Puede configurarse con `ax.set_title()`|
|`rot`|Rotación de las etiquetas del eje X o Y en grados. Útil para mejorar la legibilidad cuando las etiquetas son largas|
|`xticks`|Lista de posiciones específicas donde se colocan las etiquetas en el eje X. También se puede usar para personalizar los valores de las etiquetas|
|`yticks`|Lista de posiciones específicas donde se colocan las etiquetas en el eje Y|
|`xlim`|Límite del rango del eje X. Se define como una tupla `(min, max)`.|
|`ylim`|Límite del rango del eje Y. Se define como una tupla `(min, max)`|
|`grid`|Si es `True`, agrega líneas de cuadrícula a la gráfica|
