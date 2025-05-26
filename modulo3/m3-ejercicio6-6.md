# Módulo 3: Ejercicio 6 (Dificultad 6.6/10) - Limpiar Espacios de Entrada y Verificar

## Enunciado del Problema

Solicita al usuario que ingrese una contraseña. A menudo, los usuarios accidentalmente incluyen espacios al inicio o al final.
El programa debe:
1.  Eliminar cualquier espacio en blanco al inicio y al final de la contraseña ingresada.
2.  Verificar si la contraseña limpia tiene al menos 8 caracteres de longitud.
3.  Mostrar la contraseña limpia (para propósitos de este ejercicio; en la vida real no se mostraría la contraseña).
4.  Mostrar un mensaje indicando si la contraseña cumple con el requisito de longitud mínima (ej: "La contraseña es válida." o "La contraseña es demasiado corta.").

## Código con Errores

```python
# Ejercicio: Limpiar espacios de una contraseña y verificar longitud

contrasena_ingresada = input("Ingrese su nueva contraseña: ")

# Limpiar espacios
contrasena_limpia = contrasena_ingresada.strip # Pista 1

# Verificar longitud
longitud_minima = 8
es_valida = len(contrasena_limpia) >= longitud_minima

print(f"Contraseña procesada: '{contrasena_limpia}'")
if es_valida = True: # Pista 2
    print("La contraseña es válida.")
else:
    print("La contraseña es demasiado corta. Debe tener al menos longitud_minima caracteres.") # Pista 3
```

## Pistas para Corregir los Errores

*   **Pista 1:** Para que el método `.strip()` (o cualquier método) se ejecute y devuelva el resultado, ¿qué se necesita al final de su nombre?
*   **Pista 2:** En una condición `if`, para comparar si dos valores son iguales, ¿qué operador se utiliza? El operador `=` se usa para asignación.
*   **Pista 3:** Si quieres incluir el valor de la variable `longitud_minima` dentro de una cadena de texto en un `print`, ¿cómo puedes hacerlo usando f-strings (o concatenación)?

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Limpiar espacios de una contraseña y verificar longitud

contrasena_ingresada = input("Ingrese su nueva contraseña: ")

# Limpiar espacios llamando al método .strip()
contrasena_limpia = contrasena_ingresada.strip()

# Verificar longitud
longitud_minima = 8
es_valida = len(contrasena_limpia) >= longitud_minima

print(f"Contraseña procesada: '{contrasena_limpia}'") # En un caso real, no imprimir la contraseña

# Usar == para comparación en el if
if es_valida == True: # O simplemente 'if es_valida:'
    print("La contraseña es válida.")
else:
    # Usar f-string para incluir la variable longitud_minima
    print(f"La contraseña es demasiado corta. Debe tener al menos {longitud_minima} caracteres.")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio se enfoca en el uso del método `.strip()` para limpiar cadenas y en la lógica condicional básica (aunque los `if` se verán formalmente más adelante, aquí se introduce su uso simple para dar retroalimentación).

*   **Error 1 Corrección (Llamada a método sin paréntesis):**
    *   El código original era `contrasena_limpia = contrasena_ingresada.strip`.
    *   Al igual que con `.lower()` o `.upper()`, el método `.strip()` debe ser llamado con paréntesis `()` para que se ejecute y devuelva la cadena sin espacios al inicio/final. Sin los paréntesis, se asigna el objeto método en sí.
    *   **Solución:** `contrasena_limpia = contrasena_ingresada.strip()`

*   **Error 2 Corrección (Uso de asignación `=` en lugar de comparación `==`):**
    *   El código original era `if es_valida = True:`.
    *   En Python, `=` es el operador de asignación. Para comparar si dos valores son iguales, se utiliza el operador de comparación `==`. Usar `=` en una condición `if` de esta manera es un error de sintaxis o de lógica (en algunos lenguajes permitiría la asignación y evaluaría la veracidad del valor asignado, pero en Python es un error aquí).
    *   **Solución:** `if es_valida == True:` (o, de forma más idiomática en Python, simplemente `if es_valida:` ya que `es_valida` ya es un booleano).

*   **Error 3 Corrección (Variable no incluida en cadena de texto):**
    *   El código original era `print("La contraseña es demasiado corta. Debe tener al menos longitud_minima caracteres.")`.
    *   La palabra `longitud_minima` dentro de la cadena se imprimirá literalmente, no su valor (que es `8`). Para incluir el valor de la variable en la cadena, se debe usar una f-string o concatenación.
    *   **Solución (usando f-string):** `print(f"La contraseña es demasiado corta. Debe tener al menos {longitud_minima} caracteres.")`

El programa corregido limpia correctamente la contraseña, la compara con la longitud mínima y muestra un mensaje apropiado al usuario, utilizando f-strings para una salida más informativa.
</details>
