# Módulo 4: Ejercicio 7 (Dificultad 7.35/10) - Validador de Contraseña Simple Avanzado

## Enunciado del Problema

Escribe un programa que valide una contraseña ingresada por el usuario según las siguientes reglas (todas deben cumplirse):
1.  Debe tener al menos 8 caracteres de longitud.
2.  Debe contener al menos una letra mayúscula.
3.  Debe contener al menos un número.

Muestra un mensaje indicando si la contraseña es válida o no. Si no es válida, intenta indicar la primera regla que no se cumple (opcional, pero buen desafío).

*Ayuda: Para verificar mayúsculas y números, puedes iterar sobre la contraseña y usar métodos de cadena como `.isupper()` y `.isdigit()`.* (Este es un adelanto de bucles y métodos más avanzados, pero puedes intentar una solución más simple o enfocarte en la longitud por ahora si la iteración es muy avanzada para este punto).

Para este ejercicio, nos centraremos en la estructura condicional y en una verificación más simple, pero las pistas pueden guiar hacia la solución completa.

## Código con Errores

```python
# Ejercicio: Validador de contraseña simple avanzado

contrasena = input("Ingresa tu contraseña: ")

longitud_valida = False
tiene_mayuscula = False
tiene_numero = False

# Verificar longitud
if len(contrasena) >= 8
    longitud_valida = True # Pista 1

# Verificar mayúscula (simplificado, buscando 'A')
if "A" in contrasena: # Esta es una forma simple, pero no general
    tiene_mayuscula = True

# Verificar número (simplificado, buscando '1')
if "1" in contrasena: # Esta es una forma simple, pero no general
    tiene_numero = True

if longitud_valida and tiene_mayuscula and tiene_numero:
    print("Contraseña válida.")
else if not longitud_valida: # Pista 2
    print("Contraseña no válida: debe tener al menos 8 caracteres.")
elif not tiene_mayuscula # Pista 3
    print("Contraseña no válida: debe contener al menos una mayúscula.")
else:
    print("Contraseña no válida: debe contener al menos un número.")

```

## Pistas para Corregir los Errores

*   **Pista 1:** La línea `if` para verificar la longitud necesita los dos puntos (`:`) al final.
*   **Pista 2:** La palabra clave para "sino si" en Python es `elif`. `else if` no es una construcción válida.
*   **Pista 3:** Similar a la Pista 1, la línea `elif` para verificar la mayúscula (y otras `elif/if`) necesita los dos puntos (`:`) al final.

*Desafío Adicional (no un error directo en el código dado, pero una mejora):* Las verificaciones de mayúsculas y números usando `in "A"` o `in "1"` son muy limitadas. ¿Cómo podrías hacerlas más generales para cualquier mayúscula o cualquier número? (Esto podría requerir un bucle `for` y métodos como `.isupper()` y `.isdigit()`, que se verán en módulos posteriores, pero puedes investigar si quieres).

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Validador de contraseña simple avanzado

contrasena = input("Ingresa tu contraseña: ")

longitud_valida = False
tiene_mayuscula_real = False # Usaremos un nombre diferente para la versión general
tiene_numero_real = False    # Usaremos un nombre diferente para la versión general

# Verificar longitud
if len(contrasena) >= 8: # Falta ':'
    longitud_valida = True

# Verificar mayúscula (versión más general usando un bucle)
for caracter in contrasena:
    if caracter.isupper():
        tiene_mayuscula_real = True
        break # Si encontramos una, no necesitamos seguir buscando

# Verificar número (versión más general usando un bucle)
for caracter in contrasena:
    if caracter.isdigit():
        tiene_numero_real = True
        break # Si encontramos uno, no necesitamos seguir buscando

# Evaluar condiciones
if longitud_valida and tiene_mayuscula_real and tiene_numero_real:
    print("Contraseña válida.")
elif not longitud_valida: # Usar elif
    print("Contraseña no válida: debe tener al menos 8 caracteres.")
elif not tiene_mayuscula_real: # Falta ':'
    print("Contraseña no válida: debe contener al menos una mayúscula.")
elif not tiene_numero_real: # Esta condición es la que queda si las otras fallan
    print("Contraseña no válida: debe contener al menos un número.")
else:
    # Este else podría ser para un caso inesperado, o si la lógica anterior no cubre todo.
    # En este caso, si ninguna de las condiciones de error anteriores se cumple,
    # y la primera condición de validez total tampoco, hay un problema lógico.
    # Sin embargo, con la estructura dada, el último elif cubre el último caso de error.
    # Para ser explícito, el último mensaje podría ser el de 'tiene_numero'.
    print("Contraseña no válida por una razón no especificada (revisar lógica).")


# Solución más simple SIN bucles (como podría esperarse en Módulo 4 sin adelantar mucho)
# Esta solución no es tan robusta para mayúsculas/números pero se ajusta más a los conocimientos actuales.
# print("\n--- Solución Simplificada (sin bucles) ---")
# contrasena_s = input("Ingresa tu contraseña (para prueba simplificada): ")
# longitud_valida_s = len(contrasena_s) >= 8
#
# # Verificación muy simple (y poco efectiva) de mayúsculas y números
# # Esto es solo para ilustrar la estructura if/elif/else sin bucles
# tiene_alguna_mayuscula_simple = False
# if any(c.isupper() for c in contrasena_s): # Esto ya usa un generador, un poco avanzado
#     tiene_alguna_mayuscula_simple = True
#
# tiene_algun_numero_simple = False
# if any(c.isdigit() for c in contrasena_s): # Esto ya usa un generador
#     tiene_algun_numero_simple = True
#
# if longitud_valida_s and tiene_alguna_mayuscula_simple and tiene_algun_numero_simple:
#     print("Contraseña válida (simplificado).")
# elif not longitud_valida_s:
#     print("Contraseña no válida: debe tener al menos 8 caracteres (simplificado).")
# elif not tiene_alguna_mayuscula_simple:
#     print("Contraseña no válida: debe contener al menos una mayúscula (simplificado).")
# else: # Implica que solo falta el número
#     print("Contraseña no válida: debe contener al menos un número (simplificado).")

```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio valida una contraseña según múltiples criterios, utilizando una secuencia de `if/elif/else` para proporcionar retroalimentación específica. La solución completa para la detección de mayúsculas y números de forma general usa bucles `for`, que es un tema de módulos posteriores. La explicación se centrará en los errores sintácticos y la estructura condicional.

*   **Error 1 Corrección (Falta de dos puntos en `if`):**
    *   El código original era `if len(contrasena) >= 8`.
    *   Debe ser `if len(contrasena) >= 8:`.
    *   **Solución:** `if len(contrasena) >= 8:`

*   **Error 2 Corrección (Uso de `else if` en lugar de `elif`):**
    *   El código original era `else if not longitud_valida:`.
    *   La palabra clave correcta es `elif`.
    *   **Solución:** `elif not longitud_valida:`

*   **Error 3 Corrección (Falta de dos puntos en `elif`):**
    *   El código original era `elif not tiene_mayuscula`.
    *   Debe ser `elif not tiene_mayuscula:`.
    *   **Solución:** `elif not tiene_mayuscula_real:` (usando la variable corregida de la solución general).

**Sobre la Lógica de Verificación General (Mayúsculas y Números):**
El código original simplificaba la detección de mayúsculas y números buscando solo "A" y "1". Una solución más robusta y general requiere iterar sobre cada carácter de la contraseña y verificar su tipo:
```python
# Verificar mayúscula (general)
tiene_mayuscula_real = False
for caracter in contrasena:
    if caracter.isupper():
        tiene_mayuscula_real = True
        break # Optimización: si ya encontramos una, no es necesario seguir.

# Verificar número (general)
tiene_numero_real = False
for caracter in contrasena:
    if caracter.isdigit():
        tiene_numero_real = True
        break
```
Estos bucles `for` y los métodos `.isupper()` y `.isdigit()` son la forma estándar de realizar estas verificaciones. La estructura `if/elif/else` luego utiliza las variables booleanas (`longitud_valida`, `tiene_mayuscula_real`, `tiene_numero_real`) para determinar la validez general y dar mensajes específicos.

La secuencia de `elif` es importante: se verifica primero la longitud, luego la mayúscula, y si ambas están bien pero la contraseña aún no es válida, se asume (en esta estructura simple) que falta el número. Una lógica más exhaustiva podría requerir más `elif` o condiciones combinadas.
</details>
