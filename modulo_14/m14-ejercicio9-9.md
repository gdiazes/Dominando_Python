# Módulo 14: Ejercicio 9 (Dificultad 15.39/10) - Manejo de Errores al Abrir un Archivo

## Enunciado del Problema

Escribe un programa que intente abrir y leer un archivo cuyo nombre será ingresado por el usuario.
El programa debe manejar elegantemente el error `FileNotFoundError` si el archivo no existe, mostrando un mensaje amigable al usuario en lugar de que el programa se detenga.
Si el archivo existe, debe imprimir su contenido.

## Código con Errores

```python
# Ejercicio: Manejo de errores al abrir un archivo

nombre_archivo = input("Ingresa el nombre del archivo a leer: ")

try:
    with open(nombre_archivo, "r") as f:
        contenido = f.read()
    print("--- Contenido del archivo ---")
    print(contenido)
except FileNotFoundError: # Error 1
    print(f"Error: El archivo '{nombre_archivo}' no fue encontrado.")
    # El 'except' está bien, pero el error estará en otro lugar del bloque try/except

# Error 2: ¿Qué pasa si ocurre otro error, por ejemplo, de permisos de lectura?
# El 'except' actual solo captura FileNotFoundError.

# Error 3: La siguiente línea se ejecuta siempre, lo cual podría ser confuso si hubo un error.
print("\n--- Fin del programa ---")
# Para un flujo más claro, a menudo se usa un bloque 'finally' o se estructura diferente.
