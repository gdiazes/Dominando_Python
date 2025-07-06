# Módulo 8: Ejercicio 2 (Dificultad 2.56/10) - Intento de Modificación de una Tupla

## Enunciado del Problema

1.  Crea una tupla llamada `constantes_matematicas` con los valores `3.14159` (Pi) y `2.71828` (e).
2.  Imprime la tupla original.
3.  Intenta modificar el primer elemento de la tupla para que sea `3.14`.
4.  Intenta añadir un nuevo elemento (el número de oro, `1.618`) a la tupla.
5.  Los intentos de modificación causarán errores. El objetivo del ejercicio es reconocer por qué fallan, por lo que el código con errores las incluirá (comentadas para que el script no se detenga).

## Código con Errores

```python
# Ejercicio: Intento de modificación de una tupla

constantes_matematicas = (3.14159, 2.71828)
print(f"Original: {constantes_matematicas}")

# Intento de modificación (causará TypeError)
constantes_matematicas(0) = 3.14 # Error 1

# Intento de añadir (causará AttributeError)
constantes_matematicas.append(1.618) # Error 2

# Error 3: El siguiente código intenta "solucionar" el problema de una manera incorrecta.
constantes_matematicas + (1.618)
print(f"Tupla 'modificada': {constantes_matematicas}")
```
