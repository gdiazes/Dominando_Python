### **Tarea N° 1: Traducción Algorítmica con Python**

| **Título:** | De la Lógica del Problema a la Implementación del Código |
| :--- | :--- |
| **Competencias a Desarrollar:** | <ul><li>Traducción de un algoritmo a un script de Python.</li><li>Declaración de variables y asignación de datos.</li><li>Uso de operadores aritméticos para procesamiento de datos.</li><li>Implementación del ciclo de Entrada-Proceso-Salida.</li></ul> |
| **Contexto Previo:** | Laboratorios 1-3 (Diseño de Diagramas de Flujo y Pseudocódigo). |
| **Materiales:** | Editor de código Python (ej. VS Code, Thonny, PyCharm). |

---

#### **Paso 1. El Escenario: Presentación del Caso de Estudio**

> **El Dilema de la Cena:** Se presenta un escenario en el que un grupo de comensales debe dividir el costo de una cuenta. El cálculo debe incorporar un porcentaje de propina acordado, y el proceso manual ha demostrado ser ineficiente y susceptible a errores. Se identifica la necesidad de una solución de software estandarizada y fiable.

**Objetivo del Laboratorio:** El estudiante actuará como el desarrollador al que se le ha encomendado la tarea de crear una herramienta de software que automatice dicho cálculo. La herramienta resultante debe ser funcional y resolver el problema planteado de manera efectiva.

---

#### **Paso 2. Fase de Diseño: Estructuración del Algoritmo**

Antes de la implementación de código, es imperativo que se diseñe el plano lógico de la solución. En programación, este plano se denomina **algoritmo**. Utilizando los conceptos adquiridos en las semanas 1 a 3, se deberá definir la lógica que resolverá el caso.

**Requerimientos para el Diseño Lógico:**
1.  **Definición de Entradas:** Deben ser identificadas las tres unidades de información (datos) que son indispensables para que el programa pueda realizar sus operaciones.
2.  **Secuencia de Procesamiento:** La secuencia de cálculos debe ser detallada en el orden correcto. Se debe justificar por qué un cálculo precede a otro (ej. el cálculo de la propina antes del pago individual).
3.  **Especificación de Salidas:** Se debe determinar cuál es el resultado final que el programa presentará al usuario como solución al problema.

El entregable de esta fase es un algoritmo claramente definido, ya sea mentalmente o documentado como pseudocódigo, que servirá como guía para la fase de implementación.

---

#### **Paso 3. El Arsenal de Herramientas: Sintaxis Fundamental de Python**

Para la construcción del programa a partir del algoritmo diseñado, se utilizarán las siguientes herramientas sintácticas del lenguaje Python.

| Herramienta | Descripción | Aplicación en el Contexto del Caso |
| :--- | :--- | :--- |
| **Variables** | Son contenedores simbólicos utilizados para almacenar datos en memoria. | `total_cuenta = 150.75` |
| **Salida: `print()`** | Es una función que muestra información en la consola estándar. | `print("Bienvenido a la Calculadora de Cuentas")` |
| **Entrada: `input()`** | Es una función que captura datos ingresados por el usuario desde el teclado. | `respuesta = input("¿Cuál es el total?")` |
| **Conversión de Tipos** | Proceso que transforma datos de un tipo a otro (ej. de texto a numérico). | `monto = float(respuesta)` |
| **Operadores Aritméticos** | Símbolos que realizan operaciones matemáticas (`+`, `*`, `/`). | `monto_final = total_cuenta + propina` |

---

#### **Paso 4. Fase de Implementación: Del Algoritmo al Código Fuente**

En esta fase, el diseño lógico se traduce a código Python funcional. Se debe completar el siguiente esqueleto de código, prestando especial atención a las secciones marcadas como `[COMPLETAR]`.

```python
# =================================================================
#                     CALCULADORA DE CUENTAS
#                  Desarrollado por: [Nombre del Estudiante]
#                  Fecha: [Fecha de Desarrollo]
# =================================================================

# --- Sección 1: Interfaz de Usuario ---
print("================================================")
print("   Herramienta para el Cálculo de Cuentas      ")
print("================================================")

# --- Sección 2: Captura de Datos (ENTRADA) ---
# [1] Se solicita el monto total de la cuenta.
# El valor es almacenado como un número de punto flotante.
total_cuenta = float(input("Ingrese el monto total de la cuenta: $"))

# [2] Se solicita el porcentaje de propina.
# Este valor se asume como entero y debe ser convertido a 'int'.
porcentaje_propina = ???(input("Ingrese el porcentaje de propina a incluir (ej. 15): "))
# PISTA: La función para convertir a entero es 'int()'.

# [3] Se solicita el número de comensales.
# Este valor también es un número entero.
numero_personas = ???
# PISTA: El proceso de conversión es idéntico al del paso anterior.


# --- Sección 3: Lógica de Negocio (PROCESO) ---
# Se calcula el valor monetario de la propina.
monto_propina = total_cuenta * (porcentaje_propina / 100)

# [4] Se calcula el costo total a dividir.
# Este se compone del costo original de la cuenta más el monto de la propina.
monto_final_a_dividir = ???
# PISTA: Debe realizarse una operación de adición entre las variables relevantes.

# Se calcula la cuota individual por comensal.
pago_por_persona = monto_final_a_dividir / numero_personas


# --- Sección 4: Presentación de Resultados (SALIDA) ---
print("\n----------------- RESULTADO -----------------")
# La expresión ':.2f' formatea el número a dos decimales, lo cual es
# una práctica estándar para la representación de valores monetarios.
print(f"El monto a pagar por cada persona es: ${pago_por_persona:.2f}")
print("---------------------------------------------")

```

---

#### **Paso 5. Verificación y Reflexión Final**

La finalización de un programa requiere la verificación de su funcionalidad y la reflexión sobre los conceptos aplicados.

**A. Validación Funcional:**
El programa debe ser ejecutado y probado con un conjunto de datos de validación para asegurar la correctitud de los cálculos.
*   Datos de Entrada:
    *   Monto total de la cuenta: `125.50`
    *   Porcentaje de propina: `12`
    *   Número de personas: `4`
*   Resultado Esperado: El pago por persona debe ser **$35.14**.
Si el resultado obtenido difiere del esperado, el código de la Sección 3 debe ser depurado.

**B. Análisis Conceptual:**
1.  **Relación Diseño-Implementación:** Se debe ser capaz de explicar la correspondencia entre el algoritmo diseñado en el Paso 2 y las secciones de código implementadas en el Paso 4.
2.  **El Ciclo Fundamental:** Deben ser identificadas en el código las tres fases del ciclo **Entrada-Proceso-Salida**. Se espera que el estudiante pueda articular la importancia de este patrón en el desarrollo de software.
3.  **Generalización del Patrón:** Se debe proponer otro escenario (académico, personal o profesional) donde este mismo ciclo de desarrollo pueda ser aplicado para la creación de una herramienta de software.



### **Rúbrica de Evaluación del Laboratorio (Total: 20 Puntos)**

El desarrollo del presente laboratorio será evaluado de acuerdo con los siguientes criterios y niveles de logro. El puntaje final será la suma de los puntos obtenidos en cada uno de los cuatro criterios evaluados.

| Criterios | Excelente | Logrado | En Proceso | No aceptable | Pts |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **1. Traducción Algorítmica y Estructura del Código** | 🟢 **(6 pts)**<br>Código excepcionalmente estructurado, comentado y con fases E-P-S claramente delimitadas. | 🔵 **(4 pts)**<br>Implementa correctamente el ciclo E-P-S. La secuencia es lógica y funcional. | 🟡 **(2 pts)**<br>Secuencia lógica general, pero la delimitación de las fases E-P-S es confusa. | 🔴 **(0 pts)**<br>Sin estructura lógica discernible; fases mezcladas. | **6 pts** |
| **2. Aplicación de Sintaxis Fundamental de Python** | 🟢 **(5 pts)**<br>Domina la sintaxis y aplica buenas prácticas (ej. formato profesional con f-strings). | 🔵 **(3 pts)**<br>Uso correcto de `input`/`print`, variables, operadores y conversión de tipos. | 🟡 **(1 pto)**<br>Presenta errores menores de sintaxis o conversión de tipos inconsistente. | 🔴 **(0 pts)**<br>Errores de sintaxis recurrentes que impiden la ejecución. | **5 pts** |
| **3. Funcionalidad y Correctitud del Programa** | 🟢 **(6 pts)**<br>Correcto y robusto; funciona con diversos datos de entrada válidos. | 🔵 **(4 pts)**<br>Se ejecuta sin errores y produce el resultado correcto para los datos de prueba. | 🟡 **(2 pts)**<br>Se ejecuta, pero el resultado es incorrecto debido a un error de lógica. | 🔴 **(0 pts)**<br>No se ejecuta o produce un resultado incorrecto. | **6 pts** |
| **4. Desarrollo de Laboratorios Previos** | 🟢 **(3 pts)**<br>Entrega completa de los 3 laboratorios previos (Lab 1, 2 y 3). | 🔵 **(2 pts)**<br>Entrega de 2 de los 3 laboratorios previos. | 🟡 **(1 pto)**<br>Entrega de 1 de los 3 laboratorios previos. | 🔴 **(0 pts)**<br>No entrega los laboratorios previos. | **3 pts** |

---
**PUNTAJE TOTAL MÁXIMO: 20 PUNTOS**
