# Módulo 14: Persistiendo Datos: Archivos en Python

## Laboratorio 14 - Guía Paso a Paso

¡Bienvenido al Laboratorio 14! Hasta ahora, toda la información que nuestros programas han manejado (variables, listas, diccionarios) se pierde cuando el programa termina. Para guardar datos de forma permanente, necesitamos escribirlos en **archivos**. En este laboratorio, aprenderás a leer y escribir en archivos de texto, una habilidad fundamental para que tus programas puedan recordar información entre ejecuciones.

### El Proceso Básico de Manejo de Archivos
Trabajar con archivos en Python generalmente sigue tres pasos:
1.  **Abrir** el archivo.
2.  **Realizar operaciones** (leer o escribir).
3.  **Cerrar** el archivo.

### Abrir Archivos: La Función `open()`
La función incorporada `open()` se usa para abrir un archivo y devuelve un objeto de archivo.
**Sintaxis:** `open(ruta_del_archivo, modo)`

*   `ruta_del_archivo`: Una cadena con el nombre y la ruta del archivo (ej: `"datos.txt"` o `"C:/usuarios/docs/info.txt"`).
*   `modo`: Una cadena que especifica cómo se abrirá el archivo.

**Modos de Apertura Comunes:**
*   `'r'` (Read - Leer): Modo por defecto. Abre un archivo para lectura. Causa un error (`FileNotFoundError`) si el archivo no existe.
*   `'w'` (Write - Escribir): Abre un archivo para escritura. **Crea el archivo si no existe.** **Sobrescribe completamente el contenido si ya existe.**
*   `'a'` (Append - Añadir): Abre un archivo para añadir contenido. **Crea el archivo si no existe.** El nuevo contenido se escribe al **final** del archivo, sin borrar lo anterior.
*   `'x'` (Exclusive Creation - Creación Exclusiva): Crea un nuevo archivo y lo abre para escritura. Falla con `FileExistsError` si el archivo ya existe.

Puedes añadir un `'+'` al modo para habilitar lectura y escritura simultáneamente (ej: `'r+'`, `'w+'`).

### El Contexto `with open(...)`: La Forma Recomendada
La forma más segura y recomendada de trabajar con archivos es usando la declaración `with`. Esta sintaxis asegura que el archivo se **cierre automáticamente** al salir del bloque `with`, incluso si ocurren errores.
```python
with open("mi_archivo.txt", "w") as archivo:
    # 'archivo' es la variable que representa el objeto de archivo
    # El archivo se abre aquí
    # ... operaciones de escritura ...
# El archivo se cierra automáticamente aquí, al salir del bloque 'with'
```

### Escribir en Archivos
Dentro de un bloque `with` abierto en modo `'w'` o `'a'`.

*   `.write(cadena)`: Escribe una cadena de texto en el archivo. **No añade un salto de línea automáticamente.**
    ```python
    lineas_a_escribir = ["Primera línea.", "Segunda línea."]
    with open("diario.txt", "w") as f: # 'f' es un nombre común para el objeto de archivo
        f.write("Este es mi diario.\n") # \n para un salto de línea manual
        f.write("Hoy aprendí sobre archivos en Python.\n")
        f.write(str(12345)) # .write() solo acepta cadenas, hay que convertir otros tipos
    ```
*   `.writelines(lista_de_cadenas)`: Escribe todos los elementos de una lista de cadenas en el archivo. **Tampoco añade saltos de línea.**
    ```python
    lineas = ["Línea A\n", "Línea B\n", "Línea C\n"]
    with open("lista.txt", "w") as f:
        f.writelines(lineas)
    ```

### Leer de Archivos
Dentro de un bloque `with` abierto en modo `'r'`.

*   `.read()`: Lee el **contenido completo** del archivo y lo devuelve como una sola cadena de texto.
    ```python
    with open("diario.txt", "r") as f:
        contenido_completo = f.read()
    print(contenido_completo)
    ```
*   `.readline()`: Lee **una sola línea** del archivo, desde la posición actual hasta el siguiente salto de línea (`\n`). Devuelve una cadena vacía al final del archivo.
    ```python
    with open("lista.txt", "r") as f:
        primera_linea = f.readline()
        segunda_linea = f.readline()
    print(f"Primera: {primera_linea.strip()}") # .strip() para quitar el \n final
    print(f"Segunda: {segunda_linea.strip()}")
    ```
*   `.readlines()`: Lee **todas las líneas** del archivo y las devuelve como una **lista de cadenas**, donde cada cadena es una línea y conserva el `\n` final.
    ```python
    with open("lista.txt", "r") as f:
        todas_las_lineas = f.readlines()
    print(todas_las_lineas) # Salida: ['Línea A\n', 'Línea B\n', 'Línea C\n']
    ```

**Iterar sobre un Archivo (la forma más común de leer línea por línea):**
El objeto de archivo es iterable, lo que significa que puedes usarlo directamente en un bucle `for` para leer el archivo línea por línea. Esta es la forma más eficiente en memoria para leer archivos grandes.
```python
with open("lista.txt", "r") as f:
    print("Leyendo línea por línea:")
    for linea in f:
        print(linea.strip()) # .strip() es útil para quitar espacios y saltos de línea
```

### Manejo de Rutas de Archivo
*   **Ruta Relativa:** Si solo proporcionas el nombre del archivo (ej: `"datos.txt"`), Python buscará (o creará) el archivo en el mismo directorio donde se está ejecutando el script.
*   **Ruta Absoluta:** Puedes proporcionar la ruta completa del archivo en tu sistema (ej: `"C:/Users/TuUsuario/Documents/datos.txt"` en Windows o `"/home/tu_usuario/documentos/datos.txt"` en Linux/macOS). Para evitar problemas con las barras invertidas `\` en Windows, puedes usar barras normales `/` o cadenas "raw" `r"C:\Users..."`.

### Introducción a `try-except` con Archivos
Aunque `with` maneja el cierre, no previene errores como `FileNotFoundError` (si intentas leer un archivo que no existe). Para manejar estos errores de forma elegante, se usa `try-except`.
```python
try:
    with open("archivo_que_no_existe.txt", "r") as f:
        print(f.read())
except FileNotFoundError:
    print("¡Error! El archivo no fue encontrado.")
except Exception as e:
    print(f"Ocurrió un error inesperado: {e}")
```
El manejo de archivos es una habilidad esencial que te permite crear programas mucho más potentes y persistentes, capaces de interactuar con el sistema de archivos de una computadora.

---

## Ejercicios del Módulo 14

Estos ejercicios te guiarán a través de la escritura, lectura y manipulación de archivos de texto.

1.  **Escribir en un Archivo Simple** (Dificultad 1.71): [m14-ejercicio1-1.md](m14-ejercicio1-1.md)
2.  **Leer un Archivo Completo** (Dificultad 3.42): [m14-ejercicio2-2.md](m14-ejercicio2-2.md)
3.  **Añadir Contenido a un Archivo Existente** (Dificultad 5.13): [m14-ejercicio3-3.md](m14-ejercicio3-3.md)
4.  **Leer un Archivo Línea por Línea** (Dificultad 6.84): [m14-ejercicio4-4.md](m14-ejercicio4-4.md)
5.  **Crear una Copia de un Archivo** (Dificultad 8.55): [m14-ejercicio5-5.md](m14-ejercicio5-5.md)
6.  **Guardar una Lista en un Archivo** (Dificultad 10.26): [m14-ejercicio6-6.md](m14-ejercicio6-6.md)
7.  **Contar Palabras en un Archivo** (Dificultad 11.97): [m14-ejercicio7-7.md](m14-ejercicio7-7.md)
8.  **Buscar una Línea Específica en un Archivo** (Dificultad 13.68): [m14-ejercicio8-8.md](m14-ejercicio8-8.md)
9.  **Manejo de Errores al Abrir un Archivo** (Dificultad 15.39): [m14-ejercicio9-9.md](m14-ejercicio9-9.md)
10. **Mini-sistema de Registro (Log) de Eventos** (Dificultad 17.1): [m14-ejercicio10-10.md](m14-ejercicio10-10.md)

