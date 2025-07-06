# Módulo 5: Ejercicio 3 (Dificultad 3.3/10) - Mostrar Caracteres de una Cadena y sus Índices

## Enunciado del Problema

Solicita al usuario que ingrese una palabra.
Luego, utiliza un bucle `for` para mostrar cada carácter de la palabra en una línea separada, junto con su índice (posición).

Ejemplo de salida (si el usuario ingresa "PYTHON"):
```
Índice 0: P
Índice 1: Y
Índice 2: T
Índice 3: H
Índice 4: O
Índice 5: N
```

## Código con Errores

```python
# Ejercicio: Mostrar caracteres de una cadena y sus índices

palabra = input("Ingresa una palabra: ")
indice_actual = 0

print("Caracteres e índices:")
for caracter in palabra # Pista 1
    print(f"Índice {indice}: {caracter}") # Pista 2
    indice_actual =+ 1 # Pista 3
```

## Pistas para Corregir los Errores

*   **Pista 1:** La línea `for` que inicia el bucle debe terminar con un carácter específico.
*   **Pista 2:** La variable que almacena el índice actual se llama `indice_actual`. ¿Es ese el nombre que se está usando en la f-string?
*   **Pista 3:** El operador para incrementar una variable en 1 (o cualquier valor) y asignarlo de nuevo a la misma variable es `+=`. ¿La sintaxis `=+` es correcta para esto?

*Nota sobre la obtención de índices:* Aunque este ejercicio pide mantener un contador de índice manual, Python ofrece la función `enumerate()` que es más idiomática para obtener tanto el índice como el valor al iterar. Se mencionará en la explicación como una alternativa.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Mostrar caracteres de una cadena y sus índices

palabra = input("Ingresa una palabra: ")
indice_actual = 0

print("Caracteres e índices:")
for caracter in palabra: # Falta ':'
    # Usar la variable correcta para el índice
    print(f"Índice {indice_actual}: {caracter}")
    # Incrementar correctamente el índice
    indice_actual += 1 # Forma correcta de incrementar

# Solución alternativa usando enumerate():
# print("\nUsando enumerate():")
# for indice, caracter_enum in enumerate(palabra):
#     print(f"Índice {indice}: {caracter_enum}")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio se enfoca en iterar sobre una cadena y mantener un contador de índice manual.

*   **Error 1 Corrección (Falta de dos puntos en `for`):**
    *   El código original era `for caracter in palabra`.
    *   La declaración del bucle `for` debe terminar con dos puntos (`:`).
    *   **Solución:** `for caracter in palabra:`

*   **Error 2 Corrección (Nombre de variable incorrecto en f-string):**
    *   El código original era `print(f"Índice {indice}: {caracter}")`.
    *   La variable que se está actualizando manualmente para llevar la cuenta del índice se llama `indice_actual`. Usar `indice` (sin `_actual`) causaría un `NameError` ya que `indice` no está definido en ese contexto.
    *   **Solución:** `print(f"Índice {indice_actual}: {caracter}")`

*   **Error 3 Corrección (Operador de incremento incorrecto):**
    *   El código original era `indice_actual =+ 1`.
    *   El operador `=+` no es el operador de incremento y asignación. Se interpretaría como `indice_actual = (+1)`, es decir, asignar el valor `1` a `indice_actual` en cada iteración, lo que no incrementaría el índice.
    *   El operador correcto para "sumar 1 a `indice_actual` y guardar el resultado en `indice_actual`" es `+=`.
    *   **Solución:** `indice_actual += 1`

**Alternativa con `enumerate()`:**
Python proporciona una forma más elegante y "Pythónica" de obtener tanto el índice como el valor al iterar sobre una secuencia, utilizando la función `enumerate()`:
```python
palabra = input("Ingresa una palabra: ")
print("\nUsando enumerate():")
for indice, caracter_enum in enumerate(palabra):
    print(f"Índice {indice}: {caracter_enum}")
```
`enumerate(palabra)` devuelve pares de `(índice, valor)` en cada iteración. Esto elimina la necesidad de inicializar e incrementar manualmente una variable de índice. Aunque el ejercicio pedía la forma manual para practicar el concepto de contador, es bueno conocer `enumerate()`.
</details>
