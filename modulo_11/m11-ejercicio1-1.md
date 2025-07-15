# Módulo 11: Ejercicio 1 (Dificultad 1.48/10) - Función Sumadora con `*args`

## Enunciado del Problema

Define una función llamada `sumar_numeros` que pueda aceptar cualquier cantidad de argumentos numéricos posicionales y devuelva su suma.
Prueba la función llamándola con 2, 3 y 5 argumentos.

## Código con Errores

```python
# Ejercicio: Función sumadora con *args

def sumar_numeros(args): # Error 1
    suma = 0
    for numero in args:
        suma + numero # Error 2
    return suma

# Pruebas de la función
print(sumar_numeros(1, 5)) # Error 3
print(sumar_numeros(10, 20, 30))
print(sumar_numeros(2, 3, 5, 8, 13))
```
