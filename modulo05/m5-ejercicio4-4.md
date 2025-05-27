# Módulo 5: Ejercicio 4 (Dificultad 4.4/10) - Tabla de Multiplicar Específica Inversa

## Enunciado del Problema

Solicita al usuario un número entero.
Luego, muestra la tabla de multiplicar de ese número, pero en orden inverso, desde `numero x 10` hasta `numero x 1`.

Ejemplo de salida (si el usuario ingresa 7):
```
Tabla del 7 (inversa):
7 x 10 = 70
7 x 9 = 63
...
7 x 1 = 7
```

## Código con Errores

```python
# Ejercicio: Tabla de multiplicar inversa

numero_tabla_str = input("Ingresa un número para su tabla de multiplicar inversa: ")
numero_tabla = int(numero_tabla_str)

print(f"Tabla del {numero_tabla} (inversa):")
for i in range(10, 1, -1): # Pista 1
    resultado = numero_tabla * i
    print(f"{numero_tabla} x {i} = {Resultado}") # Pista 2
# Pista 3: ¿El bucle se detiene en el valor correcto para incluir la multiplicación por 1?
```

## Pistas para Corregir los Errores

*   **Pista 1:** La función `range(inicio, fin, paso)` genera números hasta `fin` (excluyéndolo). Si quieres que la secuencia llegue hasta 1 (inclusive) cuando vas en reversa, ¿cuál debería ser el valor de `fin`?
*   **Pista 2:** Python es sensible a mayúsculas y minúsculas en los nombres de variables. Verifica cómo se llama la variable que almacena el resultado de la multiplicación.
*   **Pista 3:** Relacionado con la Pista 1. Si `range(10, 1, -1)` se usa, el último valor de `i` será 2 (porque `1` es el límite de parada y no se incluye). ¿Cómo ajustar el `range` para que `i` llegue a ser `1`?

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Tabla de multiplicar inversa

numero_tabla_str = input("Ingresa un número para su tabla de multiplicar inversa: ")
numero_tabla = int(numero_tabla_str)

print(f"Tabla del {numero_tabla} (inversa):")
# Para que el rango incluya el 1, el segundo argumento (parada) debe ser 0
for i in range(10, 0, -1):
    resultado = numero_tabla * i
    # Usar el nombre correcto de la variable 'resultado'
    print(f"{numero_tabla} x {i} = {resultado}")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio se enfoca en usar `range()` con un paso negativo para iterar en orden inverso.

*   **Error 1 y 3 Corrección (Lógica de `range()` para secuencia inversa):**
    *   El código original era `for i in range(10, 1, -1):`.
    *   La función `range(inicio, fin, paso)` genera una secuencia hasta `fin`, pero no incluye `fin`. Cuando el `paso` es negativo, se cuenta hacia atrás.
    *   Con `range(10, 1, -1)`, la secuencia generada para `i` sería `10, 9, 8, 7, 6, 5, 4, 3, 2`. El valor `1` (que es `fin`) no se incluye.
    *   Para que la secuencia incluya el `1`, el valor de `fin` debe ser `0` cuando el paso es `-1`.
    *   **Solución:** `for i in range(10, 0, -1):`

*   **Error 2 Corrección (Nombre de variable incorrecto en f-string):**
    *   El código original era `print(f"{numero_tabla} x {i} = {Resultado}")`.
    *   La variable que almacena el resultado de la multiplicación se definió como `resultado` (todo en minúsculas). Usar `Resultado` (con mayúscula inicial) causaría un `NameError`.
    *   **Solución:** `print(f"{numero_tabla} x {i} = {resultado}")`

El programa corregido utiliza `range(10, 0, -1)` para generar la secuencia `10, 9, ..., 1`, permitiendo que el bucle `for` muestre la tabla de multiplicar en el orden inverso solicitado, desde `numero x 10` hasta `numero x 1`.
</details>
