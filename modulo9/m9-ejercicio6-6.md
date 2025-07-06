# Módulo 9: Ejercicio 6 (Dificultad 8.07/10) - Verificar si una Clave Existe

## Enunciado del Problema

1.  Crea un diccionario `inventario` que mapee nombres de productos a su cantidad en stock (ej: "manzanas": 50, "bananas": 100, "naranjas": 75).
2.  Solicita al usuario el nombre de un producto.
3.  Verifica si el producto (la clave) existe en el inventario.
4.  Si existe, muestra un mensaje como "Hay [cantidad] unidades de [producto]".
5.  Si no existe, muestra un mensaje como "El producto [producto] no se encuentra en el inventario".

## Código con Errores

```python
# Ejercicio: Verificar si una clave existe

inventario = {
    "manzanas": 50,
    "bananas": 100,
    "naranjas": 75
}

producto_buscado = input("¿Qué producto deseas consultar? ").lower()

# Verificar existencia
if inventario.has_key(producto_buscado): # Error 1
    cantidad = inventario.producto_buscado # Error 2
    print(f"Hay {cantidad} unidades de {producto_buscado}.")
else:
    print(f"El producto '{producto_buscado}' no se encuentra en el inventario.")

# Error 3: Otra forma incorrecta de verificar
# if inventario[producto_buscado] is not None:
#    print("El producto existe.")
# Este código fallaría con un KeyError si el producto no existe.
```
