.. _exhaustiva:

Método de Búsqueda Exhaustiva para Encontrar Intervalo de Mínimo Local
======================================================================

Este archivo documenta el método de búsqueda exhaustiva para encontrar un intervalo [x1, x3] que contiene un mínimo local de una función dada.

Método de Búsqueda Exhaustiva
------------------------------

.. autofunction:: exhaustive_search_method

Descripción
-----------

La función `exhaustive_search_method` implementa un algoritmo de búsqueda exhaustiva para encontrar un intervalo [x1, x3] donde una función tiene un mínimo local. Se basa en una precisión dada para determinar el tamaño del paso en la búsqueda.

Parámetros
----------

- `a` (float): Límite inferior del intervalo de búsqueda.
- `b` (float): Límite superior del intervalo de búsqueda.
- `precision` (float): Tamaño del paso para la búsqueda.
- `funcion` (callable): La función que se desea minimizar.

Retorno
-------

La función retorna un tuple (x1, x3) que representa el intervalo [x1, x3] que contiene un mínimo local de la función. Si no se encuentra tal intervalo, devuelve None.

Ejemplo de Uso
---------------

A continuación, se muestra un ejemplo básico de cómo usar `exhaustive_search_method`:

.. code-block:: python

    import numpy as np
    import matplotlib.pyplot as plt

    # Definir la función objetivo
    def funcion(x):
        return x**2

    # Aplicar el método de búsqueda exhaustiva
    intervalo = exhaustive_search_method(-1.0, 1.0, 0.01, funcion)
    print("Intervalo que contiene un mínimo local:", intervalo)
