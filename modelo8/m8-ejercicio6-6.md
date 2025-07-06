# Módulo 8: Ejercicio 6 (Dificultad 7.68/10) - Métodos de Tupla (`.count()` y `.index()`)

## Enunciado del Problema

1.  Crea una tupla `calificaciones` con varias calificaciones numéricas, incluyendo algunas repetidas. Por ejemplo: `(10, 8, 9, 7, 8, 10, 8)`.
2.  Solicita al usuario una calificación para contar.
3.  Usa el método `.count()` para contar cuántas veces aparece esa calificación. Imprime el resultado.
4.  Solicita al usuario una calificación para buscar su primera aparición.
5.  Usa el método `.index()` para encontrar el índice de la primera vez que aparece esa calificación. Imprime el resultado.

## Código con Errores

```python
# Ejercicio: Métodos de tupla .count() y .index()

calificaciones = (10, 8, 9, 7, 8, 10, 8)

# Contar una calificación
calificacion_a_contar_str = input("Ingresa la calificación a contar: ")
calificacion_a_contar = int(calificacion_a_contar_str)
conteo = calificaciones.count[calificacion_a_contar] # Error 1
print(f"La calificación {calificacion_a_contar} aparece {conteo} veces.")

# Buscar el índice de una calificación
calificacion_a_buscar_str = input("Ingresa la calificación a buscar: ")
calificacion_a_buscar = int(calificacion_a_buscar_str)
indice = calificaciones.index(calificacion_a_buscar, 1) # Error 2

print(f"La primera aparición de {calificacion_a_buscar} está en el índice {indice}.")

# Error 3: Intento de buscar un elemento que no existe, para ver el error
# (comentado para que el script no se detenga)
# indice_no_existente = calificaciones.index(5)
# print(f"Índice de 5: {indice_no_existente}")
```
