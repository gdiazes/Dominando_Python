# Módulo 10: Ejercicio 7 (Dificultad 9.87/10) - Función que Devuelve Múltiples Valores (usando una tupla)

## Enunciado del Problema

1.  Define una función `analizar_numeros` que acepte una lista de números como parámetro.
2.  Dentro de la función, calcula la suma, el promedio y el valor máximo de la lista. Puedes usar las funciones `sum()`, `len()` y `max()`.
3.  La función debe devolver estos tres valores (suma, promedio, máximo). La forma idiomática en Python es devolverlos como una tupla.
4.  Llama a la función con una lista de números.
5.  Desempaqueta el resultado devuelto en tres variables separadas.
6.  Imprime cada uno de los valores calculados.

## Código con Errores

```python
# Ejercicio: Función que devuelve múltiples valores

def analizar_numeros(lista_de_numeros):
    suma = sum(lista_de_numeros)
    if len(lista_de_numeros) > 0:
        promedio = suma / len(lista_de_numeros)
    else:
        promedio = 0
    maximo = max(lista_de_numeros)

    return suma; promedio; maximo # Error 1

numeros = [10, 20, 30, 40, 50]
resultados = analizar_numeros(numeros)

suma_obtenida, promedio_obtenido = resultados # Error 2
maximo_obtenido = resultados[2]

print(f"Suma: {suma_obtenida}")
print(f"Promedio: {promedio_obtenido}")
print(f"Máximo: {maximo_obtenido}") # Error 3: 'maximo_obtenido' se asigna, pero la línea anterior falla
```
