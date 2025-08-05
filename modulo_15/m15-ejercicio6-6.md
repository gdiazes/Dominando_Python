# Módulo 15: Ejercicio 6 (Dificultad 10.77/10) - Usar un Objeto como Atributo de Otro (Composición)

## Enunciado del Problema

1.  Define una clase `Motor` con un atributo `cilindrada` (ej: 2.0).
2.  Define una clase `Coche`. El constructor de `Coche` debe aceptar `marca`, `modelo` y un objeto `Motor`.
3.  Dentro del constructor de `Coche`, asigna estos valores a los atributos, incluyendo el objeto motor.
4.  La clase `Coche` debe tener un método `mostrar_detalles()` que imprima la marca, el modelo y la cilindrada de su motor.
5.  Crea un objeto `Motor`, luego crea un objeto `Coche` pasándole el motor, y finalmente llama a `mostrar_detalles()`.

## Código con Errores

```python
# Ejercicio: Usar un objeto como atributo de otro (Composición)

class Motor:
    def __init__(self, cilindrada):
        self.cilindrada = cilindrada

class Coche:
    def __init__(self, marca, modelo, Motor): # Error 1
        self.marca = marca
        self.modelo = modelo
        self.motor = Motor

    def mostrar_detalles(self):
        print(f"Coche: {self.marca} {self.modelo}")
        print(f"Motor - Cilindrada: {motor.cilindrada}") # Error 2

# Crear los objetos
motor_v8 = Motor(5.0)
mi_coche_potente = Coche("Ford", "Mustang", motor_v8)

mi_coche_potente.mostrar_detalles()

# Error 3: Intento de acceder a un atributo del motor directamente desde el coche de forma incorrecta
# print(mi_coche_potente.cilindrada)
```
