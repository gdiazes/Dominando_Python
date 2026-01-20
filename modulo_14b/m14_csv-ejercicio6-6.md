# Módulo 14 (CSV): Ejercicio 6 (Dificultad 7.0/10) - Añadir una Nueva Fila a un CSV Existente

## Enunciado del Problema

Añade un nuevo contacto al archivo `contactos.csv` creado en el ejercicio 1.
El programa debe solicitar al usuario un nombre y un email, y añadir esta información como una nueva fila al final del archivo CSV sin borrar el contenido existente.

## Código con Errores

```python
# Ejercicio: Añadir una nueva fila a un CSV existente

import csv

nuevo_nombre = input("Ingresa el nombre del nuevo contacto: ")
nuevo_email = input("Ingresa el email del nuevo contacto: ")
nueva_fila = [nuevo_nombre, nuevo_email]

with open('contactos.csv', 'w', newline='') as f: # Error 1
    escritor = csv.writer(f)
    escritor.writerow(nueva_fila)
    
print("Contacto añadido.")

# Error 2: Al abrir en modo 'a', si el archivo no existe, se crea.
# Pero si se quiere escribir un encabezado solo si el archivo es nuevo, se necesita lógica adicional.
# Este código no la incluye.

# Error 3: ¿Qué pasaría si 'nueva_fila' fuera un diccionario en lugar de una lista?
# escritor.writerow({'nombre': nuevo_nombre, 'email': nuevo_email}) # Causaría un error
