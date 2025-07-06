# Módulo 6: Ejercicio 7 (Dificultad 8.09/10) - Dibujar un Rectángulo de Asteriscos con Bucles Anidados `for`

## Enunciado del Problema

Solicita al usuario dos números enteros: `ancho` y `alto`.
El programa debe dibujar un rectángulo relleno de asteriscos `*` con las dimensiones `alto` (número de filas) y `ancho` (número de asteriscos por fila).

Ejemplo (si alto=3 y ancho=5):
```
*****
*****
*****
```

## Código con Errores

```python
# Ejercicio: Dibujar un rectángulo de asteriscos

alto_str = input("Ingresa el alto del rectángulo: ")
alto = int(alto_str)
ancho_str = input("Ingresa el ancho del rectángulo: ")
ancho = int(ancho_str)

if alto > 0 and ancho > 0:
    for i in range(alto) # Pista 1
        linea = ""
        for j in range(ancho):
            linea = "*" # Pista 2
        print(linea) # Pista 3
else:
    print("El alto y el ancho deben ser números positivos.")
```
