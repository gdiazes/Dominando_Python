# Módulo 1: Ejercicio 5 (Dificultad 5/10) - Datos de un Libro

## Enunciado del Problema

Escribe un programa en Python que muestre información sobre un libro ficticio o real. Debes mostrar el título, autor y año de publicación, cada uno en una línea separada.

Ejemplo de salida:
```
Título: Cien Años de Soledad
Autor: Gabriel García Márquez
Año: 1967
```

## Código con Errores

```python
# Ejercicio: Mostrar datos de un libro

print(Título: "El código Da Vinci") # Pista 1
print("Autor: Dan Brown) # Pista 2
print("Año: " 2003) # Pista 3
```

## Pistas para Corregir los Errores

*   **Pista 1:** Si una cadena de texto ya contiene comillas dobles en su interior (como parte del título), ¿qué tipo de comillas deberías usar para encerrar toda la cadena, o cómo puedes incluir comillas dentro de comillas del mismo tipo? De forma más simple aquí, ¿hay un desajuste en cómo se inicia y cómo se interpreta el texto?
*   **Pista 2:** Revisa que todas las cadenas de texto estén completamente encerradas. ¿Falta algo al final?
*   **Pista 3:** Si quieres mostrar un texto seguido de un número usando `print()` con un solo argumento de cadena, ¿cómo debes combinar el texto y el número? ¿O deberías pasarlos como argumentos separados?

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Mostrar datos de un libro

print("Título: El código Da Vinci")
# Alternativa si el título tuviera comillas que quisieras mostrar:
# print('Título: "El código Da Vinci"')
# o usando escape:
# print("Título: \"El código Da Vinci\"")

print("Autor: Dan Brown")
print("Año: 2003") # El número se puede incluir directamente en la cadena

# Alternativa para el año, separando la cadena y el número:
# print("Año:", 2003)
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio explora cómo manejar texto y cómo presentar información estructurada.

*   **Error 1 Corrección (Confusión de comillas / cadena mal formada):**
    *   El código original era `print(Título: "El código Da Vinci")`.
    *   Python ve `Título:` como si fuera una variable o una palabra clave, y luego `"El código Da Vinci"` como una cadena separada, pero la sintaxis no es correcta para `print()` de esta manera. Lo que se quiere es imprimir toda la frase "Título: El código Da Vinci".
    *   **Solución:** Encerrar toda la frase en comillas: `print("Título: El código Da Vinci")`.
    *   Si el título mismo necesitara contener comillas dobles (ej., `Título: "Cita Libro" Algo Más`), podrías usar comillas simples para delimitar la cadena principal: `print('Título: "Cita Libro" Algo Más')` o escapar las comillas internas: `print("Título: \"Cita Libro\" Algo Más")`. Para este ejercicio, la solución simple es suficiente.

*   **Error 2 Corrección (Comilla de cierre faltante):**
    *   El código original era `print("Autor: Dan Brown)`.
    *   Falta la comilla doble de cierre `"` al final de la cadena.
    *   **Solución:** `print("Autor: Dan Brown")`

*   **Error 3 Corrección (Concatenación implícita incorrecta / Número fuera de cadena):**
    *   El código original era `print("Año: " 2003)`.
    *   Python no concatena automáticamente una cadena y un número de esta forma dentro de un solo `print()` si están separados solo por un espacio. Esto resultaría en un `SyntaxError`.
    *   Hay dos formas principales de solucionarlo:
        1.  Incluir el número como parte de la cadena: `print("Año: 2003")` (la más simple para este caso).
        2.  Pasar la cadena y el número como argumentos separados a `print()`, y `print()` los unirá con un espacio: `print("Año:", 2003)`.
    *   **Solución (simple):** `print("Año: 2003")`

El programa corregido muestra cada dato del libro en una línea, utilizando cadenas de texto correctamente formadas.
</details>
