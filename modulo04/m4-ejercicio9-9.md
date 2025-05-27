# Módulo 4: Ejercicio 9 (Dificultad 9.45/10) - Conversor de Calificaciones Numéricas a Letras Avanzado

## Enunciado del Problema

Escribe un programa que convierta una calificación numérica (0-100) ingresada por el usuario a una calificación en letras, siguiendo este esquema:
*   90-100: A
*   80-89:  B
*   70-79:  C
*   60-69:  D
*   0-59:   F
*   Si la calificación está fuera del rango 0-100, mostrar "Calificación inválida".

Prioriza la verificación de validez de la calificación antes de intentar convertirla.

(Este ejercicio sirve como parte de la Práctica Calificada 1)

## Código con Errores

```python
# Ejercicio: Conversor de calificaciones numéricas a letras avanzado

calificacion_str = input("Ingresa la calificación numérica (0-100): ")
calificacion = float(calificacion_str) # Usar float para permitir decimales si es necesario

letra = ""

if calificacion < 0 or calificacion > 100:
    letra = "Calificación inválida"
elif calificacion >= 90 # Pista 1
    letra = "A"
elif calificacion >= 80 and calificacion < 90: # Pista 2 (Redundancia y posible mejora)
    letra = "B"
elif calificacion >= 70:
    letra = "C"
elif calificacion >= 60:
    letra = "D"
elif calificacion < 60: # Pista 3 (Considerar el rango ya validado)
    letra = "F"


print(f"La calificación en letra es: {letra}")
```

## Pistas para Corregir los Errores

*   **Pista 1:** Todas las líneas de condición `if` y `elif` deben terminar con un carácter específico.
*   **Pista 2:** Dada la estructura secuencial de `if-elif`, si el programa llega a `elif calificacion >= 80`, ¿es realmente necesario verificar también `calificacion < 90`? Piensa en el flujo.
*   **Pista 3:** Si ya se ha verificado que la calificación no es inválida (es decir, está entre 0 y 100) y no ha cumplido ninguna de las condiciones para A, B, C, o D, ¿qué se puede concluir sobre las calificaciones restantes (0-59)? ¿Podría esta última condición ser un `else`?

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Conversor de calificaciones numéricas a letras avanzado

calificacion_str = input("Ingresa la calificación numérica (0-100): ")
calificacion = float(calificacion_str) # Permitir decimales

letra = "" # Inicializar

if calificacion < 0 or calificacion > 100:
    letra = "Calificación inválida"
elif calificacion >= 90: # Falta ':'
    letra = "A"
# Gracias al flujo de elif, no es necesario 'and calificacion < 90'
elif calificacion >= 80:
    letra = "B"
elif calificacion >= 70:
    letra = "C"
elif calificacion >= 60:
    letra = "D"
else: # Si está en rango (0-100) y no es A, B, C, D, entonces es F (0-59)
    letra = "F"

print(f"La calificación en letra es: {letra}")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio implementa una lógica de conversión usando `if-elif-else` y destaca la importancia del orden de las condiciones.

*   **Error 1 Corrección (Falta de dos puntos en `elif`):**
    *   El código original era `elif calificacion >= 90`.
    *   Debe ser `elif calificacion >= 90:`. Este error se repetiría para otros `elif` si no tuvieran los dos puntos.
    *   **Solución:** Añadir `:` a todas las cláusulas `if` y `elif`.

*   **Error 2 Corrección (Condición redundante en `elif`):**
    *   El código original era `elif calificacion >= 80 and calificacion < 90:`.
    *   Debido a que la estructura `if-elif` se evalúa secuencialmente, si el programa llega a esta línea, significa que la condición anterior (`calificacion >= 90`) ya fue `False`. Por lo tanto, `calificacion` es implícitamente menor que 90. La parte `and calificacion < 90` es redundante.
    *   **Solución:** `elif calificacion >= 80:` (lo mismo aplica para las condiciones de C y D).

*   **Error 3 Corrección (Uso de `elif` en lugar de `else` para el caso final):**
    *   El código original era `elif calificacion < 60: letra = "F"`.
    *   Si la calificación es válida (pasó la primera verificación `calificacion < 0 or calificacion > 100`) y no cumplió ninguna de las condiciones para A, B, C, o D, entonces lógicamente debe estar en el rango de F (0-59). Un `else:` final captura este caso de manera más elegante y robusta.
    *   **Solución:** `else: letra = "F"`

El programa corregido primero valida que la calificación esté en el rango 0-100. Luego, utiliza una serie de cláusulas `elif` optimizadas (sin condiciones redundantes) y un `else` final para asignar la letra correcta. El uso de `float` para la calificación permite manejar entradas con decimales, aunque las bandas de calificación suelen ser enteras.
</details>
