# Módulo 13: Ejercicio 8 (Dificultad 13.03/10) - Importación Circular (Error Conceptual)

## Enunciado del Problema

Este ejercicio está diseñado para demostrar qué es una importación circular y por qué causa problemas.
Crea dos archivos: `modulo_a.py` y `modulo_b.py`.
1.  En `modulo_a.py`, define una función `funcion_a()` que llame a una función de `modulo_b`. Para ello, `modulo_a.py` debe importar `modulo_b`.
2.  En `modulo_b.py`, define una función `funcion_b()` que llame a la función de `modulo_a`. Para ello, `modulo_b.py` debe importar `modulo_a`.
3.  En `modulo_a.py`, después de la definición, llama a `funcion_a()`.
4.  Intenta ejecutar `modulo_a.py` y observa el `ImportError`.

## Código con Errores

*Nota: El "código con errores" aquí es precisamente la estructura que causa el error, no hay errores de sintaxis que arreglar, el error es el diseño en sí.*

**Archivo: `modulo_a.py`**
```python
# Contenido de modulo_a.py
print("Cargando modulo_a...")
import modulo_b # Error 1: Causa la importación circular

def funcion_a():
    print("Llamando desde A a B...")
    modulo_b.funcion_b()

funcion_a() # Error 2: Llamada al inicio que dispara el ciclo
```

**Archivo: `modulo_b.py`**
```python
# Contenido de modulo_b.py
print("Cargando modulo_b...")
import modulo_a # Error 3: Causa la importación circular

def funcion_b():
    print("Llamando desde B a A... (esto no se alcanzará)")
    modulo_a.funcion_a()
