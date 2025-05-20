# Módulo 2: Ejercicio 4 (Dificultad 4/10) - Cálculo de Área de Rectángulo

## Enunciado del Problema

Declara dos variables, `base_rectangulo` y `altura_rectangulo`, y asígnales valores numéricos (pueden ser enteros o flotantes).
Calcula el área del rectángulo (área = base * altura) y almacénala en una variable llamada `area_rectangulo`.
Imprime el resultado de forma descriptiva.

Ejemplo de salida (si base=5 y altura=3):
```
El área de un rectángulo con base 5 y altura 3 es: 15
```

## Código con Errores

```python
# Ejercicio: Calcular el área de un rectángulo

base_rectangulo = 10
altura_rectangulo = "7" # Pista 1
area_rectangulo = base_rectangulo * altura_rectangulo # Pista 2

print("El área de un rectángulo con base", base_rectangulo) # Pista 3
print("y altura", altura_rectangulo, "es:", area_rectangulo)
```

## Pistas para Corregir los Errores

*   **Pista 1:** Si la altura se va a usar en una multiplicación matemática, ¿cuál debería ser su tipo de dato?
*   **Pista 2:** ¿Qué sucede si intentas multiplicar un número por una cadena de texto en Python? (Pista: puede que no sea lo que esperas para un cálculo de área).
*   **Pista 3:** El mensaje de salida está dividido en dos `print`. ¿Se puede hacer en uno solo para que coincida mejor con el formato del ejemplo? Si se mantiene en dos, ¿la primera línea da toda la información necesaria?

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Calcular el área de un rectángulo

base_rectangulo = 10
altura_rectangulo = 7 # Debe ser un número, no una cadena

# La multiplicación ahora será aritmética
area_rectangulo = base_rectangulo * altura_rectangulo

# Imprimir en una sola línea para mayor claridad y como el ejemplo
print("El área de un rectángulo con base", base_rectangulo, "y altura", altura_rectangulo, "es:", area_rectangulo)
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio se enfoca en el uso de variables para cálculos y la correcta manipulación de tipos de datos.

*   **Error 1 Corrección (Tipo incorrecto para `altura_rectangulo`):**
    *   El código original era `altura_rectangulo = "7"`.
    *   Esto asigna la cadena `"7"`, no el número `7`. Para la multiplicación matemática, necesitamos un tipo numérico.
    *   **Solución:** `altura_rectangulo = 7` (o `7.0` si se quisiera flotante explícitamente).

*   **Error 2 Corrección (Operación de multiplicación incorrecta):**
    *   El código original era `area_rectangulo = base_rectangulo * altura_rectangulo`.
    *   Si `base_rectangulo` es un entero (ej. `10`) y `altura_rectangulo` es una cadena (ej. `"7"`), Python interpreta la multiplicación `*` como "repetir la cadena". Así, `10 * "7"` resultaría en la cadena `"7777777777"`, lo cual no es el área.
    *   Al corregir el Error 1 (haciendo `altura_rectangulo` un número), esta línea ahora realizará una multiplicación aritmética.
    *   **Solución (implícita al corregir Error 1):** `area_rectangulo` ahora calculará `10 * 7 = 70`.

*   **Error 3 Corrección (Salida `print` dividida e incompleta en la primera parte):**
    *   El código original dividía la salida en dos `print`:
        ```python
        print("El área de un rectángulo con base", base_rectangulo)
        print("y altura", altura_rectangulo, "es:", area_rectangulo)
        ```
    *   Esto produce dos líneas de salida. El ejemplo de salida pide una sola línea. Además, la primera línea de `print` solo menciona la base, no toda la información contextual.
    *   **Solución:** Combinar todo en una sola sentencia `print` para que coincida con el formato del ejemplo y sea más legible.
        ```python
        print("El área de un rectángulo con base", base_rectangulo, "y altura", altura_rectangulo, "es:", area_rectangulo)
        ```

El programa corregido asegura que los operandos sean numéricos para el cálculo del área y presenta el resultado en una única línea descriptiva.
</details>
