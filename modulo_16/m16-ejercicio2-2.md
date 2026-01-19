# Módulo 16: Ejercicio 2 (Dificultad 3.76/10) - Gráfico de Barras (Comparación de Poblaciones)

## Enunciado del Problema

Crea un gráfico de barras para comparar la población de tres ciudades.
1.  Usa una lista de cadenas para los nombres de las ciudades.
2.  Usa una lista de números para las poblaciones correspondientes.
3.  Añade un título y etiquetas a los ejes.
4.  Muestra el gráfico.

## Código con Errores

```python
# Ejercicio: Gráfico de barras

import matplotlib.pyplot as plt

ciudades = ["Lima", "Arequipa", "Trujillo"]
poblaciones = [9600000, 1100000, 1000000]

# Crear el gráfico
plt.barh(ciudades, poblaciones) # Error 1

# Personalizar
plt.Title("Población de Ciudades Peruanas") # Error 2
plt.xlabel("Ciudad")
plt.ylabel("Población (en millones)")

plt.show()

# Error 3: ¿Qué pasaría si el número de ciudades y poblaciones no coincide?
# ciudades_mal = ["Lima", "Arequipa"]
# poblaciones_mal = [9600000, 1100000, 1000000]
# plt.bar(ciudades_mal, poblaciones_mal) # Esto causaría un ValueError
```
