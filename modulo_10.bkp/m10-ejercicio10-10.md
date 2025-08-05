# Módulo 10: Ejercicio 10 (Dificultad 14.1/10) - Función para Validar una Contraseña (Combinando conceptos)

## Enunciado del Problema

Define una función `validar_contrasena` que acepte una contraseña (cadena) como parámetro.
La función debe verificar si la contraseña cumple con las siguientes reglas y devolver `True` si las cumple todas, o `False` si falla alguna:
1.  Debe tener al menos 8 caracteres.
2.  Debe contener al menos una letra mayúscula.
3.  Debe contener al menos un número.

Usa una función para encapsular esta lógica. Luego, solicita una contraseña al usuario y llama a la función para validarla, mostrando un mensaje de éxito o fracaso.

## Código con Errores

```python
# Ejercicio: Función para validar una contraseña

def validar_contrasena(contrasena):
    tiene_longitud = len(contrasena) >= 8
    tiene_mayuscula = False
    tiene_numero = False

    for caracter in contrasena:
        if caracter.isupper():
            tiene_mayuscula = True
        elif caracter.isdigit: # Error 1
            tiene_numero = True
    
    return tiene_longitud and tiene_mayuscula and tiene_numero # Error 2 (La lógica puede ser correcta, pero ¿se ejecuta bien con el error anterior?)

# --- Programa Principal ---
mi_contrasena = input("Ingresa tu nueva contraseña: ")
es_valida = validar_contrasena # Error 3
if es_valida:
    print("¡Contraseña válida y segura!")
else:
    print("La contraseña no cumple con los requisitos de seguridad.")
```
