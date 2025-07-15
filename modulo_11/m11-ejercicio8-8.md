# Módulo 11: Ejercicio 8 (Dificultad 11.84/10) - Uso de `sorted` con Lambda para Ordenar un Diccionario

## Enunciado del Problema (Práctica Calificada 3 - Parte A)

1.  Se te da un diccionario `productos` donde las claves son nombres de productos y los valores son sus precios.
2.  Usa la función `sorted()` junto con una función `lambda` para obtener una lista de los *ítems* del diccionario (pares clave-valor) ordenados por precio, de menor a mayor.
3.  Imprime la lista ordenada resultante.

## Código con Errores

```python
# Ejercicio: Uso de sorted con lambda para ordenar un diccionario

productos = {"laptop": 1200, "ratón": 25, "teclado": 75, "monitor": 300}

# Ordenar por precio (valor)
items_productos = productos.items()
productos_ordenados = sorted(items_productos, key=lambda item: item) # Error 1

print("Productos ordenados por precio:")
print(productos_ordenados)

# Error 2: Intento de ordenar el diccionario directamente
# productos_ordenados_alt = sorted(productos, key=lambda k: productos[k])
# Esto solo ordena las claves, no los ítems.

# Error 3: Sintaxis de lambda incorrecta
# productos_ordenados_alt2 = sorted(items_productos, key=item -> item[1])
```
