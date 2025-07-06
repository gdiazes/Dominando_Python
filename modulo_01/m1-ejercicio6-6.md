# Módulo 1: Ejercicio 6 (Dificultad 6/10) - Instrucciones Simples

## Enunciado del Problema

Escribe un programa en Python que muestre una serie de 3 instrucciones simples para una tarea cotidiana, como "Hacer un café". Cada instrucción debe estar en una nueva línea y numerada.

Ejemplo de salida:
```
Pasos para hacer café:
1. Hervir agua.
2. Poner café en la taza.
3. Añadir agua caliente.
```

## Código con Errores

```python
# Ejercicio: Mostrar instrucciones simples

print("Pasos para hacer té:) # Pista 1
print(1. Calentar agua.)
print('2. Poner la bolsita de té en la taza.) # Pista 2
print(3. Añadir el agua caliente y esperar.") # Pista 3
```

## Pistas para Corregir los Errores

*   **Pista 1:** Revisa si todas las cadenas de texto están correctamente cerradas. ¿Hay alguna comilla sin su pareja?
*   **Pista 2:** Si usas comillas simples para delimitar una cadena, ¿qué pasa si necesitas una comilla simple *dentro* de la cadena? Para este ejercicio, simplemente asegúrate de que la comilla de cierre esté presente.
*   **Pista 3:** Verifica que las comillas de apertura y cierre de la cadena sean del mismo tipo.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Mostrar instrucciones simples

print("Pasos para hacer té:") # O café, según el ejemplo original
print("1. Calentar agua.")
print("2. Poner la bolsita de té en la taza.") # O café molido
print("3. Añadir el agua caliente y esperar.")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio se centra en la correcta formación de cadenas de texto y el uso de `print()` para la salida multilínea.

*   **Error 1 Corrección (Comilla de cierre faltante):**
    *   El código original era `print("Pasos para hacer té:)`.
    *   La cadena de texto `Pasos para hacer té:` tiene una comilla doble de apertura pero le falta la comilla doble de cierre.
    *   **Solución:** `print("Pasos para hacer té:")`

*   **Error 2 Corrección (Comilla de cierre faltante con comilla simple):**
    *   El código original era `print('2. Poner la bolsita de té en la taza.)`.
    *   La cadena está delimitada por comillas simples, pero le falta la comilla simple de cierre.
    *   **Solución:** `print('2. Poner la bolsita de té en la taza.')` o, equivalentemente, `print("2. Poner la bolsita de té en la taza.")`

*   **Error 3 Corrección (Comillas de tipo mixto / faltante):**
    *   El código original era `print(3. Añadir el agua caliente y esperar.")`.
    *   Parece que se intentó iniciar una cadena sin comilla de apertura y solo se puso la de cierre. Para que sea una cadena válida, necesita comillas de apertura y cierre del mismo tipo.
    *   **Solución:** `print("3. Añadir el agua caliente y esperar.")`

El programa corregido muestra cada instrucción en una línea separada, como se requiere.
</details>
