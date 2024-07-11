.. _optimizacioneli-multivariable-random_walk:

Algoritmo Random Walk
=====================

Función Random Walk
----------------

El algoritmo Random Walk es una técnica estocástica que genera pasos aleatorios para explorar el espacio de búsqueda y encontrar soluciones óptimas.

   Parámetros
   ----------
   - ``f`` (callable): Función objetivo que se desea minimizar.
   - ``x0`` (list or numpy array): Punto de inicio del algoritmo.
   - ``max_iter`` (int): Número máximo de iteraciones.
   - ``mu`` (float): Media de la distribución normal para generar pasos aleatorios.
   - ``sigma`` (float): Desviación estándar de la distribución normal para generar pasos aleatorios.

   Retorna
   -------
   - ``numpy array``: La mejor solución encontrada que minimiza la función ``f``.
   - ``list``: Historial de puntos visitados durante la búsqueda.

   Ejemplo de Uso
   --------------

   .. code-block:: python

      import numpy as np
      from optimizacioneli.multivariable import random_walk

      # Definir una función de prueba
      def objective_function(x):
          return x[0]**2 + x[1]**2

      # Punto inicial y parámetros del algoritmo
      x0 = np.array([1.0, 2.0])
      max_iter = 1000
      mu = 0.0
      sigma = 0.1

      # Aplicar el algoritmo de Random Walk
      best_solution, history = random_walk(objective_function, x0, max_iter, mu, sigma)
      print("Mejor solución encontrada:", best_solution)
