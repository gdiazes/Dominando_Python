# Módulo 14: Ejercicio 8 (Dificultad 13.68/10) - Buscar una Línea Específica en un Archivo

## Enunciado del Problema

Escribe un programa que busque en un archivo de texto (`datos_usuarios.txt`) una línea que contenga un email específico ingresado por el usuario.
Si encuentra la línea, la debe imprimir. Si no la encuentra después de revisar todo el archivo, debe informar al usuario.

Ejemplo de `datos_usuarios.txt`:
```
ID: 101, Nombre: Ana, Email: ana@example.com
ID: 102, Nombre: Luis, Email: luis@example.com
ID: 103, Nombre: Eva, Email: eva@example.com
```

## Código con Errores

```python
# Ejercicio: Buscar una línea específica en un archivo

email_buscado = input("Ingresa el email a buscar: ")
encontrado = False

with open("datos_usuarios.txt", "r") as f:
    for linea in f:
        if email_buscado in linea:
            print("Usuario encontrado:")
            print(linea.strip())
            break
            encontrado = True # Error 1
    
if not encontrado: # Error 2
    print(f"No se encontró ningún usuario con el email '{email_buscado}'.")

# Error 3 (lógico): ¿Qué pasa si hay espacios extra en la entrada del usuario
# o diferencias de mayúsculas/minúsculas? La búsqueda fallaría.
# Por ejemplo, si el usuario escribe " ana@example.com " (con espacios).
