# Módulo 3: Ejercicio 2 (Dificultad 2.2/10) - Suma de Dos Números Ingresados por Usuario

## Enunciado del Problema

Escribe un programa que solicite al usuario ingresar dos números enteros.
Luego, el programa debe calcular la suma de estos dos números y mostrar el resultado en un formato claro, indicando los números originales y su suma.

Ejemplo de salida (si el usuario ingresa 15 y 20):
```
La suma de 15 y 20 es 35.
```

## Código con Errores

```python
# Ejercicio: Sumar dos números ingresados por el usuario

num1_str = input("Ingrese el primer número: ")
num2_str = input("Ingrese el segundo número: ) # Pista 1

num1_int = num1_str # Pista 2
num2_int = int(num2_str)

suma = num1_int + num2_int
print(f"La suma de {num1_str} y {num2_str} es {Suma}.") # Pista 3
```

## Pistas para Corregir los Errores

*   **Pista 1:** Las cadenas de texto, como los mensajes para `input()`, deben estar correctamente delimitadas por comillas.
*   **Pista 2:** La función `input()` devuelve una cadena. Si necesitas realizar operaciones aritméticas, ¿qué debes hacer con la cadena obtenida para `num1_str` antes de usarla en la suma?
*   **Pista 3:** Python es sensible a mayúsculas y minúsculas para los nombres de variables. Además, asegúrate de que las variables usadas dentro de una f-string estén definidas y escritas correctamente.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Sumar dos números ingresados por el usuario

num1_str = input("Ingrese el primer número: ")
num2_str = input("Ingrese el segundo número: ") # Comilla faltante

# Convertir ambas entradas a enteros
num1_int = int(num1_str)
num2_int = int(num2_str)

suma = num1_int + num2_int

# Usar el nombre correcto de la variable 'suma' en la f-string
print(f"La suma de {num1_int} y {num2_int} es {suma}.")
# También es válido mostrar num1_str y num2_str si se quiere mostrar la entrada original exacta:
# print(f"La suma de {num1_str} y {num2_str} es {suma}.")
# Pero para la lógica de la suma, usamos los enteros.
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio se enfoca en obtener entradas numéricas del usuario, convertirlas al tipo de dato correcto y realizar una operación aritmética.

*   **Error 1 Corrección (Comilla faltante en `input`):**
    *   El código original era `num2_str = input("Ingrese el segundo número: )`.
    *   Al mensaje de `input` le falta la comilla de cierre.
    *   **Solución:** `num2_str = input("Ingrese el segundo número: ")`

*   **Error 2 Corrección (Falta de conversión para `num1_str`):**
    *   El código original era `num1_int = num1_str`.
    *   Esto simplemente asigna la cadena de `num1_str` a `num1_int` sin cambiar su tipo. Si `num1_str` es, por ejemplo, `"15"`, `num1_int` también será `"15"`. Al intentar sumar `num1_int` (cadena) con `num2_int` (entero), se producirá un `TypeError`.
    *   Es necesario convertir `num1_str` a entero usando `int()`.
    *   **Solución:** `num1_int = int(num1_str)`

*   **Error 3 Corrección (Nombre de variable incorrecto en f-string):**
    *   El código original era `print(f"La suma de {num1_str} y {num2_str} es {Suma}.")`.
    *   La variable que almacena el resultado de la suma se llama `suma` (todo en minúsculas). Usar `Suma` (con mayúscula inicial) en la f-string causaría un `NameError` porque la variable `Suma` no está definida.
    *   **Solución:** `print(f"La suma de {num1_int} y {num2_int} es {suma}.")`
        *   Nota: En la f-string, es más coherente mostrar `num1_int` y `num2_int` si la frase se refiere a los números que se sumaron matemáticamente. Aunque mostrar `num1_str` y `num2_str` también es válido si se quiere reflejar la entrada original textual. Para la lógica de la suma, los enteros son los relevantes.

El programa corregido solicita dos números, los convierte a enteros, calcula su suma y luego muestra el resultado usando una f-string formateada correctamente con los nombres de variables correctos.
</details>
