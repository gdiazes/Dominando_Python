# Módulo 11: Ejercicio 6 (Dificultad 8.88/10) - Uso de `map` con Lambda para Duplicar Números

## Enunciado del Problema

1.  Se te da una lista de números `[1, 2, 3, 4, 5]`.
2.  Usa la función `map()` y una función `lambda` para crear una nueva lista donde cada número de la lista original esté duplicado (multiplicado por 2).
3.  Imprime la nueva lista.

## Código con Errores

```python
# Ejercicio: Uso de map con lambda para duplicar números

numeros = [1, 2, 3, 4, 5]

# Usar map y lambda
mapa_duplicados = map(lambda x: x*2, numeros) # Esto devuelve un objeto map, no una lista
numeros_duplicados = mapa_duplicados # Error 1

print("Lista original:", numeros)
print("Lista duplicada:", numeros_duplicados)

# Error 2: Intento incorrecto de usar map
# numeros_duplicados_alt = map(numeros, lambda x: x*2)

# Error 3: El objeto map solo se puede recorrer una vez.
# print(list(mapa_duplicados)) # Esto consumiría el objeto
# print(list(mapa_duplicados)) # Esto imprimiría una lista vacía
```
