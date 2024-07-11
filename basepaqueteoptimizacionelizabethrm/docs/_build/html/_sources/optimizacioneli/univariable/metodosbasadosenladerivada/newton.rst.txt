.. _newton_raphson:

Método de Newton-Raphson para Encontrar Raíces de Funciones
============================================================

Este archivo documenta el método de Newton-Raphson para encontrar una raíz de una función dada.

Método de Newton-Raphson
------------------------

.. autofunction:: optimizacioneli.univariable.metodosbasadosenladerivada.newton_raphson_method

Descripción
-----------

La función `newton_raphson_method` implementa el método de Newton-Raphson para encontrar una raíz de una función. Utiliza derivadas de primer y segundo orden calculadas mediante el método de diferencias centrales.

Parámetros
----------

- `funcion` (callable): La función objetivo cuya raíz se desea encontrar.
- `initial_guess` (float): El valor inicial para comenzar la búsqueda de la raíz.
- `delta_x_funcion` (callable): Función que determina el valor de delta_x en función de x.
- `epsilon` (float): La tolerancia para el criterio de convergencia.
- `max_iteraciones` (int, opcional): El número máximo de iteraciones permitidas (por defecto es 10000).

Retorno
-------

La función retorna una aproximación de la raíz de la función.

Ejemplo de Uso
--------------

A continuación, se muestra un ejemplo básico de cómo usar `newton_raphson_method`:

.. code-block:: python

    import numpy as np

    # Definir la función objetivo
    def funcion(x):
        return x**2 - 4

    # Definir la función que calcula delta_x
    def delta_x_func(x):
        return 0.01 * abs(x) if abs(x) > 0.01 else 0.0001

    # Aplicar el método de Newton-Raphson
    raiz = newton_raphson_method(funcion, 1.0, delta_x_func, 0.0001)
    print("Aproximación de la raíz:", raiz)

Descripción de Funciones
------------------------

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

Función `central_difference_f_double_prime`
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

La función `central_difference_f_double_prime` calcula la derivada segunda de una función en un punto dado utilizando el método de diferencias centrales.

Parámetros
~~~~~~~~~~

- `f` (callable): La función objetivo cuya derivada se quiere calcular.
- `x` (float): El punto en el cual se desea calcular la derivada.
- `delta_x` (float): El pequeño incremento alrededor de `x`.

Retorno
~~~~~~~

Retorna una aproximación de la derivada segunda de la función en `x`.
