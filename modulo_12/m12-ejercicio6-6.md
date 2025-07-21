# Módulo 12: Ejercicio 6 (Dificultad 9.33/10) - Extraer y Usar Componentes de una Fecha

## Enunciado del Problema

1.  Crea un objeto `datetime` para una fecha y hora específicas.
2.  Extrae los componentes `año`, `mes`, `día`, `hora` y `minuto` en variables separadas.
3.  Usa estos componentes para imprimir un mensaje formateado como:
    "El evento ocurrirá el día [día] del mes [mes] de [año] a las [hora]:[minuto]."

## Código con Errores

```python
# Ejercicio: Extraer componentes de una fecha

from datetime import datetime

evento = datetime(2024, 10, 26, 19, 30)

# Extraer componentes
año = evento.year
mes = evento.mes # Error 1
día = evento.day
hora = evento.hora # Error 2
minuto = evento.minute

# Imprimir mensaje
print(f"El evento ocurrirá el día {día} del mes {mes} de {año} a las {hora}:{minuto}.")

# Error 3: intento de asignar un componente, lo cual no es posible
# evento.year = 2025
