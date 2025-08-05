# Módulo 15: Ejercicio 2 (Dificultad 3.59/10) - Crear una Clase con Constructor `__init__()` (Libro)

## Enunciado del Problema

1.  Define una clase `Libro`.
2.  En el constructor `__init__`, la clase debe aceptar dos argumentos: `titulo` y `autor`.
3.  Dentro del constructor, asigna estos argumentos a los atributos del objeto: `self.titulo` y `self.autor`.
4.  Crea un objeto de la clase `Libro` con un título y autor de tu elección.
5.  Imprime el título y el autor del objeto que creaste.

## Código con Errores

```python
# Ejercicio: Crear una clase con constructor __init__()

class Libro:
    def __init__(titulo, autor): # Error 1
        titulo = titulo
        self.autor = autor

# Crear un objeto
mi_libro = Libro("El Quijote", "Miguel de Cervantes")

# Imprimir atributos
print(f"Título: {mi_libro.titulo}") # Error 2
print(f"Autor: {mi_libro.autor}")
# Error 3: Intento de acceder a un atributo no definido en el constructor
# print(f"Año: {mi_libro.anio}")
```
