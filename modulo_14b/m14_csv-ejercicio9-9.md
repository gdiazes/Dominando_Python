# Módulo 14 (CSV): Ejercicio 9 (Dificultad 10.0/10) - Manejo de Diferentes Delimitadores

## Enunciado del Problema

Tienes un archivo de datos `datos.psv` (Pipe-Separated Values) donde el separador es `|` en lugar de una coma.
```
nombre|ciudad|edad
Ana|Lima|28
Juan|Cusco|35
```
Escribe un programa que lea este archivo `datos.psv` y lo convierta a un archivo `datos_convertidos.csv` con comas como delimitador.

## Código con Errores

```python
# Ejercicio: Manejo de diferentes delimitadores

import csv

# (Asegúrate de crear 'datos.psv' con el contenido del enunciado)

datos_leidos = []
with open('datos.psv', 'r', newline='') as f_in:
    lector = csv.reader(f_in, delimiter=",") # Error 1
    for fila in lector:
        datos_leidos.append(fila)
        
with open('datos_convertidos.csv', 'w', newline='') as f_out:
    escritor = csv.writer(f_out, delimiter=',')
    escritor.writerows(datos_leidos) # Error 2

print("Archivo convertido exitosamente.")
# Error 3: El código asume que el lector funciona bien. Si no lo hace,
# 'datos_leidos' contendrá datos malformados que se escribirán incorrectamente.
