# Módulo 1: Ejercicio 10 (Dificultad 10/10) - Mensaje de Bienvenida Elaborado

## Enunciado del Problema

Escribe un programa en Python que muestre un mensaje de bienvenida más elaborado, utilizando múltiples líneas y quizás algunos caracteres para decorarlo, como un borde simple.

Ejemplo de salida:
```
*************************************
*                                   *
*   ¡Bienvenido al Mundo de Python! *
*                                   *
*************************************
```

## Código con Errores

```python
# Ejercicio: Mensaje de bienvenida elaborado

linea_superior = "*************************************"
linea_vacia = *                                   *  # Pista 1
mensaje = "*   ¡Bienvenido al Mundo de Python! *"
print(linea_superior)
print(linea_vacia
print(mensaje) # Pista 2
print(linea_vacia)
print(linea_superior # Pista 3
```

## Pistas para Corregir los Errores

*   **Pista 1:** Si quieres asignar una cadena de texto que contiene principalmente espacios y asteriscos en los extremos a una variable, ¿cómo debes delimitar esa cadena?
*   **Pista 2:** Una instrucción `print` que falta su paréntesis de cierre puede causar problemas en la línea siguiente o un error de sintaxis.
*   **Pista 3:** Cada función `print` necesita sus propios paréntesis de cierre.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Mensaje de bienvenida elaborado

linea_superior = "*************************************"
linea_vacia    = "*                                   *" # Necesitaba comillas
mensaje        = "*   ¡Bienvenido al Mundo de Python! *"

print(linea_superior)
print(linea_vacia)    # Faltaba el paréntesis de cierre en el print anterior
print(mensaje)
print(linea_vacia)
print(linea_superior) # Faltaba el paréntesis de cierre
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio final del módulo combina el uso de variables para almacenar partes del mensaje (aunque aún no hemos visto variables formalmente, se introducen aquí como un adelanto simple) y `print()` para construir una salida más compleja.

*   **Error 1 Corrección (Cadena sin comillas en asignación):**
    *   El código original era `linea_vacia = *                                   *`.
    *   Para asignar la secuencia de caracteres `*                                   *` a la variable `linea_vacia` como una cadena de texto, esta debe estar encerrada en comillas.
    *   **Solución:** `linea_vacia    = "*                                   *"`

*   **Error 2 Corrección (Paréntesis faltante en `print` anterior):**
    *   El código original tenía:
        ```python
        print(linea_vacia
        print(mensaje) # Pista 2
        ```
    *   La instrucción `print(linea_vacia` no tiene su paréntesis de cierre `)`. Esto causa un `SyntaxError`, a menudo reportado en la línea siguiente (`print(mensaje)`).
    *   **Solución:** `print(linea_vacia)`

*   **Error 3 Corrección (Paréntesis faltante en el último `print`):**
    *   El código original era `print(linea_superior # Pista 3`.
    *   Similar al error anterior, a esta instrucción `print` le falta su paréntesis de cierre `)`.
    *   **Solución:** `print(linea_superior)`

Aunque las variables (`linea_superior`, `linea_vacia`, `mensaje`) se introducen aquí brevemente, el foco principal sigue siendo el uso correcto de `print()` y la sintaxis de las cadenas. El uso de variables ayuda a no repetir las mismas cadenas literales. El concepto de variables se explorará a fondo en el Módulo 2.
</details>
