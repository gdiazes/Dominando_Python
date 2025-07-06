# Módulo 5: Ejercicio 2 (Dificultad 2.2/10) - Sumar los Primeros N Números Naturales

## Enunciado del Problema

Solicita al usuario un número entero positivo `N`.
Luego, utiliza un bucle `for` para calcular la suma de todos los números naturales desde 1 hasta `N` (inclusive).
Muestra la suma total.
Por ejemplo, si N=5, la suma es 1 + 2 + 3 + 4 + 5 = 15.

## Código con Errores

```python
# Ejercicio: Sumar los primeros N números naturales

n_str = input("Ingresa un número entero positivo N: ")
n = int(n_str)

suma_total = 0 # Inicializar acumulador

for i in range(n): # Pista 1
    suma_total = i # Pista 2

print(f"La suma de los primeros {n} números naturales es: {Suma_Total}") # Pista 3
```

## Pistas para Corregir los Errores

*   **Pista 1:** Si quieres sumar los números desde 1 hasta `N` (inclusive), ¿el `range(n)` actual genera la secuencia correcta de números a sumar, o necesita un ajuste en sus argumentos? Recuerda que `range(n)` va de `0` a `n-1`.
*   **Pista 2:** Un acumulador debe *sumar* cada nuevo valor a su total actual. La asignación directa `suma_total = i` reemplazará el valor del acumulador en cada iteración.
*   **Pista 3:** Python es sensible a mayúsculas y minúsculas en los nombres de las variables. Verifica el nombre de la variable que almacena la suma.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Sumar los primeros N números naturales

n_str = input("Ingresa un número entero positivo N: ")
n = int(n_str)

suma_total = 0 # Inicializar acumulador

# range debe ir de 1 hasta n+1 para incluir n
if n > 0: # Asegurarse de que N sea positivo para que el rango tenga sentido
    for i in range(1, n + 1):
        suma_total += i # Acumular la suma: suma_total = suma_total + i
else:
    print("N debe ser un número positivo para calcular la suma de esta manera.")
    # Opcionalmente, la suma de 0 números es 0, lo cual ya está en suma_total.

# Usar el nombre correcto de la variable 'suma_total'
print(f"La suma de los primeros {n} números naturales es: {suma_total}")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio introduce el concepto de un acumulador dentro de un bucle `for`.

*   **Error 1 Corrección (Lógica de `range()` incorrecta para el problema):**
    *   El código original era `for i in range(n):`.
    *   `range(n)` genera números desde `0` hasta `n-1`. El problema pide sumar desde `1` hasta `N` (inclusive).
    *   Para generar la secuencia `1, 2, ..., N`, se debe usar `range(1, n + 1)`.
    *   **Solución:** `for i in range(1, n + 1):`

*   **Error 2 Corrección (Acumulador no acumula):**
    *   El código original era `suma_total = i`.
    *   Esto no acumula la suma. En cada iteración, `suma_total` se sobrescribe con el valor actual de `i`. Al final, `suma_total` contendría el último valor de `i` (que sería `n-1` con el `range` original, o `n` con el `range` corregido).
    *   Para acumular, se debe sumar el valor actual de `i` al valor existente de `suma_total`.
    *   **Solución:** `suma_total += i` (que es una forma abreviada de `suma_total = suma_total + i`).

*   **Error 3 Corrección (Nombre de variable incorrecto en f-string):**
    *   El código original era `print(f"La suma de los primeros {n} números naturales es: {Suma_Total}")`.
    *   La variable que almacena la suma se definió como `suma_total` (minúsculas). Usar `Suma_Total` (con mayúsculas) causaría un `NameError`.
    *   **Solución:** `print(f"La suma de los primeros {n} números naturales es: {suma_total}")`

Adicionalmente, la solución corregida incluye una verificación simple `if n > 0:` antes del bucle, ya que sumar números hasta un `N` negativo o cero con `range(1, n+1)` no tendría el comportamiento esperado o podría generar un rango vacío. Si `n` es 0 o negativo, la suma es 0, que es el valor inicial de `suma_total`.

El programa corregido utiliza `range(1, n + 1)` para iterar sobre los números correctos y `suma_total += i` para acumular la suma correctamente.
</details>
