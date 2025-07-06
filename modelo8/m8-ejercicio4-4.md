# Módulo 8: Ejercicio 4 (Dificultad 5.12/10) - Tupla con un Solo Elemento

## Enunciado del Problema

El objetivo de este ejercicio es entender la sintaxis especial para crear una tupla con un solo elemento.
1.  Crea una variable `numero_como_tupla` que contenga el número `100` como el único elemento de una tupla.
2.  Crea una variable `numero_normal` que contenga el número `100` pero usando paréntesis de una forma que NO cree una tupla.
3.  Imprime el tipo de ambas variables usando `type()` para ver la diferencia.

## Código con Errores

```python
# Ejercicio: Tupla con un solo elemento

# Crear una tupla con un solo elemento
numero_como_tupla = (100) # Error 1

# Crear una variable que parece una tupla pero no lo es
numero_normal = 100, # Error 2

print(f"Valor de numero_como_tupla: {numero_como_tupla}")
print(f"Tipo de numero_como_tupla: {type(numero_como_tupla)}")

print(f"Valor de numero_normal: {numero_normal}")
print(f"Tipo de numero_normal: {tipo(numero_normal)}") # Error 3
```
