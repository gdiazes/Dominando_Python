# Módulo 2: Variables, Datos y Operaciones Básicas en Python

## Laboratorio 2 - Guía Paso a Paso

¡Bienvenido al Laboratorio 2! En el módulo anterior, aprendiste a mostrar mensajes en la pantalla usando `print()`. Ahora, daremos un paso fundamental: aprenderemos a almacenar y manipular información usando **variables**, a entender los diferentes **tipos de datos** con los que Python trabaja, y a realizar **operaciones aritméticas** básicas.

### ¿Qué son las Variables?
Imagina que tienes cajas donde puedes guardar cosas. En programación, una **variable** es como una de esas cajas: un espacio en la memoria de la computadora donde puedes almacenar un valor (un número, un texto, etc.) y al que le das un nombre para poder referenciarlo y usarlo más tarde.

**Asignación de Variables:**
Para guardar un valor en una variable, usamos el operador de asignación, que es el signo igual (`=`).

```python
# Sintaxis: nombre_variable = valor

# Ejemplos:
edad = 30                     # Guardamos el número 30 en la variable 'edad'
nombre = "Ana"                # Guardamos el texto "Ana" en la variable 'nombre'
altura = 1.75                 # Guardamos el número decimal 1.75 en la variable 'altura'
es_estudiante = True          # Guardamos el valor booleano True en la variable 'es_estudiante'

# Podemos usar las variables con print()
print(nombre)                 # Salida: Ana
print(edad)                   # Salida: 30
print("Hola, me llamo", nombre, "y tengo", edad, "años.")
# Salida: Hola, me llamo Ana y tengo 30 años.
```

**Reglas y Convenciones para Nombres de Variables:**
*   Pueden contener letras (a-z, A-Z), números (0-9) y el guion bajo (`_`).
*   No pueden empezar con un número.
*   No pueden ser palabras reservadas de Python (palabras que Python usa para sus propias instrucciones, como `print`, `if`, `for`, `while`, etc.).
*   Python es sensible a mayúsculas y minúsculas (`edad` es diferente de `Edad`).
*   **Convención (recomendado):** Usa nombres descriptivos y en minúsculas, separando palabras con guion bajo (esto se llama *snake_case*). Ej: `mi_nombre_completo`, `precio_total`.

### Tipos de Datos Primitivos
Python maneja diferentes tipos de datos. Los más básicos (primitivos) que usaremos inicialmente son:

1.  **Enteros (`int`):** Números completos, sin decimales.
    ```python
    numero_gatos = 5
    temperatura_celsius = -10
    ```
2.  **De Punto Flotante o Reales (`float`):** Números con decimales.
    ```python
    precio_producto = 19.99
    pi = 3.14159
    distancia_km = 0.5
    ```
3.  **Cadenas de Texto (`str`):** Secuencias de caracteres, encerradas en comillas simples (`'`) o dobles (`"`).
    ```python
    saludo = "Hola, Python!"
    letra = 'c'
    direccion = "Calle Falsa 123"
    ```
4.  **Booleanos (`bool`):** Representan valores de verdad: `True` (verdadero) o `False` (falso). Nota la mayúscula inicial.
    ```python
    es_mayor_de_edad = True
    tiene_descuento = False
    ```

**La Función `type()`:**
Puedes usar la función `type()` para saber qué tipo de dato contiene una variable.
```python
x = 10
y = "Hola"
z = 3.14
activo = False

print(type(x))  # Salida: <class 'int'>
print(type(y))  # Salida: <class 'str'>
print(type(z))  # Salida: <class 'float'>
print(type(activo)) # Salida: <class 'bool'>
```
Python es un lenguaje de **tipado dinámico**, lo que significa que no necesitas declarar explícitamente el tipo de una variable; Python lo infiere automáticamente cuando le asignas un valor. Una variable puede incluso cambiar de tipo si le asignas un valor de otro tipo.

```python
mi_variable = 100
print(type(mi_variable)) # <class 'int'>
mi_variable = "Ahora soy un texto"
print(type(mi_variable)) # <class 'str'>
```

### Operadores Aritméticos
Python soporta los operadores aritméticos comunes para realizar cálculos:

| Operador | Descripción        | Ejemplo (si a=10, b=3) | Resultado |
| :------- | :----------------- | :--------------------- | :-------- |
| `+`      | Suma               | `a + b`                | `13`      |
| `-`      | Resta              | `a - b`                | `7`       |
| `*`      | Multiplicación     | `a * b`                | `30`      |
| `/`      | División           | `a / b`                | `3.333...`|
| `//`     | División Entera    | `a // b`               | `3`       |
| `%`      | Módulo (Resto)     | `a % b`                | `1`       |
| `**`     | Exponenciación     | `a ** b`               | `1000`    |

```python
numero1 = 15
numero2 = 4

suma = numero1 + numero2
resta = numero1 - numero2
multiplicacion = numero1 * numero2
division = numero1 / numero2
division_entera = numero1 // numero2
modulo = numero1 % numero2
potencia = numero1 ** 2 # 15 elevado al cuadrado

print("Suma:", suma)                     # Salida: Suma: 19
print("Resta:", resta)                   # Salida: Resta: 11
print("Multiplicación:", multiplicacion) # Salida: Multiplicación: 60
print("División:", division)             # Salida: División: 3.75
print("División Entera:", division_entera) # Salida: División Entera: 3
print("Módulo:", modulo)                 # Salida: Módulo: 3
print("Potencia (15^2):", potencia)     # Salida: Potencia (15^2): 225
```

**Precedencia de Operadores:**
Python sigue el orden matemático estándar para evaluar expresiones (PEMDAS/BODMAS: Paréntesis, Exponentes, Multiplicación/División, Suma/Resta).
```python
resultado = 5 + 2 * 3   # Primero 2*3=6, luego 5+6=11
print(resultado)        # Salida: 11

resultado_con_parentesis = (5 + 2) * 3 # Primero 5+2=7, luego 7*3=21
print(resultado_con_parentesis) # Salida: 21
```

### Conversiones de Tipo (Casting)
A veces necesitas convertir un valor de un tipo a otro. Python ofrece funciones para esto:
*   `int(valor)`: Convierte `valor` a entero (si es posible).
*   `float(valor)`: Convierte `valor` a flotante (si es posible).
*   `str(valor)`: Convierte `valor` a cadena de texto.

```python
numero_en_texto = "25"
edad_usuario = int(numero_en_texto) # Convierte la cadena "25" al entero 25
print(edad_usuario + 5)             # Salida: 30

precio_entero = 10
precio_flotante = float(precio_entero) # Convierte el entero 10 al flotante 10.0
print(precio_flotante)                 # Salida: 10.0

cantidad = 50
mensaje = "Tenemos " + str(cantidad) + " unidades." # Convierte el entero 50 a la cadena "50"
print(mensaje)                                     # Salida: Tenemos 50 unidades.
```
**¡Importante!** No todas las conversiones son posibles. Intentar convertir `"hola"` a `int` resultará en un error (`ValueError`).

Este laboratorio te ha introducido a herramientas esenciales. Las variables te permiten almacenar datos, los tipos de datos definen qué clase de información son, y los operadores te permiten manipularlos. ¡Ahora a practicar con los ejercicios!

---

## Ejercicios del Módulo 2

A continuación, se listan los ejercicios propuestos para este módulo. Se enfocarán en la declaración y uso de variables, la identificación de tipos de datos y la aplicación de operadores aritméticos.

1.  **Declaración de Variables Personales** (Dificultad 1): [m2-ejercicio1-1.md](m2-ejercicio1-1.md)
2.  **Suma de Dos Números** (Dificultad 2): [m2-ejercicio2-2.md](m2-ejercicio2-2.md)
3.  **Identificar Tipos de Datos** (Dificultad 3): [m2-ejercicio3-3.md](m2-ejercicio3-3.md)
4.  **Cálculo de Área de Rectángulo** (Dificultad 4): [m2-ejercicio4-4.md](m2-ejercicio4-4.md)
5.  **Operaciones Mixtas** (Dificultad 5): [m2-ejercicio5-5.md](m2-ejercicio5-5.md)
6.  **Conversión de Edad** (Dificultad 6): [m2-ejercicio6-6.md](m2-ejercicio6-6.md)
7.  **Cálculo de Promedio Simple** (Dificultad 7): [m2-ejercicio7-7.md](m2-ejercicio7-7.md)
8.  **División y Resto** (Dificultad 8): [m2-ejercicio8-8.md](m2-ejercicio8-8.md)
9.  **Presupuesto Mensual Simple** (Dificultad 9): [m2-ejercicio9-9.md](m2-ejercicio9-9.md)
10. **Pequeña Calculadora de Propinas** (Dificultad 10): [m2-ejercicio10-10.md](m2-ejercicio10-10.md)
