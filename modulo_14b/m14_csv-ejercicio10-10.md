# Módulo 14 (CSV): Ejercicio 10 (Dificultad 11.0/10) - Mini-Proyecto: Convertir CSV a una Lista de Objetos

## Enunciado del Problema

Combina los conceptos de POO (Módulo 15) y manejo de CSV.
1.  Define una clase `Empleado` con atributos `id`, `nombre` y `puesto`.
2.  Tienes un archivo `empleados.csv` con las columnas `id`, `nombre`, `puesto`.
3.  Escribe un programa que lea el archivo `empleados.csv` y, para cada fila, cree un objeto de la clase `Empleado`.
4.  Almacena todos los objetos `Empleado` creados en una lista.
5.  Finalmente, itera sobre la lista de objetos e imprime la información de cada empleado usando un método de la clase.

## Código con Errores

```python
# Ejercicio: Convertir CSV a una lista de objetos

import csv

class Empleado:
    def __init__(self, id, nombre, puesto):
        self.id = id
        self.nombre = nombre
        self.puesto = puesto
    
    def mostrar_info(self):
        print(f"ID: {self.id}, Nombre: {self.nombre}, Puesto: {self.puesto}")

# (Asegúrate de tener un archivo 'empleados.csv' apropiado)

lista_empleados = []
with open('empleados.csv', 'r', newline='') as f:
    lector = csv.DictReader(f)
    for fila in lector:
        nuevo_empleado = Empleado(fila) # Error 1
        lista_empleados.append(nuevo_empleado)
        
print("--- Lista de Empleados ---")
for empleado in lista_empleados:
    empleado.mostrar_info() # Error 2

# Error 3: ¿Qué pasaría si el CSV tuviera columnas con nombres diferentes
# a los parámetros del constructor __init__?
