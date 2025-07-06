# Módulo 9: Ejercicio 2 (Dificultad 2.69/10) - Añadir y Modificar Elementos de un Diccionario

## Enunciado del Problema

1.  Crea un diccionario llamado `producto` con las claves "nombre" y "precio". Dale valores iniciales (ej: "Laptop", 1200).
2.  Imprime el diccionario original.
3.  El precio del producto ha cambiado. Actualiza el valor de la clave "precio" a un nuevo valor.
4.  Añade una nueva clave "stock" con un valor numérico al diccionario.
5.  Imprime el diccionario final actualizado.

## Código con Errores

```python
# Ejercicio: Añadir y modificar elementos de un diccionario

producto = {
    "nombre": "Laptop",
    "precio": 1200
}
print(f"Producto original: {producto}")

# Actualizar precio
producto.precio = 1150 # Error 1

# Añadir stock
producto["stock"] : 50 # Error 2

print(f"Producto actualizado: {producto}")
producto.add("garantia", "2 años") # Error 3
```
