# Módulo 8: Ejercicio 10 (Dificultad 12.8/10) - Tuplas Anidadas (Coordenadas de un Polígono)

## Enunciado del Problema

Un polígono simple (como un triángulo) puede ser representado por una tupla de sus vértices, donde cada vértice es a su vez una tupla de coordenadas (x, y).
1.  Crea una tupla `triangulo` que contenga tres tuplas, cada una representando un vértice: `(1, 1)`, `(4, 5)`, `(7, 1)`.
2.  Imprime la tupla completa del triángulo.
3.  Accede e imprime las coordenadas del segundo vértice.
4.  Calcula e imprime la coordenada 'x' del primer vértice y la coordenada 'y' del tercer vértice.
5.  Itera sobre la tupla `triangulo` para imprimir cada vértice en un formato amigable.

## Código con Errores

```python
# Ejercicio: Tuplas anidadas para representar un polígono

# Crear la tupla de vértices
triangulo = {(1, 1), (4, 5), (7, 1)} # Error 1

print(f"Vértices del triángulo: {triangulo}")

# Acceder al segundo vértice
segundo_vertice = triangulo(1) # Error 2
print(f"Segundo vértice: {segundo_vertice}")

# Acceder a coordenadas específicas
coord_x_primer_vertice = triangulo[0][0]
coord_y_tercer_vertice = triangulo[2][1]

# Iterar e imprimir
print("\nCoordenadas de cada vértice:")
for vertice in triangulo:
    x, y = vertice
    print("Vértice en (x={x}, y={y})") # Error 3
```
