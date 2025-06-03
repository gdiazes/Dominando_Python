# Módulo 6: Ejercicio 4 (Dificultad 4.62/10) - Sumar Números Hasta Ingresar Cero (con `while` y `break`)

## Enunciado del Problema

Escribe un programa que solicite al usuario ingresar números enteros uno por uno.
El programa debe sumar todos los números ingresados.
La entrada de números se detendrá cuando el usuario ingrese el número 0.
Al final, el programa debe mostrar la suma total de los números ingresados (sin incluir el 0 final).

## Código con Errores

```python
# Ejercicio: Sumar números hasta ingresar cero

suma_total = 0
print("Ingresa números para sumar. Ingresa 0 para terminar.")

while True: # Bucle infinito que dependerá de un break
    num_str = input("Número: ")
    num = int(num_str)

    if num = 0: # Pista 1
        break # Salir del bucle
    
    suma_total = num # Pista 2
    # Pista 3: ¿La indentación de la siguiente línea es correcta para que la suma se muestre solo al final?
print(f"La suma total es: {suma_total}") 
```

## Pistas para Corregir los Errores

*   **Pista 1:** Para verificar si `num` es igual a 0, ¿cuál es el operador de comparación correcto?
*   **Pista 2:** Si `suma_total` debe acumular la suma de todos los números ingresados, ¿cómo se actualiza una variable acumuladora? La asignación actual reemplaza la suma anterior.
*   **Pista 3:** El `print` que muestra la suma total debe estar *fuera* del bucle `while` para que se ejecute solo una vez, después de que el bucle haya terminado. Revisa su nivel de indentación.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Sumar números hasta ingresar cero

suma_total = 0
print("Ingresa números para sumar. Ingresa 0 para terminar.")

while True: # Bucle infinito que dependerá de un break
    num_str = input("Número: ")
    # Sería ideal usar try-except para la conversión
    if num_str.isdigit() or (num_str.startswith('-') and num_str[1:].isdigit()): # Validación simple para enteros (positivos o negativos)
        num = int(num_str)

        # Usar '==' para comparación
        if num == 0:
            break # Salir del bucle si el número es 0

        # Acumular la suma
        suma_total += num # Equivalente a suma_total = suma_total + num
    elif num_str.strip() == "0": # Caso especial si el usuario solo pone "0" con espacios
        break
    else:
        print("Entrada inválida. Por favor, ingresa un número entero.")
        continue # Saltar al siguiente ciclo del while sin procesar suma_total

# Este print debe estar fuera del bucle (sin indentación o con la misma que el while)
print(f"La suma total es: {suma_total}")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio utiliza un bucle `while True` que se rompe con `break` cuando se cumple una condición específica (ingresar 0), y acumula una suma.

*   **Error 1 Corrección (Operador de asignación en lugar de comparación):**
    *   El código original era `if num = 0:`.
    *   Se usó `=` (asignación) en lugar de `==` (comparación) para verificar si `num` es igual a 0.
    *   **Solución:** `if num == 0:`

*   **Error 2 Corrección (Actualización incorrecta del acumulador):**
    *   El código original era `suma_total = num`.
    *   Esto *reasigna* `suma_total` con el valor del número actual en cada iteración, en lugar de *sumar* el número actual a la `suma_total` existente.
    *   **Solución:** `suma_total += num` (o `suma_total = suma_total + num`).

*   **Error 3 Corrección (Indentación del `print` final):**
    *   El código original tenía `print(f"La suma total es: {suma_total}")` con la misma indentación que las líneas dentro del bucle `while`. Esto haría que la suma se imprimiera en *cada iteración* del bucle (después de la posible actualización de `suma_total`).
    *   El enunciado pide que la suma total se muestre *al final*, después de que el usuario ingrese 0 y el bucle termine.
    *   **Solución:** Desindentar la línea `print(f"La suma total es: {suma_total}")` para que quede fuera del bloque `while`.

**Mejoras en la Solución:**
La solución correcta también incluye una validación simple para la entrada del usuario (`num_str.isdigit() or ...`) para intentar asegurar que se convierta un entero. Si la entrada no es un entero válido (que no sea "0"), se imprime un mensaje de error y se usa `continue` para pasar a la siguiente iteración del bucle sin intentar sumar. Esto hace el programa un poco más robusto.

El flujo corregido es:
1.  Se inicializa `suma_total = 0`.
2.  Entra en un bucle `while True`.
3.  Pide un número.
4.  Si el número es 0, se rompe el bucle con `break`.
5.  Si no es 0 (y es un entero válido), se añade a `suma_total`.
6.  Si no es un entero válido, se muestra error y se continúa al inicio del bucle.
7.  Una vez que el bucle termina (por el `break`), se imprime `suma_total`.
</details>
