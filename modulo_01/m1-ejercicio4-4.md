# Módulo 1: Ejercicio 4 (Dificultad 4/10) - Poema Corto

## Enunciado del Problema

Escribe un programa en Python que muestre las dos primeras líneas de un poema o canción que te guste. Cada línea del poema debe aparecer en una línea separada en la salida.

Ejemplo de salida:
```
En un lugar de la Mancha,
de cuyo nombre no quiero acordarme...
```

## Código con Errores

```python
# Ejercicio: Mostrar un poema corto

print(En un lugar de la Mancha,") # Pista 1
Print('de cuyo nombre no quiero acordarme...') # Pista 2
# print("no ha mucho tiempo que vivía un hidalgo") # Pista 3 (esta línea es correcta pero está comentada)
```

## Pistas para Corregir los Errores

*   **Pista 1:** Las cadenas de texto deben estar completamente encerradas por comillas. Revisa el inicio de esta cadena.
*   **Pista 2:** Python es sensible a mayúsculas y minúsculas para sus palabras clave y nombres de funciones.
*   **Pista 3:** Los comentarios (`#`) hacen que Python ignore el resto de la línea. Si quieres que una línea se ejecute, no debe estar comentada.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Mostrar un poema corto

print("En un lugar de la Mancha,")
print("de cuyo nombre no quiero acordarme...")

# Si se quisiera añadir la tercera línea, se descomentaría:
# print("no ha mucho tiempo que vivía un hidalgo")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio refuerza el uso de `print()` para múltiples líneas y la atención a los detalles de sintaxis como mayúsculas/minúsculas y comentarios.

*   **Error 1 Corrección (Comilla de apertura faltante):**
    *   El código original era `print(En un lugar de la Mancha,")`.
    *   La cadena de texto `En un lugar de la Mancha,"` no tiene una comilla de apertura.
    *   **Solución:** `print("En un lugar de la Mancha,")`

*   **Error 2 Corrección (Nombre de función incorrecto - mayúscula):**
    *   El código original era `Print('de cuyo nombre no quiero acordarme...')`.
    *   Python es sensible a mayúsculas y minúsculas. La función para imprimir es `print` (todo en minúsculas), no `Print`. Esto causaría un `NameError`.
    *   **Solución:** `print('de cuyo nombre no quiero acordarme...')`

*   **Error 3 Corrección (Línea comentada innecesariamente para el requisito):**
    *   El código original tenía `# print("no ha mucho tiempo que vivía un hidalgo")`.
    *   Esta línea es sintácticamente correcta, pero al estar comentada con `#`, Python no la ejecuta. El enunciado pide solo dos líneas, por lo que para cumplir estrictamente, esta línea no es necesaria, o si fuera una de las dos líneas requeridas, se debería descomentar. Dado que las dos primeras líneas con errores ya formaban las dos líneas del poema requeridas, este "error" es más sobre la intención del código versus el comentario.
    *   **Solución (para el problema de dos líneas):** No es necesario cambiarla si las dos primeras líneas ya cumplen. Si esta fuera una línea requerida, se quitaría el `#`.

El programa resuelto muestra correctamente las dos primeras líneas del Quijote, cada una en una nueva línea, utilizando la función `print()` con la sintaxis adecuada.
</details>
