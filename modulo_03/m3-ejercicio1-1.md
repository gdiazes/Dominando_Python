# Módulo 3: Ejercicio 1 (Dificultad 1/10) - Saludo Personalizado Interactivo

## Enunciado del Problema

Escribe un programa que solicite al usuario su nombre utilizando la función `input()`.
Luego, el programa debe mostrar un saludo personalizado que incluya el nombre ingresado. Por ejemplo, si el usuario ingresa "Ana", el programa debería mostrar "Hola, Ana. ¡Bienvenida!".

## Código con Errores

```python
# Ejercicio: Saludo personalizado interactivo

nombre_usuario = input(Por favor, ingresa tu nombre: ) # Pista 1
print("Hola, " + nombre_usuario + . ¡Bienvenida!) # Pista 2
# Pista 3: ¿La función input necesita algo más para mostrar el mensaje correctamente?
```

## Pistas para Corregir los Errores

*   **Pista 1:** El mensaje (prompt) que se muestra al usuario con `input()` debe ser una cadena de texto. ¿Está correctamente formateado?
*   **Pista 2:** Al concatenar cadenas, asegúrate de que todas las partes sean cadenas válidas y que el operador de concatenación (`+`) se use correctamente entre ellas. Revisa la puntuación final.
*   **Pista 3:** El mensaje para `input()` debe ser una cadena de texto. Si el texto no está entre comillas, Python lo interpretará de otra manera.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Saludo personalizado interactivo

# El mensaje para input debe ser una cadena
nombre_usuario = input("Por favor, ingresa tu nombre: ")

# La parte final del saludo también debe ser una cadena
print("Hola, " + nombre_usuario + ". ¡Bienvenida!")

# Alternativa usando f-string (más recomendado):
# print(f"Hola, {nombre_usuario}. ¡Bienvenida!")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio introduce la función `input()` para obtener datos del usuario y cómo usar esos datos en una salida.

*   **Error 1 Corrección (Prompt de `input` no es una cadena):**
    *   El código original era `nombre_usuario = input(Por favor, ingresa tu nombre: )`.
    *   El texto `Por favor, ingresa tu nombre: ` que se pasa como argumento a `input()` (el "prompt" o mensaje para el usuario) debe ser una cadena de texto, es decir, estar encerrado entre comillas. Sin comillas, Python intenta interpretar `Por`, `favor,` etc., como variables o palabras clave, lo que causa un `SyntaxError`.
    *   **Solución:** `nombre_usuario = input("Por favor, ingresa tu nombre: ")`

*   **Error 2 Corrección (Error de sintaxis en concatenación):**
    *   El código original era `print("Hola, " + nombre_usuario + . ¡Bienvenida!)`.
    *   El punto `.` después de `nombre_usuario +` y antes de `¡Bienvenida!` está mal colocado y causa un `SyntaxError`. El texto `¡Bienvenida!` tampoco está formateado como una cadena para la concatenación. Se espera que todo el saludo sea una cadena coherente.
    *   **Solución:** `print("Hola, " + nombre_usuario + ". ¡Bienvenida!")`
        *   Aquí, `". ¡Bienvenida!"` es la cadena que se concatena al final.

*   **Error 3 Corrección (Reiteración del Error 1, ya que Pista 1 y Pista 3 apuntan al mismo problema):**
    *   La Pista 3 refuerza que el argumento de `input()` debe ser una cadena. Ya se corrigió en el Error 1.

La solución más idiomática y moderna en Python para este tipo de formato de cadenas es usar f-strings, como se muestra en la alternativa de la solución:
`print(f"Hola, {nombre_usuario}. ¡Bienvenida!")`
Esto es más legible y menos propenso a errores de concatenación que usar `+` múltiples veces.

El programa corregido solicita el nombre al usuario, lo almacena y luego lo usa para imprimir un saludo personalizado.
</details>
