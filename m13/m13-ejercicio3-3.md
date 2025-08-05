# Módulo 13: Ejercicio 3 (Dificultad 4.89/10) - Uso de un Módulo con Alias

## Enunciado del Problema

Crea dos archivos: `configuracion_app.py` y `main.py`.
1.  En `configuracion_app.py`, define una variable `VERSION = "1.0.2"` y una función `obtener_version()` que devuelve esa variable.
2.  En `main.py`, importa el módulo `configuracion_app` usando el alias `config`.
3.  Usa el alias para acceder tanto a la variable `VERSION` como a la función `obtener_version()` e imprime sus valores.

## Código con Errores

**Archivo: `configuracion_app.py`**
```python
# Contenido de configuracion_app.py

VERSION = "1.0.2"

def obtener_version():
    return VERSION
```

**Archivo: `main.py`**
```python
# Contenido de main.py

import configuracion_app from config # Error 1

version_var = config.VERSION
version_func = obtener_version() # Error 2

print(f"Versión (variable): {version_var}")
print(f"Versión (función): {version_func}")

# Error 3 (conceptual): ¿Qué pasaría si el alias fuera una palabra reservada?
# import configuracion_app as for
