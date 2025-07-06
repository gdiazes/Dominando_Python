# Módulo 6: Ejercicio 8 (Dificultad 9.24/10) - Menú Interactivo Simple con `while` (Sumadora/Restadora)

## Enunciado del Problema

Crea un programa que funcione como una calculadora simple con un menú interactivo.
El programa debe:
1.  Mostrar un menú:
    *   1. Sumar dos números
    *   2. Restar dos números
    *   3. Salir
2.  Utilizar un bucle `while` para que el menú se muestre repetidamente hasta que el usuario elija "Salir".
3.  Si el usuario elige Sumar o Restar:
    *   Solicitar dos números (enteros o flotantes).
    *   Realizar la operación.
    *   Mostrar el resultado.
4.  Si el usuario elige Salir, mostrar un mensaje de despedida y terminar el bucle.
5.  Si la opción no es válida, mostrar un mensaje de error y volver a mostrar el menú.

## Código con Errores

```python
# Ejercicio: Menú interactivo con while

continuar_en_menu = True
while continuar_en_menu True: # Pista 1

    print("\nCalculadora Simple:")
    print("1. Sumar dos números")
    print("2. Restar dos números")
    print("3. Salir")
    opcion_str = input("Elige una opción: ")

    if opcion_str == "1":
        num1 = float(input("Primer número: "))
        num2 = float(input("Segundo número: "))
        print(f"Resultado: {num1 + num2}")
    elif opcion_str == "2":
        num1 = float(input("Primer número: "))
        num2 = float(input("Segundo número: "))
        print(f"Resultado: {num1 - num2}")
    elif opcion_str is "3": # Pista 2
        print("¡Hasta luego!")
        continuar_en_menu = False
    else
        print("Opción no válida. Intenta de nuevo.") # Pista 3
```
