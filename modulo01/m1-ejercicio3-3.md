# Módulo 1: Ejercicio 3 (Dificultad 3/10) - Lista de Compras

## Enunciado del Problema

Escribe un programa en Python que muestre una pequeña lista de compras, con cada artículo en una nueva línea.
Ejemplo:
```
Lista de Compras:
- Manzanas
- Leche
- Pan
```

## Código con Errores

```python
# Ejercicio: Mostrar una lista de compras

print("Lista de Compras:")
print("- Manzanas) # Pista 1
print(- Leche")   # Pista 2
print(- Pan)      # Pista 3
```

## Pistas para Corregir los Errores

*   **Pista 1:** Una cadena de texto debe estar completamente encerrada por comillas. ¿Falta alguna?
*   **Pista 2:** Si inicias una cadena con un tipo de comilla, ¿debes asegurarte de que no haya otra comilla del mismo tipo *dentro* de la cadena a menos que la escapes, o usar un tipo diferente de comillas para encerrar? De forma más simple, ¿faltan las comillas de inicio o fin?
*   **Pista 3:** ¿Cómo le indicas a Python que un conjunto de caracteres es una cadena de texto literal?

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Mostrar una lista de compras

print("Lista de Compras:")
print("- Manzanas")
print("- Leche")
print("- Pan")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

El objetivo es practicar el uso de `print()` para generar múltiples líneas de salida, formando una lista.

*   **Error 1 Corrección (Comilla de cierre faltante):**
    *   El código original era `print("- Manzanas)`.
    *   La cadena de texto `"- Manzanas` tiene una comilla de apertura `"` pero le falta la comilla de cierre.
    *   **Solución:** `print("- Manzanas")`

*   **Error 2 Corrección (Comilla de apertura faltante):**
    *   El código original era `print(- Leche")`.
    *   La cadena de texto `- Leche"` tiene una comilla de cierre `"` pero le falta la comilla de apertura.
    *   **Solución:** `print("- Leche")`

*   **Error 3 Corrección (Texto sin comillas):**
    *   El código original era `print(- Pan)`.
    *   La secuencia `- Pan` no está entre comillas, por lo que Python no la interpreta como una cadena de texto literal. El guion podría interpretarse como un operador de negación si `Pan` fuera una variable numérica, pero aquí queremos mostrar el texto "- Pan".
    *   **Solución:** `print("- Pan")`

Cada llamada a `print()` con una cadena de texto correcta asegura que cada ítem de la lista, precedido por un guion, se muestre en una nueva línea, tal como se pide en el enunciado.
</details>
