# Módulo 3: Ejercicio 10 (Dificultad 10.0/10) - Mini Formulario Interactivo y Resumen

## Enunciado del Problema

Crea un mini formulario interactivo que solicite al usuario:
1.  Nombre completo.
2.  Año de nacimiento (como número).
3.  Un hobby principal.

Luego, el programa debe:
a. Limpiar cualquier espacio extra al inicio/final del nombre y del hobby.
b. Calcular la edad aproximada del usuario (asumiendo el año actual como 2024).
c. Generar un resumen formateado usando una f-string que incluya el nombre (en formato título), la edad calculada y el hobby (primera letra en mayúscula).

Ejemplo de salida (si se ingresa "  juan pérez ", "1990", " leer "):
```
--- Resumen del Usuario ---
Nombre: Juan Pérez
Edad Aproximada: 34 años
Hobby Principal: Leer
---------------------------
```

## Código con Errores

```python
# Ejercicio: Mini formulario interactivo y resumen

nombre_ingresado = input("Nombre completo: ")
ano_nacimiento_str = input("Año de nacimiento: ")
hobby_ingresado = input("Hobby principal: ")

nombre_limpio = nombre_ingresado.strip # Pista 1
hobby_limpio = hobby_ingresado.strip()

ANIO_ACTUAL = 2024
edad_aproximada = ANIO_ACTUAL - ano_nacimiento_str # Pista 2

# Formatear para la salida
nombre_formateado = nombre_limpio.title()
hobby_formateado = hobby_limpio.capitalize()

print("\n--- Resumen del Usuario ---")
print(f"Nombre: {nombre_formateado}")
print(f"Edad Aproximada: {edad_aproximada} anos") # Pista 3 (Hay dos problemas sutiles aquí)
print(f"Hobby Principal: {hobby_formateado}")
print("---------------------------")

```

## Pistas para Corregir los Errores

*   **Pista 1:** Para que un método como `.strip()` se ejecute y devuelva la cadena modificada, ¿cómo debe ser invocado?
*   **Pista 2:** La entrada `ano_nacimiento_str` es una cadena. ¿Puedes realizar una resta directamente entre un número entero (`ANIO_ACTUAL`) y una cadena? ¿Qué conversión se necesita?
*   **Pista 3:** Revisa la palabra "años" en la f-string. Si el idioma de salida es español, ¿cómo se escribe correctamente la "ñ"? Además, considera si el tipo de `edad_aproximada` es el ideal para la resta si no se corrigió Pista 2.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Mini formulario interactivo y resumen

nombre_ingresado = input("Nombre completo: ")
ano_nacimiento_str = input("Año de nacimiento: ")
hobby_ingresado = input("Hobby principal: ")

# Limpiar espacios llamando a los métodos con ()
nombre_limpio = nombre_ingresado.strip()
hobby_limpio = hobby_ingresado.strip()

ANIO_ACTUAL = 2024
# Convertir año de nacimiento a entero para el cálculo
ano_nacimiento_int = int(ano_nacimiento_str)
edad_aproximada = ANIO_ACTUAL - ano_nacimiento_int

# Formatear para la salida
nombre_formateado = nombre_limpio.title()
hobby_formateado = hobby_limpio.capitalize() # Asegurar que se llama con () si no se hizo antes

print("\n--- Resumen del Usuario ---")
print(f"Nombre: {nombre_formateado}")
# Usar la palabra "años" correctamente
print(f"Edad Aproximada: {edad_aproximada} años")
print(f"Hobby Principal: {hobby_formateado}")
print("---------------------------")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio integra la limpieza de entradas, conversión de tipos, cálculo y formateo de salida.

*   **Error 1 Corrección (Llamada a método `.strip()` sin paréntesis):**
    *   El código original era `nombre_limpio = nombre_ingresado.strip`.
    *   El método `.strip()` debe ser llamado con paréntesis `()` para ejecutarse. Sin ellos, se asigna el objeto método.
    *   **Solución:** `nombre_limpio = nombre_ingresado.strip()`
    *   (Nota: `hobby_limpio = hobby_ingresado.strip()` estaba correcto en el código con errores, la pista podría haber sido más general o aplicar a `nombre_limpio`).

*   **Error 2 Corrección (Operación aritmética con cadena):**
    *   El código original era `edad_aproximada = ANIO_ACTUAL - ano_nacimiento_str`.
    *   `ANIO_ACTUAL` es un entero, pero `ano_nacimiento_str` es una cadena (devuelta por `input()`). No se puede restar una cadena de un entero directamente; esto causa un `TypeError`.
    *   Es necesario convertir `ano_nacimiento_str` a un entero usando `int()`.
    *   **Solución:**
        ```python
        ano_nacimiento_int = int(ano_nacimiento_str)
        edad_aproximada = ANIO_ACTUAL - ano_nacimiento_int
        ```

*   **Error 3 Corrección (Error tipográfico "anos" y tipo de `edad_aproximada` si no se corrige Pista 2):**
    *   El código original era `print(f"Edad Aproximada: {edad_aproximada} anos")`.
    *   Primero, "anos" es un error tipográfico común en español; la palabra correcta es "años".
    *   Segundo, y más importante si el error de Pista 2 no se hubiera corregido, `edad_aproximada` sería el resultado de una operación inválida y el programa fallaría antes. Con la Pista 2 corregida, `edad_aproximada` es un entero, y la f-string lo manejará bien. El error principal aquí es el tipográfico.
    *   **Solución:** `print(f"Edad Aproximada: {edad_aproximada} años")`

El programa corregido limpia las entradas de texto, convierte el año de nacimiento a entero para calcular la edad correctamente, y luego presenta un resumen bien formateado y con la ortografía correcta. Se asume que el usuario ingresa un año de nacimiento numérico válido; el manejo de entradas inválidas (como texto no numérico para el año) se abordará en módulos sobre manejo de excepciones.
</details>
