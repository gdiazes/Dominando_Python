# Módulo 8: Ejercicio 7 (Dificultad 8.96/10) - Concatenar Tuplas para "Añadir" un Elemento

## Enunciado del Problema

1.  Crea una tupla inicial llamada `mi_ruta` que contenga dos ciudades (cadenas), por ejemplo: `("París", "Berlín")`.
2.  Imprime la ruta inicial.
3.  El usuario ingresará una nueva ciudad para añadir al final de la ruta.
4.  Crea una *nueva* tupla llamada `ruta_actualizada` que sea el resultado de "añadir" la nueva ciudad a la tupla `mi_ruta`.
5.  Imprime tanto la tupla original (para demostrar que no cambió) como la tupla actualizada.

## Código con Errores

```python
# Ejercicio: Concatenar tuplas para "añadir" un elemento

mi_ruta = ("París", "Berlín")
print(f"Ruta inicial: {mi_ruta}")

nueva_ciudad = input("Ingresa la siguiente ciudad en la ruta: ")

# "Añadir" la nueva ciudad
ruta_actualizada = mi_ruta + nueva_ciudad # Error 1
ruta_actualizada_2 = mi_ruta + (nueva_ciudad) # Error 2

print(f"Ruta original no cambió: {mi_ruta}")
print(f"Ruta actualizada: {ruta_actualizada}")

# Error 3: El siguiente código intenta demostrar la inmutabilidad de forma incorrecta
# mi_ruta[2] = nueva_ciudad
```
