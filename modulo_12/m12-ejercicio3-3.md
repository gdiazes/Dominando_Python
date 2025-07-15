# Módulo 12: Ejercicio 3 (Dificultad 4.66/10) - Convertir una Cadena a `datetime`

## Enunciado del Problema

1.  Se te da una cadena de texto que representa una fecha: `"25/12/2024"`.
2.  Usa `datetime.strptime()` para convertir esta cadena en un objeto `datetime`.
3.  Una vez convertido, imprime el objeto `datetime` y también el día de la semana correspondiente a esa fecha (ej: "Wednesday").

## Código con Errores

```python
# Ejercicio: Convertir una cadena a datetime

import datetime

cadena_navidad = "25/12/2024"
formato = "%d/%m/%y" # Error 1

# Convertir cadena a objeto datetime
fecha_navidad = datetime.strptime(cadena_navidad, formato) # Error 2

print(f"Objeto datetime: {fecha_navidad}")

# Obtener y mostrar el día de la semana
dia_semana = fecha_navidad.strftime("%A")
print(f"Ese día será: " dia_semana) # Error 3
