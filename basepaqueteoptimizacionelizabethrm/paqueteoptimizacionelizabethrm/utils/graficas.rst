.. _graficas:

Gráficas 2D de Funciones con y sin Restricciones
==================================================

Este archivo documenta las funciones `grafica_2d_con_restricciones`, `grafica_2d_no_restricciones` y `plot_rangos_minimos` que se utilizan para generar gráficas 2D de funciones con y sin restricciones, así como para graficar puntos mínimos para distintas precisiones.

Gráfica 2D de Función con Restricciones
--------------------------------------------

.. autofunction:: grafica_2d_con_restricciones

Descripción
------------

La función `grafica_2d_con_restricciones` genera una gráfica 2D de una función con restricciones para valores de x e y. Se utiliza una grilla de resolución especificada para evaluar la función en cada punto dentro del rango dado de x e y. Los puntos fuera de un valor de restricción específico se muestran como NaN (no un número) en la gráfica.

Parámetros
-----------

- `func` (callable): Función que devuelve el valor de la función en un punto dado.
- `x_range` (tuple, opcional): Rango de valores de x para graficar (default=(-10, 10)).
- `y_range` (tuple, opcional): Rango de valores de y para graficar (default=(-10, 10)).
- `resolution` (int, opcional): Resolución de la grilla para la gráfica (default=400).
- `constraint_value` (float, opcional): Valor de restricción para la función (default=1e6).

Gráfica 2D de Función sin Restricciones
--------------------------------------------

.. autofunction:: grafica_2d_no_restricciones

Descripción
------------

La función `grafica_2d_no_restricciones` genera una gráfica 2D de una función sin restricciones explícitas para valores de x e y. Se utiliza una grilla de resolución especificada para evaluar la función en cada punto dentro de los límites dados de x e y.

Parámetros
-----------

- `function` (callable): Función que devuelve el valor de la función en un punto dado.
- `x_limits` (tuple, opcional): Límites de valores de x para graficar (default=(-10, 10)).
- `y_limits` (tuple, opcional): Límites de valores de y para graficar (default=(-10, 10)).
- `num_points` (int, opcional): Número de puntos en cada dimensión para la gráfica (default=100).

Gráfica de Puntos Mínimos para Distintas Precisiones
------------------------------------------------------

.. autofunction:: plot_rangos_minimos

Descripción
------------

La función `plot_rangos_minimos` grafica la función dada y los puntos mínimos encontrados para distintas precisiones utilizando un método de optimización específico.

Parámetros
-----------

- `funcion` (callable): Función objetivo que se desea minimizar.
- `a` (float): Límite inferior del rango de búsqueda.
- `b` (float): Límite superior del rango de búsqueda.
- `precisiones` (list): Lista de precisiones para las cuales se ejecutará el método de optimización.
- `initial_guess` (float): Valor inicial para el método de optimización.
- `metodo_optimizacion` (callable): Función que realiza el método de optimización sobre la función dada.

Ejemplo de Uso
----------------

A continuación, se muestra un ejemplo básico de cómo usar las funciones documentadas:

.. code-block:: python

    import numpy as np
    import matplotlib.pyplot as plt

    # Definir una función con restricciones
    def funcion_restriccion(pos):
        return np.sin(pos[:, 0]) * np.cos(pos[:, 1])

    # Generar gráfica con restricciones
    grafica_2d_con_restricciones(funcion_restriccion)

    # Definir una función sin restricciones
    def funcion_sin_restriccion(pos):
        return pos[0]**2 + pos[1]**2

    # Generar gráfica sin restricciones
    grafica_2d_no_restricciones(funcion_sin_restriccion)

    # Ejemplo de uso de plot_rangos_minimos
    def funcion_ejemplo(x):
        return np.sin(x) / x

    precisiones_ejemplo = [1e-2, 1e-3, 1e-4]
    plot_rangos_minimos(funcion_ejemplo, -10, 10, precisiones_ejemplo, 0, interval_halving_method)


