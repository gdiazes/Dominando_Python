# Módulo 10: Ejercicio 4 (Dificultad 5.64/10) - Función con Valor por Defecto

## Enunciado del Problema

1.  Define una función llamada `mostrar_mensaje` que acepte dos parámetros: `mensaje` y `veces`.
2.  El parámetro `veces` debe tener un valor por defecto de 1.
3.  La función debe usar un bucle `for` para imprimir el `mensaje` el número de `veces` especificado.
4.  Llama a la función de dos maneras:
    *   Una vez solo con el argumento del mensaje, para que use el valor por defecto de `veces`.
    *   Otra vez con el mensaje y especificando un número de veces (ej: 3).

## Código con Errores

```python
# Ejercicio: Función con valor por defecto

def mostrar_mensaje(mensaje="Hola", veces): # Error 1
    for _ in range(veces):
        print(mensaje)

# Llamada con valor por defecto
mostrar_mensaje("Este es un mensaje de prueba.")

# Llamada especificando 'veces'
mostrar_mensaje("Repitiendo", 3)
# Error 2: El código anterior funciona, pero el error puede ser conceptual.
# ¿Qué pasaría si intentas llamar así?: mostrar_mensaje(veces=3)

# Error 3: Definición incorrecta de otra función con valor por defecto
# def otra_funcion(veces=veces, mensaje):
#     print(mensaje * veces)
```
