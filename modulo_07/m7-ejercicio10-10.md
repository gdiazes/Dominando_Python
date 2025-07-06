# Módulo 7: Ejercicio 10 (Dificultad 12.15/10) - Operaciones con una Lista de Listas (Matriz Simple)

## Enunciado del Problema

Se te da una "matriz" (lista de listas) que representa una tabla de datos:
`matriz_datos = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]`
1.  Imprime la matriz completa.
2.  Accede e imprime el elemento en la segunda fila, tercera columna (debería ser 6).
3.  Modifica el elemento en la primera fila, primera columna para que sea 10. Imprime la matriz modificada.
4.  Calcula e imprime la suma de todos los elementos de la segunda fila.
5.  Calcula e imprime la suma de todos los elementos de la primera columna.

## Código con Errores

```python
# Ejercicio: Operaciones con una lista de listas (matriz simple)

matriz_datos = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

print("Matriz original:")
for fila in matriz_datos:
    print(fila)

# Acceder al elemento (segunda fila, tercera columna)
elemento = matriz_datos[2][3] # Error 1
print(f"\nElemento en la segunda fila, tercera columna: {elemento}")

# Modificar elemento (primera fila, primera columna a 10)
matriz_datos[0,0] = 10 # Error 2
print("\nMatriz modificada:")
for fila in matriz_datos:
    print(fila)

# Suma de la segunda fila
suma_fila2 = 0
for elemento_fila in matriz_datos[1]: # Correcto
    suma_fila2 += elemento_fila
print(f"\nSuma de la segunda fila: {suma_fila2}")

# Suma de la primera columna
suma_columna1 = 0
for fila_idx in range(len(matriz_datos)):
    suma_columna1 = matriz_datos[0][fila_idx] # Error 3
print(f"Suma de la primera columna: {suma_columna1}")
