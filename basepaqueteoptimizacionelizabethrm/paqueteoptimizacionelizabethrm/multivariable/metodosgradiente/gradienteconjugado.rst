.. _gradienteconjugado:

Método del Gradiente Conjugado
==============================

Esta sección describe la implementación del método de gradiente conjugado para la optimización.

.. autofunction:: optimizacioneli.multivariable.gradienteconjugado
   :noindex:

Implementación del Método de Gradiente Conjugado
------------------------------------------------

La función `gradiente conjugado` implementa el método de gradiente conjugado para la optimización de funciones escalares. Admite varios métodos de búsqueda unidireccional para encontrar un tamaño de paso (`alpha`) adecuado durante cada iteración:

- **Búsqueda Fibonacci**: Utiliza el algoritmo de búsqueda Fibonacci para encontrar `alpha`.
- **Método de Newton-Raphson**: Utiliza el método de Newton-Raphson para encontrar `alpha`.
- **Búsqueda de la Sección Dorada**: Aplica la búsqueda de la sección dorada para determinar `alpha`.
- **Método de Intervalo de Mitad**: Implementa el método de intervalo de mitad para `alpha`.
- **Método de Fase de Limitación**: Utiliza el método de fase de limitación para encontrar `alpha`.
- **Método de Búsqueda Exhaustiva**: Aplica la búsqueda exhaustiva para determinar `alpha`.
- **Método de Bisección**: Implementa el método de bisección para encontrar `alpha`.
- **Método de Secante**: Utiliza el método de la secante para determinar `alpha`.

Cada uno de estos métodos ofrece diferentes enfoques para determinar el tamaño de paso `alpha` basado en el comportamiento de la función.

Función de Gradiente
--------------------

La función de gradiente calcula el gradiente de una función en un punto dado utilizando aproximaciones numéricas de las derivadas parciales.

Parámetros
^^^^^^^^^^
- ``f`` (callable): Función cuyo gradiente se desea calcular.
- ``x`` (array-like): Punto en el cual se evalúa el gradiente.
- ``deltaX`` (float, optional): Paso para la aproximación numérica de las derivadas parciales. Por defecto es 0.001.

Retorna
^^^^^^^
- ``list``: Gradiente de ``f`` en ``x``.

Ejemplo de Uso
^^^^^^^^^^^^^^

.. code-block:: python

   import numpy as np
   from optimizacioneli.multivariable import gradiente

   # Definir una función de prueba
   def f(x):
       return x[0]**2 + x[1]**2

   # Punto en el cual evaluar el gradiente
   x = np.array([1.0, 2.0])

   # Calcular el gradiente
   gradient = gradiente(f, x)
   print("Gradiente en {}: {}".format(x, gradient))


Método de Gradiente Conjugado
-----------------------------

El método de gradiente conjugado es un método iterativo para la minimización de funciones que utiliza la dirección conjugada de búsqueda para actualizar iterativamente el punto de evaluación.

Parámetros
^^^^^^^^^^
- ``f`` (callable): Función objetivo a minimizar.
- ``x0`` (array-like): Punto inicial de búsqueda.
- ``epsilon1`` (float): Tolerancia para el paso de línea.
- ``epsilon2`` (float): Tolerancia para la norma del cambio relativo.
- ``epsilon3`` (float): Tolerancia para la norma del gradiente.
- ``metodo`` (str): Método para la búsqueda de paso de línea ('biseccion', 'interval', 'bounding', 'secante', 'exhaustiva', 'dorado', 'fibonacci', 'newton').

Retorna
^^^^^^^
- ``array-like``: Punto óptimo encontrado que minimiza la función ``f``.

Ejemplo de Uso
^^^^^^^^^^^^^^

.. code-block:: python

   import numpy as np
   from optimizacioneli.multivariable import conjugate_gradient

   # Definir una función de prueba
   def f(x):
       return x[0]**2 + x[1]**2

   # Punto inicial y parámetros
   x0 = np.array([1.0, 2.0])
   epsilon1 = 1e-5
   epsilon2 = 1e-5
   epsilon3 = 1e-5
   metodo = 'biseccion'  # Seleccionar método de búsqueda de paso

   # Aplicar el método de gradiente conjugado
   optimal_point = conjugate_gradient(f, x0, epsilon1, epsilon2, epsilon3, metodo)
   print("Punto óptimo encontrado:", optimal_point)
