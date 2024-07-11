.. _bounding:

Método de la Fase de Búsqueda para Encontrar Mínimos Locales
=============================================================

Este archivo documenta el método de la fase de búsqueda para encontrar un intervalo que contiene un mínimo local de una función dada.

Método de la Fase de Búsqueda
-----------------------------

.. autofunction:: bounding_phase_method

Descripción
-----------

La función `bounding_phase_method` utiliza un enfoque iterativo para encontrar un intervalo (a, b) que contiene un mínimo local de una función, basado en una conjetura inicial (`initial_guess`) y un tamaño de paso inicial (`Delta`).

Parámetros
----------

- `funcion` (callable): La función objetivo que se desea minimizar.
- `initial_guess` (float): La conjetura inicial para el punto de inicio.
- `Delta` (float): El tamaño del paso inicial.

Retorno
-------

La función retorna un tuple (a, b) que representa el intervalo que contiene un mínimo local de la función.

Ejemplo de Uso
---------------

A continuación, se muestra un ejemplo básico de cómo usar `bounding_phase_method`:

.. code-block:: python

    import numpy as np
    import matplotlib.pyplot as plt

    # Definir la función objetivo
    def funcion(x):
        return x**2

    # Aplicar el 
