# Módulo 6: Ejercicio 3 (Dificultad 3.47/10) - Validación de Entrada Positiva con `while`

## Enunciado del Problema

Escribe un programa que solicite al usuario ingresar un número entero.
El programa debe continuar solicitando la entrada hasta que el usuario ingrese un número que sea estrictamente positivo (mayor que 0).
Una vez que se ingresa un número positivo, el programa debe imprimir "Número positivo ingresado: [número]" y terminar.

## Código con Errores

```python
# Ejercicio: Validación de entrada positiva con while

numero_valido_ingresado = false # Pista 1
numero = 0

while not numero_valido_ingresado:
    numero_str = input("Ingresa un número entero estrictamente positivo: ")
    if numero_str.isdigit: # Pista 2
        numero = int(numero_str)
        if numero > 0:
            numero_valido_ingresado = True
        else
            print("El número debe ser mayor que 0. Intenta de nuevo.") # Pista 3
    else:
        print("Entrada inválida. Debes ingresar un número entero.")

print(f"Número positivo ingresado: {numero}")
```

## Pistas para Corregir los Errores

*   **Pista 1:** Los valores booleanos en Python son `True` y `False` (con la primera letra en mayúscula).
*   **Pista 2:** El método de cadena `isdigit()` (y otros métodos) debe ser *llamado* con paréntesis para que se ejecute y devuelva un resultado.
*   **Pista 3:** La cláusula `else` que sigue a un `if` (en este caso, el `if numero > 0:`) requiere un carácter específico al final de la línea.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Validación de entrada positiva con while

# El booleano es False (mayúscula)
numero_valido_ingresado = False
numero = 0 # Inicializar 'numero' es bueno, aunque se asigna dentro del bucle

while not numero_valido_ingresado:
    numero_str = input("Ingresa un número entero estrictamente positivo: ")
    # Llamar a .isdigit() con paréntesis
    if numero_str.isdigit():
        numero = int(numero_str)
        if numero > 0:
            numero_valido_ingresado = True # Esto detendrá el bucle while
        else: # else necesita ':'
            print("El número debe ser mayor que 0. Intenta de nuevo.")
    else:
        print("Entrada inválida. Debes ingresar un número entero. Intenta de nuevo.")

print(f"Número positivo ingresado: {numero}")
```
*Alternativa de estructura del bucle (a menudo más concisa):*
```python
# numero_alt = 0
# while True: # Bucle infinito controlado por break
#     numero_str_alt = input("Ingresa un número entero estrictamente positivo: ")
#     if numero_str_alt.isdigit():
#         numero_alt = int(numero_str_alt)
#         if numero_alt > 0:
#             break # Salir del bucle si es positivo
#         else:
#             print("El número debe ser mayor que 0. Intenta de nuevo.")
#     else:
#         print("Entrada inválida. Debes ingresar un número entero. Intenta de nuevo.")
# print(f"Número positivo ingresado: {numero_alt}")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio utiliza un bucle `while` controlado por una variable booleana (un "flag" o bandera) para validar la entrada del usuario.

*   **Error 1 Corrección (Valor booleano incorrecto):**
    *   El código original era `numero_valido_ingresado = false`.
    *   En Python, el valor booleano para falso es `False` (con 'F' mayúscula). `false` (minúscula) causaría un `NameError`.
    *   **Solución:** `numero_valido_ingresado = False`

*   **Error 2 Corrección (Llamada a método sin paréntesis):**
    *   El código original era `if numero_str.isdigit:`.
    *   El método de cadena `isdigit()` debe ser llamado con paréntesis `()` para que se ejecute y devuelva `True` o `False`. Sin los paréntesis, se refiere al método en sí, no a su resultado, y en un contexto `if` se evaluaría como "verdadero" (ya que el objeto método existe), lo cual no es la lógica deseada.
    *   **Solución:** `if numero_str.isdigit():`

*   **Error 3 Corrección (Falta de dos puntos en `else`):**
    *   El código original tenía un `else` sin dos puntos al final: `else print("El número debe ser mayor que 0. Intenta de nuevo.")`.
    *   La cláusula `else` (así como `if` y `elif`) debe terminar con dos puntos (`:`).
    *   **Solución:** `else:` (seguido de la línea `print` indentada).

**Lógica del Bucle en la Solución:**
1.  `numero_valido_ingresado` se establece en `False`.
2.  El bucle `while not numero_valido_ingresado:` comienza (ya que `not False` es `True`).
3.  Se solicita la entrada.
4.  Se verifica si la entrada es un dígito.
    *   Si no es un dígito, se muestra un error y el bucle continúa (porque `numero_valido_ingresado` sigue siendo `False`).
    *   Si es un dígito, se convierte a entero.
        *   Si el número entero es `> 0`, `numero_valido_ingresado` se establece en `True`. En la siguiente iteración del `while`, la condición `not numero_valido_ingresado` (`not True`) será `False`, y el bucle terminará.
        *   Si el número entero no es `> 0`, se muestra un error y el bucle continúa.
5.  Una vez que el bucle termina, se imprime el número positivo ingresado.

La alternativa con `while True:` y `break` es otra forma común de escribir bucles de validación, donde el bucle se rompe explícitamente cuando se cumple la condición de validez.
</details>
