# Módulo 2: Ejercicio 10 (Dificultad 10/10) - Pequeña Calculadora de Propinas

## Enunciado del Problema

1.  Crea una variable `costo_comida` con un valor numérico (ej: 45.70).
2.  Crea una variable `porcentaje_propina` con el porcentaje de propina deseado como un número entero (ej: 15 para 15%).
3.  Calcula el `monto_propina`: `costo_comida * (porcentaje_propina / 100)`.
4.  Calcula el `total_a_pagar`: `costo_comida + monto_propina`.
5.  Imprime el `costo_comida`, el `monto_propina` (formateado a dos decimales si es posible, aunque para este módulo solo imprimir el valor está bien) y el `total_a_pagar`.

## Código con Errores

```python
# Ejercicio: Calculadora de propinas

costo_comida = 52.30
porcentaje_propina = "18" # Pista 1

monto_propina = costo_comida * (porcentaje_propina / 100) # Pista 2
total_a_pagar = costo_comida + monto_propina

print("Costo de la comida: $", costo_comida)
print("Monto de la propina: $", Monto_Propina) # Pista 3
print("Total a pagar: $", total_a_pagar)
```

## Pistas para Corregir los Errores

*   **Pista 1:** Si el porcentaje de propina se va a usar en una división y multiplicación, ¿qué tipo de dato debería tener?
*   **Pista 2:** ¿Puedes dividir una cadena por un número? Revisa el tipo de `porcentaje_propina` para esta operación.
*   **Pista 3:** Recuerda que Python diferencia entre mayúsculas y minúsculas en los nombres de las variables.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Calculadora de propinas

costo_comida = 52.30
porcentaje_propina = 18 # Convertir a entero o flotante

# Asegurar que porcentaje_propina sea numérico para la división
monto_propina = costo_comida * (porcentaje_propina / 100)
total_a_pagar = costo_comida + monto_propina

print("Costo de la comida: $", costo_comida)
print("Monto de la propina: $", monto_propina) # Corregir nombre de variable
print("Total a pagar: $", total_a_pagar)

# Para mostrar con dos decimales (se verá en f-strings más adelante):
# print(f"Monto de la propina: ${monto_propina:.2f}")
# print(f"Total a pagar: ${total_a_pagar:.2f}")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio final del módulo 2 combina varios conceptos: tipos de datos, operaciones aritméticas (incluyendo división para porcentajes) y atención a los nombres de variables.

*   **Error 1 Corrección (Tipo incorrecto para `porcentaje_propina`):**
    *   El código original era `porcentaje_propina = "18"`.
    *   Esto asigna la cadena `"18"`. Para usarlo en la expresión `(porcentaje_propina / 100)`, debe ser un número.
    *   **Solución:** `porcentaje_propina = 18` (o `18.0` si se prefiere flotante, o `int("18")` si la entrada fuera texto).

*   **Error 2 Corrección (Operación inválida debido al tipo de `porcentaje_propina`):**
    *   El código original era `monto_propina = costo_comida * (porcentaje_propina / 100)`.
    *   Si `porcentaje_propina` es una cadena, la operación `porcentaje_propina / 100` causará un `TypeError`.
    *   Al corregir el Error 1 (haciendo `porcentaje_propina` un número), esta línea ahora calculará correctamente el monto de la propina.
    *   **Solución (implícita al corregir Error 1):** El cálculo del `monto_propina` funcionará aritméticamente.

*   **Error 3 Corrección (Nombre de variable incorrecto - mayúsculas en `print`):**
    *   El código original era `print("Monto de la propina: $", Monto_Propina)`.
    *   La variable que almacena la propina se definió como `monto_propina` (minúsculas). Usar `Monto_Propina` (con mayúsculas) en el `print` causaría un `NameError`.
    *   **Solución:** `print("Monto de la propina: $", monto_propina)`

El programa corregido asegura que todas las variables involucradas en cálculos sean numéricas, realiza las operaciones correctamente y muestra los resultados. La nota sobre formateo a dos decimales es un adelanto a f-strings, que se verán en módulos posteriores y son la forma moderna y recomendada de formatear cadenas en Python. Para este módulo, simplemente imprimir el valor flotante es suficiente.
</details>
