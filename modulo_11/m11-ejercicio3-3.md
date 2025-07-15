# Módulo 11: Ejercicio 3 (Dificultad 4.44/10) - Creador de Perfiles con `**kwargs`

## Enunciado del Problema

Define una función `crear_perfil` que acepte un número variable de argumentos de palabra clave.
La función debe imprimir cada par clave-valor en una línea separada, con la clave capitalizada.

Ejemplo de llamada: `crear_perfil(nombre="Ana", profesion="científica", ciudad="Ginebra")`
Salida esperada:
```
Nombre: Ana
Profesion: científica
Ciudad: Ginebra
```

## Código con Errores

```python
# Ejercicio: Creador de perfiles con **kwargs

def crear_perfil(**kwargs):
    print("--- Perfil de Usuario ---")
    for clave, valor in kwargs: # Error 1
        print(f"{clave.capitalize}: {valor}") # Error 2

# Prueba de la función
crear_perfil(usuario="user123", email="user@example.com", activo=True)

# Error 3: Intento de llamar a la función con un argumento posicional
# crear_perfil("user123", email="user@example.com")
