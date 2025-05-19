# Módulo 1: Primeros Pasos en Python - ¡Tu Aventura Comienza!

## Laboratorio 1 - Guía Paso a Paso

¡Bienvenido/a al fascinante mundo de la programación con Python! Este es el primer paso en un viaje que te permitirá crear soluciones, automatizar tareas y, quién sabe, ¡quizás construir la próxima gran aplicación!

En este primer laboratorio, nos familiarizaremos con los conceptos más básicos: qué es Python, cómo decirle a la computadora que muestre mensajes, y cómo escribir nuestras primeras líneas de código. No te preocupes si todo es nuevo; iremos paso a paso.

### ¿Qué es la Programación?
Programar es, en esencia, dar instrucciones a una computadora para que realice una tarea específica. Estas instrucciones deben ser muy precisas y estar escritas en un lenguaje que la computadora pueda entender. Hay muchos lenguajes de programación, y nosotros aprenderemos Python.

### ¿Por qué Python?
Python es uno de los lenguajes de programación más populares y demandados en el mundo por varias razones:
*   **Sintaxis Sencilla y Legible:** Su código se parece mucho al inglés, lo que facilita su aprendizaje y lectura, especialmente para principiantes.
*   **Versátil:** Se usa en una gran variedad de campos: desarrollo web, ciencia de datos, inteligencia artificial, scripting, desarrollo de juegos, y mucho más.
*   **Gran Comunidad y Muchas Librerías:** Existe una enorme comunidad de desarrolladores de Python y una vasta colección de "librerías" (código preescrito) que puedes usar para realizar tareas complejas sin tener que programarlo todo desde cero.
*   **Interpretado:** Python es un lenguaje interpretado, lo que significa que puedes ejecutar tu código línea por línea y ver los resultados inmediatamente, facilitando la depuración.

### Instalación de Python y un IDE
Para escribir y ejecutar código Python, necesitas dos cosas principales:
1.  **El Intérprete de Python:** Es el programa que entiende y ejecuta tu código Python. Puedes descargarlo gratuitamente desde el sitio web oficial: [python.org](https://www.python.org/downloads/). Asegúrate de marcar la casilla "Add Python to PATH" (o similar) durante la instalación en Windows.
2.  **Un Entorno de Desarrollo Integrado (IDE) o Editor de Código:** Es una aplicación que te facilita escribir, organizar y ejecutar tu código. Algunas opciones populares para principiantes y profesionales son:
    *   **Thonny:** Un IDE muy simple y genial para principiantes. Viene con Python incorporado en algunas versiones. ([thonny.org](https://thonny.org/))
    *   **Visual Studio Code (VS Code):** Un editor de código muy potente y popular, con excelente soporte para Python a través de extensiones. ([code.visualstudio.com](https://code.visualstudio.com/))
    *   **PyCharm Community Edition:** Un IDE muy completo, específico para Python. ([jetbrains.com/pycharm/download/](https://www.jetbrains.com/pycharm/download/))

Para este curso, puedes usar el que te resulte más cómodo. Si eres completamente nuevo, Thonny puede ser una excelente opción para empezar.

**Verificar la Instalación (Opcional, desde la terminal):**
Una vez instalado Python, puedes abrir una terminal o símbolo del sistema (CMD en Windows, Terminal en macOS/Linux) y escribir:
`python --version` o `python3 --version`
Debería mostrarte la versión de Python instalada.

### Tu Primer Programa: `print("Hola, Mundo!")`
La tradición al aprender un nuevo lenguaje de programación es empezar con un programa que muestre el mensaje "Hola, Mundo!" en la pantalla.
En Python, esto es increíblemente simple. Abre tu IDE o editor, crea un nuevo archivo (por ejemplo, `hola.py` - los archivos de Python suelen tener la extensión `.py`), y escribe la siguiente línea:

```python
print("Hola, Mundo!")
```

**Explicación:**
*   `print`: Es una **función** incorporada en Python. Una función es un bloque de código que realiza una tarea específica. La función `print()` se utiliza para mostrar información en la pantalla (o consola).
*   `()`: Los paréntesis se usan después del nombre de una función para indicar que la estamos "llamando" o ejecutando, y dentro de ellos podemos pasarle "argumentos" (datos que la función necesita para trabajar).
*   `"Hola, Mundo!"`: Es una **cadena de texto** (o *string* en inglés). En Python, el texto se escribe entre comillas dobles (`"`) o comillas simples (`'`). Este es el argumento que le estamos pasando a la función `print()` para que lo muestre.

**Ejecutar tu Programa:**
La forma de ejecutar el programa varía ligeramente según el IDE:
*   **Thonny:** Hay un botón verde de "Play" o "Run".
*   **VS Code:** Puedes hacer clic derecho en el editor y seleccionar "Run Python File in Terminal", o usar el botón de "Play" si tienes la extensión de Python configurada.
*   **Desde la terminal:** Navega hasta la carpeta donde guardaste tu archivo `hola.py` y escribe: `python hola.py` o `python3 hola.py`.

Si todo va bien, deberías ver el texto `Hola, Mundo!` impreso en la consola de salida de tu IDE o en la terminal. ¡Felicidades, has escrito y ejecutado tu primer programa en Python!

### La Función `print()` - Más Detalles
La función `print()` es muy versátil:
*   **Mostrar números:**
    ```python
    print(123)
    print(3.14159)
    ```
*   **Mostrar múltiples elementos:** Puedes pasarle varios argumentos separados por comas, y `print()` los mostrará separados por un espacio por defecto.
    ```python
    print("Mi edad es:", 30, "y mi ciudad es:", "Madrid")
    # Salida: Mi edad es: 30 y mi ciudad es: Madrid
    ```

### Comentarios en Python (`#`)
A medida que tus programas crezcan, querrás añadir notas para explicar qué hace tu código. Estas notas se llaman **comentarios**. Python ignora los comentarios cuando ejecuta el código; son solo para los humanos.
En Python, cualquier texto en una línea que siga al símbolo de almohadilla (`#`) es un comentario.

```python
# Este es un comentario de línea completa. Explica lo que hace el programa.
print("Este mensaje se mostrará.") # Este es un comentario al final de una línea.
# print("Este mensaje no se mostrará porque la línea está comentada.")
```
Es una buena práctica usar comentarios para hacer tu código más entendible.

### Errores Comunes al Inicio
No te preocupes si cometes errores; ¡es parte del aprendizaje! Python te dará mensajes de error que intentan ayudarte a encontrar el problema.
*   **`SyntaxError` (Error de Sintaxis):** Ocurre cuando escribes algo que Python no entiende, como olvidar cerrar unas comillas o un paréntesis, o escribir mal una palabra clave.
    ```python
    # print("Hola Mundo!) # Error: falta la comilla de cierre
    # prin("Hola Mundo!") # Error: 'prin' no es una función conocida (a menos que la hayas definido)
    ```
*   **`IndentationError` (Error de Indentación):** Python usa la indentación (espacios al inicio de una línea) para definir bloques de código. Por ahora, asegúrate de que todas tus líneas de código comiencen en la misma columna (sin espacios extra al inicio), a menos que estés dentro de una estructura que lo requiera (lo veremos más adelante).
    ```python
    #  print("Hola") # Esto podría dar un IndentationError si no se espera indentación aquí.
    ```

### Ejecución Secuencial de Instrucciones
Por defecto, Python ejecuta las instrucciones de tu programa una por una, en el orden en que aparecen en el archivo, de arriba hacia abajo.

```python
print("Línea 1")
print("Línea 2")
print("Línea 3")
```
**Salida:**
```
Línea 1
Línea 2
Línea 3
```

¡Eso es todo por este primer laboratorio! Has aprendido mucho. Ahora, ¡a practicar con los ejercicios!

---

## Ejercicios del Módulo 1

A continuación, se listan los ejercicios propuestos para este módulo. Todos se enfocan en el uso de la función `print()` para mostrar diferentes tipos de mensajes y datos, y en la correcta sintaxis de Python.

1.  **Saludo Básico** (Dificultad 1): [m1-ejercicio1-1.md](m1-ejercicio1-1.md)
2.  **Presentación Personal** (Dificultad 2): [m1-ejercicio2-2.md](m1-ejercicio2-2.md)
3.  **Lista de Compras** (Dificultad 3): [m1-ejercicio3-3.md](m1-ejercicio3-3.md)
4.  **Poema Corto** (Dificultad 4): [m1-ejercicio4-4.md](m1-ejercicio4-4.md)
5.  **Datos de un Libro** (Dificultad 5): [m1-ejercicio5-5.md](m1-ejercicio5-5.md)
6.  **Instrucciones Simples** (Dificultad 6): [m1-ejercicio6-6.md](m1-ejercicio6-6.md)
7.  **Conversación Simulada** (Dificultad 7): [m1-ejercicio7-7.md](m1-ejercicio7-7.md)
8.  **Figuras con Caracteres** (Dificultad 8): [m1-ejercicio8-8.md](m1-ejercicio8-8.md)
9.  **Información Tabulada Simple** (Dificultad 9): [m1-ejercicio9-9.md](m1-ejercicio9-9.md)
10. **Mensaje de Bienvenida Elaborado** (Dificultad 10): [m1-ejercicio10-10.md](m1-ejercicio10-10.md)

