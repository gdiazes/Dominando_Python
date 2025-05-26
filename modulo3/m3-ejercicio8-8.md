# Módulo 3: Ejercicio 8 (Dificultad 8.8/10) - Verificar Dominio de Email Simple

## Enunciado del Problema

Solicita al usuario que ingrese su dirección de correo electrónico.
El programa debe realizar dos verificaciones simples:
1.  Verificar si el correo electrónico contiene el carácter "@".
2.  Verificar si el correo electrónico termina con ".com" (insensible a mayúsculas, es decir, ".COM" o ".Com" también serían válidos para esta parte, aunque la solución se enfocará en ".com" para simplificar, pero el estudiante podría pensar en la insensibilidad).
Muestra mensajes apropiados para cada verificación.

Ejemplo de salida (si el usuario ingresa "usuario@example.com"):
```
El correo contiene '@': True
El correo termina con '.com': True
```
Ejemplo de salida (si el usuario ingresa "usuario.example.net"):
```
El correo contiene '@': False
El correo termina con '.com': False
```

## Código con Errores

```python
# Ejercicio: Verificar dominio de email simple

email = input("Ingrese su dirección de correo electrónico: ")

# Verificar si contiene "@"
contiene_arroba = email.find['@'] # Pista 1

# Verificar si termina con ".com"
# Convertimos a minúsculas para una verificación insensible al caso para ".com"
termina_con_com = email.lower().endswith(".COM") # Pista 2

print(f"El correo contiene '@': {contiene_arroba != -1}")
print(f"El correo termina con '.com': {termina_con_com}") # Pista 3: ¿Es esta la forma más directa de mostrar el resultado de 'termina_con_com'?
```

## Pistas para Corregir los Errores

*   **Pista 1:** El método `.find()` se llama con paréntesis, no con corchetes, y devuelve un índice numérico.
*   **Pista 2:** Si estás convirtiendo el email a minúsculas para la comparación, ¿con qué cadena deberías compararlo para que la verificación de `.endswith()` sea efectiva para ".com"?
*   **Pista 3:** La variable `termina_con_com` ya almacena un valor booleano (`True` o `False`). ¿Es necesario compararla con algo más en el `print` o se puede usar directamente?

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Verificar dominio de email simple

email = input("Ingrese su dirección de correo electrónico: ")

# Verificar si contiene "@"
# .find() devuelve el índice o -1 si no se encuentra. Se llama con ().
indice_arroba = email.find('@')
contiene_arroba_booleano = indice_arroba != -1 # True si se encontró, False si no

# Verificar si termina con ".com"
# Si convertimos email a minúsculas, debemos buscar ".com" en minúsculas
termina_con_com = email.lower().endswith(".com")

print(f"El correo contiene '@': {contiene_arroba_booleano}")
# termina_con_com ya es un booleano, se puede imprimir directamente.
print(f"El correo termina con '.com': {termina_con_com}")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio utiliza los métodos `.find()`, `.lower()` y `.endswith()`.

*   **Error 1 Corrección (Uso incorrecto de `.find()`):**
    *   El código original era `contiene_arroba = email.find['@']`.
    *   El método `.find()` se llama con paréntesis: `email.find('@')`. Usar corchetes `[]` es para acceder a elementos por índice (slicing), no para llamar a este método. Esto causaría un `TypeError`. `.find('@')` devuelve el índice de `'@'` o `-1` si no se encuentra. Para obtener un booleano, comparamos este resultado con `-1`.
    *   **Solución:**
        ```python
        indice_arroba = email.find('@')
        contiene_arroba_booleano = indice_arroba != -1
        ```
        Y luego usar `contiene_arroba_booleano` en el `print`.

*   **Error 2 Corrección (Comparación inconsistente con `.endswith()`):**
    *   El código original era `termina_con_com = email.lower().endswith(".COM")`.
    *   Si conviertes `email` a minúsculas con `email.lower()`, entonces para que `.endswith()` funcione correctamente para la terminación ".com", también debes buscar la versión en minúsculas, es decir, `".com"`, no `".COM"`.
    *   **Solución:** `termina_con_com = email.lower().endswith(".com")`

*   **Error 3 Corrección (Redundancia en `print`):**
    *   La pista pregunta si la forma de mostrar `termina_con_com` es la más directa. En el código original, `print(f"El correo termina con '.com': {termina_con_com}")` es, de hecho, la forma correcta y directa de imprimir un valor booleano. No hay un error sintáctico aquí.
    *   Sin embargo, la primera línea de print `print(f"El correo contiene '@': {contiene_arroba != -1}")` está bien, ya que `contiene_arroba` (después de la corrección del error 1) contendría el índice. El booleano se genera directamente en el f-string. Si `contiene_arroba_booleano` se crea como en la solución, se usaría directamente: `print(f"El correo contiene '@': {contiene_arroba_booleano}")`.
    *   Por lo tanto, el "error" es que no hay un error directo en esa línea de `print` si `termina_con_com` ya es un booleano. La confusión podría venir de cómo se obtuvo `contiene_arroba` originalmente.
    *   **Solución (asegurando claridad):** Ambas variables booleanas (`contiene_arroba_booleano` y `termina_con_com`) se imprimen directamente.

El programa corregido realiza las verificaciones solicitadas: busca el carácter `'@'` y comprueba si el email (convertido a minúsculas) termina con `".com"`, mostrando los resultados booleanos directamente.
</details>
