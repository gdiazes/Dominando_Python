# Módulo 4: Ejercicio 1 (Dificultad 1.05/10) - Verificar Mayoría de Edad

## Enunciado del Problema

Escribe un programa que solicite al usuario su edad (como un número entero).
Luego, el programa debe determinar si el usuario es mayor de edad (considera 18 años como la mayoría de edad).
Muestra un mensaje apropiado indicando si es mayor de edad o no.

## Código con Errores

```python
# Ejercicio: Verificar mayoría de edad

edad_str = input("Por favor, ingresa tu edad: ")
edad_int = edad_str # Pista 1

MAYORIA_DE_EDAD = 18

if edad_int > MAYORIA_DE_EDAD: # Pista 2
    mensaje = "Eres mayor de edad."
else
    mensaje = "No eres mayor de edad." # Pista 3

print(mensaje)
```

## Pistas para Corregir los Errores

*   **Pista 1:** La función `input()` devuelve una cadena. Si necesitas comparar la edad como un número, ¿qué debes hacer con la cadena obtenida?
*   **Pista 2:** La condición para ser mayor de edad usualmente incluye la edad misma (18 años). ¿El operador de comparación actual (`>`) es el más adecuado o falta algo?
*   **Pista 3:** La sintaxis de la estructura `else` requiere un carácter específico al final de la línea, similar al `if`.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Verificar mayoría de edad

edad_str = input("Por favor, ingresa tu edad: ")
edad_int = int(edad_str) # Convertir la entrada a entero

MAYORIA_DE_EDAD = 18

# La condición debe ser >= para incluir los 18 años
if edad_int >= MAYORIA_DE_EDAD:
    mensaje = "Eres mayor de edad."
else: # else necesita dos puntos ':'
    mensaje = "No eres mayor de edad."

print(mensaje)
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio introduce la estructura `if-else` básica y la conversión de tipo de `input()`.

*   **Error 1 Corrección (Falta de conversión de tipo):**
    *   El código original era `edad_int = edad_str`.
    *   `input()` devuelve una cadena. Si `edad_str` es `"20"`, entonces `edad_int` también será la cadena `"20"`. Al comparar `edad_int` (cadena) con `MAYORIA_DE_EDAD` (entero) usando `>` o `>=`, Python puede intentar una comparación lexicográfica o generar un `TypeError` dependiendo de la versión y el contexto exacto, pero no es la comparación numérica deseada.
    *   **Solución:** `edad_int = int(edad_str)` para convertir la cadena a un número entero.

*   **Error 2 Corrección (Operador de comparación incorrecto):**
    *   El código original era `if edad_int > MAYORIA_DE_EDAD:`.
    *   Esto significa que solo si la edad es estrictamente mayor que 18 (por ejemplo, 19 o más) se consideraría mayor de edad. Para la mayoría de edad, una persona de 18 años también se considera mayor de edad.
    *   **Solución:** `if edad_int >= MAYORIA_DE_EDAD:` (mayor o igual que).

*   **Error 3 Corrección (Falta de dos puntos en `else`):**
    *   El código original era `else`.
    *   La cláusula `else` en Python, al igual que `if` y `elif`, debe terminar con dos puntos (`:`) para indicar el inicio de su bloque de código.
    *   **Solución:** `else:`

El programa corregido solicita la edad, la convierte a entero, y luego usa una estructura `if-else` con la condición y sintaxis correctas para determinar e imprimir si el usuario es mayor de edad.
</details>
