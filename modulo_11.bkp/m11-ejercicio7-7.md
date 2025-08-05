# Módulo 11: Ejercicio 7 (Dificultad 10.36/10) - Uso de `filter` con Lambda para Filtrar Nombres Cortos

## Enunciado del Problema

1.  Se te da una lista de nombres: `["Ana", "Cristóbal", "Eva", "Luis", "Alejandro"]`.
2.  Usa la función `filter()` y una función `lambda` para crear una nueva lista que contenga solo los nombres que tienen más de 4 caracteres.
3.  Imprime la lista filtrada.

## Código con Errores

```python
# Ejercicio: Uso de filter con lambda para filtrar nombres cortos

nombres = ["Ana", "Cristóbal", "Eva", "Luis", "Alejandro"]

# Filtrar nombres
filtro_nombres = filter(lambda nombre: len(nombre > 4), nombres) # Error 1

nombres_largos = list(filtro_nombres)
print(f"Nombres largos: {nombres_largos}")

# Error 2: La lambda no devuelve un booleano explícito
# nombres_largos_alt = list(filter(lambda x: len(x), nombres))

# Error 3: Sintaxis incorrecta de filter
# nombres_largos_alt2 = filter(nombres, len(nombre) > 4)
```
