# Módulo 15: Ejercicio 4 (Dificultad 7.18/10) - Crear Múltiples Objetos de una Clase (Estudiante)

## Enunciado del Problema

1.  Define una clase `Estudiante` con un constructor que acepte `nombre` y `id_estudiante`.
2.  La clase debe tener un método `presentarse()` que imprima "Hola, mi nombre es [nombre] y mi ID es [id_estudiante]".
3.  Crea una lista vacía llamada `lista_estudiantes`.
4.  Crea tres objetos diferentes de la clase `Estudiante` y añádelos a la lista `lista_estudiantes`.
5.  Usa un bucle `for` para iterar sobre la `lista_estudiantes` y llama al método `presentarse()` de cada estudiante.

## Código con Errores

```python
# Ejercicio: Crear múltiples objetos de una clase

class Estudiante:
    def __init__(self, nombre, id_estudiante):
        self.nombre = nombre
        self.id = id_estudiante
    
    def presentarse(self):
        print(f"Hola, mi nombre es {nombre} y mi ID es {id}.") # Error 1

lista_estudiantes = []

est1 = Estudiante("Carlos", 101)
est2 = Estudiante("Laura", 102)
est3 = Estudiante("Pedro", 103)

lista_estudiantes.append[est1, est2, est3] # Error 2

for estudiante in lista_estudiantes:
    estudiante.presentarse # Error 3
```
