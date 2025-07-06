# Módulo 7: Ejercicio 4 (Dificultad 4.86/10) - Iterar sobre una Lista y Mostrar Elementos

## Enunciado del Problema

1.  Crea una lista llamada `numeros_impares` que contenga los primeros 5 números impares positivos (1, 3, 5, 7, 9).
2.  Utiliza un bucle `for` para iterar sobre la lista.
3.  Dentro del bucle, imprime cada número de la lista precedido por el texto "Número impar: ".

## Código con Errores

```python
# Ejercicio: Iterar sobre una lista y mostrar elementos

numeros_impares = [1, 3, 5, 7, 9]

for numero in numeros_impares # Error 1
    print("Número impar: " + numero) # Error 2
    # Error 3: Considera qué pasaría si la lista estuviera vacía.
    # El bucle simplemente no se ejecutaría, lo cual es correcto,
    # pero el "error" puede ser una mala interpretación de cómo manejar
    # el bucle si se esperara alguna acción incluso con lista vacía (no es el caso aquí).
    # Para hacerlo más tangible:
    if numero == 5
        print("¡Encontramos el cinco!")
