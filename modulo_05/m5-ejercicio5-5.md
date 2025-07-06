# Módulo 5: Ejercicio 5 (Dificultad 5.5/10) - Contar Vocales y Consonantes en una Frase

## Enunciado del Problema

Solicita al usuario que ingrese una frase.
El programa debe contar y mostrar:
1.  El número total de vocales (a, e, i, o, u, sin importar mayúsculas o minúsculas).
2.  El número total de consonantes (cualquier letra que no sea vocal).
3.  No contar espacios ni otros símbolos como letras.

Ejemplo (si se ingresa "Hola Mundo 123!"):
```
Vocales: 4
Consonantes: 6
```

## Código con Errores

```python
# Ejercicio: Contar vocales y consonantes

frase = input("Ingresa una frase: ")
frase_procesar = frase.lower() # Convertir a minúsculas para facilitar conteo

contador_vocales = 0
contador_consonantes = 0
VOCALES = "aeiou"

for caracter in frase_procesar:
    if caracter in VOCALES:
        contador_vocales += 1
    elif caracter not in VOCALES: # Pista 1
        contador_consonantes += 1
    # Pista 2: ¿El bloque elif anterior cuenta correctamente solo las consonantes o también otros caracteres?
# Pista 3: La lógica para contar consonantes debe asegurar que el caracter sea una letra primero.

print(f"Vocales: {contador_vocales}")
print(f"Consonantes: {contador_consonantes}")
```

## Pistas para Corregir los Errores

*   **Pista 1:** La condición `elif caracter not in VOCALES:` es lógicamente opuesta a la primera. ¿Es necesaria o un simple `else` bastaría si solo hubiera vocales y consonantes? Sin embargo, el problema tiene una trampa mayor aquí.
*   **Pista 2:** Si un carácter no es una vocal (entra en el `elif`), ¿es automáticamente una consonante? ¿Qué pasa con los espacios, números o signos de puntuación?
*   **Pista 3:** Para contar una consonante, primero debes asegurarte de que el carácter es una letra del alfabeto, y luego que no es una vocal. ¿Falta alguna verificación?

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Contar vocales y consonantes

frase = input("Ingresa una frase: ")
frase_procesar = frase.lower() # Convertir a minúsculas para facilitar conteo

contador_vocales = 0
contador_consonantes = 0
VOCALES = "aeiou"
# Para verificar si es una letra del alfabeto (en minúsculas)
ALFABETO = "abcdefghijklmnopqrstuvwxyz" # O usar string.ascii_lowercase

for caracter in frase_procesar:
    if caracter in VOCALES:
        contador_vocales += 1
    # Para ser consonante, debe ser una letra del alfabeto Y NO una vocal
    elif caracter in ALFABETO and caracter not in VOCALES: # Corrección principal
        contador_consonantes += 1
    # Los espacios, números y otros símbolos se ignoran y no se cuentan.

print(f"Vocales: {contador_vocales}")
print(f"Consonantes: {contador_consonantes}")

# Alternativa usando métodos de cadena más directos:
# import string
# contador_vocales_alt = 0
# contador_consonantes_alt = 0
# for caracter in frase.lower(): # procesar la versión en minúsculas
#     if caracter.isalpha(): # Primero verificar si es una letra
#         if caracter in "aeiou":
#             contador_vocales_alt += 1
#         else:
#             contador_consonantes_alt += 1
# print(f"Vocales (alt): {contador_vocales_alt}")
# print(f"Consonantes (alt): {contador_consonantes_alt}")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio requiere una lógica cuidadosa para distinguir entre vocales, consonantes y otros caracteres.

*   **Error 1, 2 y 3 Corrección (Lógica incorrecta para contar consonantes):**
    *   El código original tenía:
        ```python
        if caracter in VOCALES:
            contador_vocales += 1
        elif caracter not in VOCALES: # Pista 1
            contador_consonantes += 1
        ```
    *   El problema principal es que la condición `elif caracter not in VOCALES:` es verdadera para cualquier carácter que no sea una vocal, incluyendo espacios, números, signos de puntuación, etc. Esto haría que `contador_consonantes` se incremente incorrectamente.
    *   Para que un carácter sea una consonante, debe cumplir dos condiciones:
        1.  Debe ser una letra del alfabeto.
        2.  No debe ser una vocal.
    *   **Solución:**
        ```python
        ALFABETO = "abcdefghijklmnopqrstuvwxyz" # o importar string.ascii_lowercase
        # ...
        if caracter in VOCALES:
            contador_vocales += 1
        elif caracter in ALFABETO and caracter not in VOCALES:
            contador_consonantes += 1
        ```
    *   Una forma alternativa y a menudo preferida es usar el método de cadena `.isalpha()` para verificar si un carácter es una letra:
        ```python
        if caracter.isalpha(): # Es una letra del alfabeto
            if caracter in VOCALES: # (asumiendo que caracter ya está en minúsculas)
                contador_vocales += 1
            else: # Si es una letra y no es vocal, es consonante
                contador_consonantes += 1
        ```
        Esta segunda aproximación es más robusta si se quiere manejar alfabetos con caracteres acentuados o diferentes, aunque `VOCALES` también tendría que expandirse. Para el alcance de este ejercicio, la primera solución con una cadena `ALFABETO` es clara.

La solución corregida procesa la frase en minúsculas. Luego, para cada carácter:
1.  Si está en la cadena `VOCALES`, se cuenta como vocal.
2.  Si no es vocal, se verifica adicionalmente si es una letra del `ALFABETO`. Solo si cumple ambas condiciones (ser letra y no ser vocal) se cuenta como consonante.
Esto asegura que los espacios, números y otros símbolos no se cuenten ni como vocales ni como consonantes.
</details>
