# Módulo 7: Ejercicio 3 (Dificultad 3.65/10) - Añadir y Eliminar Elementos de una Lista

## Enunciado del Problema

1.  Crea una lista vacía llamada `tareas_pendientes`.
2.  Añade tres tareas (cadenas de texto) a la lista usando el método `.append()`.
3.  Imprime la lista de tareas.
4.  Simula que completaste la primera tarea: elimínala de la lista usando su índice.
5.  Añade una nueva tarea al inicio de la lista usando `.insert()`.
6.  Imprime la lista final de tareas.

## Código con Errores

```python
# Ejercicio: Añadir y eliminar elementos de una lista

tareas_pendientes = () # Error 1

tareas_pendientes.append = "Lavar platos"
tareas_pendientes.append("Sacar la basura")
tareas_pendientes.append("Estudiar Python")

print("Tareas iniciales:", tareas_pendientes)

del tareas_pendientes[0] # Esta línea es correcta si tareas_pendientes es una lista

tareas_pendientes.insert("Comprar pan", 0) # Error 2

print("Tareas finales:", tareas_pendientes.pop(tareas_pendientes)) # Error 3
