# Módulo 1: Ejercicio 1 (Dificultad 1/10) - Saludo Básico

## Enunciado del Problema

Escribir un programa en Python que muestre el mensaje "¡Bienvenido al curso de Python!" en la pantalla.

## Código con Errores

```python
# Ejercicio: Mostrar un saludo básico

prin("¡Bienvenido al curso de Python!) # Pista 1

# print("¡Todo programador empieza con un saludo!" # Pista 2

print(Este es mi primer programa) # Pista 3
```

## Pistas para Corregir los Errores

*   **Pista 1:** Revisa cuidadosamente el nombre de la función utilizada para mostrar texto en la pantalla. ¿Está escrito correctamente?
*   **Pista 2:** Las cadenas de texto necesitan estar completamente encerradas. Si abres comillas, asegúrate de cerrarlas.
*   **Pista 3:** Cuando deseas que Python muestre una frase o un texto literal exactamente como lo escribes, este debe ir entre comillas.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Mostrar un saludo básico

# Solución para la primera línea con error:
print("¡Bienvenido al curso de Python!")

# La segunda línea original estaba comentada y tenía un error de comillas.
# Si se quisiera ejecutar correctamente, sería:
# print("¡Todo programador empieza con un saludo!")

# Solución para la tercera línea con error:
print("Este es mi primer programa")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

El objetivo de este ejercicio es familiarizarse con la función `print()` y la forma correcta de escribir cadenas de texto en Python.

*   **Error 1 Corrección (`prin` -> `print` y comilla faltante):**
    *   El código original tenía `prin("¡Bienvenido al curso de Python!)`.
    *   El primer error era que el nombre de la función estaba mal escrito. La función correcta para imprimir en Python es `print`.
    *   El segundo error en la misma línea era la falta de la comilla de cierre `"` al final de la cadena de texto.
    *   **Solución:** `print("¡Bienvenido al curso de Python!")`

*   **Error 2 Corrección (Comillas Faltantes en línea comentada):**
    *   El código original era `# print("¡Todo programador empieza con un saludo!"`.
    *   Aunque la línea estaba comentada (lo que significa que Python la ignora), si se intentara descomentar para ejecutarla, el error sería la falta de la comilla de cierre `"`.
    *   **Solución (si se descomenta):** `print("¡Todo programador empieza con un saludo!")`

*   **Error 3 Corrección (Texto sin Comillas):**
    *   El código original tenía `print(Este es mi primer programa)`.
    *   Python interpreta `Este`, `es`, `mi`, `primer`, `programa` como si fueran nombres de variables separadas o palabras clave, lo que generaría un `SyntaxError` porque no es una sintaxis válida para la función `print` con texto literal de esa forma.
    *   Para que Python trate "Este es mi primer programa" como una única cadena de texto que debe ser impresa literalmente, debe estar encerrada entre comillas (simples `' '` o dobles `" "`).
    *   **Solución:** `print("Este es mi primer programa")`

En resumen, para mostrar texto (cadenas o *strings*) con la función `print()`, el texto debe ir entre comillas (`"` o `'`) y la función debe llamarse correctamente como `print()`.
</details>


