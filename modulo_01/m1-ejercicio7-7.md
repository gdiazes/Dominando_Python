# Módulo 1: Ejercicio 7 (Dificultad 7/10) - Conversación Simulada

## Enunciado del Problema

Escribe un programa en Python que simule una breve conversación entre dos personas (A y B). Cada línea de diálogo debe aparecer en la pantalla.

Ejemplo de salida:
```
A: Hola, ¿cómo estás?
B: ¡Hola! Estoy bien, ¿y tú?
A: Muy bien, gracias por preguntar.
```

## Código con Errores

```python
# Ejercicio: Simular una conversación

print("A: Hola, ¿cómo estás?")
print(B: ¡Hola! Estoy bien, ¿y tú?) # Pista 1
Print("A: Muy bien, gracias por preguntar.") # Pista 2
# Pista 3: ¿Falta alguna línea de código si quisiéramos añadir una despedida de B?
```

## Pistas para Corregir los Errores

*   **Pista 1:** Para que Python trate un texto como una cadena literal, ¿qué debe rodearlo?
*   **Pista 2:** Python distingue entre mayúsculas y minúsculas en los nombres de sus funciones.
*   **Pista 3:** Este es más un "error de omisión" conceptual para el ejercicio. Si el diálogo necesitara una línea más, simplemente la añadirías con la sintaxis correcta. No hay un error sintáctico directo en el código mostrado respecto a una línea faltante, pero se espera que identifiques que podrías añadir más.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Simular una conversación

print("A: Hola, ¿cómo estás?")
print("B: ¡Hola! Estoy bien, ¿y tú?")
print("A: Muy bien, gracias por preguntar.")

# Si se quisiera añadir una despedida, por ejemplo:
# print("B: ¡De nada! Hasta luego.")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

El ejercicio busca practicar la salida multilínea y prestar atención a los detalles de la sintaxis de Python.

*   **Error 1 Corrección (Texto sin comillas):**
    *   El código original era `print(B: ¡Hola! Estoy bien, ¿y tú?)`.
    *   La frase `B: ¡Hola! Estoy bien, ¿y tú?` no está encerrada en comillas, por lo que Python no la reconoce como una cadena de texto.
    *   **Solución:** `print("B: ¡Hola! Estoy bien, ¿y tú?")`

*   **Error 2 Corrección (Nombre de función incorrecto - mayúscula):**
    *   El código original era `Print("A: Muy bien, gracias por preguntar.")`.
    *   La función para imprimir es `print` (minúsculas), no `Print`. Esto causaría un `NameError`.
    *   **Solución:** `print("A: Muy bien, gracias por preguntar.")`

*   **Error 3 Corrección (Conceptual - Añadir más líneas):**
    *   La pista 3 se refiere a la capacidad de añadir más diálogo. No hay un error de sintaxis en el código proporcionado que impida añadir más, pero el ejercicio implica pensar en cómo extender el programa.
    *   **Solución (si se añade más diálogo):** Simplemente se añadiría otra sentencia `print()` con la nueva línea de diálogo, por ejemplo: `print("B: ¡De nada! Hasta luego.")`.

El código corregido imprime cada línea de la conversación como una cadena de texto válida en una nueva línea.
</details>
