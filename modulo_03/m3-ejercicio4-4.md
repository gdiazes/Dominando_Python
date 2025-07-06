## Enunciado del Problema

Solicita al usuario que ingrese una frase.
Luego, el programa debe:
1.  Mostrar la frase original.
2.  Mostrar la frase convertida completamente a mayúsculas.
3.  Mostrar la frase convertida completamente a minúsculas.
4.  Mostrar la longitud (número de caracteres) de la frase original.

Ejemplo de salida (si el usuario ingresa "Python es Genial"):
```
Original: Python es Genial
MAYÚSCULAS: PYTHON ES GENIAL
minúsculas: python es genial
Longitud: 16
```

## Código con Errores

```python
# Ejercicio: Convertir frase a mayúsculas/minúsculas y mostrar longitud

frase_original = input("Ingresa una frase: ")

print(f"Original: {frase_original}")
print(f"MAYÚSCULAS: {frase_original.Upper()}") # Pista 1
frase_minusculas = frase_original.lower
print(f"minúsculas: {frase_minusculas}") # Pista 2

longitud = len(Frase_Original) # Pista 3
print(f"Longitud: {longitud}")
```

## Pistas para Corregir los Errores

*   **Pista 1:** Los nombres de los métodos de cadena en Python suelen seguir una convención específica de mayúsculas/minúsculas. Revisa cómo se llama el método para convertir a mayúsculas.
*   **Pista 2:** Cuando llamas a un método de un objeto (como los métodos de cadena), ¿qué necesitas incluir al final del nombre del método para que se ejecute?
*   **Pista 3:** Python es sensible a mayúsculas y minúsculas para los nombres de variables. La función `len()` espera el nombre exacto de la variable.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Convertir frase a mayúsculas/minúsculas y mostrar longitud

frase_original = input("Ingresa una frase: ")

print(f"Original: {frase_original}")
# El método es .upper()
print(f"MAYÚSCULAS: {frase_original.upper()}")

# Se deben llamar a los métodos con paréntesis: .lower()
frase_minusculas = frase_original.lower()
print(f"minúsculas: {frase_minusculas}")

# El nombre de la variable es frase_original
longitud = len(frase_original)
print(f"Longitud: {longitud}")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio practica el uso de métodos de cadena comunes (`.upper()`, `.lower()`) y la función `len()`.

*   **Error 1 Corrección (Nombre de método incorrecto):**
    *   El código original era `print(f"MAYÚSCULAS: {frase_original.Upper()}")`.
    *   Los métodos de cadena en Python, como el que convierte a mayúsculas, se escriben en minúsculas. El método correcto es `.upper()`, no `.Upper()`. El uso incorrecto causaría un `AttributeError`.
    *   **Solución:** `print(f"MAYÚSCULAS: {frase_original.upper()}")`

*   **Error 2 Corrección (Llamada a método sin paréntesis):**
    *   El código original era `frase_minusculas = frase_original.lower`.
    *   Cuando se utiliza un método de un objeto (como `.lower()` de una cadena), se debe llamar con paréntesis `()` al final, incluso si no toma argumentos. Sin los paréntesis, `frase_minusculas` se asignaría al objeto método en sí, no al resultado de ejecutar el método (la cadena en minúsculas). Al intentar imprimir `frase_minusculas`, se mostraría algo como `<built-in method lower of str object at ...>` en lugar de la cadena esperada.
    *   **Solución:** `frase_minusculas = frase_original.lower()`

*   **Error 3 Corrección (Nombre de variable incorrecto en `len()`):**
    *   El código original era `longitud = len(Frase_Original)`.
    *   La variable que contiene la frase ingresada por el usuario se llama `frase_original` (todo en minúsculas y con guion bajo). Usar `Frase_Original` (con mayúsculas) en la función `len()` causaría un `NameError`.
    *   **Solución:** `longitud = len(frase_original)`

El programa corregido solicita una frase, aplica correctamente los métodos `.upper()` y `.lower()` (con sus respectivos paréntesis), y utiliza `len()` con el nombre de variable correcto para obtener y mostrar la información solicitada.
</details>
