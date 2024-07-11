.. _biseccion:

Método de Bisección para Encontrar Intervalo de Mínimo Local
============================================================

Este archivo documenta el método de bisección para encontrar un intervalo [x1, x2] que contiene un mínimo local de una función dada.

Método de Bisección
-------------------

Descripción
-----------

La función `bisection_method` implementa el método de bisección para encontrar un intervalo [x1, x2] donde una función tiene un mínimo local. Utiliza la derivada primera calculada mediante el método de diferencias centrales para verificar las condiciones iniciales del método.

Parámetros
----------

- `funcion` (callable): La función objetivo que se desea minimizar.
- `a` (float): Límite inferior del intervalo inicial.
- `b` (float): Límite superior del intervalo inicial.
- `epsilon` (float): La tolerancia para la longitud del intervalo y el valor de la derivada.
- `delta_x` (float): El pequeño incremento utilizado para calcular la derivada.
- `max_iteraciones` (int, opcional): El número máximo de iteraciones permitidas (por defecto es 10000).

Retorno
-------

La función retorna un tuple (x1, x2) que representa el intervalo [x1, x2] que contiene un mínimo local de la función.

Funciones Relacionadas
----------------------

Función `central_difference_f_prime`
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

La función `central_difference_f_prime` calcula la derivada primera de una función en un punto dado utilizando el método de diferencias centrales.

Parámetros
~~~~~~~~~~

- `f` (callable): La función objetivo cuya derivada se quiere calcular.
- `x` (float): El punto en el cual se desea calcular la derivada.
- `delta_x` (float): El pequeño incremento alrededor de `x`.

Retorno
~~~~~~~

Retorna una aproximación de la derivada primera de la función en `x`.

Función `delta_x_func`
~~~~~~~~~~~~~~~~~~~~~~

La función `delta_x_func` determina el valor de delta_x en función de x.

Parámetros
~~~~~~~~~~

- `x` (float): El punto en el cual se desea determinar delta_x.

Retorno
~~~~~~~

Retorna el valor de delta_x basado en x.

Ejemplo de Uso
--------------

.. code-block:: python

   import numpy as np
   from optimizacioneli.univariable import bisection_method, central_difference_f_prime, delta_x_func

   # Definir una función de prueba
   def f(x):
       return (x - 2)**2

   # Parámetros del método de bisección
   a = 0
   b = 5
   epsilon = 1e-5
   delta_x = 1e-5
   max_iteraciones = 10000

   # Aplicar el método de bisección
   intervalo = bisection_method(f, a, b, epsilon, delta_x, max_iteraciones)
   print("Intervalo que contiene el mínimo local:", intervalo)
