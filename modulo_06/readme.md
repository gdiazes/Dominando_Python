# Módulo 6: Controlando la Repetición: El Bucle `while` y Bucles Anidados en Python

## Laboratorio 6 - Guía Paso a Paso

¡Bienvenido al Laboratorio 6! En el laboratorio anterior, exploramos el bucle `for`, que es ideal cuando sabemos de antemano cuántas veces queremos iterar o si queremos recorrer los elementos de una secuencia. Ahora, aprenderemos sobre el bucle `while`, que repite un bloque de código **mientras** una condición específica sea verdadera. También veremos cómo **anidar** bucles, es decir, poner un bucle dentro de otro.

### El Bucle `while`
El bucle `while` ejecuta un bloque de código repetidamente siempre y cuando una condición dada siga siendo `True`.

**Sintaxis básica:**
```python
while condicion:
    # Bloque de código a repetir (indentado)
    # Este bloque se ejecuta mientras 'condicion' sea True
    # ¡Es crucial que algo dentro del bucle eventualmente haga que 'condicion' sea False,
    # o se creará un bucle infinito!
```

**Ejemplo: Contar del 1 al 5 usando `while`**
```python
contador = 1 # 1. Inicializar la variable de control
while contador <= 5: # 2. Condición del bucle
    print(contador)
    contador += 1 # 3. Actualizar la variable de control (¡muy importante!)
# Salida:
# 1
# 2
# 3
# 4
# 5
print("¡Bucle terminado!")
```
Los tres componentes clave de un bucle `while` típico que se ejecuta un número controlado de veces son:
1.  **Inicialización:** Se establece una variable de control antes de que comience el bucle.
2.  **Condición:** Se evalúa antes de cada iteración. Si es `True`, el cuerpo del bucle se ejecuta.
3.  **Actualización:** Dentro del bucle, la variable de control (u otra variable que afecte la condición) debe modificarse para que, eventualmente, la condición se vuelva `False` y el bucle termine.

**Bucles Infinitos y Cómo Evitarlos:**
Si la condición de un bucle `while` nunca se vuelve `False`, el bucle se ejecutará indefinidamente, creando un **bucle infinito**. Esto suele ocurrir si olvidas actualizar la variable que controla la condición.
```python
# ¡CUIDADO! BUCLE INFINITO DE EJEMPLO (NO EJECUTAR SI NO SABES CÓMO DETENERLO - Ctrl+C)
# contador = 1
# while contador <= 5:
#     print("Esto se imprimirá para siempre...")
#     # Falta contador += 1
```

### Uso de `break` en Bucles `while`
Al igual que con los bucles `for`, la instrucción `break` se puede usar para salir de un bucle `while` prematuramente, incluso si la condición principal del bucle sigue siendo `True`.
```python
numero = 0
while numero < 10:
    print(numero)
    if numero == 3:
        print("Encontré el 3, ¡saliendo del bucle!")
        break # Termina el bucle inmediatamente
    numero += 1
# Salida:
# 0
# 1
# 2
# 3
# Encontré el 3, ¡saliendo del bucle!
```

### Uso de `continue` en Bucles `while`
La instrucción `continue` omite el resto del código dentro del cuerpo del bucle para la iteración actual y salta directamente a la siguiente evaluación de la condición del `while`.
```python
x = 0
while x < 5:
    x += 1
    if x == 3:
        print("Omitiendo el 3")
        continue # Salta el print(x) de esta iteración
    print(x)
# Salida:
# 1
# 2
# Omitiendo el 3
# 4
# 5
```

### Bucles `while` para Validación de Entrada
Un uso muy común del bucle `while` es para validar la entrada del usuario, repitiendo la solicitud hasta que se ingrese un valor válido.
```python
edad_str = input("Ingresa tu edad (debe ser un número positivo): ")

# Validar si la entrada es un dígito y luego si es positiva
while not edad_str.isdigit() or int(edad_str) <= 0:
    print("Entrada inválida.")
    edad_str = input("Por favor, ingresa tu edad (un número positivo): ")

edad = int(edad_str)
print(f"Gracias. Tu edad es {edad}.")
```

### Bucles Anidados
Puedes colocar un bucle dentro de otro bucle. Esto se conoce como **anidamiento de bucles**. El bucle interno se completa totalmente por cada iteración del bucle externo.
Se pueden anidar bucles `for` dentro de `for`, `while` dentro de `while`, `for` dentro de `while`, o `while` dentro de `for`.

**Ejemplo: Imprimir coordenadas (usando `for` anidados)**
```python
for i in range(3): # Bucle externo (0, 1, 2)
    for j in range(2): # Bucle interno (0, 1)
        print(f"({i}, {j})")
# Salida:
# (0, 0)
# (0, 1)
# (1, 0)
# (1, 1)
# (2, 0)
# (2, 1)
```
El bucle interno (`for j...`) se ejecuta completamente (0, 1) para cada valor de `i` del bucle externo.

**Ejemplo: Patrón con `while` anidados**
```python
fila = 1
while fila <= 3: # Bucle externo para las filas
    columna = 1
    linea = ""
    while columna <= fila: # Bucle interno para las 'columnas' o elementos en la fila
        linea += str(columna) + " "
        columna += 1
    print(linea)
    fila += 1
# Salida:
# 1 
# 1 2 
# 1 2 3 
```

Los bucles `while` ofrecen flexibilidad cuando el número de iteraciones no se conoce de antemano, y los bucles anidados permiten abordar problemas más complejos que requieren iteraciones multidimensionales o repetitivas dentro de otras repeticiones.

---

## Ejercicios del Módulo 6

Estos ejercicios te ayudarán a practicar el uso de bucles `while`, las sentencias `break` y `continue`, y la creación de bucles anidados.

1.  **Contador Ascendente con `while`** (Dificultad 1.16): [m6-ejercicio1-1.md](m6-ejercicio1-1.md)
2.  **Adivinar un Número Secreto (con `while`)** (Dificultad 2.31): [m6-ejercicio2-2.md](m6-ejercicio2-2.md)
3.  **Validación de Entrada Positiva con `while`** (Dificultad 3.47): [m6-ejercicio3-3.md](m6-ejercicio3-3.md)
4.  **Sumar Números Hasta Ingresar Cero (con `while` y `break`)** (Dificultad 4.62): [m6-ejercicio4-4.md](m6-ejercicio4-4.md)
5.  **Imprimir Números Pares Omitiendo Múltiplos de 4 (con `while` y `continue`)** (Dificultad 5.78): [m6-ejercicio5-5.md](m6-ejercicio5-5.md)
6.  **Tabla de Multiplicar Completa (1 al 10) usando Bucles Anidados `for`** (Dificultad 6.93): [m6-ejercicio6-6.md](m6-ejercicio6-6.md)
7.  **Dibujar un Rectángulo de Asteriscos con Bucles Anidados `for`** (Dificultad 8.09): [m6-ejercicio7-7.md](m6-ejercicio7-7.md)
8.  **Menú Interactivo Simple con `while` (Sumadora/Restadora)** (Dificultad 9.24): [m6-ejercicio8-8.md](m6-ejercicio8-8.md)
9.  **Encontrar el MCD (Máximo Común Divisor) de Dos Números usando `while`** (Dificultad 10.4): [m6-ejercicio9-9.md](m6-ejercicio9-9.md)
10. **Simulación de Batalla por Turnos Simple con Bucles `while` Anidados** (Dificultad 11.55): [m6-ejercicio10-10.md](m6-ejercicio10-10.md)
