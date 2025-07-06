# Módulo 5: Repitiendo con Elegancia: El Bucle `for` en Python

## Laboratorio 5 - Guía Paso a Paso

¡Bienvenido al Laboratorio 5! Hasta ahora, si queríamos repetir una acción, teníamos que escribir el código varias veces. Los **bucles** nos permiten ejecutar un bloque de código múltiples veces de forma automática. En este laboratorio, nos centraremos en el **bucle `for`**, ideal para cuando sabemos de antemano cuántas veces queremos repetir algo o cuando queremos procesar cada elemento de una colección.

### ¿Qué es un Bucle `for`?
Un bucle `for` en Python se utiliza para **iterar** sobre una secuencia (como una cadena de texto, una lista, una tupla, o un rango de números) u otros objetos iterables. En cada iteración, una variable toma el valor del siguiente elemento de la secuencia, y el bloque de código dentro del bucle se ejecuta.

**Sintaxis Básica:**
```python
for variable_iteradora in secuencia:
    # Bloque de código a ejecutar en cada iteración
    # Este bloque debe estar indentado
    print(variable_iteradora)
```

### Iterando sobre Cadenas de Texto
Una cadena de texto es una secuencia de caracteres. Podemos usar un bucle `for` para procesar cada carácter individualmente.

```python
saludo = "Hola"
for letra in saludo:
    print(letra)
```
Salida:
```
H
o
l
a
```

### La Función `range()`
Muy a menudo, queremos ejecutar un bucle un número específico de veces. La función `range()` es perfecta para esto, ya que genera una secuencia de números.

`range()` puede usarse de varias maneras:

1.  **`range(fin)`:** Genera números desde `0` hasta `fin - 1`.
    ```python
    print("Números del 0 al 4:")
    for i in range(5): # Genera 0, 1, 2, 3, 4
        print(i)
    ```

2.  **`range(inicio, fin)`:** Genera números desde `inicio` hasta `fin - 1`.
    ```python
    print("Números del 2 al 5:")
    for i in range(2, 6): # Genera 2, 3, 4, 5
        print(i)
    ```

3.  **`range(inicio, fin, paso)`:** Genera números desde `inicio` hasta `fin - 1`, incrementando/decrementando en `paso`.
    ```python
    print("Números pares del 0 al 8:")
    for i in range(0, 10, 2): # Genera 0, 2, 4, 6, 8
        print(i)

    print("Cuenta regresiva desde 5 hasta 1:")
    for i in range(5, 0, -1): # Genera 5, 4, 3, 2, 1
        print(i)
    ```
La variable `i` es un nombre común para la variable iteradora en bucles `for` con `range`, pero puedes usar cualquier nombre de variable válido.

### Acumuladores y Contadores dentro de Bucles `for`
Los bucles `for` son muy útiles para realizar cálculos repetitivos, como sumar una serie de números (usando un **acumulador**) o contar cuántas veces ocurre algo (usando un **contador**).

**Acumulador (Ejemplo: Sumar números del 1 al 5):**
```python
suma_total = 0 # 1. Inicializar el acumulador ANTES del bucle
for numero in range(1, 6): # Rango de 1 a 5 (1, 2, 3, 4, 5)
    suma_total = suma_total + numero # 2. Actualizar el acumulador DENTRO del bucle
    # Forma abreviada: suma_total += numero
print(f"La suma de los números del 1 al 5 es: {suma_total}") # 3. Usar el resultado DESPUÉS del bucle
# Salida: La suma de los números del 1 al 5 es: 15
```

**Contador (Ejemplo: Contar vocales en una palabra):**
```python
palabra = "murcielago"
contador_vocales = 0 # 1. Inicializar el contador
vocales = "aeiouAEIOU"

for letra in palabra:
    if letra in vocales: # Verifica si la letra es una vocal
        contador_vocales += 1 # 2. Incrementar el contador
print(f"La palabra '{palabra}' tiene {contador_vocales} vocales.") # 3. Usar el resultado
# Salida: La palabra 'murcielago' tiene 5 vocales.
```

### Ejemplo Práctico: Tabla de Multiplicar
```python
numero_tabla = int(input("Ingresa un número para ver su tabla de multiplicar: "))

print(f"--- Tabla del {numero_tabla} ---")
for i in range(1, 11): # Queremos multiplicar del 1 al 10
    resultado = numero_tabla * i
    print(f"{numero_tabla} x {i} = {resultado}")
```

Los bucles `for` son una herramienta poderosa para la automatización de tareas repetitivas y el procesamiento de datos secuenciales. Con la práctica, se convertirán en una parte esencial de tu conjunto de herramientas de programación.

---

## Ejercicios del Módulo 5

Estos ejercicios te ayudarán a practicar el uso de bucles `for` con `range()`, iterando sobre cadenas, y utilizando contadores y acumuladores.

1.  **Imprimir Números del 1 al 10** (Dificultad 1.1): [m5-ejercicio1-1.md](m5-ejercicio1-1.md)
2.  **Sumar los Primeros N Números Naturales** (Dificultad 2.2): [m5-ejercicio2-2.md](m5-ejercicio2-2.md)
3.  **Mostrar Caracteres de una Cadena** (Dificultad 3.3): [m5-ejercicio3-3.md](m5-ejercicio3-3.md)
4.  **Tabla de Multiplicar Específica** (Dificultad 4.4): [m5-ejercicio4-4.md](m5-ejercicio4-4.md)
5.  **Contar Vocales en una Frase** (Dificultad 5.5): [m5-ejercicio5-5.md](m5-ejercicio5-5.md)
6.  **Imprimir Números Pares en un Rango** (Dificultad 6.6): [m5-ejercicio6-6.md](m5-ejercicio6-6.md)
7.  **Generar una Secuencia Inversa** (Dificultad 7.7): [m5-ejercicio7-7.md](m5-ejercicio7-7.md)
8.  **Calcular Factorial de un Número** (Dificultad 8.8): [m5-ejercicio8-8.md](m5-ejercicio8-8.md)
9.  **Dibujar un Cuadrado con Asteriscos** (Dificultad 9.9): [m5-ejercicio9-9.md](m5-ejercicio9-9.md)
10. **Simulador de Lanzamiento de Dados Múltiples y Suma** (Dificultad 11.0): [m5-ejercicio10-10.md](m5-ejercicio10-10.md)
