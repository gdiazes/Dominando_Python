# Módulo 2: Ejercicio 5 (Dificultad 5/10) - Operaciones Mixtas

## Enunciado del Problema

Dadas tres variables `a = 10`, `b = 3`, `c = 5.0`:
1.  Calcula `resultado1 = a + b * c`
2.  Calcula `resultado2 = (a + b) * c`
3.  Calcula `resultado3 = a / b`
4.  Calcula `resultado4 = a // b`
5.  Calcula `resultado5 = a % c`

Imprime cada resultado con una descripción.

## Código con Errores

```python
# Ejercicio: Realizar operaciones mixtas

a = 10
b = "3" # Pista 1
c = 5.0

resultado1 = a + b * c
resultado2 = (a + b) * c
resultado3 = a / b
resultado4 = a // b
resultado5 = a % C # Pista 2

print("Resultado 1 (a + b * c):", resultado1)
print("Resultado 2 ((a + b) * c):" resultado2) # Pista 3
print("Resultado 3 (a / b):", resultado3)
print("Resultado 4 (a // b):", resultado4)
print("Resultado 5 (a % c):", resultado5)
```

## Pistas para Corregir los Errores

*   **Pista 1:** Si `b` se va a usar en operaciones aritméticas con `a` y `c`, ¿cuál debería ser su tipo de dato?
*   **Pista 2:** Python es sensible a mayúsculas y minúsculas en los nombres de variables.
*   **Pista 3:** Revisa la sintaxis de la función `print` cuando se usan múltiples argumentos. ¿Falta algún separador?

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Realizar operaciones mixtas

a = 10
b = 3   # Debe ser un número, no una cadena
c = 5.0

# Con 'b' como número, las operaciones serán aritméticas
resultado1 = a + b * c
resultado2 = (a + b) * c
resultado3 = a / b
resultado4 = a // b
resultado5 = a % c # 'c' debe ser minúscula

print("Resultado 1 (a + b * c):", resultado1)
print("Resultado 2 ((a + b) * c):", resultado2) # Coma faltante
print("Resultado 3 (a / b):", resultado3)
print("Resultado 4 (a // b):", resultado4)
print("Resultado 5 (a % c):", resultado5)
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio prueba la comprensión de la precedencia de operadores y la correcta manipulación de tipos de datos.

*   **Error 1 Corrección (Tipo incorrecto para `b`):**
    *   El código original era `b = "3"`.
    *   Esto asigna la cadena `"3"`. Al intentar usar `b` en operaciones como `b * c` o `a + b`, Python generaría un `TypeError` porque no puede multiplicar/sumar una cadena con un número (o un número con una cadena) de esa manera directamente para obtener un resultado numérico.
    *   **Solución:** `b = 3`

*   **Error 2 Corrección (Nombre de variable incorrecto - mayúscula):**
    *   El código original era `resultado5 = a % C`.
    *   La variable definida es `c` (minúscula), no `C` (mayúscula). Python es sensible a mayúsculas, por lo que `C` se consideraría una variable no definida, causando un `NameError`.
    *   **Solución:** `resultado5 = a % c`

*   **Error 3 Corrección (Coma faltante en `print`):**
    *   El código original era `print("Resultado 2 ((a + b) * c):" resultado2)`.
    *   Falta una coma `,` para separar la cadena literal `"Resultado 2 ((a + b) * c):"` del argumento de la variable `resultado2`.
    *   **Solución:** `print("Resultado 2 ((a + b) * c):", resultado2)`

Una vez corregidos estos errores:
*   `resultado1 = 10 + 3 * 5.0 = 10 + 15.0 = 25.0`
*   `resultado2 = (10 + 3) * 5.0 = 13 * 5.0 = 65.0`
*   `resultado3 = 10 / 3 = 3.333...`
*   `resultado4 = 10 // 3 = 3`
*   `resultado5 = 10 % 5.0 = 0.0` (El módulo con un flotante puede dar un resultado flotante).

El programa corregido realiza todas las operaciones correctamente y muestra los resultados.
</details>
