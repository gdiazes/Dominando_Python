# Módulo 12: Ejercicio 10 (Dificultad 15.54/10) - Agenda de Eventos Simple: ¿Cuánto falta?

## Enunciado del Problema (Práctica Calificada 3 - Parte C)

1.  Crea un diccionario llamado `agenda` donde las claves sean nombres de eventos (cadenas) y los valores sean objetos `datetime` de cuándo ocurrirán esos eventos. Incluye al menos 3 eventos futuros.
2.  Muestra al usuario una lista de los eventos disponibles (las claves del diccionario).
3.  Solicita al usuario que elija un evento.
4.  Si el evento existe en la agenda:
    *   Calcula el tiempo restante hasta ese evento (días y horas).
    *   Muestra el resultado de forma clara.
5.  Si el evento no existe, muestra un mensaje de error.

## Código con Errores

```python
# Ejercicio: Agenda de eventos simple

import datetime

# Crear agenda con fechas futuras
ahora = datetime.datetime.now()
agenda = {
    "Concierto": ahora + datetime.timedelta(days=30),
    "Viaje": ahora + datetime.timedelta(weeks=10),
    "Examen Final": ahora + datetime.timedelta(days=120, hours=5)
}

print("Eventos disponibles:", agenda.keys()) # Error 1
evento_elegido = input("Elige un evento para ver cuánto falta: ")

if evento_elegido in agenda:
    fecha_evento = agenda[evento_elegido]
    tiempo_restante = fecha_evento - datetime.datetime.now()
    dias_restantes = tiempo_restante.days() # Error 2
    horas_restantes = tiempo_restante.seconds // 3600
    print(f"Faltan {dias_restantes} días y {horas_restantes} horas para '{evento_elegido}'.")
else
    print("Ese evento no está en la agenda.") # Error 3
