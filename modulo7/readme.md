# Módulo 7: Organizando Datos: Listas en Python

## Laboratorio 7 - Guía Paso a Paso

¡Bienvenido al Laboratorio 7! Hasta ahora, hemos trabajado principalmente con variables que almacenan un solo valor (un número, una cadena, un booleano). Pero, ¿qué sucede cuando necesitamos manejar una colección de valores relacionados, como una lista de nombres, una serie de temperaturas, o las puntuaciones de un juego? Para esto, Python nos ofrece las **Listas**.

### ¿Qué son las Listas?
Una **lista** en Python es una colección ordenada y mutable de elementos.
*   **Ordenada:** Los elementos se almacenan en un orden específico y mantienen ese orden.
*   **Mutable:** Puedes cambiar los elementos de una lista después de haberla creado (añadir, eliminar, modificar).
*   **Heterogénea (generalmente):** Los elementos de una lista pueden ser de diferentes tipos de datos (aunque es común que las listas contengan elementos del mismo tipo por coherencia).

**Creación de Listas:**
Las listas se crean encerrando los elementos entre corchetes `[]`, separados por comas.
```python
# Lista vacía
lista_vacia = []
print(lista_vacia) # Salida: []

# Lista de números
numeros = [1, 2, 3, 4, 5]
print(numeros) # Salida: [1, 2, 3, 4, 5]

# Lista de cadenas
nombres = ["Ana", "Luis", "Eva"]
print(nombres) # Salida: ['Ana', 'Luis', 'Eva']

# Lista mixta (posible, pero menos común para operaciones homogéneas)
mixta = [1, "hola", 3.14, True]
print(mixta) # Salida: [1, 'hola', 3.14, True]
```

### Acceso a Elementos de una Lista (Indexación)
Puedes acceder a elementos individuales de una lista utilizando su **índice**. Los índices en Python comienzan en `0` para el primer elemento.
```python
frutas = ["manzana", "banana", "cereza", "naranja"]

# Acceder al primer elemento (índice 0)
print(frutas[0]) # Salida: manzana

# Acceder al tercer elemento (índice 2)
print(frutas[2]) # Salida: cereza

# Índices negativos: cuentan desde el final (-1 es el último, -2 el penúltimo, etc.)
print(frutas[-1]) # Salida: naranja (último elemento)
print(frutas[-2]) # Salida: cereza (penúltimo elemento)
```
Intentar acceder a un índice que no existe causará un error (`IndexError`).

### Slicing (Rebanado) de Listas
El slicing te permite obtener una **sublista** (una porción de la lista).
Sintaxis: `lista[inicio:fin:paso]`
*   `inicio`: Índice donde comienza el slice (incluido). Si se omite, es 0.
*   `fin`: Índice donde termina el slice (excluido). Si se omite, es hasta el final.
*   `paso`: El intervalo entre elementos. Si se omite, es 1.

```python
numeros = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

# Desde el índice 2 hasta el 4 (índice 5 no incluido)
print(numeros[2:5]) # Salida: [2, 3, 4]

# Desde el inicio hasta el índice 3 (índice 4 no incluido)
print(numeros[:4]) # Salida: [0, 1, 2, 3]

# Desde el índice 6 hasta el final
print(numeros[6:]) # Salida: [6, 7, 8, 9]

# Todos los elementos
print(numeros[:]) # Salida: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9] (una copia superficial)

# Con paso
print(numeros[1:7:2]) # Salida: [1, 3, 5] (del índice 1 al 6, de 2 en 2)
```

### Modificación de Listas
Como las listas son mutables, puedes cambiar sus elementos.

**Cambiar un elemento:**
```python
colores = ["rojo", "verde", "azul"]
colores[1] = "amarillo" # Cambia "verde" por "amarillo"
print(colores) # Salida: ['rojo', 'amarillo', 'azul']
```

**Añadir elementos:**
*   `.append(elemento)`: Añade `elemento` al final de la lista.
    ```python
    numeros = [1, 2, 3]
    numeros.append(4)
    print(numeros) # Salida: [1, 2, 3, 4]
    ```
*   `.insert(indice, elemento)`: Inserta `elemento` en la posición `indice`.
    ```python
    numeros = [1, 2, 4]
    numeros.insert(2, 3) # Inserta el 3 en el índice 2
    print(numeros) # Salida: [1, 2, 3, 4]
    ```
*   Concatenar con `+` (crea una nueva lista):
    ```python
    lista1 = [1, 2]
    lista2 = [3, 4]
    lista_combinada = lista1 + lista2
    print(lista_combinada) # Salida: [1, 2, 3, 4]
    ```

**Eliminar elementos:**
*   `del lista[indice]`: Elimina el elemento en la posición `indice`.
    ```python
    letras = ['a', 'b', 'c', 'd']
    del letras[1] # Elimina 'b'
    print(letras) # Salida: ['a', 'c', 'd']
    ```
*   `.pop(indice)`: Elimina y **devuelve** el elemento en `indice`. Si no se especifica `indice`, elimina y devuelve el último elemento.
    ```python
    letras = ['a', 'b', 'c']
    elemento_eliminado = letras.pop(0) # Elimina 'a' y lo guarda
    print(letras)                 # Salida: ['b', 'c']
    print(elemento_eliminado)     # Salida: a
    ultimo = letras.pop()           # Elimina y devuelve 'c'
    print(letras)                 # Salida: ['b']
    print(ultimo)                 # Salida: c
    ```
*   `.remove(valor)`: Elimina la **primera ocurrencia** del `valor` especificado. Causa un `ValueError` si el valor no está en la lista.
    ```python
    numeros = [1, 2, 3, 2, 4]
    numeros.remove(2) # Elimina la primera aparición de 2
    print(numeros)    # Salida: [1, 3, 2, 4]
    ```

### Métodos Comunes de Listas
Las listas tienen muchos métodos útiles:

*   `len(lista)` (Función): Devuelve el número de elementos en la lista.
    ```python
    mi_lista = [10, 20, 30]
    print(len(mi_lista)) # Salida: 3
    ```
*   `.sort()`: Ordena los elementos de la lista *in situ* (modifica la lista original). Por defecto, ordena en ascendente.
    ```python
    numeros = [3, 1, 4, 1, 5, 9, 2]
    numeros.sort()
    print(numeros) # Salida: [1, 1, 2, 3, 4, 5, 9]
    numeros.sort(reverse=True) # Orden descendente
    print(numeros) # Salida: [9, 5, 4, 3, 2, 1, 1]
    ```
*   `sorted(lista)` (Función): Devuelve una **nueva lista** ordenada, sin modificar la original.
    ```python
    nombres = ["Carlos", "Ana", "Bernardo"]
    nombres_ordenados = sorted(nombres)
    print(nombres)            # Salida: ['Carlos', 'Ana', 'Bernardo'] (original sin cambios)
    print(nombres_ordenados)  # Salida: ['Ana', 'Bernardo', 'Carlos']
    ```
*   `.reverse()`: Invierte el orden de los elementos de la lista *in situ*.
    ```python
    mi_lista = [1, 2, 3, 4]
    mi_lista.reverse()
    print(mi_lista) # Salida: [4, 3, 2, 1]
    ```
*   `.count(valor)`: Devuelve el número de veces que `valor` aparece en la lista.
    ```python
    numeros = [1, 2, 2, 3, 2, 4]
    print(numeros.count(2)) # Salida: 3
    ```
*   `.index(valor)`: Devuelve el índice de la primera ocurrencia de `valor`. Causa `ValueError` si no se encuentra.
    ```python
    letras = ['x', 'y', 'z', 'y']
    print(letras.index('y')) # Salida: 1
    ```
*   `valor in lista`: (Operador, no método) Devuelve `True` si `valor` está en la lista, `False` en caso contrario.
    ```python
    numeros = [10, 20, 30]
    print(20 in numeros)  # Salida: True
    print(40 in numeros)  # Salida: False
    ```

### Iterar sobre Listas con Bucles `for`
Es muy común usar bucles `for` para procesar cada elemento de una lista.
```python
nombres = ["Alicia", "Bruno", "Carmen"]
for nombre in nombres:
    print(f"Hola, {nombre}!")

# Iterar con índice y valor usando enumerate()
for indice, nombre in enumerate(nombres):
    print(f"Índice {indice}: {nombre}")
# Salida:
# Índice 0: Alicia
# Índice 1: Bruno
# Índice 2: Carmen
```

### Listas de Listas (Matrices Básicas)
Puedes tener listas cuyos elementos sean otras listas. Esto se usa a menudo para representar matrices o tablas.
```python
matriz = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

# Acceder al elemento en la fila 1, columna 2 (el 6)
print(matriz[1][2]) # Salida: 6

# Iterar sobre una matriz
for fila in matriz:
    print(fila) # Imprime cada lista interna
    for elemento in fila:
        print(elemento, end=" ") # Imprime cada elemento de la fila
    print() # Nueva línea después de cada fila
```

Las listas son una de las estructuras de datos más fundamentales y versátiles en Python. ¡Dominarlas te permitirá organizar y manipular datos de manera eficiente!

---

## Ejercicios del Módulo 7

Estos ejercicios te ayudarán a practicar la creación, manipulación, acceso e iteración de listas en Python.

1.  **Crear y Mostrar una Lista Simple** (Dificultad 1.22): [m7-ejercicio1-1.md](m7-ejercicio1-1.md)
2.  **Acceder y Modificar Elementos de una Lista** (Dificultad 2.43): [m7-ejercicio2-2.md](m7-ejercicio2-2.md)
3.  **Añadir y Eliminar Elementos de una Lista** (Dificultad 3.65): [m7-ejercicio3-3.md](m7-ejercicio3-3.md)
4.  **Iterar sobre una Lista y Mostrar Elementos** (Dificultad 4.86): [m7-ejercicio4-4.md](m7-ejercicio4-4.md)
5.  **Suma de Elementos de una Lista Numérica** (Dificultad 6.08): [m7-ejercicio5-5.md](m7-ejercicio5-5.md)
6.  **Encontrar el Elemento Mayor y Menor en una Lista** (Dificultad 7.29): [m7-ejercicio6-6.md](m7-ejercicio6-6.md)
7.  **Contar Ocurrencias de un Elemento en una Lista** (Dificultad 8.51): [m7-ejercicio7-7.md](m7-ejercicio7-7.md)
8.  **Ordenar una Lista e Invertirla** (Dificultad 9.72): [m7-ejercicio8-8.md](m7-ejercicio8-8.md) (PC2 Integrada)
9.  **Filtrar Números Pares de una Lista** (Dificultad 10.94): [m7-ejercicio9-9.md](m7-ejercicio9-9.md) (PC2 Integrada)
10. **Operaciones con una Lista de Listas (Matriz Simple)** (Dificultad 12.15): [m7-ejercicio10-10.md](m7-ejercicio10-10.md) (PC2 Integrada)

