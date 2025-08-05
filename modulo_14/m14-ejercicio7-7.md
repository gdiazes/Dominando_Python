# Módulo 14: Ejercicio 7 (Dificultad 11.97/10) - Contar Palabras en un Archivo

## Enunciado del Problema

Escribe un programa que lea un archivo de texto y cuente el número total de palabras que contiene.
Para simplificar, puedes considerar que las palabras están separadas por espacios.

## Código con Errores

```python
# Ejercicio: Contar palabras en un archivo

# (Asegúrate de tener un archivo 'texto_largo.txt')

nombre_archivo = "texto_largo.txt"
contador_palabras = 0

with open(nombre_archivo, "r") as f:
    for linea in f:
        palabras = linea.split # Error 1
        contador_palabras = len(palabras) # Error 2
        
print(f"El archivo '{nombre_archivo}' contiene {contador_palabras} palabras.")

# Error 3: El bucle 'for' está bien, pero si se usara f.read()
# y luego se dividiera, ¿cómo afectaría a la memoria con archivos muy grandes?
# (Este es un error de eficiencia/diseño más que de sintaxis).
