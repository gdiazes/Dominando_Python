# Módulo 12: Ejercicio 4 (Dificultad 6.22/10) - Calcular una Fecha Futura con `timedelta`

## Enunciado del Problema

1.  Obtén la fecha y hora actual.
2.  Crea un objeto `timedelta` que represente una duración de 100 días.
3.  Calcula cuál será la fecha y hora exactamente 100 días en el futuro.
4.  Imprime la fecha y hora actual y la fecha futura.

## Código con Errores

```python
# Ejercicio: Calcular una fecha futura con timedelta

import datetime

ahora = datetime.datetime.now()

# Crear duración
duracion = timedelta(days: 100) # Error 1

# Calcular fecha futura
fecha_futura = ahora + duracion

print(f"Fecha de hoy: {ahora}")
print(f"Fecha en 100 días: {fecha_futura}")

# Error 2: Intento de sumar un entero a una fecha
# fecha_futura_mal = ahora + 100

# Error 3: timedelta no se importó explícitamente, o no se usó con datetime.
# from datetime import datetime
# duracion_mal = timedelta(days=100) # Causaría NameError
