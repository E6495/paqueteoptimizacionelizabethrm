.. _secante:

Método de la Secante para Encontrar Intervalo de Mínimo Local
============================================================

Este archivo documenta el método de la secante para encontrar un intervalo [x1, x2] que contiene un mínimo local de una función dada.

Método de la Secante
--------------------

.. autofunction:: optimizacioneli.univariable.metodosbasadosenladerivada.secante.secant_method

Descripción
-----------

La función `secant_method` implementa un algoritmo de la secante para encontrar un intervalo [x1, x2] donde una función tiene un mínimo local. Se basa en una precisión dada para determinar el tamaño del paso en la búsqueda y utiliza diferencias centrales para calcular la derivada.

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

La función retorna un tuple (x1, x2) que representa el intervalo [x1, x2] que contiene un mínimo local de la función. Si no se encuentra tal intervalo, devuelve None.

Ejemplo de Uso
--------------

A continuación, se muestra un ejemplo básico de cómo usar `secant_method`:

.. code-block:: python

    import numpy as np

    # Definir la función objetivo
    def funcion(x):
        return x**2

    # Definir el incremento delta_x
    delta_x = 0.01

    # Aplicar el método de la secante
    intervalo = secant_method(funcion, -1.0, 1.0, 0.001, delta_x)
    print("Intervalo que contiene un mínimo local:", intervalo)
