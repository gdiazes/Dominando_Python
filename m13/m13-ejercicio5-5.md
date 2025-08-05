# Módulo 13: Ejercicio 5 (Dificultad 8.14/10) - Uso del Módulo `random`

## Enunciado del Problema

Escribe un programa que simule un sorteo simple:
1.  Crea una lista de nombres de participantes.
2.  Usa el módulo `random` para seleccionar un ganador al azar de la lista.
3.  Usa el módulo `random` para generar un número de la suerte entre 1 y 100 para el ganador.
4.  Imprime el nombre del ganador y su número de la suerte.

## Código con Errores

```python
# Ejercicio: Uso del módulo random

from random import * # Error 1 (No es un error de sintaxis, pero es una mala práctica)

participantes = ["Ana", "Juan", "Elena", "Pedro", "Sofía"]

if participantes:
    ganador = choice(participantes)
    numero_suerte = randint(1, 100)
    print(f"El ganador es: {ganador}")
    print(f"Su número de la suerte es: {numero_suerte}")
else:
    print("No hay participantes en el sorteo.")

# Error 2: Intento de usar una función con el prefijo del módulo cuando se usó 'from ... import *'
# ganador_alt = random.choice(participantes)

# Error 3: Confundir las funciones del módulo
# numero_suerte_alt = random.randrange(100) # randrange(100) va de 0 a 99, no de 1 a 100
