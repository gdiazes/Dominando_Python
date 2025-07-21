# Módulo 13: Ejercicio 1 (Dificultad 1.63/10) - Crear y Usar un Módulo Simple

## Enunciado del Problema

Crea dos archivos: `saludos.py` y `main.py`.
1.  En `saludos.py`, define una función `decir_hola()` que imprima "Hola desde el módulo saludos!".
2.  En `main.py`, importa el módulo `saludos` y llama a la función `decir_hola()`.

## Código con Errores

**Archivo: `saludos.py`**
```python
# Contenido de saludos.py

def decir_hola: # Error 1
    print("Hola desde el módulo saludos!")
```

**Archivo: `main.py`**
```python
# Contenido de main.py

importar saludos # Error 2

decir_hola() # Error 3
