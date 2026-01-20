# Módulo 14 (CSV): Ejercicio 8 (Dificultad 9.0/10) - Modificar un CSV (Leer, Modificar en Memoria, Escribir)

## Enunciado del Problema

Dado el archivo `inventario.csv` (`producto,precio,stock`).
Escribe un programa que "actualice" el stock de un producto.
1.  Lee todo el contenido del archivo CSV en una lista en memoria (por ejemplo, una lista de diccionarios).
2.  Solicita al usuario el nombre del producto a actualizar y el nuevo valor del stock.
3.  Modifica el stock de ese producto en la lista en memoria.
4.  Sobrescribe el archivo `inventario.csv` original con los datos actualizados.

## Código con Errores

```python
# Ejercicio: Modificar un CSV

import csv

nombre_archivo = 'inventario.csv'
datos_en_memoria = []

# Leer todo el archivo en memoria
with open(nombre_archivo, 'r', newline='') as f:
    lector = csv.DictReader(f)
    for fila in lector:
        datos_en_memoria.append(fila)

# Solicitar datos para la actualización
producto_a_actualizar = input("¿Qué producto quieres actualizar? ")
nuevo_stock_str = input(f"Nuevo stock para {producto_a_actualizar}: ")
nuevo_stock = int(nuevo_stock_str)

# Modificar en memoria
for fila in datos_en_memoria:
    if fila['producto'] == producto_a_actualizar:
        fila['stock'] = nuevo_stock
        break
    else: # Error 1
        print("Producto no encontrado.") # Esto se imprimirá por cada fila que no coincida

# Sobrescribir el archivo
with open(nombre_archivo, 'w', newline='') as f:
    escritor = csv.DictWriter(f) # Error 2
    escritor.writeheader()
    escritor.writerows(datos_en_memoria)

print("Archivo actualizado.")
# Error 3: Si el producto a actualizar no se encuentra, el archivo original se sobrescribe
# con el mismo contenido, pero la lógica de 'producto no encontrado' es incorrecta.
