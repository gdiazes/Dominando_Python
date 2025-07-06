# Módulo 2: Ejercicio 9 (Dificultad 9/10) - Presupuesto Mensual Simple

## Enunciado del Problema

1.  Declara una variable `ingresos_mensuales` con un valor numérico.
2.  Declara tres variables para gastos: `gasto_alquiler`, `gasto_comida`, `gasto_transporte`, con valores numéricos.
3.  Calcula el `total_gastos` sumando los tres gastos.
4.  Calcula el `saldo_restante` restando el `total_gastos` de los `ingresos_mensuales`.
5.  Imprime el `total_gastos` y el `saldo_restante` de forma descriptiva.

## Código con Errores

```python
# Ejercicio: Calcular presupuesto mensual simple

ingresos_mensuales = 1500.00
gasto_alquiler = 600
gasto_comida = "300.50" # Pista 1
gasto_transporte = 50

total_gastos = gasto_alquiler + gasto_comida + gasto_transporte
saldo_restante = Ingresos_Mensuales - total_gastos # Pista 2

print("Total de gastos: ", total_gastos)
print("Saldo restante: ", SaldoRestante) # Pista 3
```

## Pistas para Corregir los Errores

*   **Pista 1:** Si `gasto_comida` se va a sumar con otros gastos numéricos, ¿cuál debería ser su tipo?
*   **Pista 2:** Python es sensible a mayúsculas y minúsculas en los nombres de variables. Revisa el nombre de la variable de ingresos.
*   **Pista 3:** Nuevamente, la sensibilidad a mayúsculas y minúsculas es clave para los nombres de variables.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Calcular presupuesto mensual simple

ingresos_mensuales = 1500.00
gasto_alquiler = 600.00  # Es bueno ser consistente con flotantes si los ingresos lo son
gasto_comida = 300.50    # Convertir a flotante
gasto_transporte = 50.00 # Consistencia con flotantes

# La suma ahora es puramente aritmética
total_gastos = gasto_alquiler + gasto_comida + gasto_transporte

# Corregir el nombre de la variable de ingresos
saldo_restante = ingresos_mensuales - total_gastos

print("Total de gastos:", total_gastos)
print("Saldo restante:", saldo_restante) # Corregir el nombre de la variable de saldo
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio integra múltiples operaciones aritméticas y refuerza la atención a los tipos de datos y la sensibilidad a mayúsculas/minúsculas.

*   **Error 1 Corrección (Tipo incorrecto para `gasto_comida`):**
    *   El código original era `gasto_comida = "300.50"`.
    *   Esto asigna una cadena. Para sumarlo con otros gastos numéricos, debe ser un número (flotante en este caso, dado el valor).
    *   **Solución:** `gasto_comida = 300.50` (o `float("300.50")`).

*   **Error 2 Corrección (Nombre de variable incorrecto - mayúsculas):**
    *   El código original era `saldo_restante = Ingresos_Mensuales - total_gastos`.
    *   La variable de ingresos fue definida como `ingresos_mensuales` (minúsculas). Usar `Ingresos_Mensuales` (con mayúsculas) resultaría en un `NameError` porque esa variable no existe.
    *   **Solución:** `saldo_restante = ingresos_mensuales - total_gastos`

*   **Error 3 Corrección (Nombre de variable incorrecto - mayúsculas en `print`):**
    *   El código original era `print("Saldo restante: ", SaldoRestante)`.
    *   La variable que almacena el saldo fue definida como `saldo_restante` (minúsculas). Usar `SaldoRestante` (con mayúsculas) en el `print` también causaría un `NameError`.
    *   **Solución:** `print("Saldo restante:", saldo_restante)`

Adicionalmente, aunque no es un error de ejecución, es una buena práctica mantener la consistencia en los tipos de datos para valores monetarios (por ejemplo, usar flotantes para todos los gastos si los ingresos son flotantes). La solución incluye esta mejora.
El programa corregido realiza los cálculos del presupuesto correctamente y muestra los resultados.
</details>
