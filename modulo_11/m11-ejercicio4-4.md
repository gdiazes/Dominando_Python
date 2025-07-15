# Módulo 11: Ejercicio 4 (Dificultad 5.92/10) - Función Completa con Argumentos Mixtos

## Enunciado del Problema

Define una función `procesar_datos` que acepte:
-   Un argumento posicional obligatorio `id_proceso`.
-   Un número variable de argumentos posicionales `*mediciones`.
-   Un argumento de palabra clave `estado` con valor por defecto "PENDIENTE".
-   Un número variable de argumentos de palabra clave `**metadata`.

La función debe imprimir toda la información recibida de forma estructurada.

## Código con Errores

```python
# Ejercicio: Función con argumentos mixtos

def procesar_datos(id_proceso, **metadata, *mediciones, estado="PENDIENTE"): # Error 1
    print(f"ID del Proceso: {id_proceso}")
    print(f"Estado: {estado}")
    
    print("Mediciones:")
    for medicion in mediciones:
        print(f" - {medicion}")
    
    print("Metadata:")
    if metadata:
        for k, v in metadata.items: # Error 2
            print(f" - {k}: {v}")
    else:
        print(" - Sin metadata.")

# Prueba
procesar_datos(101, 12.5, 13.1, 11.9, estado="COMPLETADO", responsable="Ana", equipo="A")
# Error 3: La llamada anterior fallará debido al orden incorrecto en la definición de la función.
