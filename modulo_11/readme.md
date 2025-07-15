# Módulo 11: Avanzando con Funciones y una Introducción a Lambda

## Laboratorio 11 - Guía Paso a Paso

¡Bienvenido al Laboratorio 11! Ya has dominado la creación y uso de funciones básicas. En este laboratorio, exploraremos algunas de las características más avanzadas y elegantes de las funciones en Python, lo que te permitirá escribir código más flexible y conciso. Veremos cómo trabajar con un número variable de argumentos y daremos una primera mirada a las funciones `lambda`.

### Argumentos Variables: `*args`
A veces, no sabes de antemano cuántos argumentos posicionales necesitará recibir tu función. Python te permite manejar esto con la sintaxis `*args`.
Cuando usas `*args` como parámetro, todos los argumentos posicionales extra que se pasen a la función se agruparán en una **tupla**.

```python
# La convención es usar el nombre 'args', pero podría ser *cualquier_nombre
def sumar_todos(*numeros):
    print(f"Tipo de 'numeros': {type(numeros)}") # Verás que es una tupla
    suma = 0
    for num in numeros:
        suma += num
    return suma

# Podemos llamar a la función con diferente cantidad de argumentos
print(sumar_todos(1, 2, 3))       # Salida: Tipo de 'numeros': <class 'tuple'> \n 6
print(sumar_todos(10, 20, 30, 40)) # Salida: Tipo de 'numeros': <class 'tuple'> \n 100
print(sumar_todos(5))             # Salida: Tipo de 'numeros': <class 'tuple'> \n 5
print(sumar_todos())              # Salida: Tipo de 'numeros': <class 'tuple'> \n 0
```
`*args` es útil para funciones que realizan operaciones sobre un conjunto de valores, como promediar, sumar o encontrar el máximo.

### Argumentos Variables de Palabra Clave: `**kwargs`
De manera similar a `*args`, `**kwargs` te permite manejar un número arbitrario de **argumentos de palabra clave** (keyword arguments).
Cuando usas `**kwargs`, todos los argumentos de palabra clave extra se agrupan en un **diccionario**.

```python
# La convención es usar 'kwargs' (keyword args)
def mostrar_info_persona(**datos_persona):
    print(f"Tipo de 'datos_persona': {type(datos_persona)}") # Verás que es un diccionario
    for clave, valor in datos_persona.items():
        print(f"{clave.capitalize()}: {valor}")
    print("-" * 20)

mostrar_info_persona(nombre="Carlos", edad=42, ciudad="Madrid")
# Salida:
# Tipo de 'datos_persona': <class 'dict'>
# Nombre: Carlos
# Edad: 42
# Ciudad: Madrid
# --------------------

mostrar_info_persona(nombre="Elena", profesion="Doctora")
# Salida:
# Tipo de 'datos_persona': <class 'dict'>
# Nombre: Elena
# Profesion: Doctora
# --------------------
```
`**kwargs` es muy útil para funciones que necesitan procesar configuraciones flexibles o atributos de un objeto.

### Combinando Tipos de Argumentos
Puedes combinar argumentos normales, `*args` y `**kwargs` en una definición de función. El orden debe ser:
1.  Argumentos posicionales normales.
2.  `*args`.
3.  Argumentos de palabra clave normales (si los hay después de `*args`).
4.  `**kwargs`.

```python
def funcion_completa(arg1, arg2, *args, kwarg1="default", **kwargs):
    print(f"arg1: {arg1}")
    print(f"arg2: {arg2}")
    print(f"args: {args}")
    print(f"kwarg1: {kwarg1}")
    print(f"kwargs: {kwargs}")

funcion_completa(10, 20, 30, 40, 50, kwarg1="custom", nombre="Juan", edad=25)
# Salida:
# arg1: 10
# arg2: 20
# args: (30, 40, 50)
# kwarg1: custom
# kwargs: {'nombre': 'Juan', 'edad': 25}
```

### Funciones como Ciudadanos de Primera Clase
En Python, las funciones son "ciudadanos de primera clase". Esto significa que puedes tratarlas como cualquier otro objeto:
*   Asignarlas a variables.
*   Pasarlas como argumentos a otras funciones.
*   Devolverlas desde otras funciones.

```python
def saludar():
    return "¡Hola!"

def despedir():
    return "¡Adiós!"

# Asignar una función a una variable
mi_saludo = saludar
print(mi_saludo()) # Salida: ¡Hola!

# Pasar una función como argumento
def ejecutar_funcion(func):
    # Llama a la función que se pasó como argumento
    print(f"Ejecutando la función... Resultado: {func()}")

ejecutar_funcion(saludar)  # Salida: Ejecutando la función... Resultado: ¡Hola!
ejecutar_funcion(despedir) # Salida: Ejecutando la función... Resultado: ¡Adiós!
```
Esta capacidad es la base de muchos patrones avanzados en Python, como los decoradores.

### Funciones Anónimas: `lambda`
A veces necesitas una función pequeña y simple para un uso rápido, y definirla con `def` parece excesivo. Para esto, Python ofrece las **funciones lambda**. Son funciones anónimas (sin nombre) y de una sola línea.

**Sintaxis:**
`lambda argumentos: expresion`

La `expresion` se evalúa y se devuelve como resultado de la función.
```python
# Función normal
def duplicar(n):
    return n * 2

# Función lambda equivalente
duplicar_lambda = lambda n: n * 2

print(duplicar(5))          # Salida: 10
print(duplicar_lambda(5))   # Salida: 10

# Lambda con múltiples argumentos
sumar_lambda = lambda a, b: a + b
print(sumar_lambda(3, 4))   # Salida: 7
```
**¿Dónde se usan las lambdas?**
Son especialmente útiles cuando se usan junto a funciones que esperan otra función como argumento, como `map()`, `filter()` y `sorted()`.

*   `map(funcion, iterable)`: Aplica `funcion` a cada elemento de `iterable`.
    ```python
    numeros = [1, 2, 3, 4]
    cuadrados = list(map(lambda x: x**2, numeros))
    print(cuadrados) # Salida: [1, 4, 9, 16]
    ```
*   `filter(funcion, iterable)`: Filtra elementos de `iterable`, devolviendo solo aquellos para los que `funcion` devuelve `True`.
    ```python
    numeros = [1, 2, 3, 4, 5, 6]
    pares = list(filter(lambda x: x % 2 == 0, numeros))
    print(pares) # Salida: [2, 4, 6]
    ```
*   `sorted(iterable, key=funcion)`: Ordena un iterable. `key` es una función que se usa para extraer una clave de comparación de cada elemento.
    ```python
    nombres_con_edad = [("Ana", 30), ("Luis", 25), ("Eva", 35)]
    # Ordenar por edad (el segundo elemento de cada tupla)
    ordenados_por_edad = sorted(nombres_con_edad, key=lambda persona: persona[1])
    print(ordenados_por_edad) # Salida: [('Luis', 25), ('Ana', 30), ('Eva', 35)]
    ```

Estos conceptos avanzados de funciones te proporcionan herramientas muy flexibles para resolver problemas de formas más eficientes y elegantes.

---

## Ejercicios del Módulo 11

Estos ejercicios se centran en el uso de `*args`, `**kwargs`, y funciones `lambda` para resolver problemas de manera más flexible y concisa.

1.  **Función Sumadora con `*args`** (Dificultad 1.48): [m11-ejercicio1-1.md](m11-ejercicio1-1.md)
2.  **Concatenador de Cadenas con `*args`** (Dificultad 2.96): [m11-ejercicio2-2.md](m11-ejercicio2-2.md)
3.  **Creador de Perfiles con `**kwargs`** (Dificultad 4.44): [m11-ejercicio3-3.md](m11-ejercicio3-3.md)
4.  **Función Completa con Argumentos Mixtos** (Dificultad 5.92): [m11-ejercicio4-4.md](m11-ejercicio4-4.md)
5.  **Función Lambda Simple para Multiplicar** (Dificultad 7.4): [m11-ejercicio5-5.md](m11-ejercicio5-5.md)
6.  **Uso de `map` con Lambda para Duplicar Números** (Dificultad 8.88): [m11-ejercicio6-6.md](m11-ejercicio6-6.md)
7.  **Uso de `filter` con Lambda para Filtrar Nombres Cortos** (Dificultad 10.36): [m11-ejercicio7-7.md](m11-ejercicio7-7.md)
8.  **Uso de `sorted` con Lambda para Ordenar por Longitud** (Dificultad 11.84): [m11-ejercicio8-8.md](m11-ejercicio8-8.md) (PC3 Integrada)
9.  **Procesador de Comandos con `*args` y `**kwargs`** (Dificultad 13.32): [m11-ejercicio9-9.md](m11-ejercicio9-9.md) (PC3 Integrada)
10. **Calculadora Flexible con Lambda** (Dificultad 14.8): [m11-ejercicio10-10.md](m11-ejercicio10-10.md) (PC3 Integrada)
