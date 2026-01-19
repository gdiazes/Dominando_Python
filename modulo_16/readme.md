**`Modulo16.md`** (Archivo Principal del Módulo 16)

```markdown
# Módulo 16: Visualizando Datos: Gráficos en Python con Matplotlib

## Laboratorio 16 - Guía Paso a Paso

¡Bienvenido al Laboratorio 16! Has aprendido a procesar y analizar datos con Python. Ahora, es momento de aprender a **visualizarlos**. La visualización de datos es el arte de representar información en forma de gráficos, lo que nos permite entender patrones, tendencias y resultados de una manera mucho más intuitiva que mirando tablas de números. En este laboratorio, exploraremos una de las bibliotecas de visualización más populares y fundamentales de Python: **Matplotlib**.

### ¿Qué es Matplotlib?
Matplotlib es una biblioteca muy completa para crear visualizaciones estáticas, animadas e interactivas en Python. Es el "abuelo" de muchas otras bibliotecas de visualización y proporciona un control total sobre cada aspecto de una figura. Usaremos el sub-módulo `pyplot`, que ofrece una interfaz sencilla para crear gráficos.

**Instalación:**
Antes de empezar, necesitas instalar la biblioteca. Abre tu terminal o símbolo del sistema y ejecuta:
```bash
pip install matplotlib
```

**Importación Convencional:**
La convención para importar `pyplot` es usar el alias `plt`.
```python
import matplotlib.pyplot as plt
```

### La Anatomía de un Gráfico de Matplotlib
Un gráfico de Matplotlib se compone de varias partes:
*   **Figure (Figura):** Es el contenedor principal, la ventana o página en la que todo se dibuja.
*   **Axes (Ejes):** Es el área de trazado donde se dibujan los datos con sus coordenadas (eje x, eje y). Una figura puede contener uno o más ejes.
*   **Title (Título):** El título del gráfico.
*   **Labels (Etiquetas):** Nombres para el eje X (`xlabel`) y el eje Y (`ylabel`).
*   **Legend (Leyenda):** Describe los diferentes conjuntos de datos trazados en el gráfico.

### Creación de un Gráfico Básico: Gráfico de Líneas
Un gráfico de líneas es ideal para mostrar cómo una variable cambia con el tiempo o en relación con otra variable continua.

**Pasos para crear un gráfico:**
1.  Prepara tus datos (generalmente en listas o arrays de NumPy).
2.  Llama a `plt.plot()` para trazar los datos.
3.  Personaliza el gráfico (títulos, etiquetas, etc.).
4.  Llama a `plt.show()` para mostrar el gráfico.

```python
import matplotlib.pyplot as plt

# 1. Prepara los datos
dias = [1, 2, 3, 4, 5, 6, 7]
temperaturas = [15, 17, 16, 18, 20, 19, 21]

# 2. Trazar los datos
plt.plot(dias, temperaturas)

# 3. Personalizar el gráfico
plt.title("Temperatura Semanal")
plt.xlabel("Día de la Semana")
plt.ylabel("Temperatura (°C)")

# 4. Mostrar el gráfico
plt.show()
```
`plt.show()` abrirá una ventana mostrando el gráfico generado.

### Gráfico de Barras
Un gráfico de barras es excelente para comparar cantidades entre diferentes categorías.

```python
import matplotlib.pyplot as plt

# Datos
productos = ["Manzanas", "Bananas", "Naranjas"]
ventas = [120, 200, 85]

# Trazar los datos
plt.bar(productos, ventas)

# Personalizar
plt.title("Ventas de Frutas")
plt.xlabel("Fruta")
plt.ylabel("Cantidad Vendida")

# Mostrar
plt.show()
```

### Gráfico de Dispersión (Scatter Plot)
Un gráfico de dispersión se usa para visualizar la relación entre dos variables numéricas. Cada punto representa una observación.

```python
import matplotlib.pyplot as plt

# Datos
altura = [160, 165, 170, 175, 180, 185]
peso = [60, 68, 72, 80, 85, 90]

# Trazar los datos
plt.scatter(altura, peso)

# Personalizar
plt.title("Relación entre Altura y Peso")
plt.xlabel("Altura (cm)")
plt.ylabel("Peso (kg)")

# Mostrar
plt.show()
```

### Histograma
Un histograma se usa para visualizar la **distribución** de una sola variable numérica. Agrupa los datos en "bins" (intervalos) y cuenta cuántas observaciones caen en cada bin.

```python
import matplotlib.pyplot as plt
import random

# Generar datos de ejemplo (ej: 100 calificaciones aleatorias)
calificaciones = [random.randint(0, 100) for _ in range(100)]

# Trazar el histograma
# 'bins' controla el número de barras (intervalos)
plt.hist(calificaciones, bins=10, edgecolor='black')

# Personalizar
plt.title("Distribución de Calificaciones")
plt.xlabel("Calificación")
plt.ylabel("Frecuencia (Nº de Estudiantes)")

# Mostrar
plt.show()
```

### Gráfico de Torta (Pie Chart)
Un gráfico de torta es útil para mostrar la proporción de diferentes categorías como parte de un todo.

```python
import matplotlib.pyplot as plt

# Datos (las proporciones deben sumar 100% idealmente)
etiquetas = ["Trabajo", "Dormir", "Comer", "Ocio"]
porcentajes = [40, 30, 10, 20]

# Trazar el gráfico de torta
plt.pie(porcentajes, labels=etiquetas, autopct='%1.1f%%', startangle=90)
# autopct='%1.1f%%' muestra los porcentajes en el gráfico

# Personalizar
plt.title("Distribución del Tiempo en un Día")
plt.axis('equal')  # Asegura que el gráfico de torta sea un círculo

# Mostrar
plt.show()
```

### Personalización Avanzada
Matplotlib te permite personalizar casi todo.
```python
x = [1, 2, 3, 4, 5]
y1 = [1, 4, 9, 16, 25]
y2 = [1, 2, 3, 4, 5]

# Trazar múltiples líneas
plt.plot(x, y1, color='blue', linestyle='--', marker='o', label='x^2')
plt.plot(x, y2, color='red', marker='x', label='x')

# Añadir una cuadrícula
plt.grid(True)

# Añadir una leyenda (usa los 'label' de los plots)
plt.legend()

# Guardar la figura en un archivo
plt.savefig("mi_grafico.png") # Guarda antes de mostrar

# Mostrar
plt.show()
```

La visualización de datos es un campo enorme, y Matplotlib es la puerta de entrada. Con estas herramientas, ya puedes empezar a crear gráficos informativos y atractivos para tus proyectos.

---

## Ejercicios del Módulo 16 (Práctica Calificada 4)

Estos ejercicios forman la Práctica Calificada 4 y están diseñados para evaluar tu capacidad de seleccionar y crear el gráfico adecuado para representar diferentes tipos de datos.

1.  **Gráfico de Líneas Simple (Evolución de Temperatura)** (Dificultad 1.88): [m16-ejercicio1-1.md](m16-ejercicio1-1.md)
2.  **Gráfico de Barras (Comparación de Poblaciones)** (Dificultad 3.76): [m16-ejercicio2-2.md](m16-ejercicio2-2.md)
3.  **Gráfico de Dispersión (Correlación de Datos)** (Dificultad 5.64): [m16-ejercicio3-3.md](m16-ejercicio3-3.md)
4.  **Histograma de Datos Aleatorios** (Dificultad 7.52): [m16-ejercicio4-4.md](m16-ejercicio4-4.md)
5.  **Gráfico de Torta (Distribución de Gastos)** (Dificultad 9.4): [m16-ejercicio5-5.md](m16-ejercicio5-5.md)
6.  **Personalización de un Gráfico de Líneas** (Dificultad 11.28): [m16-ejercicio6-6.md](m16-ejercicio6-6.md)
7.  **Gráfico de Barras Horizontales** (Dificultad 13.16): [m16-ejercicio7-7.md](m16-ejercicio7-7.md)
8.  **Múltiples Gráficos en una Figura (Subplots)** (Dificultad 15.04): [m16-ejercicio8-8.md](m16-ejercicio8-8.md)
9.  **Combinar Gráfico de Líneas y Barras** (Dificultad 16.92): [m16-ejercicio9-9.md](m16-ejercicio9-9.md)
10. **Proyecto Final de Visualización: Dashboard Simple** (Dificultad 18.8): [m16-ejercicio10-10.md](m16-ejercicio10-10.md)
