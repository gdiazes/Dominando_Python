# Módulo 14: Ejercicio 10 (Dificultad 17.1/10) - Mini-sistema de Registro (Log) de Eventos

## Enunciado del Problema

Crea una función `registrar_evento(mensaje)` que:
1.  Obtenga la fecha y hora actual.
2.  Formatee un mensaje de log que incluya la fecha/hora y el `mensaje` proporcionado. (Ej: `[2023-10-27 15:45:00] - Usuario inició sesión.`)
3.  Añada esta línea de log a un archivo llamado `app.log`. Cada nuevo log debe ir en una nueva línea.

Luego, escribe un pequeño programa principal que llame a esta función varias veces para registrar diferentes eventos.

## Código con Errores

```python
# Ejercicio: Mini-sistema de registro (log) de eventos

import datetime

def registrar_evento(mensaje):
    ahora = datetime.datetime.now()
    fecha_hora_str = ahora.strftime("[%Y-%m-%d %H:%M:%S]")
    linea_log = fecha_hora_str + " - " + mensaje
    
    with open("app.log", "a") as logfile:
        logfile.write(linea_log) # Error 1

# Programa Principal
registrar_evento("El programa se ha iniciado.")
usuario = input("Ingresa tu nombre de usuario: ")
registrar_evento(f"Usuario '{usuario}' ha iniciado sesión.")
registrar_evento("El programa ha finalizado.")

print("Eventos registrados en 'app.log'")

# Error 2: La función abre el archivo cada vez, lo cual es correcto, pero
# ¿qué pasaría si se usara el modo 'w' en lugar de 'a'?

# Error 3: El mensaje de log no incluye un salto de línea, por lo que todos los
# logs se escribirán en la misma línea en el archivo.
