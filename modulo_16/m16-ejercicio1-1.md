# Módulo 16: Ejercicio 1 (Dificultad 1.88/10) - Gráfico de Líneas Simple (Evolución de Temperatura)

## Enunciado del Problema

Crea un gráfico de líneas que muestre la evolución de la temperatura a lo largo de una semana.
1.  Usa una lista para los días (ej: `[1, 2, 3, 4, 5, 6, 7]`).
2.  Usa otra lista para las temperaturas correspondientes (ej: `[22, 24, 23, 25, 26, 24, 27]`).
3.  Añade un título al gráfico y etiquetas para los ejes X e Y.
4.  Muestra el gráfico.

## Código con Errores

```python
# Ejercicio: Gráfico de líneas simple

import matplotlib.pyplot as plt

dias = [1, 2, 3, 4, 5, 6, 7]
temperaturas = [22, 24, 23, 25, 26, 24, 27]

# Crear el gráfico
plt.plot(dias) # Error 1

# Personalizar
plt.title("Evolución de la Temperatura")
plt.xlabel = "Día" # Error 2
plt.ylabel("Temperatura (°C)")

plt.show # Error 3
```
