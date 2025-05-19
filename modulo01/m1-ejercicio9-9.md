# Módulo 1: Ejercicio 9 (Dificultad 9/10) - Información Tabulada Simple

## Enunciado del Problema

Escribe un programa en Python que muestre una pequeña tabla con dos columnas (por ejemplo, "Producto" y "Precio") y tres filas de datos. Intenta alinear visualmente las columnas usando espacios.

Ejemplo de salida:
```
Producto    Precio
------------------
Manzana     0.50
Plátano     0.30
Naranja     0.40
```

## Código con Errores

```python
# Ejercicio: Mostrar información tabulada simple

print("Producto   Precio")
print("------------------"
print("Manzana    0.50) # Pista 1
print('Plátano     0.30') # Pista 2
print("Naranja     "0.40") # Pista 3
```

## Pistas para Corregir los Errores

*   **Pista 1:** Cada instrucción `print` debe ser una unidad completa. ¿Hay algún paréntesis faltante de una instrucción `print` anterior que esté afectando a esta línea? Además, ¿está la cadena actual correctamente cerrada?
*   **Pista 2:** Esta línea parece sintácticamente correcta. El "error" aquí podría ser más sutil, como una alineación imperfecta o un tipo de comilla diferente al resto si buscas consistencia (aunque no es un error de ejecución). Para los 3 errores, considera que el primer error podría estar en la línea anterior.
*   **Pista 3:** Cuando se combinan cadenas literales y lo que parecen ser números (aunque aquí son parte de la cadena), asegúrate de que toda la secuencia que deseas imprimir como una sola cadena esté correctamente formateada. ¿Hay comillas de más o mal puestas?

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Mostrar información tabulada simple

print("Producto    Precio")
print("------------------") # Faltaba el paréntesis de cierre en la línea anterior
print("Manzana     0.50")
print("Plátano     0.30")
print("Naranja     0.40")

# Nota: La alineación perfecta puede ser engañosa con fuentes proporcionales.
# En módulos posteriores se verán formas más robustas de formatear tablas (ej. f-strings con alineación).
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio busca que el estudiante use `print()` y espacios para simular una tabla simple.

*   **Error 1 Corrección (Paréntesis faltante en `print` anterior y comilla faltante en la actual):**
    *   El código original tenía:
        ```python
        print("------------------"
        print("Manzana    0.50) # Pista 1
        ```
    *   El primer `print("------------------")` no tiene su paréntesis de cierre `)`. Esto hace que Python interprete la siguiente línea `print("Manzana    0.50)` como parte de la instrucción `print` anterior, lo cual es un `SyntaxError`.
    *   Adicionalmente, la cadena `"Manzana    0.50"` le falta la comilla de cierre.
    *   **Solución:**
        ```python
        print("------------------") # Añadir paréntesis de cierre
        print("Manzana     0.50")  # Añadir comilla de cierre
        ```

*   **Error 2 Corrección (Línea correcta, pero se asume un error para el ejercicio):**
    *   La línea `print('Plátano     0.30')` es sintácticamente correcta. Para el propósito de tener 3 errores, podríamos imaginar que se esperaba consistencia en el uso de comillas (todas dobles) o que la alineación no era perfecta, pero no es un error de ejecución. Dado el error anterior, este se resuelve al corregir la estructura.
    *   Si el "error" fuera una alineación (que es subjetiva con espacios), se ajustarían los espacios: `print("Plátano     0.30")`.

*   **Error 3 Corrección (Comillas extra / malformación de cadena):**
    *   El código original era `print("Naranja     "0.40")`.
    *   Python interpreta `"Naranja     "` como una cadena y luego `"0.40"` como otra, con un espacio entre ellas. Esto no es una sintaxis válida para concatenar cadenas directamente en un `print` de esta manera (a menos que estén una al lado de la otra sin espacio, lo que se llama concatenación de literales de cadena, pero aquí el espacio causa el problema). Se pretende que sea una sola cadena.
    *   **Solución:** `print("Naranja     0.40")`

La solución final usa espacios para intentar alinear las columnas. Es importante notar que la alineación visual perfecta con espacios puede ser difícil debido a las fuentes proporcionales donde diferentes caracteres ocupan anchos distintos. Métodos más avanzados (como f-strings con especificadores de formato) se aprenden más adelante para un control preciso.
</details>
