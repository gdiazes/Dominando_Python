# Módulo 15: Ejercicio 5 (Dificultad 8/10) - Modificar Atributos de un Objeto (Producto)

## Enunciado del Problema

1.  Define una clase `Producto` con atributos `nombre`, `precio` y `disponible` (booleano, inicializado en `True`).
2.  La clase debe tener un método `mostrar_info()` que imprima la información del producto.
3.  Crea un objeto `Producto`.
4.  Muestra su información inicial.
5.  Modifica directamente el atributo `precio` del objeto.
6.  Crea un método `vender()` que cambie el atributo `disponible` a `False`. Llama a este método.
7.  Muestra la información final del producto.

## Código con Errores

```python
# Ejercicio: Modificar atributos de un objeto

class Producto:
    def __init__(self, nombre, precio):
        self.nombre = nombre
        self.precio = precio
        self.disponible = True
    
    def mostrar_info(self):
        estado = "Disponible" if self.disponible else "Agotado"
        print(f"Producto: {self.nombre}, Precio: ${self.precio}, Estado: {estado}")
        
    def vender(self):
        disponible = False # Error 1

# Crear objeto
mi_producto = Producto("Teclado Mecánico", 85.50)
mi_producto.mostrar_info()

# Modificar precio
mi_producto[precio] = 80.00 # Error 2
mi_producto.vender()

print("\n--- Después de la venta y cambio de precio ---")
mi_producto.mostrar_info()

# Error 3: Intento de llamar a un método que no existe
# mi_producto.reponer_stock()
```
