# Módulo 13: Ejercicio 9 (Dificultad 14.66/10) - Crear y Usar un Paquete Simple

## Enunciado del Problema

Crea una estructura de directorios que represente un paquete:
```
proyecto/
├── main.py
└── mi_paquete/
    ├── __init__.py
    ├── aritmetica.py
    └── texto.py
```
1.  En `mi_paquete/aritmetica.py`, define una función `multiplicar(a, b)`.
2.  En `mi_paquete/texto.py`, define una función `capitalizar_frase(frase)`.
3.  En el `__init__.py` del paquete, puedes importar las funciones para hacerlas más accesibles (opcional pero buena práctica).
4.  En `main.py`, importa y usa ambas funciones desde `mi_paquete`.

## Código con Errores

**Archivo: `mi_paquete/__init__.py`**
```python
# Contenido de __init__.py (intento de hacer las funciones accesibles)
from aritmetica import multiplicar # Error 1
from .texto import capitalizar_frase
```

**Archivo: `mi_paquete/aritmetica.py`**
```python
# Contenido de aritmetica.py
def multiplicar(a, b): return a * b
```

**Archivo: `mi_paquete/texto.py`**
```python
# Contenido de texto.py
def capitalizar_frase(frase): return frase.capitalize()
```

**Archivo: `main.py`**
```python
# Contenido de main.py

from mi_paquete import multiplicar, capitalizar_frase # Asumiendo que __init__.py funciona

# Error 2: Intento de importar de una forma que no es la más estándar si __init__.py está vacío
# import mi_paquete.aritmetica
# import mi_paquete.texto

resultado_mult = mi_paquete.aritmetica.multiplicar(5, 4)
resultado_texto = mi_paquete.texto.capitalizar_frase("hola mundo")

print(f"Multiplicación: {resultado_mult}")
print(f"Texto capitalizado: {resultado_texto}")

# Error 3: La llamada 'mi_paquete.aritmetica.multiplicar' es correcta, pero si el objetivo
# era usar la importación del __init__.py, la llamada directa 'multiplicar(5,4)' fallaría
# si el import principal es solo 'import mi_paquete'.
