# Módulo 7: Ejercicio 6 (Dificultad 7.29/10) - Encontrar el Elemento Mayor y Menor en una Lista

## Enunciado del Problema

1.  Crea una lista de al menos 5 números (enteros o flotantes) llamada `datos_medidos`.
2.  Encuentra el valor máximo y el valor mínimo en la lista. Puedes hacerlo iterando y comparando, o usando funciones incorporadas.
3.  Imprime el valor máximo y el mínimo.

## Código con Errores

```python
# Ejercicio: Encontrar el elemento mayor y menor en una lista

datos_medidos = [12.5, 8.0, 15.3, 7.1, 11.0, 9.5]

if not datos_medidos:
    print("La lista está vacía.")
else:
    mayor = datos_medidos[0] # Asumir el primero como mayor/menor inicial
    menor = datos_medidos[0]

    for dato in datos_medidos:
        if dato > mayor
            mayor = datos # Error 1 (nombre de variable incorrecto)
        elif dato < menor:
            menor = dato

    print(f"Valor máximo: {maximo}") # Error 2
    print(f"Valor mínimo: {min(datos_medidos, menor)}") # Error 3 (uso incorrecto de min o lógica)
