### **Guía de Laboratorio 8: De Datos Aislados a Inteligencia Colectiva con Listas**

** Metodología:** Aprendizaje Basado en Casos (ABC)
** Semana:** 8
** Temas:** Listas en Python (creación, métodos, iteración, análisis de datos).

### **Paso 1: La Presentación del Caso**

**El Caso de Estudio: "El Reporte de Desempeño de la Profesora Ana"**

La profesora Ana necesita una herramienta más poderosa que su simple calculadora. No solo quiere el promedio de las notas de un examen, quiere entender el **panorama completo del desempeño** de su clase. Anotar las notas en papel es lento, calcular estadísticas a mano es propenso a errores y, sobre todo, no le da una visión rápida de la distribución del rendimiento (cuántos aprobaron, quién tuvo la nota más alta, etc.).

**El Dilema de la Profesora Ana:**
"Necesito un programa que me permita ingresar un número variable de calificaciones. Una vez que termine de ingresarlas, el sistema debe generar automáticamente un reporte completo que incluya el total de estudiantes, el promedio, las notas extremas (la más alta y la más baja) y un conteo de aprobados y reprobados. ¿Cómo puedo construir esto si no sé cuántos estudiantes tengo en cada examen?"


### **Paso 2: Análisis del Caso y Descubrimiento de la Necesidad**

**Tu Misión:** Antes de escribir una sola línea de código, ponte en el lugar de un ingeniero de software que escucha los requisitos de su cliente (la profesora Ana).

**Preguntas para Reflexionar (discute con un compañero si es posible):**
1.  **La Gran Limitación:** ¿Qué problema fundamental enfrentarías si intentaras resolver esto solo con las variables que conoces hasta ahora (`un_numero = 15`, `otro_numero = 18`, etc.)?
2.  **Diseñando la Solución Ideal:** Si pudieras inventar una "super-variable", ¿qué características tendría que tener para resolver el dilema de Ana? (Pista: Piensa en cómo guardarías múltiples valores en un solo lugar y cómo podrías añadir más valores fácilmente).

Después de esta reflexión, la necesidad de una **colección ordenada y modificable de datos** se vuelve evidente. Esa "super-variable" que has imaginado es, precisamente, lo que en Python llamamos una **lista**.


### **Paso 3: Introducción a la Herramienta Teórica**

**Nuestra Herramienta: La Lista de Python**
Una lista es un contenedor que te permite almacenar múltiples valores en una sola variable.

*   **Creación:** Se crea una lista vacía con corchetes: `mi_lista = []`
*   **Adición de Elementos:** Se usa el método `.append()` para agregar un elemento al final: `mi_lista.append(nuevo_valor)`

Esta es toda la teoría que necesitas para empezar a construir la solución.


### **Paso 4: Aplicación y Resolución del Caso (¡Manos al Código!)**

Ahora, traducirás el análisis a una solución práctica. El programa se construirá en dos fases.

#### **Fase 1: Recopilación de Datos - Poblando la Lista**

El primer objetivo es crear la funcionalidad para que la profesora Ana ingrese todas las calificaciones.

**Instrucciones:** Completa el siguiente esqueleto de código. Presta atención a los comentarios `###` que indican dónde debes intervenir.

```python
# --- FASE 1: RECOPILACIÓN DE DATOS ---

# Inicializamos el contenedor que almacenará todas las calificaciones.
calificaciones = []
print("Sistema de Registro de Calificaciones")
print("Ingrese las calificaciones una por una. Escriba -1 para finalizar.")

while True:
    entrada = input("Ingrese una calificación (o -1 para terminar): ")

    # ### TU CÓDIGO AQUÍ (1/2) ###
    # Debemos comprobar si el usuario quiere terminar el ingreso de datos.
    if entrada == ???:
        # PISTA: El caso nos dice que un valor específico detiene el bucle.
        # ¿Qué palabra clave de Python usamos para romper un bucle de forma inmediata?
        break

    # Convertimos la entrada a un número para poder usarla en cálculos.
    nota = float(entrada)
    
    # ### TU CÓDIGO AQUÍ (2/2) ###
    # Ahora que tenemos una nota válida, debemos guardarla en nuestro contenedor.
    calificaciones.???(nota)
    # PISTA: Revisa la sección "Nuestra Herramienta: La Lista". ¿Cuál es el *método*
    # que se usa para añadir un elemento al final de una lista?

print("\n--- Carga de datos finalizada. ---")
print(f"Se han ingresado {len(calificaciones)} calificaciones.")
print(f"Las calificaciones son: {calificaciones}")

```

#### **Fase 2: Análisis de Datos - Generando el Reporte**

Con todas las calificaciones almacenadas en la lista, ahora podemos procesarlas para generar el reporte que Ana necesita.

**Instrucciones:** Continúa en el mismo archivo y completa el esqueleto de la Fase 2.

```python
# --- FASE 2: ANÁLISIS DE DATOS ---

if len(calificaciones) > 0:
    suma_total = 0.0
    nota_mas_alta = calificaciones[0]
    contador_aprobados = 0
    UMBRAL_APROBACION = 11.0
    
    # ### TU CÓDIGO AQUÍ (1/3) ###
    # Necesitamos una variable para guardar la nota más baja.
    # Una buena estrategia es empezar asumiendo que el primer elemento es el más bajo.
    nota_mas_baja = ???
    # PISTA: ¿Cómo accedemos al primer elemento de una lista? La sintaxis es similar
    # a como inicializamos 'nota_mas_alta'.

    for nota in calificaciones:
        suma_total += nota

        if nota > nota_mas_alta:
            nota_mas_alta = nota
            
        # ### TU CÓDIGO AQUÍ (2/3) ###
        # Ahora, haz la lógica para encontrar la nota más baja.
        if nota < ???:
            # PISTA: El razonamiento es el inverso a encontrar la nota más alta.
            # Si la nota actual es menor que nuestro mínimo guardado... ¿qué hacemos?
            nota_mas_baja = nota

        # ### TU CÓDIGO AQUÍ (3/3) ###
        # Debemos contar cuántos estudiantes aprobaron.
        if nota >= ???:
            # PISTA: Compara la 'nota' actual con el umbral definido para aprobar.
            # Si la condición se cumple, debemos incrementar nuestro contador.
            contador_aprobados += 1

    # Calculamos el promedio una vez terminado el bucle.
    promedio = suma_total / len(calificaciones)

    # Mostramos el reporte final, bien formateado.
    print("\n------ REPORTE DE DESEMPEÑO ------")
    print(f"Promedio del curso: {promedio:.2f}")
    print(f"Calificación más alta: {nota_mas_alta}")
    print(f"Calificación más baja: {nota_mas_baja}")
    print(f"Estudiantes aprobados (>= {UMBRAL_APROBACION}): {contador_aprobados}")
    print(f"Estudiantes reprobados: {len(calificaciones) - contador_aprobados}")
else:
    print("\nNo se ingresaron datos para generar un reporte.")
```
### **Paso 5: Síntesis y Reflexión**

Una vez que tu programa funcione, reflexiona sobre lo que has logrado:
*   ¿Cómo la estructura de la lista simplificó radicalmente la resolución del caso de Ana?
*   ¿Qué otros problemas del mundo real (en los negocios, la ciencia, los juegos) podrías modelar y resolver utilizando listas?
  
