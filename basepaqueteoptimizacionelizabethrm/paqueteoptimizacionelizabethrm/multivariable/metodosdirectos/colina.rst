.. _optimizacioneli-multivariable-random_walk:

Algoritmo de Colina
=========================

El algoritmo de Colina es una técnica de optimización que genera pasos aleatorios para explorar el espacio de búsqueda en busca de un mínimo global.

Función generación random
--------------

   Parámetros
   ----------
   - ``x`` (array-like): Punto actual en el espacio de búsqueda.
   - ``sigma`` (float): Desviación estándar para la distribución normal que genera el paso aleatorio.

   Retorna
   -------
   - ``np.ndarray``: Nuevo punto generado como un paso aleatorio desde x.

Función colina
----------

   Parámetros
   ----------
   - ``f`` (callable): Función objetivo que se desea minimizar.
   - ``terminate`` (callable): Función de terminación que determina cuándo detener el algoritmo.
   - ``max_iter`` (int): Número máximo de iteraciones permitidas.
   - ``x0`` (array-like): Punto inicial de la búsqueda.
   - ``sigma`` (float): Desviación estándar para generar pasos aleatorios.

   Retorna
   -------
   - ``tuple``: Mejor punto encontrado y lista de puntos históricos durante la búsqueda.

   Ejemplo de Uso
   --------------

   .. code-block:: python

      import numpy as np
      from optimizacioneli.multivariable import random_walk_colina, max_iterations_terminate

      # Función objetivo de prueba (parábola)
      def objective_function(x):
          return x[0]**2 + x[1]**2

      # Criterio de terminación basado en el número máximo de iteraciones
      max_iter = 100
      terminate_condition = max_iterations_terminate(max_iter)

      # Parámetros del algoritmo
      x0 = np.array([5.0, 5.0])
      sigma = 0.5

      # Aplicar el algoritmo de Colina
      best_solution, history = random_walk_colina(objective_function, terminate_condition, max_iter, x0, sigma)
      print("Mejor solución encontrada:", best_solution)
      print("Historial de puntos explorados:", history)
