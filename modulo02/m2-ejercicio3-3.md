# Módulo 2: Ejercicio 3 (Dificultad 3/10) - Identificar Tipos de Datos

## Enunciado del Problema

Declara las siguientes variables con los valores indicados:
*   `valor_a = 100`
*   `valor_b = -5.5`
*   `valor_c = "Python"`
*   `valor_d = False`

Luego, para cada variable, imprime su valor y su tipo de dato utilizando la función `type()`.

Ejemplo de salida para `valor_a`:
```
El valor es 100 y su tipo es <class 'int'>
```

## Código con Errores

```python
# Ejercicio: Identificar tipos de datos

valor_a = 100
valor_b = -5.5
valor_c = Python # Pista 1
valor_d = "True" # Pista 2

print("El valor es", valor_a, "y su tipo es", type(valor_a)
print("El valor es", valor_b, "y su tipo es", Type(valor_b)) # Pista 3
print("El valor es", valor_c, "y su tipo es", type(valor_c))
print("El valor es", valor_d, "y su tipo es", type(valor_d))
```

## Pistas para Corregir los Errores

*   **Pista 1:** Si `Python` es un texto que quieres asignar a una variable, ¿cómo debes escribirlo?
*   **Pista 2:** Los valores booleanos en Python son `True` y `False` (con mayúscula inicial y sin comillas). Si lo pones entre comillas, ¿qué tipo de dato será?
*   **Pista 3:** Python es sensible a mayúsculas y minúsculas para sus funciones y palabras clave. Revisa el nombre de la función `type`. Además, ¿falta algo al final de la línea anterior?

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Identificar tipos de datos

valor_a = 100
valor_b = -5.5
valor_c = "Python"  # Debe ser una cadena
valor_d = True      # Debe ser un booleano, no una cadena "True" (o False, según el enunciado original)

# Faltaba un paréntesis de cierre en el print anterior
print("El valor es", valor_a, "y su tipo es", type(valor_a))
print("El valor es", valor_b, "y su tipo es", type(valor_b)) # type en minúscula
print("El valor es", valor_c, "y su tipo es", type(valor_c))
print("El valor es", valor_d, "y su tipo es", type(valor_d))
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio se enfoca en la correcta asignación de diferentes tipos de datos y el uso de la función `type()`.

*   **Error 1 Corrección (Cadena sin comillas):**
    *   El código original era `valor_c = Python`.
    *   Python intentaría interpretar `Python` como el nombre de otra variable o una palabra clave, pero se quiere asignar la cadena de texto "Python".
    *   **Solución:** `valor_c = "Python"` (o `'Python'`).

*   **Error 2 Corrección (Booleano como cadena):**
    *   El código original era `valor_d = "True"`.
    *   Esto asigna la cadena de texto `"True"` a `valor_d`, no el valor booleano `True`. El enunciado pide `False`, pero si fuera `True`, debe ser sin comillas. Para `False`, sería `valor_d = False`.
    *   **Solución (para que sea booleano como pide el enunciado implícitamente y el ejemplo de uso de booleano `False` en la guía):** `valor_d = False`. Si se quisiera `True`, sería `valor_d = True`.

*   **Error 3 Corrección (Nombre de función incorrecto y paréntesis faltante):**
    *   El código original tenía `print("El valor es", valor_a, "y su tipo es", type(valor_a)` (faltaba un paréntesis de cierre) y luego `Type(valor_b))` (la función es `type`, no `Type`).
    *   El `print` para `valor_a` no tenía su paréntesis de cierre, lo que causa un `SyntaxError`.
    *   La función para obtener el tipo es `type()` (todo en minúsculas). `Type()` con mayúscula causaría un `NameError`.
    *   **Solución:**
        ```python
        print("El valor es", valor_a, "y su tipo es", type(valor_a)) # Añadir paréntesis
        print("El valor es", valor_b, "y su tipo es", type(valor_b)) # Corregir 'Type' a 'type'
        ```

El programa corregido asigna correctamente los valores con sus tipos esperados y utiliza `type()` correctamente para mostrar la clase de cada variable.
</details>
