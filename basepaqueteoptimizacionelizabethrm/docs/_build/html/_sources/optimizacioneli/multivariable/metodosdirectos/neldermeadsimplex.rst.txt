.. _neldermeadsimplex:
.. _optimizacioneli-multivariable-mead_simplex:

Algoritmo de Mead (Nelder-Mead)
===============================

El algoritmo de Mead, también conocido como método Nelder-Mead, es un método de optimización sin restricciones que utiliza un simplex para encontrar el mínimo de una función.

Función Simplex
--------------

   Parámetros
   ----------
   - ``alpha`` (float): Parámetro de ajuste para calcular los puntos del simplex inicial.
   - ``punto_inicial`` (list): Punto inicial alrededor del cual se genera el simplex.

   Retorna
   -------
   - ``list``: Lista de puntos que conforman el simplex inicial.

Funcion Mead Simplex
--------------------
   Parámetros
   ----------
   - ``funcion`` (callable): Función objetivo que se desea minimizar.
   - ``punto_inicial`` (list): Punto inicial alrededor del cual se realiza la búsqueda.
   - ``epsilon`` (float): Criterio de convergencia, diferencia mínima entre los valores de la función.
   - ``gamma`` (float): Parámetro de reflexión.
   - ``beta`` (float): Parámetro de contracción.

   Retorna
   -------
   - ``tuple``: Punto óptimo encontrado y lista de simplex en cada iteración.

   Ejemplo de Uso
   --------------

   .. code-block:: python

      import numpy as np
      from optimizacioneli.multivariable import simplex_inicial, mead_simplex

      # Definir una función de prueba
      def objective_function(x):
          return (x[0] - 1)**2 + (x[1] - 2)**2

      # Punto inicial y parámetros del algoritmo
      x0 = [0.0, 0.0]
      epsilon = 1e-5
      gamma = 1.0
      beta = 0.5

      # Generar el simplex inicial
      initial_simplex = simplex_inicial(0.5, x0)
      print("Simplex inicial:", initial_simplex)

      # Aplicar el algoritmo de Mead (Nelder-Mead)
      best_solution, history = mead_simplex(objective_function, x0, epsilon, gamma, beta)
      print("Mejor solución encontrada:", best_solution)
