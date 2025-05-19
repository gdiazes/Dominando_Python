# Módulo 1: Ejercicio 8 (Dificultad 8/10) - Figuras con Caracteres

## Enunciado del Problema

Escribe un programa en Python que dibuje una figura simple usando caracteres (como asteriscos, guiones, etc.). Por ejemplo, un pequeño cuadrado o un triángulo. La figura debe mostrarse en la consola.

Ejemplo de un cuadrado pequeño:
```
****
*  *
*  *
****
```

## Código con Errores

```python
# Ejercicio: Dibujar una figura simple

print("++++")
print("+  +"   # Pista 1: ¿Qué falta al final de esta línea para que sea una instrucción completa?
print('+  +)   # Pista 2: Comillas de apertura y cierre deben ser del mismo tipo.
print("----") # Pista 3: Esta línea es correcta. El "error" aquí es que la figura no coincide con el ejemplo. ¿Puedes modificarla y las anteriores para hacer el cuadrado del ejemplo?
```

## Pistas para Corregir los Errores

*   **Pista 1:** Cada llamada a la función `print` necesita estar correctamente estructurada. A menudo, los errores de sintaxis ocurren por paréntesis faltantes.
*   **Pista 2:** Python requiere que las cadenas de texto estén encerradas por comillas que coincidan (ambas simples o ambas dobles).
*   **Pista 3:** Este error es más sobre la lógica de la figura. El código dado produce *una* figura, pero el enunciado pide un cuadrado específico. Ajusta los caracteres dentro de las cadenas `print` para que coincidan con el ejemplo del cuadrado.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Dibujar una figura simple (un cuadrado)

print("****")
print("*  *")
print("*  *")
print("****")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio combina el uso de `print()` con la creatividad para formar figuras simples.

*   **Error 1 Corrección (Paréntesis de cierre faltante en `print`):**
    *   El código original era `print("+  +"   # Pista 1`.
    *   Le falta el paréntesis de cierre `)` para la función `print`.
    *   **Solución (sintáctica):** `print("+  +")` (y luego ajustar los caracteres para el cuadrado).

*   **Error 2 Corrección (Comillas no coincidentes):**
    *   El código original era `print('+  +)   # Pista 2`.
    *   La cadena comienza con una comilla simple `'` pero intenta cerrarse con una comilla doble `"` (implícitamente, ya que `)` está después). Esto es un error de sintaxis. Deben ser comillas del mismo tipo, o la que cierra está mal puesta. La intención era `print('+  +')`.
    *   **Solución (sintáctica):** `print('+  +')` o `print("+  +")` (y luego ajustar los caracteres).

*   **Error 3 Corrección (Lógica de la figura):**
    *   El código original, incluso con los errores sintácticos corregidos, dibujaría:
        ```
        ++++
        +  +
        +  +
        ----
        ```
    *   Esto no es el cuadrado `****` del ejemplo. Para formar el cuadrado del enunciado, las cadenas dentro de `print()` deben ser:
        *   `"****"`
        *   `"*  *"`
        *   `"*  *"`
        *   `"****"`
    *   **Solución (lógica de la figura):**
        ```python
        print("****")
        print("*  *")
        print("*  *")
        print("****")
        ```

El programa final, con las correcciones sintácticas y lógicas, dibuja el cuadrado solicitado.
</details>
