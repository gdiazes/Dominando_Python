# Módulo 8: Ejercicio 1 (Dificultad 1.28/10) - Crear y Acceder a una Tupla

## Enunciado del Problema

1.  Crea una tupla llamada `info_persona` que contenga tu nombre (cadena), edad (entero) y ciudad de residencia (cadena).
2.  Imprime la tupla completa.
3.  Imprime el primer elemento (nombre) y el último elemento (ciudad) de la tupla.

## Código con Errores

```python
# Ejercicio: Crear y acceder a una tupla

info_persona = ["Juan Pérez", 30, "Madrid"] # Error 1

print(f"Tupla completa: {info_persona}")

nombre = info_persona[1] # Error 2
ciudad = info_persona[-0] # Error 3

print(f"Nombre: {nombre}")
print(f"Ciudad: {ciudad}")
```
