# Módulo 13: Ejercicio 7 (Dificultad 11.4/10) - Mover Funcionalidad a Múltiples Módulos

## Enunciado del Problema

Refactoriza un programa. Inicialmente, todo el código está en un solo archivo `main.py`.
Debes mover la funcionalidad a dos módulos separados: `calculadora.py` y `impresora.py`.
1.  `calculadora.py`: Debe contener las funciones `sumar(a, b)` y `restar(a, b)`.
2.  `impresora.py`: Debe contener una función `imprimir_resultado(descripcion, resultado)`.
3.  `main.py`: Debe importar y usar las funciones de ambos módulos para sumar dos números e imprimir el resultado.

## Código con Errores

**Archivo: `main.py` (Versión final)**
```python
# Contenido de main.py (final)

import calculadora
from impresora import imprimir_resultado as print_res # Error 1 (sintaxis de importación)

num1 = 20
num2 = 15

suma = calculadora.sumar(num1, num2)
resta = restar(num1, num2) # Error 2

print_res("El resultado de la suma es", suma)
impresora.imprimir_resultado("El resultado de la resta es", resta) # Error 3
```

**Archivo: `calculadora.py`**
```python
# Contenido de calculadora.py
def sumar(a, b): return a + b
def restar(a, b): return a - b
```

**Archivo: `impresora.py`**
```python
# Contenido de impresora.py
def imprimir_resultado(descripcion, resultado):
    print(f"{descripcion}: {resultado}")
