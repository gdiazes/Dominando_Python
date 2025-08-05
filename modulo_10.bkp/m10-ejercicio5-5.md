# Módulo 10: Ejercicio 5 (Dificultad 7.05/10) - Función para Verificar si un Número es Par

## Enunciado del Problema

1.  Define una función llamada `es_par` que acepte un número como parámetro.
2.  La función debe devolver `True` si el número es par, y `False` si es impar.
3.  Solicita al usuario un número.
4.  Llama a la función con el número del usuario y, basándote en el valor devuelto, imprime si el número es par o impar.

## Código con Errores

```python
# Ejercicio: Función para verificar si un número es par

def es_par(numero):
    if numero % 2 == 0:
        return True
    # Error 1: ¿Qué devuelve la función si el número es impar?

numero_usuario_str = input("Ingresa un número: ")
numero_usuario = int(numero_usuario_str)

resultado = es_par() # Error 2

if resultado:
    print(f"El número {numero_usuario} es par.")
else:
    print(f"El número {numero_usuario} no es par.") # Error 3 (esta línea estaría bien si 'resultado' fuera correcto)
```
