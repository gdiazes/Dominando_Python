# Módulo 2: Ejercicio 1 (Dificultad 1/10) - Declaración de Variables Personales

## Enunciado del Problema

Declara tres variables:
1.  Una llamada `nombre_completo` que almacene tu nombre completo como una cadena de texto.
2.  Una llamada `edad_actual` que almacene tu edad como un número entero.
3.  Una llamada `altura_metros` que almacene tu altura en metros como un número flotante (por ejemplo, 1.75).

Luego, imprime cada una de estas variables en una línea separada, precedida por una descripción.
Ejemplo de salida:
```
Mi nombre es: [Tu Nombre Completo Aquí]
Mi edad es: [Tu Edad Aquí]
Mi altura es: [Tu Altura Aquí] metros
```

## Código con Errores

```python
# Ejercicio: Declarar variables personales e imprimirlas

nombre_completo = Carlos Santana" # Pista 1
edad.actual = 35
altura_metros = "1.82" # Pista 2

print("Mi nombre es: " + nombre_completo)
print("Mi edad es: " + edad_actual) # Pista 3
print("Mi altura es: ", altura_metros, " metros")
```

## Pistas para Corregir los Errores

*   **Pista 1:** Las cadenas de texto deben estar completamente encerradas por comillas. Revisa el inicio de esta asignación.
*   **Pista 2:** Si la altura debe ser un número flotante para posibles cálculos futuros, ¿es correcto asignarla como una cadena de texto? ¿Cómo se representa un número flotante directamente?
*   **Pista 3:** No se puede concatenar directamente una cadena con un número entero usando el operador `+`. ¿Cómo puedes solucionarlo, o qué otra forma de usar `print` con múltiples elementos conoces?

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Declarar variables personales e imprimirlas

nombre_completo = "Carlos Santana" # Comilla de apertura faltante
edad_actual = 35                   # Nombre de variable corregido
altura_metros = 1.82               # Convertido a float, no string

print("Mi nombre es:", nombre_completo)
print("Mi edad es:", edad_actual) # Usar coma para print o str(edad_actual) para concatenar
print("Mi altura es:", altura_metros, "metros")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio se enfoca en la correcta declaración de variables con diferentes tipos de datos y su impresión.

*   **Error 1 Corrección (Comilla de apertura faltante en cadena):**
    *   El código original era `nombre_completo = Carlos Santana"`.
    *   La cadena de texto `Carlos Santana"` no tiene una comilla de apertura.
    *   **Solución:** `nombre_completo = "Carlos Santana"`

*   **Error 2 Corrección (Nombre de variable inválido y tipo incorrecto para altura):**
    *   El código original para la edad era `edad.actual = 35`. Los puntos no son válidos en los nombres de variables de esta manera (se usan para acceder a atributos de objetos, lo cual es un concepto más avanzado). Se esperaba `edad_actual`.
    *   El código original para la altura era `altura_metros = "1.82"`. Esto asigna la cadena de texto "1.82", no el número flotante 1.82. Si bien se puede imprimir, no se podrían hacer cálculos matemáticos directamente con ella.
    *   **Solución para edad:** `edad_actual = 35`
    *   **Solución para altura:** `altura_metros = 1.82` (sin comillas para que sea un número flotante).

*   **Error 3 Corrección (Concatenación de cadena y entero con `+`):**
    *   El código original era `print("Mi edad es: " + edad_actual)`.
    *   En Python, no puedes usar el operador `+` para concatenar directamente una cadena de texto (`"Mi edad es: "`) con un número entero (`edad_actual`) o flotante. Esto causa un `TypeError`.
    *   Hay dos formas principales de solucionarlo:
        1.  **Convertir el número a cadena:** `print("Mi edad es: " + str(edad_actual))`
        2.  **Usar comas en `print`:** `print("Mi edad es:", edad_actual)`. La función `print` puede tomar múltiples argumentos separados por comas y los imprimirá separados por un espacio por defecto. Esta es a menudo la forma más simple y legible para estos casos.
    *   **Solución (usando comas):** `print("Mi edad es:", edad_actual)`

El programa corregido declara las variables con los tipos y nombres correctos, y luego las imprime utilizando el método de pasar múltiples argumentos a `print()` separados por comas, lo cual maneja automáticamente la conversión a cadena para la visualización.
</details>
