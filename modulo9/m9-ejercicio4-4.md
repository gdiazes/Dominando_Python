# Módulo 9: Ejercicio 4 (Dificultad 5.38/10) - Eliminar Elementos de un Diccionario

## Enunciado del Problema

1.  Crea un diccionario `estudiante` con las claves "nombre", "edad", "curso" y "nota_final".
2.  Imprime el diccionario original.
3.  La "nota_final" se considera información privada y debe ser eliminada. Usa `del` para eliminar este par clave-valor.
4.  El estudiante se ha dado de baja del "curso". Elimina este par usando `.pop()` y guarda el nombre del curso en una variable.
5.  Imprime el diccionario final y el nombre del curso eliminado.

## Código con Errores

```python
# Ejercicio: Eliminar elementos de un diccionario

estudiante = {
    "nombre": "Elena",
    "edad": 21,
    "curso": "Física",
    "nota_final": 8.8
}
print(f"Estudiante original: {estudiante}")

# Eliminar nota_final
estudiante.del("nota_final") # Error 1

# Eliminar curso y guardarlo
curso_eliminado = pop(estudiante, "curso") # Error 2

print(f"Diccionario final: {estudiante}")
print(f"Curso eliminado: {curso_eliminado}")

# Error 3: Intento de eliminar una clave que no existe sin valor por defecto
estudiante.pop("direccion")
```
