### **Guía de Laboratorio: Sistema de Gestión de Tareas Personales**

**Título del Proyecto:** "Mi Gestor de Tareas v1.0"

**Objetivo del Proyecto:**
¡Vamos a construir una aplicación real! Crearás un programa de consola para gestionar tus tareas personales. Con este proyecto, pondrás en práctica todo lo que has aprendido sobre **diccionarios** para almacenar datos, **tuplas** para información fija, el módulo `datetime` para manejar **fechas**, y **funciones** para organizar tu código de manera profesional.

**Contexto y Justificación (Aprendizaje Basado en Proyectos):**
Este no es un ejercicio aislado; es la construcción de una herramienta funcional de principio a fin. Te enfrentarás al desafío de hacer que diferentes partes de tu código (funciones, estructuras de datos) trabajen juntas para crear una aplicación cohesiva. Es la mejor manera de consolidar tus conocimientos y empezar a pensar como un desarrollador de software.


### **Requisitos Funcionales de la Aplicación:**

Tu gestor de tareas debe tener un menú interactivo con las siguientes opciones:

1.  **Añadir Tarea:**
    *   Pide al usuario que escriba la descripción de una nueva tarea.
    *   Pide también una fecha límite en formato "YYYY-MM-DD".
    *   Guarda la tarea con un ID único, su descripción, la fecha límite y un estado que, por defecto, será "pendiente".

2.  **Marcar Tarea como Completada:**
    *   Muestra al usuario todas las tareas que están "pendientes".
    *   Permite al usuario elegir una tarea por su ID para cambiar su estado a "completada".

3.  **Mostrar Todas las Tareas:**
    *   Imprime una lista clara de *todas* tus tareas (tanto pendientes como completadas).
    *   Para cada tarea, debes mostrar su ID, descripción, estado y fecha límite.
    *   ¡El reto! Para las tareas que aún están pendientes, calcula y muestra cuántos días faltan para que venzan.

4.  **Salir:**
    *   Una opción para cerrar la aplicación.


### **Requisitos Técnicos y Estructura del Código:**

Para que tu proyecto sea evaluado correctamente, asegúrate de seguir estas directrices:

1.  **Estructura de Datos Principal:** Tu "base de datos" de tareas debe ser un **diccionario**. Te recomiendo usar el ID de la tarea como clave.
2.  **Modularidad con Funciones:** ¡No escribas todo en un solo bloque! Organiza tu código en, al menos, las siguientes **funciones**:
    *   `mostrar_menu()`
    *   `anadir_tarea()`
    *   `marcar_completada()`
    *   `mostrar_tareas()`
    *   Tu programa principal será un bucle `while` que llame a estas funciones.
3.  **Uso de Tuplas:** Encuentra un lugar lógico en tu código para usar una **tupla**. Por ejemplo, para almacenar datos que no deberían cambiar, como las cabeceras de la tabla de tareas que vas a imprimir.
4.  **Gestión de Fechas (`datetime`):**
    *   Usa `datetime.strptime()` para convertir la fecha que ingrese el usuario (que es texto) a un objeto de fecha real.
    *   Usa `datetime.strftime()` para que las fechas se vean bien cuando las imprimas.
    *   Usa `timedelta` para hacer el cálculo de los días que faltan para el vencimiento de una tarea.


### **Entregables**

Para este proyecto, necesitarás entregar dos cosas:

1.  **Código Fuente:** Tu programa completo en un único archivo `.py`. No olvides añadir comentarios para explicar las partes clave.
2.  **Video Explicativo:**
    *   Graba un video corto (¡**máximo 5 minutos**!).
    *   Súbelo a YouTube como "No listado" (Unlisted).
    *   Pega el enlace del video en un comentario al inicio de tu archivo `.py`.
    *   Este video es tu oportunidad para "sustentar" tu proyecto y demostrar que entiendes lo que hiciste.


### **Rúbrica de Evaluación (sobre 20 puntos)**

Tu nota se basará en la evidencia que presentes en tu **código** y, fundamentalmente, en tu **video explicativo**. Prepárate para demostrar y explicar los siguientes puntos en tu video.

| Criterio Evaluado en el Video y Código                 | Puntos | Descripción del Logro (para obtener puntaje máximo)                                                                                             |
| ------------------------------------------------------ | :----: | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Modularidad con Funciones**                       | **5**  | En el video, explicas y demuestras una estructura de código organizada en funciones claras, mostrando cómo se comunican entre sí.                |
| **2. Manipulación de Diccionarios**                    | **5**  | Demuestras en el video el uso efectivo de un diccionario como estructura principal, explicando cómo realizas las operaciones de añadir/modificar. |
| **3. Gestión de Fechas con `datetime`**                | **5**  | El video muestra y explica el código donde manejas fechas: conversión de texto a fecha, formateo y cálculo de diferencias de tiempo.          |
| **4. Uso de Tuplas y Otros Conceptos**                 | **1**  | Señalas explícitamente en el video dónde y por qué utilizaste una tupla en tu programa.                                                          |
| **5. Calidad y Claridad del Video**                    | **2**  | El video es conciso (dentro del tiempo), el audio es claro y tu explicación demuestra una comprensión sólida del proyecto.                        |
| **6. Funcionalidad y Calidad del Código**              | **2**  | El programa demostrado en el video es completamente funcional. El código fuente entregado es legible, está comentado y sigue buenas prácticas.    |
| **Total**                                              | **20** |                                                                                                                                                 |
