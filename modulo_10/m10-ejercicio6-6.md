# Módulo 10: Ejercicio 6 (Dificultad 8.46/10) - Función para Calcular el Área de un Círculo

## Enunciado del Problema

1.  Define una función `calcular_area_circulo` que acepte un parámetro `radio`.
2.  Dentro de la función, define una variable local `pi` con el valor `3.14159`.
3.  La función debe calcular el área (área = pi * radio²) y devolverla.
4.  Fuera de la función, solicita un radio al usuario, llama a la función y muestra el área calculada, formateada a dos decimales.
5.  Intenta acceder a la variable `pi` fuera de la función para demostrar el alcance de las variables locales.

## Código con Errores

```python
# Ejercicio: Función para calcular el área de un círculo

def calcular_area_circulo(radio):
    pi = 3.14159
    area = pi * radio ** 2
    # Error 1: La función no devuelve el valor calculado

radio_usuario = float(input("Ingresa el radio del círculo: "))

area_calculada = calcular_area_circulo(radio_usuario)
print(f"El área del círculo es: {area_calculada:.2f}")

# Error 2: Intento de acceder a una variable local desde fuera de la función
print(f"El valor de pi usado fue: {pi}")

# Error 3: Llamada a la función de forma incorrecta
# area_calculada_2 = calcular_area_circulo(radio=radio_usuario, pi=3.14)
```
