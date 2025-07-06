# Módulo 8: Ejercicio 5 (Dificultad 6.4/10) - Iterar sobre una Tupla

## Enunciado del Problema

1.  Crea una tupla llamada `meses` que contenga los nombres de los primeros seis meses del año.
2.  Utiliza un bucle `for` para iterar sobre la tupla e imprimir cada mes.
3.  Dentro del mismo bucle, usa `enumerate()` para imprimir también el número del mes (empezando en 1, no en 0) junto con su nombre.

Ejemplo de salida:
```
Mes 1: Enero
Mes 2: Febrero
...
```

## Código con Errores

```python
# Ejercicio: Iterar sobre una tupla

meses = ("Enero", "Febrero", "Marzo", "Abril", "Mayo", "Junio")

for mes in meses:
    print(mes)

# Iterar con enumerate
for indice, mes in enumerate(meses) # Error 1
    numero_mes = indice + 1
    print("Mes {numero_mes}: {mes}") # Error 2

# Error 3: ¿Qué pasaría si intentamos iterar modificando el elemento?
# for mes in meses:
#     mes = mes.upper()
# print(meses) # El error es conceptual: la tupla original no cambiará.
```
