# Módulo 8: Ejercicio 3 (Dificultad 3.84/10) - Desempaquetado de Tuplas

## Enunciado del Problema

1.  Una tupla `datos_vuelo` contiene la información de un vuelo: código del vuelo, origen y destino. Por ejemplo: `("IB304", "Madrid", "Londres")`.
2.  Desempaqueta esta tupla en tres variables separadas: `codigo`, `origen` y `destino`.
3.  Imprime cada una de estas variables.
4.  Luego, intenta desempaquetar la misma tupla en solo dos variables para ver el error que produce.

## Código con Errores

```python
# Ejercicio: Desempaquetado de tuplas

datos_vuelo = ("IB304", "Madrid", "Londres")

codigo, origen = datos_vuelo # Error 1

print(f"Código de vuelo: {codigo}")
print(f"Origen: {origen}")
print(f"Destino: {destino}") # Error 2

# Intento de desempaquetado en variables con nombres incorrectos
vuelo, ciudad_origen, ciudad_destino = ("IB304", "Madrid", "Londres")
print(f"Vuelo: {vuelo}, Origen: {origen}") # Error 3
```
