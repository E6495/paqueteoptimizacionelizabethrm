.. _golden:

Método de Búsqueda Dorada para Encontrar un Mínimo Local
===========================================================

Este archivo documenta el método de búsqueda dorada para encontrar un mínimo local de una función dada.

Método de Búsqueda Dorada
--------------------------

.. autofunction:: busquedaDorada

Descripción
------------

La función `busquedaDorada` implementa el método de búsqueda dorada, que utiliza la razón áurea para ajustar iterativamente un intervalo [a, b] que contiene un mínimo local de la función objetivo. La función itera hasta que la longitud del intervalo en términos de w (la escala en el intervalo [0, 1]) sea menor que una tolerancia `epsilon`.

Parámetros
-----------

- `funcion` (callable): La función objetivo que se desea minimizar.
- `epsilon` (float): La tolerancia para la longitud del intervalo [a, b].
- `a` (float, opcional): Límite inferior del intervalo inicial. Por defecto es None.
- `b` (float, opcional): Límite superior del intervalo inicial. Por defecto es None.

Retorno
--------

La función retorna un float que representa una aproximación del punto que minimiza la función en el intervalo [a, b].

Ejemplo de Uso
----------------

A continuación, se muestra un ejemplo básico de cómo usar `busquedaDorada`:

.. code-block:: python

    import numpy as np
    import matplotlib.pyplot as plt

    # Definir la función objetivo
    def funcion(x):
        return x**2

    # Aplicar el método de búsqueda dorada
    minimo_local = busquedaDorada(funcion, 0.001, -1.0, 1.0)
    print("Aproximación del mínimo local:", minimo_local)
