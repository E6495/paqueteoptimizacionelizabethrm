.. _intervalhalving:

Método de Interval Halving Method para Encontrar un Mínimo Local
===========================================================

Este archivo documenta el método de interval halving method para encontrar un intervalo que contiene un mínimo local de una función dada.

Método de Bisección
--------------------------

.. autofunction:: interval_halving_method

Descripción
------------

La función `interval_halving_method` implementa el método de Interval halving Method, que divide iterativamente un intervalo [a, b] en la mitad y decide en cuál mitad buscar el mínimo local de la función objetivo. La función itera hasta que la longitud del intervalo sea menor que una tolerancia `epsilon`.

Parámetros
-----------

- `a` (float): Límite inferior del intervalo inicial.
- `b` (float): Límite superior del intervalo inicial.
- `funcion` (callable): La función objetivo que se desea minimizar.
- `epsilon` (float): La tolerancia para la longitud del intervalo.

Retorno
--------

La función retorna un tuple que representa el intervalo [a, b] que contiene un mínimo local de la función.

Ejemplo de Uso
----------------

A continuación, se muestra un ejemplo básico de cómo usar `interval_halving_method`:

.. code-block:: python

    import numpy as np
    import matplotlib.pyplot as plt

    # Definir la función objetivo
    def funcion(x):
        return x**2 - 2*x + 1

    # Aplicar el método de bisección
    intervalo_minimo = interval_halving_method(0, 2, funcion, 0.01)
    print("Intervalo que contiene el mínimo local:", intervalo_minimo)

