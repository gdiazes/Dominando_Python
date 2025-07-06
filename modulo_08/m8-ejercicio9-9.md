# Módulo 8: Ejercicio 9 (Dificultad 11.52/10) - Uso de Tuplas para Devolver Múltiples Valores de una "Función Simulada"

## Enunciado del Problema

Imagina que tienes una función que analiza un texto y devuelve varias métricas. Para simular esto:
1.  Crea una cadena de texto, `texto_analizar`.
2.  "Calcula" tres métricas:
    *   La longitud total del texto (`len()`).
    *   El número de palabras (puedes simularlo contando los espacios y sumando 1, o usando `.split()` que devuelve una lista de palabras).
    *   El número de veces que aparece la letra 'a' (insensible a mayúsculas).
3.  Almacena estas tres métricas en una sola tupla llamada `resultados_analisis`.
4.  Desempaqueta la tupla `resultados_analisis` en tres variables separadas: `longitud`, `num_palabras`, y `conteo_a`.
5.  Imprime las tres métricas.

## Código con Errores

```python
# Ejercicio: Tuplas para devolver múltiples valores simulados

texto_analizar = "Python es un lenguaje de programacion versatil"

# "Calcular" métricas
longitud = len(texto_analizar)
palabras = texto_analizar.split( ) # Esto devuelve una lista de palabras
num_palabras = len(palabras)
conteo_a = texto_analizar.count('a') # Error 1

# Almacenar en una tupla
resultados_analisis = (longitud, num_palabras, conteo_a)

# Desempaquetar
longitud, num_palabras = resultados_analisis # Error 2

print(f"Longitud del texto: {longitud}")
print(f"Número de palabras: {num_palabras}")
print(f"Número de 'a's: {conteo_a}") # Error 3
```
