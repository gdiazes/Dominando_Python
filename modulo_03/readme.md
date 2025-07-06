# Módulo 3: Interactuando con el Usuario y Cadenas de Texto en Profundidad

## Laboratorio 3 - Guía Paso a Paso

¡Bienvenido al Laboratorio 3! Hasta ahora, nuestros programas han trabajado con datos que definimos nosotros mismos dentro del código. En este laboratorio, aprenderemos a hacer nuestros programas **interactivos** usando la función `input()` para solicitar datos al usuario. Además, profundizaremos en las **cadenas de texto (`str`)**, explorando cómo formatearlas y manipularlas con diversas funciones y métodos.

### Interactuando con el Usuario: La Función `input()`
La función `input()` permite a tu programa pausar y esperar a que el usuario escriba algo en la consola y presione Enter. El texto que el usuario ingresa es devuelto por la función como una **cadena de texto (`str`)**.

```python
# input() sin mensaje
print("Por favor, escribe tu nombre:")
nombre_usuario = input() # El programa espera aquí
print("Hola,", nombre_usuario)

# input() con un mensaje (prompt)
ciudad_usuario = input("¿En qué ciudad vives? ") # El mensaje se muestra antes de esperar la entrada
print("¡Qué bonito es", ciudad_usuario + "!")
```
**Importante: `input()` siempre devuelve una cadena de texto.**
Si necesitas que la entrada del usuario sea un número (para hacer cálculos), debes convertirla explícitamente usando `int()` o `float()`.

```python
edad_texto = input("¿Cuántos años tienes? ")
edad_numero = int(edad_texto) # Convertimos la cadena a entero

print("Dentro de 5 años, tendrás", edad_numero + 5, "años.")

precio_texto = input("Introduce el precio del producto: ")
precio_numero = float(precio_texto) # Convertimos la cadena a flotante
print("El precio con IVA (21%) es:", precio_numero * 1.21)
```
Si el usuario ingresa un texto que no puede convertirse al tipo deseado (por ejemplo, escribe "hola" cuando se espera un número para `int()`), el programa generará un error (`ValueError`). El manejo de errores se verá en módulos posteriores.

### Formateo Avanzado de Cadenas: f-strings
Las **f-strings** (cadenas literales formateadas) son una forma moderna, concisa y muy legible de incrustar expresiones dentro de cadenas de texto en Python (disponibles desde Python 3.6). Se definen prefijando la cadena con una `f` o `F` y escribiendo las expresiones entre llaves `{}`.

```python
nombre = "Carlos"
edad = 30
profesion = "ingeniero"

# Forma tradicional (concatenando o usando comas en print)
print("Me llamo " + nombre + ", tengo " + str(edad) + " años y soy " + profesion + ".")
print("Me llamo", nombre, ", tengo", edad, "años y soy", profesion + ".")

# Con f-strings
mensaje_fstring = f"Me llamo {nombre}, tengo {edad} años y soy {profesion}."
print(mensaje_fstring)
# Salida para todos: Me llamo Carlos, tengo 30 años y soy ingeniero.

# También puedes poner expresiones directamente dentro de las llaves:
numero1 = 10
numero2 = 5
print(f"La suma de {numero1} y {numero2} es {numero1 + numero2}.")
# Salida: La suma de 10 y 5 es 15.
```
Las f-strings también permiten opciones de formato más avanzadas, como especificar el número de decimales para flotantes:
```python
precio = 45.6789
print(f"El precio es: ${precio:.2f}") # :.2f formatea el flotante a 2 decimales
# Salida: El precio es: $45.68 (nota el redondeo)
```

### Métodos Comunes de Cadenas de Texto
Las cadenas de texto en Python son objetos y tienen muchos **métodos** útiles (funciones asociadas a un objeto) que puedes usar para manipularlas. Los métodos se llaman usando la sintaxis `nombre_de_la_cadena.nombre_del_metodo()`.

Aquí algunos de los más comunes:

*   **`len(cadena)` (Función, no método):** Devuelve la longitud de la cadena (número de caracteres).
    ```python
    texto = "Hola"
    print(len(texto)) # Salida: 4
    ```

*   **`.upper()`:** Devuelve una nueva cadena con todos los caracteres en mayúsculas.
    ```python
    saludo = "buenos días"
    print(saludo.upper()) # Salida: BUENOS DÍAS
    ```

*   **`.lower()`:** Devuelve una nueva cadena con todos los caracteres en minúsculas.
    ```python
    grito = "¡AYUDA!"
    print(grito.lower()) # Salida: ¡ayuda!
    ```

*   **`.capitalize()`:** Devuelve una nueva cadena con el primer carácter en mayúscula y el resto en minúsculas.
    ```python
    frase = "me gusta python."
    print(frase.capitalize()) # Salida: Me gusta python.
    ```

*   **`.title()`:** Devuelve una nueva cadena con el primer carácter de cada palabra en mayúscula.
    ```python
    titulo_libro = "el señor de los anillos"
    print(titulo_libro.title()) # Salida: El Señor De Los Anillos
    ```

*   **`.strip()`:** Devuelve una nueva cadena eliminando los espacios en blanco (o caracteres especificados) del inicio y del final.
    *   `.lstrip()`: elimina del inicio (left strip).
    *   `.rstrip()`: elimina del final (right strip).
    ```python
    usuario_con_espacios = "  admin  "
    print(f"'{usuario_con_espacios.strip()}'")  # Salida: 'admin'
    print(f"'{usuario_con_espacios.lstrip()}'") # Salida: 'admin  '
    print(f"'{usuario_con_espacios.rstrip()}'") # Salida: '  admin'
    ```

*   **`.replace(viejo, nuevo)`:** Devuelve una nueva cadena donde todas las ocurrencias de la subcadena `viejo` son reemplazadas por `nuevo`.
    ```python
    descripcion = "Python es divertido y Python es fácil."
    print(descripcion.replace("Python", "Programar"))
    # Salida: Programar es divertido y Programar es fácil.
    ```

*   **`.find(subcadena)`:** Devuelve el índice de la primera ocurrencia de `subcadena`. Si no se encuentra, devuelve `-1`.
    ```python
    email = "usuario@ejemplo.com"
    print(email.find("@"))    # Salida: 7 (el índice donde empieza "@")
    print(email.find("."))    # Salida: 15
    print(email.find("xyz"))  # Salida: -1
    ```

*   **`.startswith(prefijo)`:** Devuelve `True` si la cadena comienza con `prefijo`, `False` en caso contrario.
*   **`.endswith(sufijo)`:** Devuelve `True` si la cadena termina con `sufijo`, `False` en caso contrario.
    ```python
    archivo = "documento.txt"
    print(archivo.startswith("doc")) # Salida: True
    print(archivo.endswith(".pdf"))  # Salida: False
    ```

**Importante:** Los métodos de cadena como `.upper()`, `.lower()`, `.replace()`, etc., **no modifican la cadena original**. Devuelven una *nueva* cadena con los cambios. Si quieres conservar el cambio, debes reasignarlo a una variable (puede ser la misma).
```python
mi_texto = "hola"
texto_mayusculas = mi_texto.upper()
print(mi_texto)         # Salida: hola (original no cambia)
print(texto_mayusculas) # Salida: HOLA

# Para cambiar la original:
mi_texto = mi_texto.upper()
print(mi_texto)         # Salida: HOLA
```

### Concatenación y Repetición de Cadenas
Ya hemos visto la concatenación con `+`. También puedes repetir cadenas usando el operador `*`.
```python
parte1 = "Hola"
parte2 = "Mundo"
saludo_completo = parte1 + " " + parte2 # Añadimos un espacio
print(saludo_completo) # Salida: Hola Mundo

linea_decorativa = "-" * 20 # Repite el guion 20 veces
print(linea_decorativa)     # Salida: --------------------
```

Dominar la entrada de usuario y la manipulación de cadenas te permitirá crear programas mucho más dinámicos y útiles. ¡Es hora de ponerlo en práctica!

---

## Ejercicios del Módulo 3

Los siguientes ejercicios te ayudarán a practicar el uso de `input()`, la conversión de tipos de datos de entrada, el formateo con f-strings y la aplicación de diversos métodos de cadenas.

1.  **Saludo Personalizado Interactivo** (Dificultad 1): [m3-ejercicio1-1.md](m3-ejercicio1-1.md)
2.  **Suma de Dos Números Ingresados por Usuario** (Dificultad 2): [m3-ejercicio2-2.md](m3-ejercicio2-2.md)
3.  **Información Personal con f-strings** (Dificultad 3): [m3-ejercicio3-3.md](m3-ejercicio3-3.md)
4.  **Convertir a Mayúsculas y Minúsculas** (Dificultad 4): [m3-ejercicio4-4.md](m3-ejercicio4-4.md)
5.  **Contar Caracteres de un Nombre** (Dificultad 5): [m3-ejercicio5-5.md](m3-ejercicio5-5.md)
6.  **Limpiar Espacios de Entrada** (Dificultad 6): [m3-ejercicio6-6.md](m3-ejercicio6-6.md)
7.  **Reemplazar Palabras en una Frase** (Dificultad 7): [m3-ejercicio7-7.md](m3-ejercicio7-7.md)
8.  **Verificar Prefijo y Sufijo** (Dificultad 8): [m3-ejercicio8-8.md](m3-ejercicio8-8.md)
9.  **Generador de Nombre de Usuario Simple** (Dificultad 9): [m3-ejercicio9-9.md](m3-ejercicio9-9.md)
10. **Mini Formulario Interactivo** (Dificultad 10): [m3-ejercicio10-10.md](m3-ejercicio10-10.md)

```

