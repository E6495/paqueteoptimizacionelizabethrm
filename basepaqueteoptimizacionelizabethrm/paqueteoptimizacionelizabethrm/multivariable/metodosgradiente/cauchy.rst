.. _cauchy:

Método del Cauchy
================

Esta sección describe la implementación del método de Cauchy para la optimización.

.. autofunction:: optimizacioneli.multivariable.cauchy
   :noindex:

Implementación del Método de Cauchy
-----------------------------------

La función `Cauchy` implementa el método de Cauchy para la optimización de funciones escalares. Admite varios métodos de búsqueda unidireccional para encontrar un tamaño de paso (`alpha`) adecuado durante cada iteración:

- **Búsqueda Fibonacci**: Utiliza el algoritmo de búsqueda Fibonacci para encontrar `alpha`.
- **Método de Cauchy-Raphson**: Utiliza el método de Cauchy-Raphson para encontrar `alpha`.
- **Búsqueda de la Sección Dorada**: Aplica la búsqueda de la sección dorada para determinar `alpha`.
- **Método de Intervalo de Mitad**: Implementa el método de intervalo de mitad para `alpha`.
- **Método de Fase de Limitación**: Utiliza el método de fase de limitación para encontrar `alpha`.
- **Método de Búsqueda Exhaustiva**: Aplica la búsqueda exhaustiva para determinar `alpha`.
- **Método de Bisección**: Implementa el método de bisección para encontrar `alpha`.
- **Método de Secante**: Utiliza el método de la secante para determinar `alpha`.

Cada uno de estos métodos ofrece diferentes enfoques para determinar el tamaño de paso `alpha` basado en el comportamiento de la función.

Función de Gradiente
-----------------------------------

La función de gradiente calcula el gradiente de una función en un punto dado utilizando aproximaciones numéricas de las derivadas parciales.

   Parámetros
   ----------
   - ``f`` (callable): Función cuyo gradiente se desea calcular.
   - ``x`` (array-like): Punto en el cual se evalúa el gradiente.
   - ``deltaX`` (float, optional): Paso para la aproximación numérica de las derivadas parciales. Por defecto es 0.001.

   Retorna
   -------
   - ``list``: Gradiente de ``f`` en ``x``.

   Ejemplo de Uso
   --------------

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

.. _optimizacioneli-multivariable-conjugate_gradient:

Método de Cauchy
-----------------------------------

El método de Cauchy trabaja bien cuando el punto inicial se encuentra lejos del óptimo. 
Cuando el punto actual está muy cercano el cambio en el gradiente es pequeño. Esto hace que la convergencia se lenta, para acelerarla se puede usar las derivadas de segundo orden.

   Parámetros
   ----------
   - ``funcion`` (callable): Función objetivo a minimizar.
   - ``x0`` (array-like): Punto inicial de búsqueda.
   - ``epsilon1`` (float): Tolerancia para la norma del gradiente que determina la convergencia.
   - ``epsilon2`` (float): Tolerancia para la diferencia relativa entre dos iteraciones consecutivas.
   - ``M`` (int): Número máximo de iteraciones permitidas.
   - ``metodo`` (str): Método para la búsqueda de paso de línea ('biseccion', 'interval', 'bounding', 'secante', 'exhaustiva', 'dorado', 'fibonacci', 'newton').

   Retorna
   -------
   - ``array-like``: Punto óptimo encontrado que minimiza la función ``f``.

   Ejemplo de Uso
   --------------

   .. code-block:: python

      import numpy as np
      from optimizacioneli.multivariable import cauchy

      # Definir una función de prueba
      def f(x):
          return x[0]**2 + x[1]**2

      # Punto inicial y parámetros
      x0 = np.array([0.0, 0.0])
      epsilon1 = 1e-5
      epsilon2 = 1e-5
      M = 100
      metodo = 'secante'  # Seleccionar método de búsqueda de paso

      # Aplicar el método de Cauchy
      optimal_point = cauchy(f, x0, epsilon1, epsilon2, M, metodo)
      print("Punto óptimo encontrado:", optimal_point)
