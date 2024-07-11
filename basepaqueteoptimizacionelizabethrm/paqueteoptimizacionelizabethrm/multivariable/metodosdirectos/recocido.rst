.. _optimizacioneli-multivariable-tweak:

Método de Recocido Simulado
==================================

Función tweak
-------------------

La función `tweak` aplica una pequeña pertubación aleatoria a una matriz dada.


   Parámetros
   ----------
   - ``X`` (numpy array): Matriz de entrada a la cual se le aplicará la perturbación.

   Retorna
   -------
   - ``numpy array``: Matriz perturbada con valores aleatorios uniformemente distribuidos dentro del rango [-0.5, 0.5].

   Ejemplo de Uso
   --------------

   .. code-block:: python

      import numpy as np
      from optimizacioneli.multivariable import tweak

      # Matriz original
      X = np.array([[1, 2], [3, 4]])

      # Aplicar Recocido Simulado
      perturbed_X = tweak(X)
      print("Matriz perturbada:", perturbed_X)

.. _optimizacioneli-multivariable-simulated_annealing:

Algoritmo de Recocido Simulado
-------------------

El algoritmo de Recocido Simulado es una técnica de optimización estocástica que simula el proceso físico de enfriamiento de metales para encontrar el mínimo global de una función.

   Parámetros
   ----------
   - ``f`` (function): Función objetivo que se desea minimizar.
   - ``x0`` (list or numpy array): Punto inicial de la búsqueda.
   - ``alpha`` (float): Factor de enfriamiento para la temperatura.
   - ``T_initial`` (float): Temperatura inicial.
   - ``T_min`` (float): Temperatura mínima en la que se detiene la búsqueda.
   - ``metropolis_size`` (int): Número de iteraciones por cada temperatura.

   Retorna
   -------
   - ``numpy array``: El mejor punto encontrado que minimiza la función ``f``.
   - ``list``: Historial de puntos explorados durante la búsqueda.

   Ejemplo de Uso
   --------------

   .. code-block:: python

      import numpy as np
      from optimizacioneli.multivariable import simulated_annealing

      # Definir una función de prueba
      def objective_function(x):
          return x[0]**2 + x[1]**2

      # Punto inicial y parámetros del algoritmo
      x0 = np.array([1.0, 2.0])
      alpha = 0.9
      T_initial = 100.0
      T_min = 0.1
      metropolis_size = 10

      # Aplicar el algoritmo de Recocido Simulado
      best_solution, history = simulated_annealing(objective_function, x0, alpha, T_initial, T_min, metropolis_size)
      print("Mejor solución encontrada:", best_solution)
