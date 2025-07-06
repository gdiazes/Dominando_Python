# Módulo 4: Ejercicio 10 (Dificultad 10.5/10) - Cajero Automático Básico (Menú y Operaciones)

## Enunciado del Problema

Simula un cajero automático muy básico. El programa debe:
1.  Mostrar un saldo inicial (ej: $1000).
2.  Presentar un menú al usuario:
    *   1. Consultar Saldo
    *   2. Depositar Dinero
    *   3. Retirar Dinero
    *   4. Salir
3.  Solicitar al usuario que elija una opción (1-4).
4.  Según la opción:
    *   Si es 1: Mostrar el saldo actual.
    *   Si es 2: Solicitar un monto a depositar, sumarlo al saldo y mostrar el nuevo saldo.
    *   Si es 3: Solicitar un monto a retirar. Si el monto es menor o igual al saldo, restarlo y mostrar el nuevo saldo. Si no, mostrar "Fondos insuficientes".
    *   Si es 4: Mostrar "Gracias por usar el cajero. ¡Hasta pronto!" y terminar.
    *   Si es cualquier otra opción: Mostrar "Opción no válida."

(Este ejercicio sirve como parte de la Práctica Calificada 1)

## Código con Errores

```python
# Ejercicio: Cajero Automático Básico

saldo = 1000.00
continuar_operaciones = True

print("Bienvenido al Cajero Automático")

# Bucle principal (se introduce un bucle simple para que el menú se repita hasta salir)
# Aunque los bucles se ven en Módulos 6 y 7, un while simple es manejable aquí.
# Si no se quiere bucle, se puede ejecutar una sola vez. Para este ejercicio, omitiremos el bucle
# y haremos una sola transacción para enfocarnos en if/elif/else.

print(f"Saldo actual: ${saldo:.2f}") # Se muestra saldo inicial, no es un error
print("\nMenú de Opciones:")
print("1. Consultar Saldo")
print("2. Depositar Dinero")
print("3. Retirar Dinero")
print("4. Salir")

opcion_str = input("Seleccione una opción (1-4): ")
opcion = int(opcion_str)

if opcion == 1:
    print(f"Su saldo actual es: ${saldo:.2f}")
elif opcion = 2: # Pista 1
    monto_deposito_str = input("Ingrese el monto a depositar: $")
    monto_deposito = float(monto_deposito_str)
    saldo = saldo + monto_deposito # Esto podría ser saldo += monto_deposito
    print(f"Depósito exitoso. Nuevo saldo: ${saldo:.2f}")
elif opcion == 3:
    monto_retiro_str = input("Ingrese el monto a retirar: $")
    monto_retiro = float(monto_retiro_str)
    if monto_retiro <= saldo # Pista 2
        saldo -= monto_retiro # Equivalente a saldo = saldo - monto_retiro
        print(f"Retiro exitoso. Nuevo saldo: ${saldo:.2f}")
    else:
        print("Fondos insuficientes.")
elif opcion == "4": # Pista 3
    print("Gracias por usar el cajero. ¡Hasta pronto!")
else:
    print("Opción no válida.")

```

## Pistas para Corregir los Errores

*   **Pista 1:** Para comparar si la `opcion` es igual a 2, ¿cuál es el operador de comparación correcto? `=` se usa para asignación.
*   **Pista 2:** La línea de condición `if` para verificar si el monto de retiro es menor o igual al saldo necesita los dos puntos (`:`) al final.
*   **Pista 3:** La variable `opcion` fue convertida a un entero (`int`). ¿Es correcto compararla con la cadena de texto `"4"`?

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Cajero Automático Básico

saldo = 1000.00

print("Bienvenido al Cajero Automático")

print(f"Saldo inicial: ${saldo:.2f}") # Mostrar saldo inicial
print("\nMenú de Opciones:")
print("1. Consultar Saldo")
print("2. Depositar Dinero")
print("3. Retirar Dinero")
print("4. Salir")

opcion_str = input("Seleccione una opción (1-4): ")

# Es buena idea validar la entrada de opción aquí,
# por ejemplo, con un try-except para la conversión a int,
# pero se omite para mantener el foco en if/elif/else según el módulo.
# Si el usuario ingresa texto no numérico, int(opcion_str) fallará.

if not opcion_str.isdigit(): # Simple validación de que sea un dígito
    print("Opción no válida. Por favor, ingrese un número.")
else:
    opcion = int(opcion_str)

    if opcion == 1:
        print(f"Su saldo actual es: ${saldo:.2f}")
    elif opcion == 2: # Usar '==' para comparación
        monto_deposito_str = input("Ingrese el monto a depositar: $")
        # Se podría añadir validación para que monto_deposito_str sea numérico
        monto_deposito = float(monto_deposito_str)
        if monto_deposito > 0:
            saldo += monto_deposito # saldo = saldo + monto_deposito
            print(f"Depósito exitoso. Nuevo saldo: ${saldo:.2f}")
        else:
            print("El monto a depositar debe ser positivo.")
    elif opcion == 3:
        monto_retiro_str = input("Ingrese el monto a retirar: $")
        # Se podría añadir validación para que monto_retiro_str sea numérico
        monto_retiro = float(monto_retiro_str)
        if monto_retiro > saldo: # Condición de fondos insuficientes
            print("Fondos insuficientes.")
        elif monto_retiro <= 0:
            print("El monto a retirar debe ser positivo.")
        else: # Si hay fondos suficientes y el monto es positivo
            saldo -= monto_retiro # saldo = saldo - monto_retiro; Falta ':' en el if anidado original
            print(f"Retiro exitoso. Nuevo saldo: ${saldo:.2f}")
    elif opcion == 4: # Comparar con el entero 4
        print("Gracias por usar el cajero. ¡Hasta pronto!")
    else:
        print("Opción no válida. Por favor, elija entre 1 y 4.")

```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio simula un cajero automático, requiriendo una estructura `if-elif-else` anidada para manejar las diferentes opciones y validaciones.

*   **Error 1 Corrección (Uso de asignación en lugar de comparación):**
    *   El código original era `elif opcion = 2:`.
    *   Para comparar si `opcion` es igual a `2`, se debe usar el operador de comparación `==`. El operador `=` es para asignación.
    *   **Solución:** `elif opcion == 2:`

*   **Error 2 Corrección (Falta de dos puntos en `if` anidado):**
    *   El código original dentro de la opción 3 era `if monto_retiro <= saldo`.
    *   Esta línea de condición `if` necesita dos puntos (`:`) al final para indicar el inicio de su bloque.
    *   **Solución:** `if monto_retiro <= saldo:` (Dentro de la lógica corregida, esta condición se invierte o se maneja de forma diferente para dar mensajes más claros, pero el error sintáctico es la falta de `:`).
    *   En la solución propuesta, la lógica de retiro se reestructura para verificar primero fondos insuficientes y montos no positivos. Si el `if` original se mantuviera, necesitaría los dos puntos.

*   **Error 3 Corrección (Comparación de entero con cadena):**
    *   El código original era `elif opcion == "4":`.
    *   La variable `opcion` se obtiene al convertir `opcion_str` a un entero: `opcion = int(opcion_str)`. Por lo tanto, `opcion` almacena un valor numérico entero. Compararla con la cadena de texto `"4"` siempre resultará en `False`.
    *   **Solución:** `elif opcion == 4:` (comparar con el número entero 4).

**Mejoras Adicionales en la Solución Propuesta:**
*   **Validación de entrada para `opcion`:** Se añade una verificación simple `if not opcion_str.isdigit():` para manejar casos donde el usuario no ingrese un número para la opción. Una solución más robusta usaría `try-except`.
*   **Validación de montos:** Para depósito y retiro, se añade una verificación para asegurar que los montos sean positivos.
*   **Lógica de retiro mejorada:** En la opción 3, se verifica primero si hay fondos insuficientes o si el monto es no positivo, antes de proceder con el retiro. Esto hace los mensajes más claros.

El programa corregido maneja las diferentes opciones del cajero, realiza las conversiones de tipo necesarias, aplica las validaciones y utiliza la estructura `if-elif-else` (incluyendo anidamiento) de forma correcta.
</details>
