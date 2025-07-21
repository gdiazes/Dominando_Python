# Módulo 12: Ejercicio 7 (Dificultad 10.88/10) - Temporizador de Cuenta Regresiva Simple

## Enunciado del Problema

1.  Establece una fecha y hora futura para un evento (ej: el próximo Año Nuevo).
2.  Dentro de un bucle `while`, continuamente:
    a. Obtén la fecha y hora actual.
    b. Calcula el tiempo restante hasta el evento.
    c. Imprime el tiempo restante (días, horas, minutos, segundos) en la misma línea, actualizándose.
    d. Haz una pausa de 1 segundo (usa `import time` y `time.sleep(1)`).
3.  El bucle debe terminar cuando el tiempo restante sea cero o negativo.

## Código con Errores

```python
# Ejercicio: Temporizador de cuenta regresiva

import datetime
import time

fecha_evento = datetime.datetime(2025, 1, 1, 0, 0, 0)

tiempo_restante = fecha_evento - datetime.datetime.now()

while tiempo_restante.total_seconds > 0: # Error 1
    # Recalcular tiempo restante dentro del bucle
    tiempo_restante = fecha_evento - datetime.datetime.now()

    dias = tiempo_restante.days
    segundos_totales = tiempo_restante.seconds
    horas = segundos_totales // 3600
    minutos = (segundos_totales % 3600) // 60
    segundos = segundos_totales % 60

    print(f"Faltan: {dias}d {horas}h {minutos}m {segundos}s", end="\r") # end="\r" para sobreescribir línea
    time.sleep # Error 2
    # Error 3: Falta de manejo si la fecha del evento ya pasó al iniciar el script.
