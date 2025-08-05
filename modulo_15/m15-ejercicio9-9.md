# Módulo 15: Ejercicio 9 (Dificultad 16.15/10) - Sobrescribir un Método del Padre

## Enunciado del Problema

1.  Crea una clase padre `Animal` con un método `hacer_sonido()` que imprima "El animal hace un sonido genérico".
2.  Crea dos clases hijas, `Perro` y `Gato`, que hereden de `Animal`.
3.  En la clase `Perro`, **sobrescribe** el método `hacer_sonido()` para que imprima "¡Guau!".
4.  En la clase `Gato`, **sobrescribe** el método `hacer_sonido()` para que imprima "¡Miau!".
5.  Crea un objeto de cada clase (un `Animal`, un `Perro`, un `Gato`) y llama al método `hacer_sonido()` de cada uno para ver el polimorfismo en acción.

## Código con Errores

```python
# Ejercicio: Sobrescribir un método del padre

class Animal:
    def hacer_sonido(self):
        print("El animal hace un sonido genérico")

class Perro(Animal):
    def hacer_sonido(self):
        super().hacer_sonido() # Error 1
        print("¡Guau!")

class Gato(Animal):
    def hacer_sonido(): # Error 2
        print("¡Miau!")
        
# Crear objetos
animal_generico = Animal()
mi_perro = Perro()
mi_gato = Gato()

# Llamar a los métodos
animal_generico.hacer_sonido()
mi_perro.hacer_sonido()
mi_gato.hacer_sonido() # Error 3
```
