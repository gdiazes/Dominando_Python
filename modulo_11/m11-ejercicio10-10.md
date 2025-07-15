# Módulo 11: Ejercicio 10 (Dificultad 14.8/10) - Calculadora Flexible con Lambda y Diccionario

## Enunciado del Problema (Práctica Calificada 3 - Parte C)

Crea una "calculadora" que almacena operaciones como funciones `lambda` dentro de un diccionario.
1.  Crea un diccionario `operaciones` donde las claves sean los símbolos de operación (`"+"`, `"-"`, `"*"` , `"/"`) y los valores sean funciones `lambda` que realicen la operación correspondiente con dos argumentos `a` y `b`.
2.  Solicita al usuario dos números y un operador.
3.  Busca el operador en el diccionario. Si existe, obtén la función `lambda` correspondiente y llámala con los dos números para obtener el resultado.
4.  Si el operador no existe, muestra un mensaje de error.
5.  Imprime el resultado de la operación.

## Código con Errores

```python
# Ejercicio: Calculadora flexible con lambda y diccionario

operaciones = {
    "+": lambda a, b: a + b,
    "-": (a, b) => a - b, # Error 1
    "*": lambda a, b: a * b,
    "/": lambda a, b: a / b if b != 0 else "Error: división por cero"
}

num1 = float(input("Primer número: "))
num2 = float(input("Segundo número: "))
operador = input("Operador (+, -, *, /): ")

if operador in operaciones:
    funcion_a_ejecutar = operaciones.operador # Error 2
    resultado = funcion_a_ejecutar(num1, num2)
    print(f"Resultado: {resultado}")
else:
    print("Operador no válido.")

# Error 3: Intento de llamar a una lambda que no existe
# division_entera = operaciones["//"](num1, num2)
