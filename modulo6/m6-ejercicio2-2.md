# Módulo 6: Ejercicio 2 

## Enunciado del Problema

Crea un juego donde el programa tiene un número secreto (por ejemplo, 7).
El programa debe solicitar repetidamente al usuario que adivine el número hasta que lo haga correctamente.
Cuando el usuario adivine, el programa debe felicitarlo y terminar.
No se necesitan pistas de "muy alto" o "muy bajo" para este ejercicio, solo la repetición hasta acertar.

## Código con Errores

```python
# Ejercicio: Adivinar un número secreto con while

NUMERO_SECRETO = 7
suposicion = 0 # Pista 1 (Considera el valor inicial y la condición del bucle)

while suposicion != NUMERO_SECRETO
    suposicion_str = input("Adivina el número secreto: ")
    suposicion = int(suposicion_str) # Pista 2 (¿Qué pasa si el usuario no ingresa un número?)
    
# Pista 3: ¿Dónde debería ir el mensaje de felicitación?
print("¡Felicidades! Adivinaste el número secreto.") 
```

## Pistas para Corregir los Errores

*   **Pista 1:** La variable `suposicion` se usa en la condición del `while`. Asegúrate de que su valor inicial permita que el bucle comience al menos una vez si es necesario, o que la lógica de la primera entrada esté bien manejada. Además, ¿falta algo en la línea del `while`?
*   **Pista 2:** La conversión `int(suposicion_str)` podría fallar si el usuario ingresa texto no numérico (como "hola"). Aunque el manejo completo de errores con `try-except` se verá más adelante, para este ejercicio, el error principal está en la estructura del bucle y la condición.
*   **Pista 3:** El mensaje de felicitación solo debe imprimirse *después* de que el usuario haya adivinado correctamente, es decir, una vez que el bucle `while` haya terminado porque la condición se volvió falsa (suposición == NÚMERO_SECRETO).

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Adivinar un número secreto con while

NUMERO_SECRETO = 7
suposicion = None # Inicializar a algo que no sea el número secreto, o no inicializar y leer antes del bucle

# Bucle while necesita ':'
# La condición se evalúa. Si suposicion es None, None != 7 es True.
while suposicion != NUMERO_SECRETO:
    suposicion_str = input("Adivina el número secreto (pista: es 7): ") # Añadida pista para facilitar prueba
    # Idealmente, usar try-except para la conversión, pero lo omitimos por ahora
    if suposicion_str.isdigit(): # Una validación simple
        suposicion = int(suposicion_str)
        if suposicion != NUMERO_SECRETO:
            print("Intenta de nuevo.") # Mensaje opcional para intentos fallidos
    else:
        print("Por favor, ingresa un número.")
        # 'suposicion' no se actualiza a un número, el bucle continuará
        # pidiendo la entrada. Si se quiere que el bucle no se trabe en None:
        # suposicion = None # o algún valor que no sea el secreto

# Este print se ejecuta solo cuando el bucle while termina
# (es decir, cuando suposicion == NUMERO_SECRETO)
print("¡Felicidades! Adivinaste el número secreto.")
```
*Alternativa con lectura antes del bucle (a veces más simple para la primera entrada):*
```python
# NUMERO_SECRETO_ALT = 7
# suposicion_str_alt = input("Adivina el número secreto (pista: es 7): ")
# if suposicion_str_alt.isdigit():
#     suposicion_alt = int(suposicion_str_alt)
# else:
#     suposicion_alt = -1 # Un valor que no sea el secreto y que no sea None si se quiere evitar un error de tipo

# while suposicion_alt != NUMERO_SECRETO_ALT:
#     print("Intenta de nuevo.")
#     suposicion_str_alt = input("Adivina el número secreto (pista: es 7): ")
#     if suposicion_str_alt.isdigit():
#         suposicion_alt = int(suposicion_str_alt)
#     else:
#         print("Por favor, ingresa un número.")
#         suposicion_alt = -1 # Para que el bucle pueda continuar si se ingresó texto

# print("¡Felicidades! Adivinaste el número secreto.")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio utiliza un bucle `while` para repetir una acción (pedir una suposición) hasta que se cumpla una condición (adivinar el número).

*   **Error 1 Corrección (Inicialización de `suposicion` y sintaxis de `while`):**
    *   El código original tenía `suposicion = 0` y `while suposicion != NUMERO_SECRETO`.
    *   Si `NUMERO_SECRETO` fuera 0, el bucle no se ejecutaría ni una vez. Es mejor inicializar `suposicion` a un valor que garantice que la condición del `while` sea verdadera la primera vez (por ejemplo, `None`, o cualquier valor que no sea `NUMERO_SECRETO`), o leer la primera suposición *antes* del bucle.
    *   La línea `while suposicion != NUMERO_SECRETO` debe terminar con dos puntos (`:`).
    *   **Solución:**
        ```python
        suposicion = None # O cualquier valor no igual a NUMERO_SECRETO
        while suposicion != NUMERO_SECRETO: # Añadir ':'
            # ... cuerpo del bucle ...
        ```

*   **Error 2 Corrección (Manejo de entrada no numérica - conceptual):**
    *   La Pista 2 menciona que `int(suposicion_str)` fallará si la entrada no es un número. Aunque la solución completa a esto es `try-except` (que se verá más adelante), una validación simple usando `.isdigit()` puede ayudar a prevenir algunos errores o guiar al usuario. La solución correcta añade esta validación simple. Si la entrada no es un dígito, `suposicion` no se actualiza a un entero, y el bucle continúa (o se podría reasignar `suposicion` a `None` para forzar que siga siendo diferente al secreto si la última suposición válida fue el secreto).

*   **Error 3 Corrección (Ubicación del mensaje de felicitación):**
    *   El código original tenía `print("¡Felicidades! ...")` fuera del bucle. Esto es correcto. El bucle `while` se ejecuta *mientras* la suposición sea incorrecta. Cuando la suposición es correcta, la condición `suposicion != NUMERO_SECRETO` se vuelve falsa, el bucle termina, y el código que sigue al bucle (el `print` de felicitación) se ejecuta. No hay error sintáctico aquí, la pista era para asegurar la comprensión del flujo.

**Lógica del Bucle en la Solución:**
1.  `suposicion` se inicializa a `None` (o un valor distinto al `NUMERO_SECRETO`).
2.  El bucle `while suposicion != NUMERO_SECRETO:` comienza:
    *   Se solicita la entrada al usuario.
    *   Se hace una validación simple con `isdigit()`. Si es un número, se convierte a `int` y se guarda en `suposicion`.
    *   Si `suposicion` sigue sin ser igual a `NUMERO_SECRETO`, se imprime "Intenta de nuevo." (opcional) y el bucle vuelve a empezar.
    *   Si la entrada no es un dígito, se informa al usuario, y `suposicion` no se actualiza a un entero (o se podría reestablecer a `None`), por lo que la condición del `while` probablemente seguirá siendo verdadera y pedirá otra entrada.
3.  Cuando el usuario finalmente ingresa el `NUMERO_SECRETO`, la variable `suposicion` se actualiza a ese valor. En la siguiente comprobación de la condición del `while`, `suposicion != NUMERO_SECRETO` será `False`, y el bucle terminará.
4.  Se ejecuta la línea `print("¡Felicidades!...")` que está después del bucle.

La alternativa de leer la primera entrada *antes* del bucle es otra forma común de estructurar este tipo de problema, evitando la necesidad de inicializar `suposicion` a un valor artificial.
</details>
