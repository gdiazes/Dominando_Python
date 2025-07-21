# Módulo 12: Ejercicio 8 (Dificultad 12.44/10) - Validador de Formato de Fecha

## Enunciado del Problema (Práctica Calificada 3 - Parte A)

1.  Define una función `es_formato_fecha_valido` que acepte una cadena de texto `fecha_str` y una cadena de `formato`.
2.  La función debe devolver `True` si `fecha_str` se puede convertir a un objeto `datetime` usando el `formato` proporcionado, y `False` en caso contrario. (Pista: necesitarás usar `try-except` para atrapar el `ValueError`).
3.  Solicita al usuario una fecha.
4.  Llama a la función para verificar si la fecha ingresada por el usuario tiene el formato "YYYY-MM-DD".
5.  Muestra un mensaje indicando si el formato es válido o no.

## Código con Errores

```python
# Ejercicio: Validador de formato de fecha

import datetime

def es_formato_fecha_valido(fecha_str, formato):
    try:
        datetime.datetime.strptime(fecha_str, formato)
        return True
    except: # Error 1
        return False

# Programa principal
fecha_usuario = input("Ingresa una fecha en formato YYYY-MM-DD: ")
formato_esperado = "YY-MM-DD" # Error 2

if es_formato_fecha_valido(fecha_usuario, formato_esperado):
    print("El formato de la fecha es válido.")
else:
    print("El formato de la fecha es inválido.")

# Error 3: Llamada incorrecta a la función
# es_valido = es_formato_fecha_valido(formato_esperado, fecha_usuario)
