# Módulo 1: Ejercicio 2 (Dificultad 2/10) - Presentación Personal

## Enunciado del Problema

Escribe un programa en Python que muestre tu nombre completo y tu edad en dos líneas separadas.
Por ejemplo:
```
Nombre: [Tu Nombre Completo Aquí]
Edad: [Tu Edad Aquí]
```

## Código con Errores

```python
# Ejercicio: Mostrar nombre y edad

print(Nombre: Juan Pérez") # Pista 1
print('Edad: 30) # Pista 2
print(Mi pasatiempo favorito es programar) # Pista 3
```

## Pistas para Corregir los Errores

*   **Pista 1:** Las cadenas de texto deben comenzar y terminar con el mismo tipo de comilla. Si empiezas con comillas dobles, debes terminar con comillas dobles.
*   **Pista 2:** Revisa si todas las comillas que abriste han sido cerradas correctamente.
*   **Pista 3:** Aunque esta línea no es parte del requisito original, si quisieras imprimirla como una cadena literal, ¿qué le falta?

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Mostrar nombre y edad

print("Nombre: Ana García") # Reemplaza con tu nombre
print("Edad: 25")         # Reemplaza con tu edad

# La tercera línea original no era parte del requisito,
# pero si se quisiera imprimir correctamente:
# print("Mi pasatiempo favorito es programar")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio se enfoca en usar múltiples llamadas a `print()` para mostrar información en líneas separadas y en la correcta delimitación de cadenas de texto.

*   **Error 1 Corrección (Comilla de apertura faltante):**
    *   El código original era `print(Nombre: Juan Pérez")`.
    *   El problema es que la cadena de texto "Nombre: Juan Pérez" no tiene una comilla de apertura. Python espera que las cadenas estén completamente encerradas.
    *   **Solución:** `print("Nombre: Juan Pérez")` (o usando comillas simples: `print('Nombre: Juan Pérez')`)

*   **Error 2 Corrección (Comilla de cierre faltante):**
    *   El código original era `print('Edad: 30)`.
    *   Aquí, la cadena 'Edad: 30' tiene una comilla simple de apertura pero le falta la comilla simple de cierre.
    *   **Solución:** `print('Edad: 30')` (o usando comillas dobles: `print("Edad: 30")`)

*   **Error 3 Corrección (Texto sin comillas):**
    *   El código original era `print(Mi pasatiempo favorito es programar)`.
    *   Al igual que en el ejercicio anterior, para que Python interprete esto como una cadena de texto literal, debe estar entre comillas.
    *   **Solución (si se quisiera incluir):** `print("Mi pasatiempo favorito es programar")`

El programa final utiliza dos sentencias `print()` separadas. Cada `print()` por defecto añade un salto de línea al final, por lo que el nombre y la edad aparecerán en líneas distintas.
</details>
