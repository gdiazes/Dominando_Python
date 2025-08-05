# Módulo 15: Ejercicio 10 (Dificultad  17/10) - Mini-Proyecto POO: Figuras Geométricas

## Enunciado del Problema

Crea una estructura de clases para representar figuras geométricas.
1.  Crea una clase padre `Figura` con un método `area()` que simplemente devuelva `0` (ya que una figura genérica no tiene área).
2.  Crea una clase hija `Rectangulo` que herede de `Figura`. Su constructor debe aceptar `base` y `altura`. Sobrescribe el método `area()` para que devuelva el área correcta (`base * altura`).
3.  Crea una clase hija `Circulo` que herede de `Figura`. Su constructor debe aceptar `radio`. Sobrescribe el método `area()` para que devuelva el área correcta (`pi * radio²`). Puedes usar `3.14159` para `pi`.
4.  Crea un objeto de cada clase (`Rectangulo` y `Circulo`) y muestra sus áreas.

## Código con Errores

```python
# Ejercicio: Mini-proyecto POO de figuras geométricas

PI = 3.14159

class Figura:
    def area():
        return 0

class Rectangulo(Figura):
    def __init__(self, base, altura):
        self.base = base
        self.altura = altura
    
    def area(self):
        return self.base * self.altura

class Circulo(Figura):
    def __init__(self, radio):
        self.radio = radio
    
    def area(self):
        return PI * self.radio # Error 1

# Crear objetos
mi_rectangulo = Rectangulo(10, 5)
mi_circulo = Circulo(radio=7)

# Calcular y mostrar áreas
area_rect = mi_rectangulo.area # Error 2
area_circ = mi_circulo.area()

print(f"Área del rectángulo: {area_rect}")
print(f"Área del círculo: {area_circ}")

# Error 3: La clase Figura tiene un método 'area' sin 'self'
# figura_generica = Figura()
# figura_generica.area()
```
