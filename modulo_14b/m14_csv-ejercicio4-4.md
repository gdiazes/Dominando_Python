# Módulo 14 (CSV): Ejercicio 4 (Dificultad 5.0/10) - Escribir una Lista de Diccionarios a CSV (`csv.DictWriter`)

## Enunciado del Problema

Tienes una lista de diccionarios que representan productos.
Escribe un programa que guarde esta información en un archivo `productos.csv` usando `csv.DictWriter`. El archivo debe tener un encabezado.

## Código con Errores

```python
# Ejercicio: Escribir una lista de diccionarios a CSV

import csv

productos = [
    {'id': 'P101', 'nombre': 'Mouse', 'precio': 25.50},
    {'id': 'P102', 'nombre': 'Monitor', 'precio': 300.00},
    {'id': 'P103', 'nombre': 'USB-C Cable', 'precio': 12.00}
]
nombres_columnas = ['id', 'nombre', 'precio']

with open('productos.csv', 'w', newline='') as f:
    escritor = csv.DictWriter(f, fieldnames=nombres_columnas)
    
    escritor.writerows(productos) # Error 1
    
    # Error 2: Intento de escribir un diccionario con una clave que no está en fieldnames
    # escritor.writerow({'id': 'P104', 'nombre': 'Webcam', 'resolucion': '1080p'})
    
    # Error 3: El objeto 'escritor' no tiene el método 'writerow' sin 's'
    # escritor.writerow({'id': 'P105', 'nombre': 'Silla', 'precio': 150})
```
```

---
**5. `m14_csv-ejercicio5-5.md`**
```markdown
# Módulo 14 (CSV): Ejercicio 5 (Dificultad 6.0/10) - Leer un CSV como Diccionarios (`csv.DictReader`)

## Enunciado del Problema

Usando el archivo `productos.csv` del ejercicio anterior.
Escribe un programa que lea el archivo usando `csv.DictReader` y muestre los datos de cada producto en un formato legible.

## Código con Errores

```python
# Ejercicio: Leer un CSV como diccionarios

import csv

print("--- Inventario de Productos ---")
with open('productos.csv', 'r', newline='') as f:
    lector = csv.DictReader(f, fieldnames=['ID', 'Producto', 'Precio']) # Error 1
    
    for fila in lector:
        print(f"ID: {fila['ID']}, Producto: {fila.Producto}, Precio: ${float(fila['Precio']):.2f}") # Error 2
        
# Error 3 (conceptual): DictReader asume que la primera fila es el encabezado
# si no se proveen 'fieldnames'. Si el CSV no tuviera encabezado,
# ¿cómo funcionaría DictReader?
