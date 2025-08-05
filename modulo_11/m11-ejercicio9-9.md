# Módulo 11: Ejercicio 9 (Dificultad 13.32/10) - Procesador de Comandos con `*args` y `**kwargs`

## Enunciado del Problema (Práctica Calificada 3 - Parte B)

Define una función `ejecutar_comando` que simule la ejecución de un comando del sistema. Debe aceptar:
-   `comando`: El comando principal a ejecutar (cadena).
-   `*argumentos`: Argumentos adicionales para el comando (cadenas).
-   `**opciones`: Opciones de configuración para la ejecución (booleanos, como `sudo=True` o `verbose=False`).

La función debe construir y devolver una cadena que represente el comando completo que se ejecutaría.
-   Si `sudo=True` está en las opciones, la cadena debe empezar con "sudo ".
-   Luego el comando principal.
-   Luego todos los `*argumentos` separados por espacios.
-   Finalmente, si `verbose=True`, debe añadir " --verbose" al final.

## Código con Errores

```python
# Ejercicio: Procesador de comandos con *args y **kwargs

def ejecutar_comando(comando, *argumentos, **opciones):
    comando_final = ""
    
    if opciones.get(sudo): # Error 1
        comando_final += "sudo "
        
    comando_final += comando
    
    # Unir argumentos
    comando_final += " " + " ".join(argumentos)
    
    # Añadir opciones
    if opciones["verbose"] == True: # Error 2
        comando_final += " --verbose"
        
    return comando_final

# Prueba
comando_generado = ejecutar_comando("ls", "-l", "/home", sudo=True, verbose=true) # Error 3
print(f"Comando a ejecutar: '{comando_generado}'")
```
