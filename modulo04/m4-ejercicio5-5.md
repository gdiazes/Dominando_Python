# Módulo 4: Ejercicio 5 (Dificultad 5.25/10) - Clasificación de Triángulos (por lados)

## Enunciado del Problema

Solicita al usuario las longitudes de los tres lados de un triángulo (lado_a, lado_b, lado_c) como números.
Luego, clasifica el triángulo y muestra el resultado:
*   **Equilátero:** Si los tres lados son iguales.
*   **Isósceles:** Si exactamente dos lados son iguales.
*   **Escaleno:** Si los tres lados son diferentes.

(Nota: Para simplificar, no se validará si los lados forman un triángulo válido, solo se clasifica según las longitudes dadas).

## Código con Errores

```python
# Ejercicio: Clasificación de triángulos por lados

lado_a_str = input("Longitud del lado a: ")
lado_b_str = input("Longitud del lado b: ")
lado_c_str = input("Longitud del lado c: ")

lado_a = float(lado_a_str)
lado_b = float(lado_b_str)
lado_c = lado_c_str # Pista 1

tipo_triangulo = "Desconocido"

if lado_a == lado_b == lado_c: # Pista 2 (Esta sintaxis es válida en Python, pero el error está en cómo se llega aquí)
    tipo_triangulo = "Equilátero"
elif (lado_a == lado_b) or (lado_a == lado_c) or (lado_b == lado_c)
    tipo_triangulo = "Isósceles" # Pista 3
else
    tipo_triangulo = "Escaleno"

print(f"El triángulo es: {tipo_triangulo}")
```

## Pistas para Corregir los Errores

*   **Pista 1:** Todos los lados deben ser números para poder compararlos correctamente. ¿Se ha convertido `lado_c_str` a un tipo numérico?
*   **Pista 2:** La sintaxis `lado_a == lado_b == lado_c` es una forma válida en Python de verificar si los tres son iguales. Sin embargo, si uno de los lados no es del tipo numérico correcto (ver Pista 1), esta comparación podría no funcionar como se espera o dar un error.
*   **Pista 3:** La línea de la condición `elif` requiere un carácter específico al final, y el bloque `else` también.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Clasificación de triángulos por lados

lado_a_str = input("Longitud del lado a: ")
lado_b_str = input("Longitud del lado b: ")
lado_c_str = input("Longitud del lado c: ")

lado_a = float(lado_a_str)
lado_b = float(lado_b_str)
lado_c = float(lado_c_str) # Convertir lado_c a flotante

tipo_triangulo = "Desconocido" # Buena práctica inicializar

# La lógica de clasificación debe ser cuidadosa para evitar falsos positivos.
# Primero el caso más específico (Equilátero).
if lado_a == lado_b and lado_b == lado_c: # Más explícito que a == b == c, aunque el último también funciona
    tipo_triangulo = "Equilátero"
# Luego Isósceles, asegurándose de que no sea Equilátero (ya cubierto arriba)
elif (lado_a == lado_b) or (lado_a == lado_c) or (lado_b == lado_c): # Falta ':'
    # Esta condición es cierta para equiláteros también.
    # Para que sea estrictamente isósceles (y no equilátero), las condiciones se complican,
    # o se confía en el orden: si es equilátero, ya entró en el primer if.
    # Para un isósceles "puro":
    # if (lado_a == lado_b != lado_c) or \
    #    (lado_a == lado_c != lado_b) or \
    #    (lado_b == lado_c != lado_a):
    # Pero la estructura if/elif se encarga del orden, así que la condición original es válida
    # si el equilátero se prueba primero.
    tipo_triangulo = "Isósceles"
else: # Falta ':' ; si no es equilátero ni isósceles, es escaleno
    tipo_triangulo = "Escaleno"

print(f"El triángulo es: {tipo_triangulo}")
```
*Nota sobre la lógica de Isósceles:* La condición `(lado_a == lado_b) or (lado_a == lado_c) or (lado_b == lado_c)` es verdadera tanto para triángulos isósceles como para equiláteros. Sin embargo, debido a que la condición de equilátero se prueba *primero* en la estructura `if-elif-else`, si un triángulo es equilátero, entrará en el primer bloque `if` y no se evaluarán las condiciones `elif` posteriores. Por lo tanto, si llega al `elif` de isósceles, significa que *no* es equilátero, y si cumple la condición, es isósceles. Esta es una característica importante del flujo de `if-elif-else`.

La solución corregida se asegura de que todas las entradas se conviertan a `float`, añade los dos puntos faltantes y la lógica de clasificación se basa en el orden de evaluación de `if/elif/else`.
Faltaban los `:` en el `elif` y `else`.

```python
# SOLUCIÓN CORRECTA REFINADA:
lado_a_str = input("Longitud del lado a: ")
lado_b_str = input("Longitud del lado b: ")
lado_c_str = input("Longitud del lado c: ")

lado_a = float(lado_a_str)
lado_b = float(lado_b_str)
lado_c = float(lado_c_str)

tipo_triangulo = ""

if lado_a == lado_b and lado_b == lado_c:
    tipo_triangulo = "Equilátero"
elif lado_a == lado_b or lado_a == lado_c or lado_b == lado_c:
    tipo_triangulo = "Isósceles"
else:
    tipo_triangulo = "Escaleno"

print(f"El triángulo es: {tipo_triangulo}")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio requiere múltiples comparaciones y una estructura `if-elif-else` para clasificar.

*   **Error 1 Corrección (Falta de conversión de tipo para `lado_c`):**
    *   El código original era `lado_c = lado_c_str`.
    *   `lado_c_str` es una cadena devuelta por `input()`. Para compararla numéricamente con `lado_a` y `lado_b` (que son flotantes), `lado_c` también debe ser un flotante.
    *   **Solución:** `lado_c = float(lado_c_str)`

*   **Error 2 Corrección (Impacto de tipo incorrecto en la comparación):**
    *   La sintaxis `if lado_a == lado_b == lado_c:` es válida en Python para verificar si los tres son iguales. Sin embargo, si `lado_c` fuera una cadena (debido al Error 1) y `lado_a`, `lado_b` fueran flotantes, la comparación `lado_b == lado_c` probablemente daría `False` (comparando un número con una cadena) o un `TypeError` en algunos contextos si Python no puede realizar una comparación sensata. Una vez que `lado_c` es un flotante, esta comparación funciona como se espera.
    *   Para mayor claridad, a veces se prefiere `if lado_a == lado_b and lado_b == lado_c:`, aunque `a == b == c` es idiomático en Python. El error principal aquí era el tipo de `lado_c`.

*   **Error 3 Corrección (Falta de dos puntos en `elif` y `else`):**
    *   El código original tenía:
        ```python
        elif (lado_a == lado_b) or (lado_a == lado_c) or (lado_b == lado_c)
            tipo_triangulo = "Isósceles"
        else
            tipo_triangulo = "Escaleno"
        ```
    *   Tanto la línea del `elif` como la del `else` deben terminar con dos puntos (`:`).
    *   **Solución:**
        ```python
        elif (lado_a == lado_b) or (lado_a == lado_c) or (lado_b == lado_c):
            tipo_triangulo = "Isósceles"
        else:
            tipo_triangulo = "Escaleno"
        ```

**Lógica de Clasificación Importante:**
La secuencia `if` (Equilátero) -> `elif` (Isósceles) -> `else` (Escaleno) es crucial.
1.  Se verifica primero si es Equilátero. Si lo es, se asigna "Equilátero" y se salta el resto.
2.  Si no es Equilátero, se verifica si es Isósceles. La condición `(lado_a == lado_b) or (lado_a == lado_c) or (lado_b == lado_c)` será verdadera si al menos dos lados son iguales. Como ya sabemos que no es equilátero (porque no entró en el primer `if`), si esta condición es verdadera, entonces es Isósceles.
3.  Si no es Equilátero NI Isósceles, entonces por eliminación debe ser Escaleno, y entra en el `else`.

El programa corregido convierte todas las entradas a números flotantes y utiliza la estructura `if-elif-else` con la sintaxis correcta para clasificar el triángulo.
</details>
