# Módulo 13: Ejercicio 2 (Dificultad 3.26/10) - Importar Funciones Específicas de un Módulo

## Enunciado del Problema

Crea dos archivos: `operaciones.py` y `main.py`.
1.  En `operaciones.py`, define dos funciones: `sumar(a, b)` que devuelve la suma, y `restar(a, b)` que devuelve la resta.
2.  En `main.py`, importa **específicamente** la función `sumar` del módulo `operaciones`.
3.  Llama a la función `sumar` e imprime su resultado.
4.  Intenta llamar a la función `restar` y observa el error (el código con errores incluirá este intento).

## Código con Errores

**Archivo: `operaciones.py`**
```python
# Contenido de operaciones.py

def sumar(a, b):
    a + b # Error 1

def restar(a, b):
    return a - b
```

**Archivo: `main.py`**
```python
# Contenido de main.py

from operaciones import sumar, restar as r # Error 2 (la importación es confusa o errónea para el objetivo)

resultado_suma = sumar(10, 2)
print(f"La suma es: {resultado_suma}")

resultado_resta = r(10, 2)
print(f"La resta es: {resultado_resta}")

# El enunciado pide importar solo 'sumar'. El código importa ambas.
# El error 3 estará en cómo se intenta llamar a 'restar' si no se importara.
# Para el ejercicio, asumamos que la importación correcta es solo 'from operaciones import sumar'
# y el siguiente código es el que contiene el error:
# resultado_resta = operaciones.restar(10, 2) # Error 3
