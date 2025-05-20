# Módulo 2: Ejercicio 2 (Dificultad 2/10) - Suma de Dos Números

## Enunciado del Problema

Declara dos variables, `numero1` y `numero2`, y asígnales dos números enteros cualesquiera.
Luego, crea una tercera variable, `suma_total`, que almacene la suma de `numero1` y `numero2`.
Finalmente, imprime el resultado de la suma de una forma descriptiva.

Ejemplo de salida (si numero1=10 y numero2=5):
```
La suma de 10 y 5 es: 15
```

## Código con Errores

```python
# Ejercicio: Sumar dos números

numero1 = "20" # Pista 1
numero2 = 15
suma_total = numero1 + numero2 # Pista 2

print("La suma de", numero1, "y", numero2, "es: " suma_total) # Pista 3
```

## Pistas para Corregir los Errores

*   **Pista 1:** Si quieres realizar operaciones aritméticas con un número, ¿debe estar almacenado como una cadena de texto o como un tipo numérico (entero o flotante)?
*   **Pista 2:** ¿Qué sucede si intentas "sumar" (usando `+`) una cadena de texto con un número? Python tiene reglas específicas para esto.
*   **Pista 3:** Cuando usas `print` con múltiples argumentos, ¿cómo debes separar el último texto literal de la variable que le sigue si ambos son argumentos distintos?

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Sumar dos números

numero1 = 20  # Debe ser un entero, no una cadena
numero2 = 15
suma_total = numero1 + numero2 # Ahora la suma será aritmética

# Se necesita una coma antes de suma_total si es un argumento separado
print("La suma de", numero1, "y", numero2, "es:", suma_total)
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio se centra en la correcta asignación de tipos de datos para operaciones aritméticas y la sintaxis de `print` con múltiples argumentos.

*   **Error 1 Corrección (Tipo incorrecto para `numero1`):**
    *   El código original era `numero1 = "20"`.
    *   Esto asigna la cadena de texto `"20"` a `numero1`, no el número entero `20`. Para realizar una suma matemática, necesitamos que `numero1` sea un tipo numérico.
    *   **Solución:** `numero1 = 20` (sin comillas).

*   **Error 2 Corrección (Operación inválida entre cadena y entero):**
    *   El código original era `suma_total = numero1 + numero2`.
    *   Si `numero1` es una cadena (como `"20"`) y `numero2` es un entero (como `15`), el operador `+` intentará una concatenación de cadenas, pero fallará porque `numero2` no es una cadena. Esto resultaría en un `TypeError`.
    *   Al corregir el Error 1 (haciendo `numero1` un entero), esta línea ahora realizará una suma aritmética correctamente.
    *   **Solución (implícita al corregir Error 1):** `suma_total` ahora calculará `20 + 15 = 35`.

*   **Error 3 Corrección (Coma faltante en `print`):**
    *   El código original era `print("La suma de", numero1, "y", numero2, "es: " suma_total)`.
    *   La función `print` puede tomar múltiples argumentos separados por comas. Entre la cadena literal `"es: "` y la variable `suma_total` falta una coma. Python interpreta `"es: " suma_total` como un intento de concatenar dos cadenas literales (si `suma_total` fuera una cadena) o como un error de sintaxis.
    *   **Solución:** `print("La suma de", numero1, "y", numero2, "es:", suma_total)`

El programa corregido primero asegura que ambas variables numéricas sean del tipo correcto (entero) para que la operación de suma funcione como se espera. Luego, utiliza `print` con múltiples argumentos separados por comas para mostrar el resultado de forma clara.
</details>
