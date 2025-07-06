# Módulo 6: Ejercicio 6 (Dificultad 6.93/10) - Tabla de Multiplicar Completa (1 al N) usando Bucles Anidados `for`

## Enunciado del Problema

Solicita al usuario un número entero `N` (por ejemplo, 5).
El programa debe generar y mostrar las tablas de multiplicar desde el 1 hasta `N`.
Cada tabla individual debe ir del 1 al 10.
Separa cada tabla con una línea de guiones o un mensaje claro.

Ejemplo (si N=2):
```
--- Tabla del 1 ---
1 x 1 = 1
1 x 2 = 2
...
1 x 10 = 10
--- Tabla del 2 ---
2 x 1 = 2
2 x 2 = 4
...
2 x 10 = 20
```

## Código con Errores

```python
# Ejercicio: Tablas de multiplicar completas (1 al N)

limite_tablas_str = input("¿Hasta qué número quieres generar las tablas? ")
limite_tablas = int(limite_tablas_str)

for tabla_actual in range(1, limite_tablas): # Pista 1
    print(f"\n--- Tabla del {tabla_actual} ---")
    for i in range(1, 11) # Pista 2
        resultado = tabla_actual * i
        print(f"{tabla_actual} x {i} = {resultado}")
    # Pista 3: Si 'limite_tablas' es 1, ¿se imprime alguna tabla con el rango actual del bucle externo?
```
