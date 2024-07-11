.. _optimizacioneli-multivariable-hooke_jeeves:

Método de Hooke-Jeeves
=======================

El método de Hooke-Jeeves es un algoritmo de optimización heurístico que utiliza un enfoque de búsqueda directa y patrones para encontrar el mínimo de una función.

Función de movimiento exploratorio
--------------------

   Parámetros
   ----------
   - ``xc`` (array-like): Punto actual en el espacio de búsqueda.
   - ``delta`` (array-like): Vector de pasos para moverse en cada dirección.
   - ``function`` (callable): Función objetivo que se desea minimizar.

   Retorna
   -------
   - ``tuple``: Nuevo punto en el espacio de búsqueda, arreglo booleano indicando éxito de cada movimiento, punto anterior.

Función de movimiento de patrón
------------------

   Parámetros
   ----------
   - ``x_current`` (array-like): Punto actual en el espacio de búsqueda.
   - ``x_previous`` (array-like): Punto anterior en el espacio de búsqueda.

   Retorna
   -------
   - ``array-like``: Nuevo punto calculado según el movimiento de patrón.

Función de Hooke Jeeves
---------------------

   Parámetros
   ----------
   - ``initial_point`` (array-like): Punto inicial de búsqueda.
   - ``deltas`` (array-like): Vector de pasos para moverse en cada dirección.
   - ``alpha`` (float): Factor de reducción de pasos en caso de fracaso en la búsqueda.
   - ``epsilon`` (float): Tolerancia para detener el algoritmo.
   - ``function`` (callable): Función objetivo que se desea minimizar.

   Retorna
   -------
   - ``tuple``: Punto óptimo encontrado que minimiza la función, número de iteraciones realizadas.

   Ejemplo de Uso
   --------------

   .. code-block:: python

      import numpy as np
      from optimizacioneli.multivariable import exploratory_move, pattern_movement, hooke_jeeves

      # Función objetivo de prueba (parábola)
      def objective_function(x, y):
          return x**2 + y**2

      # Punto inicial y parámetros del algoritmo
      initial_point = [5.0, 5.0]
      deltas = [1.0, 1.0]
      alpha = 2.0
      epsilon = 1e-5

      # Aplicar el método de Hooke-Jeeves
      best_solution, iterations = hooke_jeeves(initial_point, deltas, alpha, epsilon, objective_function)
      print("Mejor solución encontrada:", best_solution)
      print("Iteraciones realizadas:", iterations)
