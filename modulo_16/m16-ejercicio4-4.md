# Módulo 16: Ejercicio 4 (Dificultad 7.52/10) - Histograma de Datos Aleatorios

## Enunciado del Problema

Crea un histograma para visualizar la distribución de 200 edades generadas aleatoriamente entre 18 y 65 años.
1.  Importa el módulo `random`.
2.  Genera una lista de 200 edades aleatorias.
3.  Crea un histograma de estas edades con 10 `bins`.
4.  Añade título y etiquetas a los ejes.

## Código con Errores

```python
# Ejercicio: Histograma de datos aleatorios

import matplotlib.pyplot as plt
import random

# Generar datos
edades = []
for _ in range(200):
    edades.append(random.rand(18, 65)) # Error 1

# Crear el histograma
plt.histogram(edades, bins=10) # Error 2

# Personalizar
plt.title("Distribución de Edades")
plt.xlabel("Edad")
plt.ylabel("Frecuencia")

plt.show()

# Error 3 (conceptual): ¿Qué pasaría si se usa plt.bar en lugar de plt.hist?
# El gráfico no representaría la distribución de frecuencia correctamente.
```
