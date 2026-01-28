Esta es la propuesta final y completa de la Guía de Laboratorio Calificado. Está diseñada bajo un enfoque pedagógico constructivista, orientada a Objetos (POO) y adaptada específicamente para su ejecución en **Google Colab**.

---

# GUÍA DE LABORATORIO CALIFICADO: POO y Análisis de Datos
**Curso:** Programación con Python | **Tema:** Estructuras de Datos, POO y Archivos

## I. PLANTEAMIENTO DEL PROBLEMA
Una empresa de telecomunicaciones ("TelcoData") requiere un sistema automatizado para auditar la calidad de su servicio. Usted ha sido contratado para desarrollar una solución en Python utilizando **Google Colab**.

El sistema debe simular y analizar una encuesta aplicada a una muestra de **20 clientes**. La encuesta evalúa 5 dimensiones del servicio (Cobertura, Atención, Precio, Internet, Promociones) utilizando una escala de Likert de 3 puntos:
*   1: Insatisfecho / Malo
*   2: Neutro / Regular
*   3: Satisfecho / Bueno

**Objetivo:** Desarrollar un programa modular basado en Clases que permita simular la data, visualizarla en consola y exportar reportes CSV para la gerencia.

---

## II. PROCEDIMIENTO A ALTO NIVEL
El desarrollo debe realizarse en un cuaderno de Colab (`.ipynb`) siguiendo estrictamente este flujo de trabajo:

1.  **Definición de Clases:** Diseñar el "molde" para los encuestados y el "controlador" para gestionar el grupo.
2.  **Instanciación (Simulación):** Crear dinámicamente objetos que representen a los 20 clientes, asignándoles respuestas aleatorias.
3.  **Visualización:** Recorrer la lista de objetos para imprimir sus atributos en formato de tabla.
4.  **Persistencia (I/O):** Utilizar los métodos de la clase controladora para escribir la información de los objetos en archivos de texto plano (CSV) dentro del entorno de archivos de Colab.

---

## III. ARQUITECTURA DEL SOFTWARE (Diagrama de Clases)
Para aprobar el laboratorio, su código debe reflejar la siguiente estructura de objetos. No utilice programación lineal desordenada; respete el encapsulamiento.

```text
+-------------------------------------------------------+
|                   EncuestaCliente                     |
|            (Representa una fila de datos)             |
+-------------------------------------------------------+
| - id_cliente : str   (Ej: "CL-001")                   |
| - votos      : list  (Ej: [3, 1, 2, 3, 1])            |
+-------------------------------------------------------+
| + __init__(id: str)                                   |
| + simular_votos() : void                              |
|   (Llena la lista 'votos' con 5 enteros al azar 1-3)  |
| + obtener_datos_csv() : list                          |
|   (Retorna una lista combinada [id, v1, v2...])       |
| + __str__() : str                                     |
|   (Retorna el string formateado para imprimir)        |
+-------------------------------------------------------+
                          ^
                          | (Agregación)
                          |
+-------------------------------------------------------+
|                   AnalizadorDatos                     |
|           (Logica de negocio y reportes)              |
+-------------------------------------------------------+
| - lista_encuestas : list [EncuestaCliente]            |
| - encabezados     : list [str]                        |
+-------------------------------------------------------+
| + __init__()                                          |
| + generar_muestra(n=20) : void                        |
|   (Crea 'n' objetos EncuestaCliente y los guarda)     |
| + imprimir_tabla() : void                             |
| + exportar_data_cruda(filename: str) : void           |
|   (Genera archivo con todas las respuestas)           |
| + exportar_resumen(filename: str) : void              |
|   (Calcula promedios por pregunta y guarda archivo)   |
+-------------------------------------------------------+
```

---

## IV. INSTRUCCIONES TÉCNICAS
1.  **Nombre del Archivo:** Guarde su notebook como `LC04_Apellidos_Nombres.ipynb`.
2.  **Interacción:** Todo el proceso debe controlarse mediante un **Menú Interactivo** dentro de un ciclo `while`.
3.  **Archivos CSV:**
    *   Debe generar `ApellidoPaterno_raw.csv`: Contiene los datos tal cual se generaron.
    *   Debe generar `ApellidoMaterno_stats.csv`: Contiene el análisis (ej. Pregunta vs. Promedio).
    *   *Nota para Colab:* Los archivos se guardarán en la carpeta `/content/` (panel izquierdo de Colab). No es necesario descargarlos automáticamente, basta con que se generen allí.

---

## V. RESULTADOS ESPERADOS (Vistas de Pantalla)
A continuación se muestra cómo debe comportarse la salida de la celda de código en Colab al ejecutar el programa.

### 1. Menú Principal
*(El sistema espera una entrada del usuario)*

```text
==================================================
   AUDITORÍA DE CALIDAD - TELCODATA (POO)
==================================================
[1] Generar Muestra de Clientes (Simulación)
[2] Mostrar Tabulación de Datos
[3] Generar Archivos CSV (Raw & Stats)
[4] Salir
==================================================
Ingrese una opción: 
```

### 2. Opción 2: Mostrar Tabulación
*(Se visualizan los objetos creados. Observe el formato alineado)*

```text
Ingrese una opción: 2

 REPORTE DE ENCUESTAS EN MEMORIA
------------------------------------------------------------
 CLIENTE    |  COB  |  ATN  |  PRE  |  INT  |  PRO 
------------------------------------------------------------
 CL-001     |   3   |   1   |   2   |   3   |   1  
 CL-002     |   2   |   2   |   3   |   1   |   2  
 CL-003     |   1   |   1   |   1   |   2   |   3  
 ...
 CL-020     |   3   |   3   |   2   |   1   |   1  
------------------------------------------------------------
[INFO] Total de registros mostrados: 20
```

### 3. Opción 3: Generación de Archivos
*(Confirmación de que los métodos de exportación funcionaron)*

```text
Ingrese una opción: 3

[PROCESANDO] Exportando datos...
 --> Archivo generado: 'Perez_raw.csv' (Datos detallados)
 --> Archivo generado: 'Gomez_stats.csv' (Resumen estadístico)

[INFO] Revise el panel de archivos de Colab para descargar.
```

### 4. Contenido de los Archivos (Verificación)
*(El estudiante debe verificar que los archivos tengan este contenido interno)*

**A. Perez_raw.csv**
```csv
ID,Cobertura,Atencion,Precio,Internet,Promociones
CL-001,3,1,2,3,1
CL-002,2,2,3,1,2
...
```

**B. Gomez_stats.csv**
```csv
Indicador,Promedio_Satisfaccion
Cobertura,2.45
Atencion,1.80
Precio,2.10
...
```
