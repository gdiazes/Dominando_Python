# Módulo 2: Ejercicio 6 (Dificultad 6/10) - Conversión de Edad

## Enunciado del Problema

1.  Crea una variable `edad_texto` y asígnale una edad como cadena de texto (por ejemplo, `"25"`).
2.  Convierte esta variable a un número entero y guárdala en una nueva variable `edad_numero`.
3.  Crea una variable `annos_en_una_decada` con el valor `10`.
4.  Calcula la edad que tendrá la persona en una década (`edad_futura = edad_numero + annos_en_una_decada`).
5.  Imprime la `edad_numero` y la `edad_futura` de forma descriptiva.

Ejemplo de salida (si edad_texto = "25"):
```
Edad actual: 25
Edad en una década: 35
```

## Código con Errores

```python
# Ejercicio: Conversión de edad y cálculo futuro

edad_texto = "30"
edad_numero = edad_texto # Pista 1
annos_en_una_decada = "10" # Pista 2
edad_futura = edad_numero + annos_en_una_decada

print("Edad actual: ", edad_numero)
print("Edad en una década: " + edad_futura) # Pista 3
```

## Pistas para Corregir los Errores

*   **Pista 1:** Simplemente asignar `edad_texto` a `edad_numero` no cambia su tipo. ¿Qué función necesitas para convertir una cadena a un entero?
*   **Pista 2:** Si `annos_en_una_decada` se va a sumar a un número, ¿debería ser una cadena o un entero?
*   **Pista 3:** Revisa la operación de "suma" entre `edad_numero` y `edad_futura` en el `print`. Si `edad_futura` es un número, ¿puedes concatenarlo directamente con una cadena usando `+`?

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Conversión de edad y cálculo futuro

edad_texto = "30"
edad_numero = int(edad_texto) # Convertir a entero
annos_en_una_decada = 10      # Debe ser un entero

# Ahora la suma es aritmética
edad_futura = edad_numero + annos_en_una_decada

print("Edad actual:", edad_numero) # Usar coma para print
print("Edad en una década:", edad_futura) # Usar coma para print o str(edad_futura) para concatenar
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio se centra en la conversión de tipos (casting) y su importancia para realizar operaciones aritméticas.

*   **Error 1 Corrección (Conversión de tipo faltante):**
    *   El código original era `edad_numero = edad_texto`.
    *   Si `edad_texto` es `"30"` (una cadena), entonces `edad_numero` también se convierte en la cadena `"30"`. No se realiza una conversión a tipo numérico.
    *   Para convertir la cadena a un entero, se debe usar la función `int()`.
    *   **Solución:** `edad_numero = int(edad_texto)`

*   **Error 2 Corrección (Tipo incorrecto para `annos_en_una_decada`):**
    *   El código original era `annos_en_una_decada = "10"`.
    *   Esto asigna la cadena `"10"`. Para la suma aritmética con `edad_numero` (que ahora será un entero), `annos_en_una_decada` también debe ser un entero.
    *   **Solución:** `annos_en_una_decada = 10`

*   **Error 3 Corrección (Concatenación de cadena y número con `+` en `print`):**
    *   El código original era `print("Edad en una década: " + edad_futura)`.
    *   Si `edad_futura` es un número (resultado de `edad_numero + annos_en_una_decada`), no se puede concatenar directamente con la cadena `"Edad en una década: "` usando el operador `+`. Esto causaría un `TypeError`.
    *   **Soluciones posibles:**
        1.  Convertir `edad_futura` a cadena: `print("Edad en una década: " + str(edad_futura))`
        2.  Usar comas en `print`: `print("Edad en una década:", edad_futura)` (preferido por simplicidad aquí).
    *   **Solución (usando comas):** `print("Edad en una década:", edad_futura)`
    *   De manera similar, el primer `print` también se beneficia de usar comas por consistencia: `print("Edad actual:", edad_numero)`

El programa corregido primero convierte la edad de texto a un número, asegura que los años a sumar también sean un número, realiza la suma aritmética y finalmente imprime los resultados de manera segura.
</details>
