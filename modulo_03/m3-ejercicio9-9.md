# Módulo 3: Ejercicio 9 (Dificultad 9.0/10) - Generador de Nombre de Usuario Simple y Email

## Enunciado del Problema

Solicita al usuario su nombre y su apellido.
Luego, el programa debe generar:
1.  Un nombre de usuario simple: las primeras 3 letras del nombre + las primeras 3 letras del apellido, todo en minúsculas.
2.  Una dirección de correo electrónico sugerida: el nombre de usuario generado + "@empresa.com".
Asegúrate de manejar casos donde el nombre o apellido puedan tener menos de 3 letras (en tal caso, usa el nombre/apellido completo).

Ejemplo (Nombre: "Carlos", Apellido: "Santana"):
```
Nombre de usuario sugerido: carsan
Email sugerido: carsan@empresa.com
```
Ejemplo (Nombre: "Ana", Apellido: "Li"):
```
Nombre de usuario sugerido: anali
Email sugerido: anali@empresa.com
```

## Código con Errores

```python
# Ejercicio: Generador de nombre de usuario y email

nombre = input("Ingresa tu nombre: ")
apellido = input("Ingresa tu apellido: ")

# Tomar partes del nombre y apellido
parte_nombre = nombre[0:3].lower # Pista 1
if len(apellido) < 3:
    parte_apellido = apellido.lower()
else:
    parte_apellido = apellido[0:3].lower()

nombre_usuario = parte_nombre + parte_apellido
email_sugerido = nombre_usuario + @empresa.com # Pista 2

print(f"Nombre de usuario sugerido: {nombre_usuario}")
print(f"Email sugerido: {Email_Sugerido}") # Pista 3
```

## Pistas para Corregir los Errores

*   **Pista 1:** Para obtener la subcadena y luego convertirla a minúsculas, el método `.lower()` debe ser llamado correctamente. ¿Qué falta? (Considera también si `nombre[0:3]` podría fallar si el nombre es muy corto).
*   **Pista 2:** Cuando concatenas una cadena con un literal de texto que forma parte de una dirección de correo, ese literal también debe ser una cadena.
*   **Pista 3:** Presta atención a la coincidencia exacta (mayúsculas/minúsculas) entre el nombre de la variable definida y cómo se usa en la f-string.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Generador de nombre de usuario y email

nombre = input("Ingresa tu nombre: ")
apellido = input("Ingresa tu apellido: ")

# Tomar partes del nombre y apellido, manejando longitudes cortas
# y llamando a .lower() con paréntesis
if len(nombre) < 3:
    parte_nombre = nombre.lower()
else:
    parte_nombre = nombre[0:3].lower()

if len(apellido) < 3:
    parte_apellido = apellido.lower()
else:
    parte_apellido = apellido[0:3].lower()

nombre_usuario = parte_nombre + parte_apellido
# El dominio del email debe ser una cadena
email_sugerido = nombre_usuario + "@empresa.com"

print(f"Nombre de usuario sugerido: {nombre_usuario}")
# Nombre de variable corregido en la f-string
print(f"Email sugerido: {email_sugerido}")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio combina slicing de cadenas, métodos de conversión de caso, concatenación y manejo de condiciones simples para la longitud.

*   **Error 1 Corrección (Llamada a método `.lower()` y manejo de longitud):**
    *   El código original era `parte_nombre = nombre[0:3].lower`.
    *   Primero, `.lower` sin paréntesis `()` no ejecuta el método, sino que referencia al método mismo. Debe ser `.lower()`.
    *   Segundo, si `nombre` tiene menos de 3 caracteres, `nombre[0:3]` no dará error (Python maneja bien el slicing que excede los límites), pero es más explícito y robusto manejarlo con una condición, como se hizo para `apellido` y como se pide en el enunciado ("usa el nombre/apellido completo").
    *   **Solución:**
        ```python
        if len(nombre) < 3:
            parte_nombre = nombre.lower()
        else:
            parte_nombre = nombre[0:3].lower()
        ```
        La lógica para `parte_apellido` en el código original ya era correcta en cuanto al manejo de longitud, solo necesitaba la llamada correcta a `.lower()`.

*   **Error 2 Corrección (Literal de dominio no es cadena):**
    *   El código original era `email_sugerido = nombre_usuario + @empresa.com`.
    *   El texto `@empresa.com` debe ser una cadena de texto para poder concatenarse con `nombre_usuario`. Sin comillas, Python lo interpreta como sintaxis inválida (el `@` podría interpretarse como un decorador en contextos avanzados, pero aquí es un error).
    *   **Solución:** `email_sugerido = nombre_usuario + "@empresa.com"`

*   **Error 3 Corrección (Nombre de variable incorrecto en f-string):**
    *   El código original era `print(f"Email sugerido: {Email_Sugerido}")`.
    *   La variable se definió como `email_sugerido` (minúsculas). Usar `Email_Sugerido` (mayúsculas) causaría un `NameError`.
    *   **Solución:** `print(f"Email sugerido: {email_sugerido}")`

El programa corregido maneja adecuadamente las longitudes de nombre y apellido, llama correctamente a los métodos de cadena y construye el email con la sintaxis adecuada.
</details>
