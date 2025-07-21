# Módulo 13: Ejercicio 4 (Dificultad 6.51/10) - Uso del Módulo `math`

## Enunciado del Problema

Escribe un programa que realice las siguientes operaciones usando el módulo `math`:
1.  Solicita al usuario un número.
2.  Calcula e imprime la raíz cuadrada de ese número.
3.  Calcula e imprime el factorial de ese número (solo si es un entero no negativo).
4.  Imprime el valor de la constante pi del módulo `math`.

## Código con Errores

```python
# Ejercicio: Uso del módulo math

import math

num_str = input("Ingresa un número: ")
num = float(num_str)

# Raíz cuadrada
raiz = math.sqrt(num)
print(f"La raíz cuadrada de {num} es: {raiz}")

# Factorial
if num >= 0 and num.is_integer():
    factorial = math.factorial(num) # Error 1
    print(f"El factorial de {int(num)} es: {factorial}")
else:
    print("El factorial solo se calcula para enteros no negativos.")

# Valor de PI
pi_valor = math.pi() # Error 2

print(f"El valor de PI es: {pi_valor}")

# Error 3: Intento de usar una función que no existe
# logaritmo_base_e = math.log_e(num)
