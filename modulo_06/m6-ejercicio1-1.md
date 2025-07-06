# Módulo 6: Ejercicio 1 (Dificultad 1.16/10) - Contador Ascendente con `while`

## Enunciado del Problema

Escribe un programa que utilice un bucle `while` para imprimir los números del 1 al 5, cada uno en una nueva línea.
Asegúrate de inicializar correctamente tu contador, establecer la condición del bucle y actualizar el contador en cada iteración.

## Código con Errores

```python
# Ejercicio: Contador ascendente con while

contador = 0 # Pista 1

while contador < 5:
    contador + 1 # Pista 2
    print(f"Número: {contador}")
# Pista 3: ¿El bucle se detendrá alguna vez si 'contador' no se actualiza correctamente para afectar la condición?
```

## Pistas para Corregir los Errores

*   **Pista 1:** Si quieres imprimir números del 1 al 5, ¿cuál debería ser el valor inicial de `contador` si la primera acción dentro del bucle es actualizarlo *antes* de imprimir, o si lo actualizas *después* de imprimir? Considera el orden de las operaciones.
*   **Pista 2:** La expresión `contador + 1` calcula un nuevo valor, pero no lo *asigna* de nuevo a la variable `contador`. ¿Cómo se actualiza el valor de una variable?
*   **Pista 3:** Si la variable `contador` no se modifica de una manera que eventualmente haga que la condición `contador < 5` (o la condición correcta) sea falsa, el bucle se ejecutará infinitamente.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Contador ascendente con while

# Opción 1: Inicializar en 1, imprimir, luego incrementar
contador = 1
while contador <= 5: # Condición para incluir el 5
    print(f"Número: {contador}")
    contador += 1 # Actualizar el contador (contador = contador + 1)

# Opción 2: Inicializar en 0, incrementar, luego imprimir (como en el código con errores, pero corregido)
# contador_op2 = 0
# while contador_op2 < 5: # Condición para 5 iteraciones (0, 1, 2, 3, 4 para el índice)
#     contador_op2 += 1 # Primero actualizar
#     print(f"Número: {contador_op2}") # Luego imprimir (1, 2, 3, 4, 5)
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio es una introducción básica al bucle `while`, enfocándose en los tres componentes clave: inicialización, condición y actualización.

*   **Error 1 Corrección (Valor inicial de `contador` y orden de operaciones):**
    *   El código con errores tenía `contador = 0` y luego `contador + 1` (que no actualizaba) y `print(f"Número: {contador}")`. Si la intención era imprimir 1, 2, 3, 4, 5:
        *   Si `contador` empieza en 0 y se incrementa *antes* de imprimir, la condición del `while` debería ser `contador < 5` (para 5 iteraciones donde el `contador` interno llega hasta 5).
        *   Si `contador` empieza en 1 y se incrementa *después* de imprimir, la condición del `while` debería ser `contador <= 5`.
    *   La "Solución Correcta - Opción 1" (preferida por claridad para este problema) inicializa `contador = 1`.

*   **Error 2 Corrección (Actualización incorrecta de `contador`):**
    *   El código original era `contador + 1`.
    *   Esta línea calcula `contador + 1` pero no guarda el resultado de nuevo en `contador`. La variable `contador` nunca cambia su valor dentro del bucle.
    *   **Solución:** `contador = contador + 1` o, de forma abreviada y más común, `contador += 1`.

*   **Error 3 Corrección (Prevención de bucle infinito):**
    *   Este error es una consecuencia directa del Error 2. Si `contador` nunca se actualiza para que `contador < 5` se vuelva falso, el bucle sería infinito. Al corregir la actualización (Error 2), este problema se resuelve.
    *   La condición del `while` también es importante. Si `contador` se inicializa en `1` y queremos imprimir hasta `5`, la condición debe ser `contador <= 5`. Si se usa `contador < 5`, solo se imprimiría hasta 4.

**Solución Detallada (Opción 1):**
1.  `contador = 1`: Inicializa el contador en 1.
2.  `while contador <= 5:`: La condición se verifica.
    *   1ra iteración: `1 <= 5` es True. Se imprime "Número: 1". `contador` se vuelve 2.
    *   2da iteración: `2 <= 5` es True. Se imprime "Número: 2". `contador` se vuelve 3.
    *   ...
    *   5ta iteración: `5 <= 5` es True. Se imprime "Número: 5". `contador` se vuelve 6.
    *   6ta iteración: `6 <= 5` es False. El bucle termina.

**Solución Detallada (Opción 2, basada en la estructura del error):**
1.  `contador_op2 = 0`: Inicializa el contador en 0.
2.  `while contador_op2 < 5:`: La condición se verifica (para 5 iteraciones: `contador_op2` será 0, 1, 2, 3, 4).
    *   1ra iteración: `0 < 5` es True. `contador_op2` se vuelve 1. Se imprime "Número: 1".
    *   2da iteración: `1 < 5` es True. `contador_op2` se vuelve 2. Se imprime "Número: 2".
    *   ...
    *   5ta iteración: `4 < 5` es True. `contador_op2` se vuelve 5. Se imprime "Número: 5".
    *   Siguiente: `contador_op2` es 5. `5 < 5` es False. El bucle termina.

Ambas opciones en la solución logran el resultado deseado. La Opción 1 es a menudo más intuitiva cuando se piensa en "contar del 1 al 5".
</details>
