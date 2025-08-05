# Módulo 11: Ejercicio 2 (Dificultad 2.96/10) - Concatenador de Cadenas con `*args`

## Enunciado del Problema

Define una función `unir_palabras` que acepte un número variable de cadenas de texto.
La función debe unirlas todas en una sola frase, separadas por un espacio.
Si no se pasa ninguna palabra, debe devolver una cadena vacía.

Ejemplo: `unir_palabras("Hola", "mundo", "Python")` debe devolver `"Hola mundo Python"`.

## Código con Errores

```python
# Ejercicio: Concatenador de cadenas con *args

def unir_palabras(*palabras):
    if not palabras:
        return ""
    
    frase_completa = ""
    for palabra in *palabras: # Error 1
        frase_completa = palabra + " " # Error 2
    
    return frase_completa.strip() # .strip() es correcto para quitar el último espacio

# Prueba
resultado = unir_palabras("Python", "es", "genial")
print(resultado)
# Error 3: El resultado de la prueba será incorrecto debido a la lógica de concatenación.
```
