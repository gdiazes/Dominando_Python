# Módulo 7: Ejercicio 9 (Dificultad 10.94/10) - Filtrar Números Pares de una Lista y Calcular su Suma

## Enunciado del Problema.

1.  Crea una lista de números enteros llamada `numeros_mixtos` que contenga tanto números pares como impares.
2.  Crea una nueva lista llamada `solo_pares` que contenga únicamente los números pares de la lista `numeros_mixtos`.
3.  Calcula la suma de los elementos en la lista `solo_pares`.
4.  Imprime la lista `solo_pares` y la suma calculada.

## Código con Errores

```python
# Ejercicio: Filtrar números pares y calcular su suma

numeros_mixtos = [3, 8, 1, 12, 5, 22, 17, 6, 10, 9]
solo_pares = []
suma_pares = 0

for numero in numeros_mixtos:
    if numero % 2 = 0: # Error 1
        solo_pares.add(numero) # Error 2
        suma_pares = numero # Error 3

print(f"Números pares encontrados: {solo_pares}")
print(f"Suma de los números pares: {suma_pares}")
