.. _fibonacci:

Método de Búsqueda de Fibonacci para Encontrar Intervalo de Mínimo Local
===========================================================================

Este archivo documenta el método de búsqueda de Fibonacci para encontrar un intervalo [a, b] que contiene un mínimo local de una función dada.

Método de Búsqueda de Fibonacci
--------------------------------

.. autofunction:: fibonacci_search

Descripción
-----------

La función `fibonacci_search` implementa un método iterativo basado en la secuencia de Fibonacci para buscar un intervalo [a, b] que contenga un mínimo local de la función objetivo. Se utiliza un número dado de iteraciones para ajustar el tamaño del intervalo en cada paso.

Parámetros
----------

- `funcion` (callable): La función objetivo que se desea minimizar.
- `a` (float): Límite inferior del intervalo inicial.
- `b` (float): Límite superior del intervalo inicial.
- `n` (int): Número de iteraciones, relacionado con la precisión deseada del método.

Retorno
-------

La función retorna un tuple (a, b) que representa el intervalo [a, b] que contiene un mínimo local de la función. Los límites a y b se actualizan iterativamente según el método de búsqueda de Fibonacci.

Ejemplo de Uso
---------------

A continuación, se muestra un ejemplo básico de cómo usar `fibonacci_search`:

.. code-block:: python

    import numpy as np
    import matplotlib.pyplot as plt

    # Definir la función objetivo
    def funcion(x):
        return x**2

    # Aplicar el método de búsqueda de Fibonacci
    intervalo = fibonacci_search(funcion, -1.0, 1.0, 5)
    print("Intervalo que contiene un mínimo local:", intervalo)

