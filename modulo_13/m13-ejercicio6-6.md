# Módulo 13: Ejercicio 6 (Dificultad 9.77/10) - Estructura de Módulo con `if __name__ == "__main__"`

## Enunciado del Problema

Crea dos archivos: `utilidades_texto.py` y `main.py`.
1.  En `utilidades_texto.py`, define una función `contar_palabras(texto)` que devuelva el número de palabras en un texto.
2.  En `utilidades_texto.py`, añade un bloque `if __name__ == "__main__":` que ejecute una pequeña prueba para tu función `contar_palabras`. Por ejemplo, probarla con una frase y verificar que el resultado es el esperado.
3.  En `main.py`, importa y usa la función `contar_palabras` con un texto diferente.
4.  Ejecuta ambos archivos por separado y observa la diferencia en la salida.

## Código con Errores

**Archivo: `utilidades_texto.py`**
```python
# Contenido de utilidades_texto.py

def contar_palabras(texto):
    palabras = texto.split()
    return len(palabras)

# Bloque de prueba
if _name_ == "_main_": # Error 1
    frase_prueba = "Esta es una frase de prueba."
    conteo_esperado = 5
    conteo_real = contar_palabras(frase_prueba)
    assert conteo_real = conteo_esperado # Error 2
    print("Prueba de contar_palabras pasada.")
```

**Archivo: `main.py`**
```python
# Contenido de main.py

import utilidades_texto as ut

mi_texto = "Este es el texto que se usa en el programa principal."
num_palabras = ut.contar_palabras(mi_texto)

print(f"El texto tiene {num_palabras} palabras.")

# Error 3: Intento de llamar a una variable local del bloque __main__ del otro módulo
# print(ut.frase_prueba)
