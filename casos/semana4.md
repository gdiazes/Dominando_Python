
### **Guía de Laboratorio 4: De una Idea Lógica a una Solución Funcional en Python**
---
**Metodología:** Aprendizaje Basado en Casos (ABC)
**Semana:** 4
**Temas:** Sintaxis básica, Variables, Operadores, Entrada/Salida en Python.
---

### **Paso 1: La Presentación del Caso**

**El Caso de Estudio: "El Cálculo Justo de la Cena entre Amigos"**

Estás cenando con un grupo de amigos. Al final de la comida, llega la cuenta. El ambiente es relajado, pero surge el típico pequeño dilema: ¿cómo dividir el total de forma rápida, justa y sin errores? Alguien sugiere un porcentaje de propina, otro pregunta cuánto le toca a cada uno, y empiezan a sacar los móviles para usar la calculadora, pero es un proceso torpe.

**El Dilema del Grupo:**
"Necesitamos una forma sencilla y directa de resolver esto siempre. Una herramienta que nos pregunte el total de la cuenta, qué porcentaje de propina queremos dejar y entre cuántas personas se va a dividir. Luego, debe decirnos exactamente cuánto tiene que poner cada uno. No más errores de cálculo ni confusiones."


### **Paso 2: Análisis del Caso y Descubrimiento de la Necesidad**

**Tu Misión:** Antes de pensar en código, piensa como el solucionador de problemas del grupo. Vas a diseñar la "receta" lógica para resolver este dilema.

**Preguntas para Reflexionar (diseña la solución en tu mente o en papel):**
1.  **Las Piezas de Información (Entradas):** ¿Qué tres datos fundamentales necesitas *pedirle* al usuario para poder hacer los cálculos?
2.  **Los Cálculos Clave (Procesos):** Una vez que tienes esos datos, ¿qué operaciones matemáticas necesitas realizar y en qué orden? Descríbelo paso a paso (Ej: "Primero, calculo el monto de la propina...").
3.  **El Resultado Final (Salida):** ¿Qué pieza de información es la que tus amigos realmente quieren saber al final?

Al responder estas preguntas, has creado un **algoritmo**: una secuencia de pasos lógicos para resolver un problema. Esta es la habilidad más importante en la programación, incluso antes de conocer un lenguaje.


### **Paso 3: Introducción a la Herramienta Teórica**

**Nuestra Herramienta: El Lenguaje Python**
Para convertir tu "receta" lógica en un programa real, necesitas un lenguaje. Python nos proporciona las herramientas básicas:

*   **Variables:** Cajas para guardar información. Ejemplo: `total_cuenta = 100.50`
*   **Función `print()`:** Para mostrar mensajes en pantalla. Ejemplo: `print("Hola, amigos")`
*   **Función `input()`:** Para pedirle información al usuario. Ejemplo: `nombre = input("¿Cómo te llamas? ")`
*   **Operadores Aritméticos:** Para hacer matemáticas: `+` (suma), `*` (multiplicación), `/` (división).
*   **Conversión de Tipos:** `input()` siempre da texto. Para hacer cálculos, debemos convertirlo a número con `float()` (para decimales) o `int()` (para enteros). Ejemplo: `gasto = float(input("¿Cuánto gastaste? "))`


### **Paso 4: Aplicación y Resolución del Caso (¡Manos al Código!)**

Ahora, vamos a construir la herramienta que resolverá el dilema de la cena.

**Instrucciones:** Completa el siguiente esqueleto de código. Los comentarios `###` te guiarán sobre lo que debes hacer en cada sección.

```python
# --- El Calculador de Cuentas ---

print("Bienvenido a la Calculadora de Cuentas Justas")

# --- FASE 1: OBTENER LOS DATOS (ENTRADAS) ---

# ### TU CÓDIGO AQUÍ (1/3) ###
# Necesitamos guardar el monto total de la cuenta en una variable.
# Recuerda pedirle el dato al usuario y convertirlo a un número con decimales.
total_cuenta = float(input("¿Cuál es el monto total de la cuenta? $"))
# PISTA: La estructura es similar a la línea anterior. ¿Qué función usamos
# para pedirle datos al usuario? ¿Y para convertir el texto en un número?

# ### TU CÓDIGO AQUÍ (2/3) ###
# Ahora, pregunta por el porcentaje de propina. La gente suele dar un número entero
# (10, 15, 20), así que conviértelo a entero.
porcentaje_propina = ???(input("¿Qué porcentaje de propina quieren dejar (ej. 15)? "))
# PISTA: Si para decimales usamos float(), ¿qué función usamos para números enteros?

# ### TU CÓDIGO AQUÍ (3/3) ###
# Finalmente, pregunta por el número de personas.
# No puede haber "media persona", así que también debe ser un número entero.
numero_personas = ???
# PISTA: Sigue la misma lógica que en el paso anterior.


# --- FASE 2: REALIZAR LOS CÁLCULOS (PROCESOS) ---

# Calculamos el monto total de la propina.
monto_propina = total_cuenta * (porcentaje_propina / 100)

# ### TU CÓDIGO AQUÍ (ÚNICA PARTE) ###
# Ahora, calcula el monto final (la cuenta original + la propina que acabas de calcular).
monto_final = ???
# PISTA: Ya tienes las dos variables que necesitas: 'total_cuenta' y 'monto_propina'.
# ¿Qué operador aritmético las une?

# Calculamos cuánto debe pagar cada persona.
pago_por_persona = monto_final / numero_personas


# --- FASE 3: MOSTRAR EL RESULTADO (SALIDA) ---

print("\n------ ¡Cuenta Calculada! ------")

# Usamos f-strings para presentar los resultados de forma clara.
# El :.2f formatea el número para que siempre muestre dos decimales, ideal para dinero.
print(f"Cada persona debe pagar: ${pago_por_persona:.2f}")

```


### **Paso 5: Síntesis y Reflexión**

Una vez que tu programa funcione, tómate un momento para reflexionar sobre tu logro:
*   Has creado tu primer programa completo que resuelve un problema del mundo real.
*   ¿Ves la conexión directa entre el diseño lógico que hiciste en el Paso 2 y cada bloque de código que escribiste en el Paso 4?
*   Has aprendido el flujo fundamental de casi cualquier programa simple: **Entrada -> Proceso -> Salida**. Este patrón se repetirá una y otra vez en tu carrera como programador. ¡Felicidades
