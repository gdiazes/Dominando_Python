# Módulo 14: Ejercicio 1 (Dificultad 1.71/10) - Escribir en un Archivo Simple

## Enunciado del Problema

Escribe un programa que cree un nuevo archivo llamado `poema.txt`.
Dentro del archivo, escribe dos líneas de un poema o canción que te guste. Asegúrate de que cada línea aparezca en una línea separada dentro del archivo.

## Código con Errores

```python
# Ejercicio: Escribir en un archivo simple

with open("poema.txt") as archivo: # Error 1
    linea1 = "En un lugar de la Mancha,"
    linea2 = "de cuyo nombre no quiero acordarme."
    
    archivo.write(linea1) # Error 2
    archivo.write(linea2)

# Error 3: El bloque 'with' cierra el archivo. ¿Qué pasaría si intentas escribir después?
# archivo.write("Tercera línea fuera de lugar.")
