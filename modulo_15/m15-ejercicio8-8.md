# Módulo 15: Ejercicio 8 (Dificultad 14/10) - Llamar al Constructor del Padre con `super()`

## Enunciado del Problema

1.  Usa la clase `Vehiculo` del ejercicio anterior.
2.  Crea una clase hija `Bicicleta` que herede de `Vehiculo`.
3.  El constructor de `Bicicleta` debe aceptar `velocidad_maxima` y un atributo adicional, `tipo` (ej: "Montaña", "Carrera").
4.  Dentro del constructor de `Bicicleta`, usa `super().__init__()` para llamar al constructor de `Vehiculo` y así inicializar `velocidad_maxima`.
5.  Crea un objeto `Bicicleta` y muestra todos sus atributos.

## Código con Errores

```python
# Ejercicio: Llamar al constructor del padre con super()

class Vehiculo:
    def __init__(self, velocidad_maxima):
        self.velocidad_maxima = velocidad_maxima

class Bicicleta(Vehiculo):
    def __init__(self, tipo, velocidad_maxima):
        # Error 1: 'super' es una función que necesita ser llamada
        super.__init__(velocidad_maxima)
        self.tipo = tipo

# Crear objeto
mi_bici = Bicicleta("Montaña", 30)

print(f"Tipo de bicicleta: {mi_bici.tipo}")
print(f"Velocidad Máxima: {velocidad_maxima}") # Error 2

# Error 3: Llamada incorrecta al constructor del padre
# class Moto(Vehiculo):
#     def __init__(self, cilindrada, velocidad_maxima):
#         Vehiculo.__init__(velocidad_maxima)
#         self.cilindrada = cilindrada
```
