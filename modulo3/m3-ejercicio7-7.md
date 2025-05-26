# Módulo 3: Ejercicio 7 (Dificultad 7.7/10) - Reemplazar Palabras y Formatear Salida

## Enunciado del Problema

Se te da la siguiente frase: "El lenguaje_favorito es un lenguaje de programación popular y versátil."
1.  Solicita al usuario que ingrese su lenguaje de programación favorito.
2.  Reemplaza la subcadena "lenguaje_favorito" en la frase original con el lenguaje ingresado por el usuario.
3.  Muestra la frase modificada.
4.  Además, muestra la frase modificada pero con cada palabra comenzando en mayúscula (formato de título).

## Código con Errores

```python
# Ejercicio: Reemplazar palabras y formatear

frase_plantilla = "El lenguaje_favorito es un lenguaje de programación popular y versátil."

lenguaje_usuario = input("¿Cuál es tu lenguaje de programación favorito? ")

# Reemplazar en la plantilla
frase_modificada = frase_plantilla.replace("lenguaje_favorito", lenguaje_usuario) # Pista 1 (Este error es sutil o de omisión para el objetivo final)

print("Frase modificada: {frase_modificada}") # Pista 2
frase_titulo = frase_modificada.Title()
print(f"Frase en formato título: {frase_titulo}") # Pista 3
```

## Pistas para Corregir los Errores

*   **Pista 1:** El método `.replace()` funciona correctamente como está escrito para el reemplazo básico. El "error" aquí es más bien una oportunidad perdida: si el usuario ingresa su lenguaje en minúsculas (ej. "python") y la plantilla espera un formato específico o si quisiéramos asegurar una capitalización consistente en el reemplazo, podríamos necesitar un paso adicional. Para este ejercicio, consideremos que la lógica del reemplazo está bien, pero un error más adelante depende de esta línea.
*   **Pista 2:** Para que las variables se sustituyan dentro de una cadena usando llaves `{}`, ¿qué carácter especial debe preceder a la cadena?
*   **Pista 3:** Revisa el nombre del método para convertir una cadena a formato de título (primera letra de cada palabra en mayúscula). Python es sensible a mayúsculas/minúsculas.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Reemplazar palabras y formatear

frase_plantilla = "El lenguaje_favorito es un lenguaje de programación popular y versátil."

lenguaje_usuario = input("¿Cuál es tu lenguaje de programación favorito? ")

# Reemplazar en la plantilla
# No hay error sintáctico aquí, el reemplazo funciona.
# Si quisiéramos, por ejemplo, capitalizar el lenguaje del usuario antes de insertarlo:
# lenguaje_usuario_formateado = lenguaje_usuario.capitalize()
# frase_modificada = frase_plantilla.replace("lenguaje_favorito", lenguaje_usuario_formateado)
# Pero para el ejercicio, el reemplazo directo es aceptable y el error Pista 1 es más bien para dirigir la atención.
frase_modificada = frase_plantilla.replace("lenguaje_favorito", lenguaje_usuario)


# Usar f-string para la impresión
print(f"Frase modificada: {frase_modificada}")

# El método es .title()
frase_titulo = frase_modificada.title()
print(f"Frase en formato título: {frase_titulo}")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio utiliza el método `.replace()` y `.title()`.

*   **Error 1 Corrección (Sugerencia de mejora, no error sintáctico directo):**
    *   La línea `frase_modificada = frase_plantilla.replace("lenguaje_favorito", lenguaje_usuario)` es funcional. La pista sugiere pensar en el formato. Si el usuario ingresa "python" y la frase original es "El lenguaje_favorito...", el resultado será "El python es...". Si se deseara "El Python es...", se podría hacer `lenguaje_usuario.capitalize()` antes del reemplazo. Sin embargo, para el propósito de encontrar 3 errores "corregibles" en el código dado, esta línea no tiene un error de sintaxis o ejecución directa. El enunciado no exige una capitalización específica del `lenguaje_usuario` insertado.

*   **Error 2 Corrección (Falta de `f` para f-string):**
    *   El código original era `print("Frase modificada: {frase_modificada}")`.
    *   Para que `{frase_modificada}` sea interpretada como una variable cuyo valor se inserta en la cadena (es decir, para usar una f-string), la cadena debe comenzar con el prefijo `f`. Sin la `f`, `{frase_modificada}` se imprime literalmente.
    *   **Solución:** `print(f"Frase modificada: {frase_modificada}")`

*   **Error 3 Corrección (Nombre de método incorrecto):**
    *   El código original era `frase_titulo = frase_modificada.Title()`.
    *   El método para convertir una cadena a formato de título (la primera letra de cada palabra en mayúscula) es `.title()` (todo en minúsculas), no `.Title()`. Esto causaría un `AttributeError`.
    *   **Solución:** `frase_titulo = frase_modificada.title()`

El programa corregido reemplaza correctamente la subcadena, utiliza f-strings para la salida y aplica el método `.title()` correctamente.
</details>
