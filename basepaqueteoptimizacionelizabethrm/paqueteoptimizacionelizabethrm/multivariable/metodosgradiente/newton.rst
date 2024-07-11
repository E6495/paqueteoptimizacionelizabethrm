.. _newton_section:

Método de Newton (Gradiente)
================

Esta sección describe la implementación del método de Newton para la optimización.

El método de Newton usa las derivadas de segundo orden para crear las direcciones de búsqueda. Lo que permite una mayor velocidad de convergencia. Este método es adecuado y eficiente cuando el punto inicial está cerca del punto óptimo. Sin embargo no se garantiza la reducción de la función objetivo a cada iteración , por lo que, ocasionalmente es necesario reiniciar el punto de inicio.

Implementación del Método de Newton
-----------------------------------

La función `newton` implementa el método de Newton para la optimización de funciones escalares. Admite varios métodos de búsqueda unidireccional para encontrar un tamaño de paso (`alpha`) adecuado durante cada iteración:

- **Búsqueda Fibonacci**: Utiliza el algoritmo de búsqueda Fibonacci para encontrar `alpha`.
- **Método de Newton-Raphson**: Utiliza el método de Newton-Raphson para encontrar `alpha`.
- **Búsqueda de la Sección Dorada**: Aplica la búsqueda de la sección dorada para determinar `alpha`.
- **Método de Intervalo de Mitad**: Implementa el método de intervalo de mitad para `alpha`.
- **Método de Fase de Limitación**: Utiliza el método de fase de limitación para encontrar `alpha`.
- **Método de Búsqueda Exhaustiva**: Aplica la búsqueda exhaustiva para determinar `alpha`.
- **Método de Bisección**: Implementa el método de bisección para encontrar `alpha`.
- **Método de Secante**: Utiliza el método de la secante para determinar `alpha`.

Cada uno de estos métodos ofrece diferentes enfoques para determinar el tamaño de paso `alpha` basado en el comportamiento de la función.

Parámetros
----------

- ``funcion`` (callable): Función objetivo a minimizar.
- ``x0`` (array-like): Punto inicial para la optimización.
- ``epsilon1`` (float): Tolerancia para la norma del gradiente para lograr la convergencia.
- ``epsilon2`` (float): Tolerancia para la diferencia relativa entre iteraciones consecutivas.
- ``M`` (int): Número máximo de iteraciones permitidas.
- ``metodo`` (str): Método para la búsqueda unidireccional ('fibonacci', 'newton', 'dorado', 'interval', 'bounding', 'exhaustiva', 'biseccion', 'secante').

Retorna
-------

- ``np.ndarray``: Punto optimizado que aproxima el mínimo de la función.

Ejemplo de Uso
--------------

.. code-block:: python
    
    import numpy as np
    from optimizacioneli.multivariable import newton

    # Define tu función objetivo
    def funcion_objetivo(x):
        return x**2

    # Punto inicial y parámetros
    x0 = np.array([1.0])
    epsilon1 = 1e-5
    epsilon2 = 1e-5
    M = 100
    metodo = 'newton'  # Elige el método de búsqueda unidireccional

    # Aplica el método de Newton
    resultado = newton(funcion_objetivo, x0, epsilon1, epsilon2, M, metodo)
    print("Solución óptima:", resultado)
