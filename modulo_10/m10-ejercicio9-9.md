# Módulo 10: Ejercicio 9 (Dificultad 12.69/10) - Función para Contar Vocales en un Texto

## Enunciado del Problema

1.  Define una función `contar_vocales` que acepte una cadena de texto como parámetro.
2.  La función debe ser insensible a mayúsculas/minúsculas.
3.  Debe devolver el número total de vocales (a, e, i, o, u) en el texto.
4.  Prueba la función con una frase de tu elección.

## Código con Errores

```python
# Ejercicio: Función para contar vocales en un texto

def contar_vocales(texto):
    vocales = "aeiou"
    contador = 0
    for caracter in texto:
        if caracter in vocales:
            contador += 1
    # Error 1: La función no devuelve el contador.

texto_de_prueba = "Esto Es Una Frase De Prueba"
# Error 2: El conteo es sensible a mayúsculas y minúsculas tal como está
# llamado aquí, aunque la función en sí lo podría manejar.
# El error está en no aplicar la conversión a minúsculas.
numero_vocales = contar_vocales(texto_de_prueba.lower)

print(f"La frase '{texto_de_prueba}' tiene {numero_vocales} vocales.")

# Error 3: Definición incorrecta de la función
# def contar_vocales(texto, contador=0):
#     # ...
#     return contador
```
