# Módulo 14 (CSV): Ejercicio 7 (Dificultad 8.0/10) - Filtrar Datos de un CSV

## Enunciado del Problema

Dado el archivo `productos.csv` de ejercicios anteriores.
Escribe un programa que lea el archivo y cree un nuevo archivo `productos_caros.csv` que contenga solo los productos cuyo precio sea mayor a $50.

## Código con Errores

```python
# Ejercicio: Filtrar datos de un CSV

import csv

with open('productos.csv', 'r', newline='') as f_in, open('productos_caros.csv', 'w', newline='') as f_out:
    lector = csv.DictReader(f_in)
    nombres_columnas = lector.fieldnames
    
    escritor = csv.DictWriter(f_out, fieldnames=nombres_columnas)
    escritor.writeheader()
    
    for fila in lector:
        if fila['precio'] > 50: # Error 1
            escritor.writerow(fila)
            
print("Archivo 'productos_caros.csv' creado con los productos filtrados.")

# Error 2: El 'fieldnames' del DictWriter podría no ser el mismo si quisiéramos
# escribir solo algunas columnas. Aquí usamos el mismo, lo cual está bien.
# El error puede ser más sutil: ¿qué pasa si la clave 'precio' tiene mayúscula?
# if fila['Precio'] > 50:

# Error 3: El archivo de salida se crea, pero no se verifica si se escribió algo.
# Si ningún producto cumple la condición, el archivo de salida solo tendrá el encabezado.
