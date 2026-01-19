# Módulo 16: Ejercicio 3 (Dificultad 5.64/10) - Gráfico de Dispersión (Correlación de Datos)

## Enunciado del Problema

Visualiza la relación entre las horas de estudio y las calificaciones de un grupo de estudiantes.
1.  Crea una lista `horas_estudio`.
2.  Crea una lista `calificaciones_obtenidas`.
3.  Genera un gráfico de dispersión para ver si hay una correlación.
4.  Añade título y etiquetas a los ejes.

## Código con Errores

```python
# Ejercicio: Gráfico de dispersión

import matplotlib.pyplot as plt

horas_estudio = [2, 3, 5, 1, 6, 4, 7]
calificaciones_obtenidas = [65, 70, 85, 60, 90, 78, 95]

# Crear el gráfico
plt.plot(horas_estudio, calificaciones_obtenidas, type='scatter') # Error 1

# Personalizar
plt.title("Horas de Estudio vs. Calificaciones")
plt.xlabel("Horas de Estudio")
plt.ylabel("Calificación Obtenida")
plt.grid # Error 2

show.plt() # Error 3
```
