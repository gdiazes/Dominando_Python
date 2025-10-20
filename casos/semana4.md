### **Tarea N° 1: Traducción Algorítmica con Python**

| **Título:** | De la Lógica del Problema a la Implementación del Código |
| :--- | :--- |
| **Competencias a Desarrollar:** | <ul><li>Traducción de un algoritmo a un script de Python.</li><li>Declaración de variables y asignación de datos.</li><li>Uso de operadores aritméticos para procesamiento de datos.</li><li>Implementación del ciclo de Entrada-Proceso-Salida.</li></ul> |
| **Contexto Previo:** | Laboratorios 1-3 (Diseño de Diagramas de Flujo y Pseudocódigo). |
| **Materiales:** | Editor de código Python (ej. VS Code, Thonny, PyCharm). |

---

#### **Paso 1. El Escenario: Presentación del Caso de Estudio**

> **El Dilema de la Cena:** Un grupo de amigos comparte una cena. Al recibir la cuenta, surge el desafío recurrente: calcular la división del total de manera precisa, incluyendo un porcentaje de propina acordado por el grupo. El proceso manual, utilizando calculadoras de teléfono, es fragmentado y propenso a errores. Se necesita una solución estandarizada y fiable.

**Misión Principal:** Tu rol es actuar como el desarrollador encargado de crear una herramienta de software simple y eficaz que automatice este cálculo. La herramienta debe ser intuitiva y resolver el problema de forma definitiva.

---

#### **Paso 2. Fase de Diseño: El Plano del Arquitecto**

Antes de colocar un solo "ladrillo" (escribir código), un buen arquitecto diseña el plano. En programación, este plano es el **algoritmo**. Basándote en tus conocimientos de las semanas 1 a 3, define la lógica que resolverá el caso.

**Preguntas de Diseño Lógico:**
1.  **Requerimientos de Entrada:** ¿Cuáles son las tres piezas de información (datos) indispensables que el programa debe solicitar al usuario para funcionar?
2.  **Secuencia de Procesamiento:** Detalla los cálculos necesarios en el orden correcto. ¿Qué se calcula primero, el monto de la propina o el pago individual? ¿Por qué ese orden es crucial?
3.  **Especificación de Salida:** ¿Cuál es el único y más importante resultado que el programa debe presentar al usuario final?

El resultado de esta fase es una "receta" clara en tu mente o en papel (pseudocódigo) que servirá como guía para la implementación.

---

#### **Paso 3. El Arsenal de Herramientas: Sintaxis Fundamental de Python**

Para construir el programa a partir de tu plano, necesitarás las siguientes herramientas básicas del lenguaje Python.

| Herramienta | Descripción | Ejemplo de Uso en Nuestro Caso |
| :--- | :--- | :--- |
| **Variables** | Contenedores para almacenar datos en memoria. | `total_cuenta = 150.75` |
| **Salida: `print()`** | Muestra información y mensajes en la consola. | `print("Bienvenido a la Calculadora de Cuentas")` |
| **Entrada: `input()`** | Captura datos ingresados por el usuario desde el teclado. | `respuesta = input("¿Cuál es el total?")` |
| **Conversión de Tipos** | Transforma datos de un tipo a otro (ej. de texto a número). | `monto = float(respuesta)` |
| **Operadores Aritméticos** | Realizan operaciones matemáticas (`+`, `*`, `/`). | `monto_final = total_cuenta + propina` |

---

#### **Paso 4. Fase de Implementación: Del Plano al Programa**

Es hora de traducir tu diseño lógico a código Python funcional. Completa el siguiente esqueleto de código, prestando especial atención a las secciones marcadas como `[TU MISIÓN]`.

```python
# =================================================================
#                     CALCULADORA DE CUENTAS
#                  Autor: [Tu Nombre]
#                  Fecha: [Fecha de Hoy]
# =================================================================

# --- Sección 1: Bienvenida e Interfaz de Usuario ---
print("================================================")
print("   Herramienta para el Cálculo de Cuentas      ")
print("================================================")

# --- Sección 2: Captura de Datos (ENTRADA) ---
# [1] TU MISIÓN: Solicitar el monto total de la cuenta.
# El valor debe ser almacenado como un número decimal (flotante).
total_cuenta = float(input("Ingrese el monto total de la cuenta: $"))

# [2] TU MISIÓN: Solicitar el porcentaje de propina deseado.
# Este valor es típicamente un entero (ej. 15), así que conviértelo a 'int'.
porcentaje_propina = ???(input("Ingrese el porcentaje de propina a incluir (ej. 15): "))
# PISTA: Revisa la tabla de herramientas. Si 'float()' es para decimales, 
# ¿qué función se utiliza para números enteros?

# [3] TU MISIÓN: Solicitar el número de comensales.
# El número de personas siempre será un entero.
numero_personas = ???
# PISTA: La lógica es idéntica a la misión anterior.


# --- Sección 3: Lógica de Negocio (PROCESO) ---
# Calculamos el valor monetario de la propina.
monto_propina = total_cuenta * (porcentaje_propina / 100)

# [4] TU MISIÓN: Calcular el costo total final.
# Este debe incluir el costo original de la cuenta más el monto de la propina.
monto_final_a_dividir = ???
# PISTA: Ya tienes las dos variables que componen este total.
# ¿Qué operador aritmético las combina?

# Calculamos la cuota individual.
pago_por_persona = monto_final_a_dividir / numero_personas


# --- Sección 4: Presentación de Resultados (SALIDA) ---
print("\n----------------- RESULTADO -----------------")
# La expresión ':.2f' dentro del f-string es una buena práctica profesional.
# Asegura que el resultado monetario siempre se muestre con dos decimales.
print(f"El monto a pagar por cada persona es: ${pago_por_persona:.2f}")
print("---------------------------------------------")

```

---

#### **Paso 5. Verificación y Reflexión Final**

Un programa no está completo hasta que se verifica su correcto funcionamiento y se reflexiona sobre el aprendizaje.

**A. Prueba de Fuego (Verificación):**
Ejecuta tu programa y utiliza los siguientes datos de prueba para asegurar que tus cálculos son correctos:
*   Monto total de la cuenta: `125.50`
*   Porcentaje de propina: `12`
*   Número de personas: `4`

El resultado esperado para el pago por persona es **$35.14**. ¿Tu programa arroja este resultado? Si no es así, depura tu código revisando la lógica de la Sección 3.

**B. Conexión de Conceptos (Reflexión):**
1.  **Del Diseño a la Realidad:** Describe con tus propias palabras la relación entre el algoritmo que diseñaste en el Paso 2 y cada sección de código que implementaste en el Paso 4.
2.  **El Ciclo Fundamental:** Identifica en tu código las tres partes del ciclo **Entrada-Proceso-Salida**. ¿Por qué crees que este patrón es tan fundamental en la programación?
3.  **Más Allá del Caso:** ¿En qué otro escenario simple (personal, académico o profesional) podrías aplicar este mismo ciclo para crear una herramienta útil?
