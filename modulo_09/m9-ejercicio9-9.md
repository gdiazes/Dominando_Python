# Módulo 9: Ejercicio 9 (Dificultad 12.1/10) - Diccionario Anidado (Información de Múltiples Usuarios)

## Enunciado del Problema

Crea un diccionario llamado `usuarios` donde las claves sean IDs de usuario (cadenas, ej: "user1", "user2") y los valores sean otros diccionarios que contengan información de cada usuario (nombre y email).
1.  Crea este diccionario con al menos dos usuarios.
2.  Imprime la información completa de "user2".
3.  Accede e imprime solo el email de "user1".
4.  Añade un nuevo usuario ("user3") al diccionario `usuarios`.

## Código con Errores

```python
# Ejercicio: Diccionario anidado

usuarios = {
    "user1": {
        "nombre": "Alice",
        "email": "alice@example.com"
    },
    "user2": {
        "nombre": "Bob"
        "email": "bob@example.com" # Error 1
    }
}

# Imprimir info de user2
info_user2 = usuarios["user2"]
print(f"Información de user2: {info_user2}")

# Imprimir email de user1
email_user1 = usuarios["user1.email"] # Error 2
print(f"Email de user1: {email_user1}")

# Añadir un nuevo usuario
nuevo_usuario_info = {"nombre": "Charlie", "email": "charlie@example.com"}
usuarios.user3 = nuevo_usuario_info # Error 3

print("\nDiccionario de usuarios actualizado:")
print(usuarios)
```
