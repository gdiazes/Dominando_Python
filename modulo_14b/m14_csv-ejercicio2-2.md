# Módulo 14 (CSV): Ejercicio 2 (Dificultad 3.0/10) - Leer un CSV Básico (`csv.reader`)

## Enunciado del Problema

Asumiendo que tienes el archivo `contactos.csv` del ejercicio anterior.
Escribe un programa que lea el archivo e imprima cada contacto en un formato amigable.
Asegúrate de omitir la fila del encabezado.

## Código con Errores

```python
# Ejercicio: Leer un CSV básico

import csv

with open('contactos.csv', mode='r') as archivo:
    lector = csv.reader(archivo)
    
    # Omitir encabezado
    next(lector)
    
    for fila in lector:
        nombre = fila[0]
        email = fila.get(1) # Error 1
        print(f"Nombre: {nombre}, Email: {email}")

# Error 2: Intento de leer un archivo que no existe
# with open('no_existe.csv', 'r') as f:
#     lector_falso = csv.reader(f)

# Error 3: El archivo se abre sin el argumento 'newline=""', lo que puede causar
# filas en blanco extra en algunos sistemas operativos.
