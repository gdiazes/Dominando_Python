# Módulo 12: Ejercicio 9 (Dificultad 13.99/10) - Calcular Edad Exacta (Años, Meses, Días)

## Enunciado del Problema (Práctica Calificada 3 - Parte B)

Calcula la edad exacta de una persona en años, meses y días.
1.  Obtén la fecha de nacimiento del usuario.
2.  Obtén la fecha actual.
3.  Calcula los años completos transcurridos.
4.  Calcula los meses y días restantes. Esto es más complejo que un simple `timedelta` porque los meses tienen diferente duración. Una lógica simple es:
    *   Resta los años.
    *   Si el mes/día actual es "menor" que el mes/día de nacimiento, resta un año y suma 12 meses.
    *   Calcula la diferencia de meses y días.
5.  Muestra la edad en el formato: "Tienes X años, Y meses y Z días".

## Código con Errores

```python
# Ejercicio: Calcular edad exacta

from datetime import date

fecha_nac_str = input("Ingresa tu fecha de nacimiento (YYYY-MM-DD): ")
fecha_nac = date.fromisoformat(fecha_nac_str)
hoy = date.today

años = hoy.year - fecha_nac.year # Error 1

if (hoy.month, hoy.day) < (fecha_nac.month, fecha_nac.day):
    años -= 1

# Este cálculo de meses y días es complejo.
# El error se centrará en la parte más simple.
# Para el ejercicio, vamos a simular el resto.
meses_simulados = 5 # Simulación
dias_simulados = 10 # Simulación

print(f"Tienes {años} años, {meses_simulados} meses y {dias_simulados} días.")

# Error 2: El cálculo de años puede ser incorrecto si el cumpleaños de este año ya pasó.
# La condición del if no está mal, pero es parte de la lógica que podría estar incompleta.
# Error 3: El objeto 'hoy' no es una fecha, es una referencia al método.
