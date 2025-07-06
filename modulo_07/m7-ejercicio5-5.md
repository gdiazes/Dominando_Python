# Módulo 7: Ejercicio 5 (Dificultad 6.08/10) - Suma de Elementos de una Lista Numérica

## Enunciado del Problema

1.  Crea una lista llamada `puntuaciones` que contenga al menos 5 puntuaciones numéricas (enteros o flotantes).
2.  Calcula la suma total de todas las puntuaciones en la lista. Puedes usar un bucle `for` y un acumulador, o una función incorporada si la conoces.
3.  Imprime la suma total.

## Código con Errores

```python
# Ejercicio: Suma de elementos de una lista numérica

puntuaciones = [10, 25, 15.5, 30, 20]
suma_total = "0" # Error 1

for puntaje in puntuaciones:
    suma_total = suma_total + str(puntaje) # Error 2

print(f"La suma total de las puntuaciones es: {suma_total}")
# Error 3: El tipo de dato de suma_total al final, ¿permitirá futuros cálculos matemáticos
# si fueran necesarios, o es solo para visualización?
# Y si las puntuaciones fueran todas cadenas, ¿qué haría el '+'?
# Para el error:
if suma_total > 100:
    print("Suma muy alta!")
