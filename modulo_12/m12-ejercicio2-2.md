# Módulo 12: Ejercicio 2 (Dificultad 3.11/10) - Crear una Fecha Específica y Formatearla

## Enunciado del Problema

1.  Importa la clase `datetime` del módulo `datetime`.
2.  Crea un objeto `datetime` que represente el 4 de julio de 1776, a las 14:00 horas.
3.  Usando `.strftime()`, formatea esa fecha para que se muestre como "Día de la Independencia: July 4, 1776".
4.  Imprime la cadena formateada.

## Código con Errores

```python
# Ejercicio: Crear una fecha específica y formatearla

from datetime import datetime

# Crear fecha
fecha_independencia = datetime(1776, 7, 4, 14) # Esta línea es correcta

# Formatear fecha
formato = "%B %d, %Y"
cadena_formateada = fecha_independencia.strftime("Día de la Independencia: ", formato) # Error 1

print(cadena_formateada)

# Error 2: Uso de códigos de formato incorrectos
# formato_malo = "%d de %m de %y"
# print(fecha_independencia.strftime(formato_malo))

# Error 3: Intento de llamar a strftime en la clase en lugar del objeto
# print(datetime.strftime(formato))
