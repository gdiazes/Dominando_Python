# Módulo 4: Ejercicio 2 (Dificultad 2.1/10) - Número Positivo, Negativo o Cero

## Enunciado del Problema

Escribe un programa que solicite al usuario ingresar un número entero.
El programa debe determinar si el número es positivo, negativo o cero, y mostrar un mensaje correspondiente.

## Código con Errores

```python
# Ejercicio: Determinar si un número es positivo, negativo o cero

numero_str = input("Ingresa un número entero: ")
numero = int(numero_str)

if numero > 0
    mensaje = "El número es positivo." # Pista 1
elif numero < 0:
    mensaje = "El número es negativo."
elif numero = 0: # Pista 2
    mensaje = "El número es cero."
# Pista 3: ¿Qué sucede si ninguna de las condiciones anteriores se cumple? ¿Se asigna siempre un valor a 'mensaje'?

print(mensaje)
```

## Pistas para Corregir los Errores

*   **Pista 1:** La sintaxis de la estructura `if` (y `elif`) requiere un carácter específico al final de la línea para indicar el inicio de un bloque de código.
*   **Pista 2:** Para comparar si un número es igual a cero (o a cualquier valor), ¿cuál es el operador de comparación correcto? El operador `=` se usa para asignación.
*   **Pista 3:** Si el programa está estructurado con `if/elif/elif` sin un `else` final, y ninguna de las condiciones de `if` o `elif` se cumple, la variable `mensaje` podría no ser definida antes de intentar imprimirla, lo que causaría un `NameError`. ¿Hay alguna condición que falte o cómo se podría asegurar que `mensaje` siempre tenga un valor? (En este caso específico, las tres condiciones cubren todos los enteros, pero es un buen punto de reflexión para estructuras más complejas).

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Determinar si un número es positivo, negativo o cero

numero_str = input("Ingresa un número entero: ")
numero = int(numero_str)

mensaje = "" # Inicializar mensaje para evitar NameError en casos más complejos

if numero > 0: # Necesita dos puntos ':'
    mensaje = "El número es positivo."
elif numero < 0:
    mensaje = "El número es negativo."
elif numero == 0: # Usar '==' para comparación
    mensaje = "El número es cero."
# En este caso, una de las tres condiciones siempre se cumplirá para un entero.
# Un 'else' no es estrictamente necesario aquí si las condiciones cubren todos los casos,
# pero inicializar 'mensaje' es una buena práctica defensiva.
# Alternativamente, el último 'elif' podría ser un 'else':
# else:
#     mensaje = "El número es cero."


print(mensaje)
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio utiliza la estructura `if-elif-elif` (o `if-elif-else`) para clasificar un número.

*   **Error 1 Corrección (Falta de dos puntos en `if`):**
    *   El código original era `if numero > 0`.
    *   La línea de la condición `if` (así como `elif` y `else`) debe terminar con dos puntos (`:`) para indicar el inicio del bloque de código indentado.
    *   **Solución:** `if numero > 0:`

*   **Error 2 Corrección (Uso de asignación `=` en lugar de comparación `==`):**
    *   El código original era `elif numero = 0:`.
    *   El operador `=` se usa para asignar un valor a una variable. Para comparar si `numero` es igual a `0`, se debe usar el operador de comparación `==`.
    *   **Solución:** `elif numero == 0:`

*   **Error 3 Corrección (Posible `NameError` y estructura condicional):**
    *   La Pista 3 señala un problema potencial si `mensaje` no se define en todas las rutas posibles del código. En este caso particular (números enteros), una de las tres condiciones (`>0`, `<0`, `==0`) siempre será verdadera. Sin embargo, es una buena práctica de programación defensiva inicializar la variable `mensaje` (por ejemplo, a una cadena vacía `""` o un valor predeterminado) antes del bloque `if` o asegurarse de que haya una cláusula `else` que capture todos los demás casos.
    *   **Solución (Defensiva):** `mensaje = ""` al inicio.
    *   **Solución (Alternativa Estructural):** La última condición `elif numero == 0:` podría reemplazarse por `else:`, ya que si el número no es mayor que cero y no es menor que cero, necesariamente debe ser cero.
        ```python
        if numero > 0:
            mensaje = "El número es positivo."
        elif numero < 0:
            mensaje = "El número es negativo."
        else: # Si no es positivo ni negativo, es cero
            mensaje = "El número es cero."
        ```
    *   Ambas soluciones son válidas. La solución proporcionada en "Mostrar Solución Correcta" mantiene la estructura `elif numero == 0:` e inicializa `mensaje` para ilustrar la práctica defensiva, aunque el `else` también sería muy apropiado aquí.

El programa corregido solicita un número, lo convierte a entero y luego utiliza la estructura condicional `if-elif-elif` (o `if-elif-else`) con la sintaxis y los operadores de comparación correctos para determinar e imprimir si el número es positivo, negativo o cero.
</details>
