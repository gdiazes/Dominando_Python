# Módulo 10: Ejercicio 2 (Dificultad 2.82/10) - Función con un Parámetro

## Enunciado del Problema

1.  Define una función llamada `saludar_usuario` que acepte un parámetro llamado `nombre`.
2.  Dentro de la función, imprime un saludo personalizado usando el nombre, por ejemplo: "Hola, [nombre], ¡qué tengas un buen día!".
3.  Solicita al usuario que ingrese su nombre y guárdalo en una variable.
4.  Llama a la función `saludar_usuario` pasándole como argumento la variable que contiene el nombre del usuario.

## Código con Errores

```python
# Ejercicio: Función con un parámetro

def saludar_usuario(nombre):
    print(f"Hola, {nombre}, ¡qué tengas un buen día!")

nombre_ingresado = input("¿Cuál es tu nombre? ")
saludar_usuario # Error 1

# Error 2: Intento de llamar a la función con un nombre de parámetro incorrecto
saludar_usuario(usuario=nombre_ingresado)

# Error 3: La función se define pero no se usa con el valor ingresado de la forma más directa.
def saludar_a_alguien(name):
    print(f"Un saludo para {name}")
# No se llama a esta función.
```
