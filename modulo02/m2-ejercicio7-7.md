# Módulo 2: Ejercicio 7 (Dificultad 7/10) - Cálculo de Promedio Simple

## Enunciado del Problema

Declara tres variables, `nota1`, `nota2` y `nota3`, y asígnales tres calificaciones numéricas (pueden ser flotantes, ej: 7.5, 8.0, 9.5).
Calcula el promedio de estas tres notas y almacénalo en una variable `promedio_final`.
Imprime el promedio final de forma descriptiva.
La fórmula del promedio es: (nota1 + nota2 + nota3) / 3

## Código con Errores

```python
# Ejercicio: Calcular el promedio de tres notas

nota1 = 8.0
nota2 = "7.5" # Pista 1
nota3 = 9

promedio_final = nota1 + nota2 + nota3 / 3 # Pista 2
print("El promedio final es: " promedio_final) # Pista 3
```

## Pistas para Corregir los Errores

*   **Pista 1:** Si `nota2` se va a usar en cálculos numéricos, ¿es correcto que sea una cadena?
*   **Pista 2:** Revisa la precedencia de operadores. ¿La división se realizará antes o después de las sumas según está escrito? ¿Cómo puedes asegurar que primero se sumen todas las notas?
*   **Pista 3:** Al usar `print` con una cadena literal seguida de una variable, ¿qué separador se necesita entre ellas?

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Calcular el promedio de tres notas

nota1 = 8.0
nota2 = 7.5  # Convertir a flotante o entero
nota3 = 9.0  # Puede ser entero o flotante; consistencia es buena

# Usar paréntesis para asegurar el orden correcto de operaciones
promedio_final = (nota1 + nota2 + nota3) / 3

# Coma faltante en print
print("El promedio final es:", promedio_final)
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio se enfoca en la correcta manipulación de tipos para cálculos y la importancia de la precedencia de operadores.

*   **Error 1 Corrección (Tipo incorrecto para `nota2`):**
    *   El código original era `nota2 = "7.5"`.
    *   Esto asigna la cadena `"7.5"`. Para usarla en la suma del promedio, debe ser un número (flotante en este caso).
    *   **Solución:** `nota2 = 7.5` (o `float("7.5")` si la entrada viniera obligatoriamente como texto).

*   **Error 2 Corrección (Precedencia de operadores incorrecta):**
    *   El código original era `promedio_final = nota1 + nota2 + nota3 / 3`.
    *   Debido a la precedencia de operadores, la división (`nota3 / 3`) se realizaría primero. Luego, se sumarían `nota1`, `nota2` y el resultado de esa división. Esto no es el cálculo correcto del promedio.
    *   Para calcular el promedio correctamente, primero se deben sumar todas las notas y luego dividir el resultado por 3. Esto se logra usando paréntesis.
    *   **Solución:** `promedio_final = (nota1 + nota2 + nota3) / 3`

*   **Error 3 Corrección (Coma faltante en `print`):**
    *   El código original era `print("El promedio final es: " promedio_final)`.
    *   Falta una coma `,` entre la cadena literal y la variable `promedio_final` para que `print` los trate como argumentos separados.
    *   **Solución:** `print("El promedio final es:", promedio_final)`

El programa corregido asegura que todas las notas sean numéricas, calcula la suma antes de la división usando paréntesis, y luego imprime el resultado correctamente. Es buena práctica que todas las notas (y por ende el promedio) sean del mismo tipo numérico si es posible (ej. todos flotantes).
</details>
