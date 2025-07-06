# Módulo 10: Ejercicio 8 (Dificultad 11.28/10) - Función que Trabaja con una Lista (Encontrar Máximo sin `max()`)

## Enunciado del Problema

1.  Define una función `encontrar_maximo_en_lista` que acepte una lista de números como parámetro.
2.  La función **no** debe usar la función incorporada `max()`.
3.  Debe manejar el caso de que la lista esté vacía (en cuyo caso debería devolver `None`).
4.  Si la lista no está vacía, debe iterar sobre ella para encontrar y devolver el número más grande.
5.  Prueba la función con una lista de números y con una lista vacía.

## Código con Errores

```python
# Ejercicio: Función para encontrar el máximo en una lista sin usar max()

def encontrar_maximo_en_lista(numeros):
    if not numeros:
        return None

    maximo_actual = 0 # Error 1
    for numero in numeros:
        if numero > maximo_actual:
            maximo_actual = numero
    return

mi_lista1 = [5, 2, 9, 1, 7]
max_valor1 = encontrar_maximo_en_lista(mi_lista1)
print(f"El máximo de {mi_lista1} es: {max_valor1}")

mi_lista2 = [-10, -5, -2, -1]
max_valor2 = encontrar_maximo_en_lista(mi_lista2)
print(f"El máximo de {mi_lista2} es: {max_valor2}")

# Error 2: La función no devuelve el valor encontrado.
# Error 3: El valor inicial de 'maximo_actual' puede dar resultados incorrectos para listas con solo números negativos.
```
