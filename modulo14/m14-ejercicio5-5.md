# Módulo 14: Ejercicio 5 (Dificultad 8.55/10) - Crear una Copia de un Archivo

## Enunciado del Problema

Escribe un programa que cree una copia de un archivo de texto existente.
1.  Abre un archivo de origen para lectura (ej: `original.txt`).
2.  Abre un archivo de destino para escritura (ej: `copia.txt`).
3.  Lee el contenido del archivo de origen y escríbelo en el archivo de destino.

## Código con Errores

```python
# Ejercicio: Crear una copia de un archivo

# (Asegúrate de tener un archivo 'original.txt' con algo de texto)

archivo_origen_nombre = "original.txt"
archivo_copia_nombre = "copia.txt"

with open(archivo_origen_nombre, "r") as origen:
    contenido = origen.read
    with open(archivo_copia_nombre, "w") as destino:
        destino.write(contenido) # Error 1
        
print(f"Archivo '{archivo_origen_nombre}' copiado a '{archivo_copia_nombre}'.")

# Error 2: Intento de abrir ambos archivos en el mismo 'with' de forma incorrecta
# with open(archivo_origen_nombre, "r") as origen, open(archivo_copia_nombre, "a") as destino:
#     destino.writelines(origen) # .writelines espera una lista de cadenas, no un objeto de archivo

# Error 3: Olvidar cerrar los archivos si no se usa 'with'
# origen = open(archivo_origen_nombre, "r")
# destino = open(archivo_copia_nombre, "w")
# destino.write(origen.read())
# # No se llama a origen.close() ni a destino.close()
