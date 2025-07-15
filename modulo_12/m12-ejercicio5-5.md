# Módulo 12: Ejercicio 5 (Dificultad 7.77/10) - Calcular Días Vividos

## Enunciado del Problema

1.  Solicita al usuario su fecha de nacimiento en formato "dd/mm/aaaa".
2.  Convierte la cadena ingresada a un objeto `datetime`.
3.  Obtén la fecha actual.
4.  Calcula la diferencia entre la fecha actual y la fecha de nacimiento.
5.  Imprime el número total de días que ha vivido la persona.

## Código con Errores

```python
# Ejercicio: Calcular días vividos

import datetime

fecha_nac_str = input("Ingresa tu fecha de nacimiento (dd/mm/aaaa): ")
formato = "%d/%m/%Y"
fecha_nac_obj = datetime.datetime.strptime(fecha_nac_str, formato)

fecha_hoy = datetime.date.today() # Error 1

# Calcular diferencia
diferencia = fecha_hoy - fecha_nac_obj

print(f"Has vivido un total de {diferencia} días.") # Error 2
# Error 3: El objeto diferencia no es solo un número.
# diferencia_en_dias = diferencia.days()
# print(f"Días vividos: {diferencia_en_dias}")
