# Módulo 14: Manejo de Datos Tabulares con Archivos CSV

## Laboratorio 14 - Guía Paso a Paso

¡Bienvenido al Laboratorio 14! Ya sabes cómo leer y escribir en archivos de texto simples. Ahora, daremos un paso más para trabajar con datos estructurados en uno de los formatos más comunes: los archivos **CSV (Comma-Separated Values)**. Python tiene un módulo incorporado, `csv`, que hace que trabajar con estos archivos sea increíblemente fácil y robusto.

### ¿Qué es un Archivo CSV?
Un archivo CSV es un archivo de texto plano que se utiliza para almacenar datos tabulares (como en una hoja de cálculo o una tabla de base de datos).
*   Cada línea del archivo representa una **fila** de datos.
*   Dentro de cada fila, los valores (o **columnas**) están separados por un delimitador, que comúnmente es una **coma** `,`.
*   La primera línea suele ser una **fila de encabezado** que nombra cada columna.

**Ejemplo de un archivo `estudiantes.csv`:**
```csv
id,nombre,calificacion
101,Ana,95
102,Luis,88
103,Eva,92
```

### El Módulo `csv` de Python
El módulo `csv` nos proporciona herramientas para leer y escribir datos de archivos CSV sin tener que preocuparnos por los detalles de dividir las líneas o manejar comillas dentro de los datos. Para usarlo, primero debemos importarlo:
```python
import csv
```

### Lectura de Archivos CSV
Hay dos formas principales de leer un archivo CSV: como una lista de listas (`csv.reader`) o como una lista de diccionarios (`csv.DictReader`).

#### 1. Leer con `csv.reader` (como listas)
`csv.reader` trata cada fila del archivo CSV como una **lista de cadenas**.

**Pasos:**
1.  Abre el archivo en modo lectura (`'r'`).
2.  Crea un objeto `reader` pasándole el archivo.
3.  Itera sobre el objeto `reader` para acceder a cada fila.

```python
import csv

with open('estudiantes.csv', mode='r', newline='') as archivo_csv:
    lector_csv = csv.reader(archivo_csv)
    
    # Opcional: Omitir la fila de encabezado
    encabezado = next(lector_csv)
    print(f"Encabezado: {encabezado}")
    
    print("\nContenido:")
    for fila in lector_csv:
        # 'fila' es una lista de cadenas: ['101', 'Ana', '95']
        id_estudiante = int(fila[0])
        nombre = fila[1]
        calificacion = int(fila[2])
        print(f"ID: {id_estudiante}, Nombre: {nombre}, Calificación: {calificacion}")
```
*Nota sobre `newline=''`*: Es una buena práctica recomendada en la documentación de Python para evitar problemas con los finales de línea en diferentes sistemas operativos.

#### 2. Leer con `csv.DictReader` (como diccionarios - ¡muy recomendado!)
`csv.DictReader` es aún más poderoso. Trata cada fila como un **diccionario**, donde las claves son los nombres de las columnas (tomados de la primera fila del encabezado) y los valores son los datos de esa fila.

```python
import csv

with open('estudiantes.csv', mode='r', newline='') as archivo_csv:
    lector_dict = csv.DictReader(archivo_csv)
    
    print("Contenido (como diccionarios):")
    for fila_dict in lector_dict:
        # 'fila_dict' es un diccionario: {'id': '101', 'nombre': 'Ana', 'calificacion': '95'}
        # ¡Ojo! Los valores siguen siendo cadenas, hay que convertirlos si es necesario.
        id_estudiante = int(fila_dict['id'])
        nombre = fila_dict['nombre']
        calificacion = int(fila_dict['calificacion'])
        print(f"ID: {id_estudiante}, Nombre: {nombre}, Calificación: {calificacion}")
```

### Escritura en Archivos CSV
De manera similar a la lectura, tenemos `csv.writer` y `csv.DictWriter`.

#### 1. Escribir con `csv.writer` (desde listas)
`csv.writer` te permite escribir filas en un archivo CSV a partir de listas.

**Pasos:**
1.  Abre el archivo en modo escritura (`'w'`).
2.  Crea un objeto `writer`.
3.  Usa `.writerow()` para escribir una sola fila (una lista).
4.  Usa `.writerows()` para escribir múltiples filas (una lista de listas).

```python
import csv

encabezado = ['producto', 'precio', 'stock']
datos = [
    ['Laptop', 1200, 50],
    ['Teclado', 75, 200],
    ['Ratón', 25, 500]
]

with open('inventario.csv', mode='w', newline='') as archivo_csv:
    escritor_csv = csv.writer(archivo_csv)
    
    escritor_csv.writerow(encabezado)  # Escribir la fila de encabezado
    escritor_csv.writerows(datos)     # Escribir todas las filas de datos
    
print("Archivo 'inventario.csv' creado exitosamente.")
```

#### 2. Escribir con `csv.DictWriter` (desde diccionarios)
`csv.DictWriter` te permite escribir filas a partir de diccionarios. Es muy útil porque no tienes que preocuparte por el orden de los datos, solo por los nombres de las claves.

**Pasos:**
1.  Define los nombres de las columnas (`fieldnames`).
2.  Abre el archivo en modo escritura (`'w'`).
3.  Crea un objeto `DictWriter`, pasándole el archivo y los `fieldnames`.
4.  Usa `.writeheader()` para escribir la fila de encabezado.
5.  Usa `.writerow()` para escribir una sola fila (un diccionario).
6.  Usa `.writerows()` para escribir múltiples filas (una lista de diccionarios).

```python
import csv

fieldnames = ['nombre', 'edad', 'ciudad']
datos_dict = [
    {'nombre': 'Carlos', 'edad': 34, 'ciudad': 'Madrid'},
    {'nombre': 'Laura', 'edad': 29, 'ciudad': 'Bogotá'},
    {'nombre': 'Kenji', 'edad': 41, 'ciudad': 'Tokio'}
]

with open('usuarios.csv', mode='w', newline='') as archivo_csv:
    escritor_dict = csv.DictWriter(archivo_csv, fieldnames=fieldnames)
    
    escritor_dict.writeheader()      # Escribir el encabezado: nombre,edad,ciudad
    escritor_dict.writerows(datos_dict) # Escribir la lista de diccionarios
    
print("Archivo 'usuarios.csv' creado exitosamente.")
```

Manejar archivos CSV es una habilidad de programación de datos fundamental. El módulo `csv` de Python te da las herramientas para hacerlo de manera eficiente y sin errores.

---

## Ejercicios del Módulo 14 (CSV)

Estos ejercicios te guiarán en la lectura y escritura de archivos CSV, utilizando tanto el enfoque basado en listas como el basado en diccionarios.

1.  **Escribir Datos Simples a un CSV (`csv.writer`)** (Dificultad 2.0): [m14_csv-ejercicio1-1.md](m14_csv-ejercicio1-1.md)
2.  **Leer un CSV Básico (`csv.reader`)** (Dificultad 3.0): [m14_csv-ejercicio2-2.md](m14_csv-ejercicio2-2.md)
3.  **Calcular un Promedio desde un CSV (`csv.reader`)** (Dificultad 4.0): [m14_csv-ejercicio3-3.md](m14_csv-ejercicio3-3.md)
4.  **Escribir una Lista de Diccionarios a CSV (`csv.DictWriter`)** (Dificultad 5.0): [m14_csv-ejercicio4-4.md](m14_csv-ejercicio4-4.md)
5.  **Leer un CSV como Diccionarios (`csv.DictReader`)** (Dificultad 6.0): [m14_csv-ejercicio5-5.md](m14_csv-ejercicio5-5.md)
6.  **Añadir una Nueva Fila a un CSV Existente** (Dificultad 7.0): [m14_csv-ejercicio6-6.md](m14_csv-ejercicio6-6.md)
7.  **Filtrar Datos de un CSV** (Dificultad 8.0): [m14_csv-ejercicio7-7.md](m14_csv-ejercicio7-7.md)
8.  **Modificar un CSV (Leer, Modificar en Memoria, Escribir)** (Dificultad 9.0): [m14_csv-ejercicio8-8.md](m14_csv-ejercicio8-8.md)
9.  **Manejo de Diferentes Delimitadores** (Dificultad 10.0): [m14_csv-ejercicio9-9.md](m14_csv-ejercicio9-9.md)
10. **Mini-Proyecto: Convertir CSV a una Lista de Objetos** (Dificultad 11.0): [m14_csv-ejercicio10-10.md](m14_csv-ejercicio10-10.md)


