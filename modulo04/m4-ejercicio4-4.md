# Módulo 4: Ejercicio 4 (Dificultad 4.2/10) - Calculadora de Descuento Simple

## Enunciado del Problema

Un comercio ofrece un descuento del 10% si el monto total de la compra es mayor o igual a $100.
Escribe un programa que solicite al usuario el monto total de la compra.
Luego, calcula y muestra el monto del descuento (si aplica) y el precio final a pagar.
Si no aplica descuento, indícalo.

## Código con Errores

```python
# Ejercicio: Calculadora de descuento simple

monto_compra_str = input("Ingrese el monto total de la compra: $")
monto_compra = float(monto_compra_str)

PORCENTAJE_DESCUENTO = 0.10
UMBRAL_DESCUENTO = 100.0
monto_descuento = 0.0 # Inicializar

if monto_compra >= UMBRAL_DESCUENTO # Pista 1
    monto_descuento = monto_compra * PORCENTAJE_DESCUENTO
    precio_final = monto_compra - monto_descuento
    print(f"Descuento aplicado: ${monto_descuento:.2f}")
else monto_compra < UMBRAL_DESCUENTO: # Pista 2
    precio_final = monto_compra
    print("No aplica descuento.")

print(f"Precio final a pagar: ${precio_final:.2f}") # Pista 3
```

## Pistas para Corregir los Errores

*   **Pista 1:** La línea de la condición `if` requiere un carácter específico al final.
*   **Pista 2:** Si la primera condición `if` no se cumple, ¿cómo se especifica el bloque de código alternativo? Si se quiere añadir otra condición aquí, ¿cuál es la palabra clave correcta? La sintaxis actual para el `else` con una condición es incorrecta.
*   **Pista 3:** Si el descuento no se aplica (dentro del bloque `else`), ¿la variable `precio_final` se calcula o se asigna correctamente antes de ser usada en el último `print`? Considera todas las rutas del código.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Calculadora de descuento simple

monto_compra_str = input("Ingrese el monto total de la compra: $")
monto_compra = float(monto_compra_str)

PORCENTAJE_DESCUENTO = 0.10
UMBRAL_DESCUENTO = 100.0
monto_descuento = 0.0
precio_final = monto_compra # Inicializar precio_final con el monto original

if monto_compra >= UMBRAL_DESCUENTO: # Falta ':'
    monto_descuento = monto_compra * PORCENTAJE_DESCUENTO
    precio_final = monto_compra - monto_descuento # Actualizar precio_final si hay descuento
    print(f"Descuento aplicado: ${monto_descuento:.2f}")
else: # 'else' no lleva condición, o si se necesita condición usar 'elif'
    # precio_final ya es monto_compra si no hay descuento (gracias a la inicialización)
    print("No aplica descuento.")
    # No es necesario reasignar precio_final = monto_compra aquí si se inicializó antes.

print(f"Precio final a pagar: ${precio_final:.2f}")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio aplica una condición `if-else` para determinar si se otorga un descuento.

*   **Error 1 Corrección (Falta de dos puntos en `if`):**
    *   El código original era `if monto_compra >= UMBRAL_DESCUENTO`.
    *   La declaración `if` debe terminar con dos puntos (`:`).
    *   **Solución:** `if monto_compra >= UMBRAL_DESCUENTO:`

*   **Error 2 Corrección (Sintaxis incorrecta para `else` con condición):**
    *   El código original era `else monto_compra < UMBRAL_DESCUENTO:`.
    *   La cláusula `else` no toma una condición. Se ejecuta si la condición del `if` (o `elif` precedentes) es falsa.
    *   Si se quisiera verificar otra condición específica, se usaría `elif monto_compra < UMBRAL_DESCUENTO:`. Sin embargo, en este caso, si `monto_compra >= UMBRAL_DESCUENTO` es falso, entonces `monto_compra < UMBRAL_DESCUENTO` es necesariamente verdadero, por lo que un simple `else:` es suficiente.
    *   **Solución:** `else:`

*   **Error 3 Corrección (Manejo de `precio_final` en todas las rutas):**
    *   En el código original con errores, si el `else` se ejecutaba, `precio_final` se asignaba correctamente como `monto_compra`. Si el `if` se ejecutaba, `precio_final` se calculaba. El problema era la sintaxis del `else`.
    *   Una práctica robusta es inicializar `precio_final` antes del bloque `if-else`, por ejemplo, con el valor original de `monto_compra`. De esta manera, si el `else` no hiciera ninguna asignación a `precio_final` (quizás por un error lógico más complejo), `precio_final` aún tendría un valor definido.
    *   **Solución (Mejora y aseguramiento):**
        ```python
        precio_final = monto_compra # Inicializar
        if monto_compra >= UMBRAL_DESCUENTO:
            # ... calcular descuento y actualizar precio_final ...
        else:
            # ... precio_final ya es monto_compra ...
            print("No aplica descuento.")
        print(f"Precio final a pagar: ${precio_final:.2f}")
        ```
    *   La solución corregida asigna `precio_final = monto_compra - monto_descuento` dentro del `if` y se basa en la inicialización `precio_final = monto_compra` para el caso `else`.

El programa corregido calcula correctamente el descuento y el precio final, aplicando la lógica condicional `if-else` y asegurando que `precio_final` siempre tenga el valor correcto antes de imprimirlo.
</details>
