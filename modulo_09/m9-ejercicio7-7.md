# Módulo 9: Ejercicio 7 (Dificultad 9.41/10) - Contador de Frecuencia de Palabras

## Enunciado del Problema

1.  Se te da una cadena de texto (una frase).
2.  Crea un diccionario para contar la frecuencia de cada palabra en la frase.
3.  Primero, convierte la frase a minúsculas y divídela en una lista de palabras.
4.  Itera sobre la lista de palabras. Para cada palabra:
    *   Si la palabra ya está en el diccionario de frecuencias, incrementa su contador.
    *   Si no está, añádela al diccionario con un contador de 1.
5.  Imprime el diccionario de frecuencias resultante.

## Código con Errores

```python
# Ejercicio: Contador de frecuencia de palabras

frase = "La casa es grande y la puerta de la casa es roja"
palabras = frase.lower().split()

frecuencias = {} # Diccionario para almacenar las frecuencias

for palabra in palabras:
    if frecuencias.get(palabra):
        frecuencias[palabra] =+ 1 # Error 1
    else:
        frecuencias.add(palabra, 1) # Error 2

print("Frecuencia de palabras:")
print(frecuencias)

# Error 3: Intento de acceder a una frecuencia de una palabra que podría no estar, de forma insegura.
# print(f"Frecuencia de 'techo': {frecuencias['techo']}")
```
