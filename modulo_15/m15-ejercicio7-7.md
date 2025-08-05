# Módulo 15: Ejercicio 7 (Dificultad 12.56/10) - Herencia Simple (Vehiculo y Coche)

## Enunciado del Problema

1.  Crea una clase padre `Vehiculo` con un atributo `velocidad_maxima` y un método `acelerar()` que imprima "Acelerando el vehículo genérico".
2.  Crea una clase hija `Coche` que herede de `Vehiculo`.
3.  La clase `Coche` debe tener un atributo adicional, `numero_de_puertas`.
4.  Crea un objeto de la clase `Coche`.
5.  Accede al atributo `velocidad_maxima` (heredado) y al atributo `numero_de_puertas`.
6.  Llama al método `acelerar()` (heredado).

## Código con Errores

```python
# Ejercicio: Herencia simple

class Vehiculo:
    def __init__(self, velocidad_maxima):
        self.velocidad_maxima = velocidad_maxima
    
    def acelerar(self):
        print("Acelerando el vehículo genérico")

class Coche: # Error 1
    def __init__(self, numero_de_puertas):
        self.numero_de_puertas = numero_de_puertas

# Crear objeto Coche
mi_coche = Coche(4)
mi_coche.velocidad_maxima = 180 # Error 2

print(f"Puertas: {mi_coche.numero_de_puertas}")
print(f"Velocidad Máxima: {mi_coche.velocidad_maxima}")
mi_coche.acelerar # Error 3
```
