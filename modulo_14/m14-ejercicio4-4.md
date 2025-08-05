# Módulo 14: Ejercicio 4 (Dificultad 6.84/10) - Leer un Archivo Línea por Línea

## Enunciado del Problema

Asumiendo que tienes un archivo `instrucciones.txt` con varias líneas.
Escribe un programa que lea el archivo línea por línea usando un bucle `for`.
Para cada línea leída, imprímela en la consola precedida por el número de línea (empezando en 1).

Ejemplo de salida (para un archivo con 3 líneas):
```
1: Primera instrucción.
2: Segunda instrucción.
3: Tercera instrucción.
```

## Código con Errores

```python
# Ejercicio: Leer un archivo línea por línea

# (Asegúrate de tener un archivo 'instrucciones.txt' con algunas líneas)

numero_linea = 1
with open("instrucciones.txt", "r") as f:
    for linea in f:
        print(f"{numero_linea}: {linea}") # Error 1
        numero_linea # Error 2
    
# Error 3: ¿Qué pasa con el objeto 'f' después de que el bucle 'for' ha terminado?
# ultima_linea = f.readline()
# print(f"Última línea leída de nuevo: {ultima_linea}")
