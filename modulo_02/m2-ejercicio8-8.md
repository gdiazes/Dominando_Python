# Módulo 2: Ejercicio 8 (Dificultad 8/10) - División y Resto

## Enunciado del Problema

Dados dos números enteros, `dividendo` y `divisor`:
1.  Calcula el cociente de la división entera entre `dividendo` y `divisor`.
2.  Calcula el resto de la división entera entre `dividendo` y `divisor`.
Imprime ambos resultados de forma descriptiva.

Ejemplo (si dividendo=27 y divisor=4):
```
27 dividido entre 4:
Cociente: 6
Resto: 3
```

## Código con Errores

```python
# Ejercicio: Calcular división entera y resto

dividendo = "27" # Pista 1
divisor = 4

cociente = dividendo // divisor
resto = dividendo % divisor # Pista 2

print(dividendo, "dividido entre", divisor ":") # Pista 3
print("Cociente:", cociente)
print("Resto:", resto)
```

## Pistas para Corregir los Errores

*   **Pista 1:** Para realizar operaciones de división o módulo, ¿el dividendo debe ser una cadena o un número?
*   **Pista 2:** Si el `dividendo` es una cadena, ¿qué tipo de error esperarías al intentar usar el operador módulo `%` con un divisor numérico? (Similar al error de `//`).
*   **Pista 3:** Revisa la sintaxis al combinar cadenas literales y variables en `print`. ¿Hay algún carácter inesperado o faltante?

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Calcular división entera y resto

dividendo = 27  # Convertir a entero
divisor = 4

# Las operaciones ahora serán aritméticas
cociente = dividendo // divisor
resto = dividendo % divisor

# Corregir la sintaxis del print, eliminando los dos puntos fuera de lugar
print(dividendo, "dividido entre", divisor, ":") # ':' debe ser parte de la cadena o un argumento separado
# O una forma más limpia:
# print(f"{dividendo} dividido entre {divisor}:") # Usando f-string (se verá más adelante)

print("Cociente:", cociente)
print("Resto:", resto)
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio se enfoca en los operadores de división entera (`//`) y módulo (`%`), y la importancia de los tipos de datos correctos.

*   **Error 1 Corrección (Tipo incorrecto para `dividendo`):**
    *   El código original era `dividendo = "27"`.
    *   Esto asigna la cadena `"27"`. Los operadores `//` y `%` esperan operandos numéricos. Intentar usarlos con una cadena y un número resultará en un `TypeError`.
    *   **Solución:** `dividendo = 27`

*   **Error 2 Corrección (Operación inválida debido al tipo de `dividendo`):**
    *   El código original era `resto = dividendo % divisor`.
    *   Este error es una consecuencia directa del Error 1. Si `dividendo` es una cadena, la operación módulo `%` no se puede realizar con un divisor numérico.
    *   **Solución (implícita al corregir Error 1):** La operación `resto = dividendo % divisor` ahora funcionará correctamente.

*   **Error 3 Corrección (Sintaxis incorrecta en `print`):**
    *   El código original era `print(dividendo, "dividido entre", divisor ":")`.
    *   Los dos puntos `:` están colocados incorrectamente. Si se pretende que sean parte del texto, deberían estar dentro de una cadena o ser un argumento de cadena separado. Tal como está, causa un `SyntaxError` porque `divisor ":" ` no es una expresión válida.
    *   **Soluciones posibles:**
        1.  Hacer los dos puntos parte de la cadena anterior: `print(dividendo, "dividido entre", str(divisor) + ":")` (menos ideal porque requiere `str()`)
        2.  Hacer los dos puntos un argumento de cadena separado: `print(dividendo, "dividido entre", divisor, ":")` (más simple y común).
        3.  Incluir el divisor y los dos puntos en la misma cadena: `print(dividendo, "dividido entre", str(divisor) + ":")` o usando f-strings (más avanzado): `print(f"{dividendo} dividido entre {divisor}:")`
    *   **Solución (simple y efectiva):** `print(dividendo, "dividido entre", divisor, ":")`

El programa corregido asegura que ambos operandos sean enteros, permitiendo que los operadores `//` y `%` funcionen como se espera, y la salida se formatea correctamente.
</details>
