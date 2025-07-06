# Módulo 4: Ejercicio 8 (Dificultad 8.4/10) - Juego de Adivinar Número (con pistas)

## Enunciado del Problema

Crea un juego simple donde el programa "piensa" en un número secreto (por ejemplo, fijo en el código, digamos 42).
El programa solicita al usuario que adivine el número.
1.  Si el usuario adivina correctamente, muestra un mensaje de felicitación.
2.  Si el usuario no adivina, el programa debe dar una pista: si el número ingresado es mayor o menor que el número secreto.
3.  El usuario tiene solo un intento.

(Este ejercicio sirve como parte de la Práctica Calificada 1)

## Código con Errores

```python
# Ejercicio: Juego de adivinar el número (un intento)

NUMERO_SECRETO = 42

print("¡Bienvenido al juego de adivinar el número!")
print("He pensado en un número entre 1 y 100. Tienes un intento.")

intento_str = input("Ingresa tu suposición: ")
intento = intento_str # Pista 1

if intento == NUMERO_SECRETO
    print("¡Felicidades! ¡Has adivinado el número!") # Pista 2
elif intento < NUMERO_SECRETO:
    print("Demasiado bajo. El número secreto es mayor.")
else intento > NUMERO_SECRETO: # Pista 3
    print("Demasiado alto. El número secreto es menor.")

print("Gracias por jugar.")
```

## Pistas para Corregir los Errores

*   **Pista 1:** La entrada del usuario `input()` es una cadena. Para compararla con `NUMERO_SECRETO` (que es un entero), ¿qué conversión necesitas realizar?
*   **Pista 2:** Revisa la sintaxis de la línea `if`. ¿Falta algún carácter esencial al final?
*   **Pista 3:** Si las condiciones anteriores (`if` y `elif`) no se cumplen, la última opción se maneja con `else:`, no con una condición explícita en la misma línea de `else`. Si quisieras una condición aquí, ¿qué palabra clave usarías en lugar de `else`?

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Juego de adivinar el número (un intento)

NUMERO_SECRETO = 42

print("¡Bienvenido al juego de adivinar el número!")
print("He pensado en un número entre 1 y 100. Tienes un intento.")

intento_str = input("Ingresa tu suposición: ")
# Convertir la entrada a entero para la comparación
intento = int(intento_str)

if intento == NUMERO_SECRETO: # Falta ':'
    print("¡Felicidades! ¡Has adivinado el número!")
elif intento < NUMERO_SECRETO:
    print("Demasiado bajo. El número secreto es mayor.")
else: # Si no es igual ni menor, debe ser mayor. 'else' es apropiado.
    print("Demasiado alto. El número secreto es menor.")

print("Gracias por jugar.")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio implementa un juego simple usando estructuras condicionales para dar retroalimentación.

*   **Error 1 Corrección (Falta de conversión de tipo):**
    *   El código original era `intento = intento_str`.
    *   `input()` devuelve una cadena. Si `intento_str` es, por ejemplo, `"50"`, entonces `intento` también será la cadena `"50"`. Al compararlo con `NUMERO_SECRETO` (un entero), la comparación no será numérica y podría llevar a resultados incorrectos o errores.
    *   **Solución:** `intento = int(intento_str)`

*   **Error 2 Corrección (Falta de dos puntos en `if`):**
    *   El código original era `if intento == NUMERO_SECRETO`.
    *   La declaración `if` debe terminar con dos puntos (`:`).
    *   **Solución:** `if intento == NUMERO_SECRETO:`

*   **Error 3 Corrección (Sintaxis incorrecta para `else` con condición):**
    *   El código original era `else intento > NUMERO_SECRETO:`.
    *   La cláusula `else` no toma una condición. Se ejecuta si todas las condiciones `if` y `elif` precedentes son falsas.
    *   En este caso, si `intento` no es igual a `NUMERO_SECRETO` y no es menor que `NUMERO_SECRETO`, entonces lógicamente debe ser mayor que `NUMERO_SECRETO`. Por lo tanto, un simple `else:` es la construcción correcta.
    *   Si se quisiera mantener una condición explícita, se debería usar `elif intento > NUMERO_SECRETO:`.
    *   **Solución (usando `else`):** `else:`

El programa corregido convierte la suposición del usuario a un entero y luego utiliza una estructura `if-elif-else` para compararla con el número secreto, proporcionando la retroalimentación adecuada.
</details>
