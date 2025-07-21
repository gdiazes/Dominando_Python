# Módulo 14: Ejercicio 2 (Dificultad 3.42/10) - Leer un Archivo Completo

## Enunciado del Problema

Asumiendo que tienes un archivo `saludo.txt` con el siguiente contenido:
```
¡Hola, mundo!
Bienvenido a la lectura de archivos.
```
Escribe un programa que abra `saludo.txt`, lea todo su contenido en una sola variable, y luego imprima ese contenido en la consola.

## Código con Errores

```python
# Ejercicio: Leer un archivo completo

# (Asegúrate de tener un archivo 'saludo.txt' con el contenido del enunciado)

archivo = open("saludo.txt", "r") # Error 1

contenido = archivo.read()
print("Contenido del archivo:")
print(contenido)

# Error 2: La siguiente línea intentaría leer de nuevo, pero el "cursor" ya está al final.
# contenido_extra = archivo.readline() 
# print(f"Contenido extra: {contenido_extra}")

# Error 3: El archivo se abrió pero nunca se cerró explícitamente.
```
```

---
**3. `m14-ejercicio3-3.md`**
```markdown
# Módulo 14: Ejercicio 3 (Dificultad 5.13/10) - Añadir Contenido a un Archivo Existente

## Enunciado del Problema

1.  Crea un archivo `lista_compras.txt` y escribe "1. Manzanas" en él.
2.  Luego, escribe un programa que abra `lista_compras.txt` y **añada** dos nuevos ítems al final del archivo: "2. Leche" y "3. Pan", cada uno en una nueva línea.
3.  El contenido final del archivo debe ser:
    ```
    1. Manzanas
    2. Leche
    3. Pan
    ```

## Código con Errores

```python
# Ejercicio: Añadir contenido a un archivo existente

# Paso 1: Crear el archivo inicial
with open("lista_compras.txt", "w") as f:
    f.write("1. Manzanas\n")

# Paso 2: Programa para añadir nuevos ítems
with open("lista_compras.txt", "w") as archivo: # Error 1
    archivo.write("2. Leche\n")
    archivo.writelines(["3. Pan\n"]) # Error 2

# Error 3: Intento de leer el archivo en modo de escritura
# with open("lista_compras.txt", "w") as f_lectura:
#     contenido = f_lectura.read() 
#     print(contenido)
```
```

---
**4. `m14-ejercicio4-4.md`**
```markdown
# Módulo 14: Ejercicio 4 (Dificultad 6.84/10) - Leer un Archivo Línea por Línea

## Enunciado del Problema

Asumiendo que tienes un archivo `instrucciones.txt` con varias líneas.
Escribe un programa que lea el archivo línea por línea usando un bucle `for`.
Para cada línea leída, imprímela en la consola precedida por el número de línea (empezando en 1).

Ejemplo de salida (para un archivo con 3 líneas):
```
1: Primera instrucción.
2: Segunda instrucción.
3: Tercera instrucción.
```

## Código con Errores

```python
# Ejercicio: Leer un archivo línea por línea

# (Asegúrate de tener un archivo 'instrucciones.txt' con algunas líneas)

numero_linea = 1
with open("instrucciones.txt", "r") as f:
    for linea in f:
        print(f"{numero_linea}: {linea}") # Error 1
        numero_linea # Error 2
    
# Error 3: ¿Qué pasa con el objeto 'f' después de que el bucle 'for' ha terminado?
# ultima_linea = f.readline()
# print(f"Última línea leída de nuevo: {ultima_linea}")
```
```

---
**5. `m14-ejercicio5-5.md`**
```markdown
# Módulo 14: Ejercicio 5 (Dificultad 8.55/10) - Crear una Copia de un Archivo

## Enunciado del Problema

Escribe un programa que cree una copia de un archivo de texto existente.
1.  Abre un archivo de origen para lectura (ej: `original.txt`).
2.  Abre un archivo de destino para escritura (ej: `copia.txt`).
3.  Lee el contenido del archivo de origen y escríbelo en el archivo de destino.

## Código con Errores

```python
# Ejercicio: Crear una copia de un archivo

# (Asegúrate de tener un archivo 'original.txt' con algo de texto)

archivo_origen_nombre = "original.txt"
archivo_copia_nombre = "copia.txt"

with open(archivo_origen_nombre, "r") as origen:
    contenido = origen.read
    with open(archivo_copia_nombre, "w") as destino:
        destino.write(contenido) # Error 1
        
print(f"Archivo '{archivo_origen_nombre}' copiado a '{archivo_copia_nombre}'.")

# Error 2: Intento de abrir ambos archivos en el mismo 'with' de forma incorrecta
# with open(archivo_origen_nombre, "r") as origen, open(archivo_copia_nombre, "a") as destino:
#     destino.writelines(origen) # .writelines espera una lista de cadenas, no un objeto de archivo

# Error 3: Olvidar cerrar los archivos si no se usa 'with'
# origen = open(archivo_origen_nombre, "r")
# destino = open(archivo_copia_nombre, "w")
# destino.write(origen.read())
# # No se llama a origen.close() ni a destino.close()
```
```

---
**6. `m14-ejercicio6-6.md`**
```markdown
# Módulo 14: Ejercicio 6 (Dificultad 10.26/10) - Guardar una Lista en un Archivo

## Enunciado del Problema

1.  Crea una lista de cadenas, por ejemplo, `invitados = ["Ana", "Pedro", "Marta", "Luis"]`.
2.  Escribe un programa que guarde cada nombre de la lista en una nueva línea dentro de un archivo llamado `invitados.txt`.

## Código con Errores

```python
# Ejercicio: Guardar una lista en un archivo

invitados = ["Ana", "Pedro", "Marta", "Luis"]

with open("invitados.txt", "w") as archivo:
    for invitado in invitados:
        archivo.write(invitado) # Error 1
    
    archivo.writelines(invitados) # Error 2 (Duplicaría el contenido y aún sin saltos de línea)

# Error 3 (conceptual): ¿Qué pasaría si la lista contuviera números en lugar de cadenas?
# numeros = [1, 2, 3]
# with open("numeros.txt", "w") as f:
#     f.writelines(numeros) # Esto causaría un TypeError
```
```

---
**7. `m14-ejercicio7-7.md`**
```markdown
# Módulo 14: Ejercicio 7 (Dificultad 11.97/10) - Contar Palabras en un Archivo

## Enunciado del Problema

Escribe un programa que lea un archivo de texto y cuente el número total de palabras que contiene.
Para simplificar, puedes considerar que las palabras están separadas por espacios.

## Código con Errores

```python
# Ejercicio: Contar palabras en un archivo

# (Asegúrate de tener un archivo 'texto_largo.txt')

nombre_archivo = "texto_largo.txt"
contador_palabras = 0

with open(nombre_archivo, "r") as f:
    for linea in f:
        palabras = linea.split # Error 1
        contador_palabras = len(palabras) # Error 2
        
print(f"El archivo '{nombre_archivo}' contiene {contador_palabras} palabras.")

# Error 3: El bucle 'for' está bien, pero si se usara f.read()
# y luego se dividiera, ¿cómo afectaría a la memoria con archivos muy grandes?
# (Este es un error de eficiencia/diseño más que de sintaxis).
```
```

---
**8. `m14-ejercicio8-8.md`**
```markdown
# Módulo 14: Ejercicio 8 (Dificultad 13.68/10) - Buscar una Línea Específica en un Archivo

## Enunciado del Problema

Escribe un programa que busque en un archivo de texto (`datos_usuarios.txt`) una línea que contenga un email específico ingresado por el usuario.
Si encuentra la línea, la debe imprimir. Si no la encuentra después de revisar todo el archivo, debe informar al usuario.

Ejemplo de `datos_usuarios.txt`:
```
ID: 101, Nombre: Ana, Email: ana@example.com
ID: 102, Nombre: Luis, Email: luis@example.com
ID: 103, Nombre: Eva, Email: eva@example.com
```

## Código con Errores

```python
# Ejercicio: Buscar una línea específica en un archivo

email_buscado = input("Ingresa el email a buscar: ")
encontrado = False

with open("datos_usuarios.txt", "r") as f:
    for linea in f:
        if email_buscado in linea:
            print("Usuario encontrado:")
            print(linea.strip())
            break
            encontrado = True # Error 1
    
if not encontrado: # Error 2
    print(f"No se encontró ningún usuario con el email '{email_buscado}'.")

# Error 3 (lógico): ¿Qué pasa si hay espacios extra en la entrada del usuario
# o diferencias de mayúsculas/minúsculas? La búsqueda fallaría.
# Por ejemplo, si el usuario escribe " ana@example.com " (con espacios).
```
```

---
**9. `m14-ejercicio9-9.md`**
```markdown
# Módulo 14: Ejercicio 9 (Dificultad 15.39/10) - Manejo de Errores al Abrir un Archivo

## Enunciado del Problema

Escribe un programa que intente abrir y leer un archivo cuyo nombre será ingresado por el usuario.
El programa debe manejar elegantemente el error `FileNotFoundError` si el archivo no existe, mostrando un mensaje amigable al usuario en lugar de que el programa se detenga.
Si el archivo existe, debe imprimir su contenido.

## Código con Errores

```python
# Ejercicio: Manejo de errores al abrir un archivo

nombre_archivo = input("Ingresa el nombre del archivo a leer: ")

try:
    with open(nombre_archivo, "r") as f:
        contenido = f.read()
    print("--- Contenido del archivo ---")
    print(contenido)
except FileNotFoundError: # Error 1
    print(f"Error: El archivo '{nombre_archivo}' no fue encontrado.")
    # El 'except' está bien, pero el error estará en otro lugar del bloque try/except

# Error 2: ¿Qué pasa si ocurre otro error, por ejemplo, de permisos de lectura?
# El 'except' actual solo captura FileNotFoundError.

# Error 3: La siguiente línea se ejecuta siempre, lo cual podría ser confuso si hubo un error.
print("\n--- Fin del programa ---")
# Para un flujo más claro, a menudo se usa un bloque 'finally' o se estructura diferente.
```
```

---
**10. `m14-ejercicio10-10.md`**
```markdown
# Módulo 14: Ejercicio 10 (Dificultad 17.1/10) - Mini-sistema de Registro (Log) de Eventos

## Enunciado del Problema

Crea una función `registrar_evento(mensaje)` que:
1.  Obtenga la fecha y hora actual.
2.  Formatee un mensaje de log que incluya la fecha/hora y el `mensaje` proporcionado. (Ej: `[2023-10-27 15:45:00] - Usuario inició sesión.`)
3.  Añada esta línea de log a un archivo llamado `app.log`. Cada nuevo log debe ir en una nueva línea.

Luego, escribe un pequeño programa principal que llame a esta función varias veces para registrar diferentes eventos.

## Código con Errores

```python
# Ejercicio: Mini-sistema de registro (log) de eventos

import datetime

def registrar_evento(mensaje):
    ahora = datetime.datetime.now()
    fecha_hora_str = ahora.strftime("[%Y-%m-%d %H:%M:%S]")
    linea_log = fecha_hora_str + " - " + mensaje
    
    with open("app.log", "a") as logfile:
        logfile.write(linea_log) # Error 1

# Programa Principal
registrar_evento("El programa se ha iniciado.")
usuario = input("Ingresa tu nombre de usuario: ")
registrar_evento(f"Usuario '{usuario}' ha iniciado sesión.")
registrar_evento("El programa ha finalizado.")

print("Eventos registrados en 'app.log'")

# Error 2: La función abre el archivo cada vez, lo cual es correcto, pero
# ¿qué pasaría si se usara el modo 'w' en lugar de 'a'?

# Error 3: El mensaje de log no incluye un salto de línea, por lo que todos los
# logs se escribirán en la misma línea en el archivo.
```
```
