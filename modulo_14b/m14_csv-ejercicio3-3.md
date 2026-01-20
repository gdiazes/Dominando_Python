# Módulo 14 (CSV): Ejercicio 3 (Dificultad 4.0/10) - Calcular un Promedio desde un CSV (`csv.reader`)

## Enunciado del Problema

Tienes un archivo `calificaciones.csv` con el siguiente contenido:
```csv
estudiante,nota
Carlos,85
Laura,92
Pedro,78
```
Escribe un programa que lea este archivo, calcule la nota promedio y la imprima.

## Código con Errores

```python
# Ejercicio: Calcular un promedio desde un CSV

import csv

# (Asegúrate de crear 'calificaciones.csv' con el contenido del enunciado)

suma_notas = 0
num_estudiantes = 0

with open('calificaciones.csv', 'r', newline='') as f:
    lector = csv.reader(f)
    encabezado = next(lector)
    
    for fila in lector:
        suma_notas += fila[1] # Error 1
        num_estudiantes += 1

promedio = suma_notas / num_estudiantes
print(f"La nota promedio es: {promedio}")

# Error 2: ¿Qué pasa si una nota en el CSV no es un número? (ej: 'ausente')
# La conversión int() fallaría.

# Error 3: El archivo se lee pero no se escribe el resultado en ningún lado.
# Una mejora sería guardar el promedio en otro archivo.
# Para el error, intentaremos una operación inválida:
# with open('calificaciones.csv', 'r+') as f:
#     f.write(f"Promedio,{promedio}")
