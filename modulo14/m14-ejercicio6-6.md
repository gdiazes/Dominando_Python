# Módulo 14: Ejercicio 6 (Dificultad 10.26/10) - Guardar una Lista en un Archivo

## Enunciado del Problema

1.  Crea una lista de cadenas, por ejemplo, `invitados = ["Ana", "Pedro", "Marta", "Luis"]`.
2.  Escribe un programa que guarde cada nombre de la lista en una nueva línea dentro de un archivo llamado `invitados.txt`.

## Código con Errores

```python
# Ejercicio: Guardar una lista en un archivo

invitados = ["Ana", "Pedro", "Marta", "Luis"]

with open("invitados.txt", "w") as archivo:
    for invitado in invitados:
        archivo.write(invitado) # Error 1
    
    archivo.writelines(invitados) # Error 2 (Duplicaría el contenido y aún sin saltos de línea)

# Error 3 (conceptual): ¿Qué pasaría si la lista contuviera números en lugar de cadenas?
# numeros = [1, 2, 3]
# with open("numeros.txt", "w") as f:
#     f.writelines(numeros) # Esto causaría un TypeError
