# Módulo 4: Ejercicio 3 (Dificultad 3.15/10) - Acceso a Club con Doble Condición

## Enunciado del Problema

Para ingresar a un club exclusivo, una persona debe cumplir dos condiciones:
1.  Ser mayor de edad (18 años o más).
2.  Tener una membresía activa (representada por una variable booleana).

Escribe un programa que solicite la edad de la persona y si tiene membresía activa (el usuario podría ingresar "si" o "no", que deberás interpretar como un booleano).
Luego, determina si la persona puede ingresar al club y muestra un mensaje apropiado.

## Código con Errores

```python
# Ejercicio: Acceso a club con doble condición

edad_str = input("Ingresa tu edad: ")
edad = int(edad_str)

respuesta_membresia = input("¿Tienes membresía activa? (si/no): ")
tiene_membresia = respuesta_membresia.lower() == "sí" # Pista 1 ('sí' con tilde)

MAYORIA_EDAD = 18

if edad >= MAYORIA_EDAD and tiene_membresia = True: # Pista 2
    mensaje = "Bienvenido al club."
else if edad < MAYORIA_EDAD: # Pista 3
    mensaje = "No cumples con la edad mínima para ingresar."
else:
    mensaje = "No puedes ingresar. Verifica tu edad o estado de membresía."

print(mensaje)
```

## Pistas para Corregir los Errores

*   **Pista 1:** Si el usuario responde "si" (sin tilde) para la membresía, ¿la comparación actual con "sí" (con tilde) funcionará como se espera? Considera cómo manejar la entrada del usuario de forma más robusta.
*   **Pista 2:** En una condición `if`, al verificar si una variable booleana es `True`, ¿es necesario compararla explícitamente con `True` usando `==` (o `=` que es incorrecto aquí)? ¿Y cómo se escribe correctamente la combinación de `if` con `and`?
*   **Pista 3:** La palabra clave para una condición "sino si" en Python es `elif`, no `else if`.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Acceso a club con doble condición

edad_str = input("Ingresa tu edad: ")
edad = int(edad_str)

respuesta_membresia = input("¿Tienes membresía activa? (si/no): ").lower() # Convertir a minúsculas inmediatamente
# Comparar con "si" (sin tilde) para ser más flexible
tiene_membresia = respuesta_membresia == "si"

MAYORIA_EDAD = 18

# Para una variable booleana, simplemente 'if tiene_membresia:' es suficiente.
# No es necesario '== True'.
if edad >= MAYORIA_EDAD and tiene_membresia:
    mensaje = "Bienvenido al club."
# Usar 'elif' en lugar de 'else if'
elif edad < MAYORIA_EDAD and not tiene_membresia:
    mensaje = "No cumples con la edad mínima y no tienes membresía."
elif edad < MAYORIA_EDAD:
    mensaje = "No cumples con la edad mínima para ingresar."
elif not tiene_membresia: # Si llegó aquí, es mayor de edad pero no tiene membresía
    mensaje = "Eres mayor de edad, pero necesitas una membresía activa."
# El 'else' original era un poco ambiguo, se puede mejorar la lógica
# o si las condiciones anteriores cubren todo, podría no ser necesario un 'else' final
# o el else original estaría bien si las condiciones anteriores fueran mutuamente excluyentes
# de forma diferente.
# Para simplificar y asegurar cobertura, un 'else' final puede ser:
else: # Este caso es teóricamente imposible si las anteriores están bien estructuradas.
      # Pero como ejemplo de estructura completa.
    mensaje = "No cumples con los requisitos de ingreso."


print(mensaje)
```
*Nota sobre la lógica del `else` en la solución:* La estructura `if/elif` proporcionada en la solución es más detallada. Una estructura más simple si solo importa el acceso o no, podría ser:
```python
if edad >= MAYORIA_EDAD and tiene_membresia:
    mensaje = "Bienvenido al club."
else:
    # Aquí se podría detallar más por qué no, o un mensaje genérico.
    if edad < MAYORIA_EDAD and not tiene_membresia:
        mensaje = "No cumples con la edad mínima y no tienes membresía."
    elif edad < MAYORIA_EDAD:
        mensaje = "No cumples con la edad mínima."
    elif not tiene_membresia:
        mensaje = "Necesitas una membresía activa."
    else: # Nunca debería llegar aquí con la lógica anterior
        mensaje = "No puedes ingresar."
print(mensaje)
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio introduce el uso del operador `and` para combinar condiciones y la interpretación de entrada de usuario para valores booleanos.

*   **Error 1 Corrección (Comparación de membresía sensible a tildes y mayúsculas/minúsculas):**
    *   El código original era `tiene_membresia = respuesta_membresia.lower() == "sí"`.
    *   Comparar con `"sí"` (con tilde) es muy específico. Si el usuario escribe "si" (común), la condición sería falsa. Es mejor convertir la entrada del usuario a minúsculas (`.lower()`) y compararla con `"si"`.
    *   **Solución:** `respuesta_membresia = input("¿Tienes membresía activa? (si/no): ").lower()` (convertir a minúsculas al recibir la entrada) y luego `tiene_membresia = respuesta_membresia == "si"`.

*   **Error 2 Corrección (Comparación innecesaria/incorrecta con `True`):**
    *   El código original era `if edad >= MAYORIA_EDAD and tiene_membresia = True:`.
    *   Primero, `tiene_membresia = True` es una asignación, no una comparación. Para comparar sería `tiene_membresia == True`.
    *   Segundo, si `tiene_membresia` ya es una variable booleana, no es necesario compararla explícitamente con `True`. Simplemente `if tiene_membresia:` es suficiente y más idiomático en Python.
    *   **Solución:** `if edad >= MAYORIA_EDAD and tiene_membresia:`

*   **Error 3 Corrección (Uso de `else if` en lugar de `elif`):**
    *   El código original era `else if edad < MAYORIA_EDAD:`.
    *   En Python, la palabra clave para "sino si" es `elif`. `else if` no es una construcción válida y causaría un `SyntaxError`.
    *   **Solución:** `elif edad < MAYORIA_EDAD:`

La lógica de los mensajes en las cláusulas `elif` y `else` también fue refinada en la solución para ser más específica sobre por qué no se permite el acceso. Por ejemplo, si es mayor de edad pero no tiene membresía. La estructura `if/elif/else` debe cubrir todas las combinaciones relevantes de manera clara. La solución proporcionada intenta dar mensajes más específicos.
</details>
