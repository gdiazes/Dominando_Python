# Módulo 10: Ejercicio 3 (Dificultad 4.23/10) - Función que Devuelve un Valor (Suma)

## Enunciado del Problema

1.  Define una función llamada `sumar_dos_numeros` que acepte dos parámetros, `num1` y `num2`.
2.  Dentro de la función, calcula la suma de los dos números.
3.  La función debe **devolver** el resultado de la suma.
4.  Llama a la función con dos números de tu elección, guarda el resultado en una variable, y luego imprime esa variable.

## Código con Errores

```python
# Ejercicio: Función que devuelve un valor (suma)

def sumar_dos_numeros(num1, num2) # Error 1
    resultado = num1 + num2
    print(resultado) # Error 2

resultado_suma = sumar_dos_numeros(10, 5)

if resultado_suma > 10: # Error 3
    print("La suma es mayor que 10.")
else:
    print("La suma es 10 o menos.")
```
