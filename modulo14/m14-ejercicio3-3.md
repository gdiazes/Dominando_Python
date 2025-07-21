# Módulo 14: Ejercicio 3 (Dificultad 5.13/10) - Añadir Contenido a un Archivo Existente

## Enunciado del Problema

1.  Crea un archivo `lista_compras.txt` y escribe "1. Manzanas" en él.
2.  Luego, escribe un programa que abra `lista_compras.txt` y **añada** dos nuevos ítems al final del archivo: "2. Leche" y "3. Pan", cada uno en una nueva línea.
3.  El contenido final del archivo debe ser:
    ```
    1. Manzanas
    2. Leche
    3. Pan
    ```

## Código con Errores

```python
# Ejercicio: Añadir contenido a un archivo existente

# Paso 1: Crear el archivo inicial
with open("lista_compras.txt", "w") as f:
    f.write("1. Manzanas\n")

# Paso 2: Programa para añadir nuevos ítems
with open("lista_compras.txt", "w") as archivo: # Error 1
    archivo.write("2. Leche\n")
    archivo.writelines(["3. Pan\n"]) # Error 2

# Error 3: Intento de leer el archivo en modo de escritura
# with open("lista_compras.txt", "w") as f_lectura:
#     contenido = f_lectura.read() 
#     print(contenido)
