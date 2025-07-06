# Módulo 10: Reutilizando Código: Funciones en Python

## Laboratorio 10 - Guía Paso a Paso

¡Bienvenido al Laboratorio 10! Hasta ahora, hemos escrito nuestros programas como una secuencia de instrucciones. A medida que los programas crecen, este enfoque se vuelve difícil de manejar y propenso a la repetición de código. Las **funciones** son la solución a este problema. Nos permiten nombrar un bloque de código y ejecutarlo cuando queramos, tantas veces como queramos.

### ¿Qué son las Funciones?
Una **función** es un bloque de código organizado y reutilizable que realiza una acción específica. Las funciones ayudan a dividir nuestro programa en partes más pequeñas y modulares, haciendo el código más fácil de leer, probar y depurar.

Hemos estado usando funciones incorporadas desde el principio: `print()`, `len()`, `input()`, `int()`, `list()`, etc. Ahora, aprenderemos a crear las nuestras.

### Definición de una Función
Para definir una función en Python, usamos la palabra clave `def`, seguida del nombre de la función, paréntesis `()`, y dos puntos `:`. El código dentro de la función debe estar indentado.

**Sintaxis básica:**
```python
def nombre_de_la_funcion():
    # Bloque de código de la función (indentado)
    print("¡Esta función ha sido llamada!")
```

**Llamada a una Función:**
Para ejecutar el código dentro de una función, simplemente "la llamamos" escribiendo su nombre seguido de paréntesis.
```python
# Definición de la función
def saludar():
    print("¡Hola, bienvenido al mundo de las funciones!")

# Llamada a la función
saludar() # Salida: ¡Hola, bienvenido al mundo de las funciones!
saludar() # Podemos llamarla cuantas veces queramos
```

### Parámetros y Argumentos
Las funciones se vuelven mucho más poderosas cuando pueden aceptar datos para trabajar. Los datos que una función recibe se llaman **parámetros**. Los valores que le pasamos a la función cuando la llamamos se llaman **argumentos**.

```python
# 'nombre' es un parámetro de la función
def saludar_personalizado(nombre):
    print(f"¡Hola, {nombre}!")

# "Ana" y "Luis" son los argumentos que pasamos a la función
saludar_personalizado("Ana")  # Salida: ¡Hola, Ana!
saludar_personalizado("Luis") # Salida: ¡Hola, Luis!
```

**Múltiples Parámetros:**
Una función puede tener varios parámetros, separados por comas.
```python
def sumar(a, b):
    resultado = a + b
    print(f"La suma de {a} y {b} es {resultado}")

sumar(5, 3) # Salida: La suma de 5 y 3 es 8
sumar(100, -20) # Salida: La suma de 100 y -20 es 80
```

**Parámetros con Valores por Defecto:**
Puedes asignar un valor por defecto a un parámetro. Si no se proporciona un argumento para ese parámetro al llamar a la función, se usará el valor por defecto.
```python
def potencia(base, exponente=2): # 'exponente' tiene un valor por defecto de 2
    resultado = base ** exponente
    print(f"{base} elevado a {exponente} es {resultado}")

potencia(5)      # Usa el exponente por defecto 2. Salida: 5 elevado a 2 es 25
potencia(5, 3)   # Proporcionamos un argumento para exponente. Salida: 5 elevado a 3 es 125
```

### Retorno de Valores: La Sentencia `return`
Hasta ahora, nuestras funciones solo han impreso resultados en la pantalla. A menudo, queremos que una función **devuelva** un valor que podamos usar en otras partes de nuestro programa. Para esto, usamos la sentencia `return`.

Cuando Python encuentra una sentencia `return`, sale inmediatamente de la función y devuelve el valor especificado.
```python
def multiplicar(a, b):
    resultado = a * b
    return resultado

# Llamamos a la función y guardamos el valor devuelto en una variable
producto = multiplicar(6, 7)
print(f"El valor devuelto por la función es: {producto}") # Salida: 42
print(f"El producto más 10 es: {producto + 10}") # Podemos usar el valor en más cálculos

# Una función puede devolver cualquier tipo de dato
def crear_lista_pares(limite):
    pares = []
    for i in range(2, limite + 1, 2):
        pares.append(i)
    return pares

lista_resultante = crear_lista_pares(10)
print(lista_resultante) # Salida: [2, 4, 6, 8, 10]
```
Una función sin una sentencia `return` (o con `return` sin un valor) devuelve `None` por defecto.

### Alcance de Variables (Scope)
El **alcance** (o *scope*) de una variable se refiere a la parte del programa donde esa variable es accesible.

*   **Variables Locales:** Las variables creadas **dentro** de una función son locales a esa función. Solo existen y son accesibles dentro de esa función.
    ```python
    def mi_funcion():
        variable_local = "Soy local"
        print(variable_local)

    mi_funcion()
    # print(variable_local) # Esto causaría un NameError porque la variable no existe fuera de la función.
    ```

*   **Variables Globales:** Las variables creadas **fuera** de cualquier función son globales. Son accesibles desde cualquier parte del script, incluyendo dentro de las funciones (solo para lectura por defecto).
    ```python
    variable_global = "Soy global"

    def mostrar_global():
        print(f"Dentro de la función, puedo ver: {variable_global}")

    mostrar_global()
    print(f"Fuera de la función, también puedo ver: {variable_global}")
    ```
Modificar una variable global desde dentro de una función requiere la palabra clave `global`, pero esto generalmente se considera una mala práctica y debe evitarse si es posible. Es mejor que las funciones reciban datos a través de parámetros y devuelvan resultados con `return`.

### Docstrings: Documentando tus Funciones
Es una buena práctica documentar tus funciones para explicar qué hacen, qué parámetros reciben y qué devuelven. Esto se hace con una **docstring**, que es una cadena de texto multilínea justo después de la definición de la función.
```python
def calcular_area_circulo(radio):
    """
    Calcula el área de un círculo dado su radio.

    Parámetros:
    radio (int o float): El radio del círculo.

    Devuelve:
    float: El área calculada del círculo.
    """
    pi = 3.14159
    return pi * (radio ** 2)

# Puedes acceder a la docstring con help()
help(calcular_area_circulo)
```

El uso de funciones es la clave para escribir código limpio, modular, reutilizable y fácil de mantener. ¡Es una de las habilidades más importantes que aprenderás como programador!

---

## Ejercicios del Módulo 10

Estos ejercicios te guiarán en la creación y uso de tus propias funciones, cubriendo la definición básica, parámetros, valores de retorno y alcance.

1.  **Función de Saludo Simple** (Dificultad 1.41): [m10-ejercicio1-1.md](m10-ejercicio1-1.md)
2.  **Función con un Parámetro** (Dificultad 2.82): [m10-ejercicio2-2.md](m10-ejercicio2-2.md)
3.  **Función que Devuelve un Valor (Suma)** (Dificultad 4.23): [m10-ejercicio3-3.md](m10-ejercicio3-3.md)
4.  **Función con Valor por Defecto** (Dificultad 5.64): [m10-ejercicio4-4.md](m10-ejercicio4-4.md)
5.  **Función para Verificar si un Número es Par** (Dificultad 7.05): [m10-ejercicio5-5.md](m10-ejercicio5-5.md)
6.  **Función para Calcular el Área de un Círculo** (Dificultad 8.46): [m10-ejercicio6-6.md](m10-ejercicio6-6.md)
7.  **Función que Devuelve Múltiples Valores (usando una tupla)** (Dificultad 9.87): [m10-ejercicio7-7.md](m10-ejercicio7-7.md)
8.  **Función que Trabaja con una Lista (Encontrar Máximo)** (Dificultad 11.28): [m10-ejercicio8-8.md](m10-ejercicio8-8.md)
9.  **Función para Contar Vocales en un Texto** (Dificultad 12.69): [m10-ejercicio9-9.md](m10-ejercicio9-9.md)
10. **Función para Validar una Contraseña (Combinando conceptos)** (Dificultad 14.1): [m10-ejercicio10-10.md](m10-ejercicio10-10.md)

```
