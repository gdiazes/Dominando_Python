# Módulo 5: Ejercicio 1 (Dificultad 1.1/10) - Imprimir Números del 1 al 10

## Enunciado del Problema

Escribe un programa en Python que utilice un bucle `for` y la función `range()` para imprimir los números del 1 al 10, cada uno en una nueva línea.

## Código con Errores

```python
# Ejercicio: Imprimir números del 1 al 10

print("Números del 1 al 10:")
for numero in range(10): # Pista 1
    print(numero) # Pista 2
# Pista 3: ¿El bucle está correctamente estructurado para imprimir 10 números? ¿La indentación es correcta en todo el bloque?
```

## Pistas para Corregir los Errores

*   **Pista 1:** La función `range(N)` genera números desde 0 hasta `N-1`. Si quieres que la secuencia comience en 1 y termine en 10, ¿cómo deberías ajustar los argumentos de `range()`?
*   **Pista 2:** El `print(numero)` dentro del bucle actual imprimirá los números generados por `range(10)`. ¿Necesita algún ajuste para imprimir del 1 al 10 si modificas el `range` o si lo dejas como está?
*   **Pista 3:** No hay un error de sintaxis directo en la indentación en el código proporcionado. Esta pista es más para hacer reflexionar sobre la estructura general y el comportamiento del bucle. Si la Pista 1 se aborda correctamente, la Pista 2 se vuelve más relevante. Un "error" podría ser que la intención no se cumple.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Imprimir números del 1 al 10

print("Números del 1 al 10:")
# range(inicio, fin_mas_uno)
# Para incluir el 10, el segundo argumento de range debe ser 11.
for numero in range(1, 11):
    print(numero)
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio introduce el uso básico de `for` con `range()`.

*   **Error 1 Corrección (Lógica de `range()`):**
    *   El código original era `for numero in range(10):`.
    *   `range(10)` genera la secuencia de números `0, 1, 2, 3, 4, 5, 6, 7, 8, 9`. El enunciado pide imprimir del 1 al 10.
    *   Para generar números desde un `inicio` hasta un `fin` (incluido), se usa `range(inicio, fin + 1)`.
    *   **Solución:** `for numero in range(1, 11):`

*   **Error 2 Corrección (Ajuste de `print` basado en `range`):**
    *   Con el `range(10)` original, `print(numero)` imprimiría de 0 a 9. Si quisiéramos mantener `range(10)` y aun así imprimir de 1 a 10, tendríamos que hacer `print(numero + 1)`.
    *   Sin embargo, la solución más directa y clara es ajustar el `range` como se hizo en el Error 1. Con `range(1, 11)`, `print(numero)` imprimirá directamente los valores 1, 2, ..., 10.
    *   **Solución (consistente con la corrección del Error 1):** `print(numero)` (esta línea ya era correcta si `range` se ajusta).

*   **Error 3 Corrección (Reflexión sobre estructura):**
    *   No había un error de sintaxis de indentación. La pista apuntaba a asegurar que el bucle cumpliera el objetivo. Al corregir `range(10)` a `range(1, 11)`, el bucle `for numero in range(1, 11): print(numero)` cumple correctamente el requisito de imprimir los números del 1 al 10.

El programa corregido utiliza `range(1, 11)` para generar la secuencia de números del 1 al 10 (inclusive), y el bucle `for` itera sobre esta secuencia, imprimiendo cada número.
</details>
