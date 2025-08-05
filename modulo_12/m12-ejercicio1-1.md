# Módulo 12: Ejercicio 1 (Dificultad 1.55/10) - Mostrar Fecha y Hora Actual

## Enunciado del Problema

1.  Importa el módulo `datetime`.
2.  Obtén la fecha y hora actual usando `datetime.datetime.now()`.
3.  Imprime la fecha y hora actual completa.

## Código con Errores

```python
# Ejercicio: Mostrar fecha y hora actual

datetime = import datetime # Error 1

ahora = datetime.now() # Error 2

print(f"La fecha y hora actual es: {ahora}")

# Error 3 (conceptual): ¿Qué pasa si la clase no se especifica?
# ahora_mal = datetime.now
# print(ahora_mal)
