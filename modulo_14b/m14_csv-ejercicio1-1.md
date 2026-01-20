# Módulo 14 (CSV): Ejercicio 1 (Dificultad 2.0/10) - Escribir Datos Simples a un CSV (`csv.writer`)

## Enunciado del Problema

Crea un programa que escriba una pequeña lista de contactos en un archivo llamado `contactos.csv`.
El archivo debe tener un encabezado ("nombre", "email") y dos filas de datos.

## Código con Errores

```python
# Ejercicio: Escribir datos simples a un CSV

import csv

encabezado = ["nombre", "email"]
datos = [
    ["Ana", "ana@example.com"],
    ["Luis", "luis@example.com"]
]

with open('contactos.csv', 'w') as archivo: # Error 1
    escritor = csv.writer(archivo)
    escritor.writerow(encabezado)
    escritor.writerow(datos) # Error 2

# Error 3 (conceptual): El archivo se cierra automáticamente,
# pero ¿qué pasaría si se intentara escribir después del bloque 'with'?
# escritor.writerow(["Eva", "eva@example.com"])
