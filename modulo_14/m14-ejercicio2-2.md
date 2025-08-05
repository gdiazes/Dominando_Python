# Módulo 14: Ejercicio 2 (Dificultad 3.42/10) - Leer un Archivo Completo

## Enunciado del Problema

Asumiendo que tienes un archivo `saludo.txt` con el siguiente contenido:
```
¡Hola, mundo!
Bienvenido a la lectura de archivos.
```
Escribe un programa que abra `saludo.txt`, lea todo su contenido en una sola variable, y luego imprima ese contenido en la consola.

## Código con Errores

```python
# Ejercicio: Leer un archivo completo

# (Asegúrate de tener un archivo 'saludo.txt' con el contenido del enunciado)

archivo = open("saludo.txt", "r") # Error 1

contenido = archivo.read()
print("Contenido del archivo:")
print(contenido)

# Error 2: La siguiente línea intentaría leer de nuevo, pero el "cursor" ya está al final.
# contenido_extra = archivo.readline() 
# print(f"Contenido extra: {contenido_extra}")

# Error 3: El archivo se abrió pero nunca se cerró explícitamente.
