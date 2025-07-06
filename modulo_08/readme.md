# Módulo 8: Colecciones Inmutables y Secuencias Ordenadas: Tuplas en Python

## Laboratorio 8 - Guía Paso a Paso

¡Bienvenido al Laboratorio 8! Ya conoces las listas, que son colecciones ordenadas y *mutables*. Ahora, vamos a explorar otra estructura de datos fundamental en Python: las **tuplas**. Las tuplas son muy similares a las listas, pero con una diferencia crucial: son **inmutables**.

### ¿Qué son las Tuplas?
Una **tupla** es una colección ordenada e **inmutable** de elementos.
*   **Ordenada:** Al igual que las listas, los elementos en una tupla tienen un orden definido y lo mantienen.
*   **Inmutable:** Una vez que una tupla es creada, no puedes cambiar, añadir o eliminar sus elementos. Intentarlo resultará en un error (`TypeError`).

**¿Por qué usar Tuplas si tenemos Listas?**
1.  **Seguridad de los datos:** Al ser inmutables, las tuplas protegen tus datos contra modificaciones accidentales. Son ideales para datos que no deben cambiar, como coordenadas, constantes, o registros fijos.
2.  **Rendimiento:** Las tuplas pueden ser ligeramente más rápidas que las listas en términos de procesamiento, ya que su tamaño fijo permite a Python realizar optimizaciones internas.
3.  **Uso como claves de diccionario:** Debido a su inmutabilidad, las tuplas pueden ser usadas como claves en diccionarios, mientras que las listas no. (Veremos diccionarios más adelante).

**Creación de Tuplas:**
Las tuplas se crean encerrando los elementos entre paréntesis `()`, separados por comas.
```python
# Tupla vacía
tupla_vacia = ()
print(tupla_vacia) # Salida: ()

# Tupla de números
coordenadas = (10, 20)
print(coordenadas) # Salida: (10, 20)

# Tupla de cadenas
dias_semana = ("Lunes", "Martes", "Miércoles")
print(dias_semana) # Salida: ('Lunes', 'Martes', 'Miércoles')

# Los paréntesis son opcionales en muchos casos si la coma está presente
mi_tupla = 1, 2, 3
print(mi_tupla) # Salida: (1, 2, 3)

# ¡Caso especial! Creación de una tupla con un solo elemento
# No es suficiente poner (valor). Debes incluir una coma al final.
tupla_un_elemento = (5,) # La coma es crucial
print(tupla_un_elemento) # Salida: (5,)

sin_coma = (5) # Esto es solo el número 5, no una tupla
print(sin_coma) # Salida: 5
```

### Acceso y Slicing de Tuplas
El acceso a elementos y el rebanado (slicing) en las tuplas funcionan exactamente igual que en las listas, usando índices entre corchetes `[]`.
```python
punto_3d = (10, 20, 30)

# Acceder al primer elemento
print(punto_3d[0]) # Salida: 10

# Acceder al último elemento
print(punto_3d[-1]) # Salida: 30

# Slicing para obtener una nueva tupla
sub_tupla = punto_3d[0:2]
print(sub_tupla) # Salida: (10, 20)
```

### La Inmutabilidad en Acción
A diferencia de las listas, no puedes modificar una tupla una vez creada.
```python
mi_tupla = (1, 2, 3)

# Esto causará un TypeError: 'tuple' object does not support item assignment
# mi_tupla[0] = 100

# Esto causará un AttributeError: 'tuple' object has no attribute 'append'
# mi_tupla.append(4)

# Esto causará un AttributeError: 'tuple' object has no attribute 'pop'
# mi_tupla.pop()
```
**¿Qué hacer si necesitas "modificar" una tupla?**
No puedes modificar la tupla original. La solución es crear una *nueva* tupla basada en la anterior.
```python
tupla_vieja = (1, 2, 3)
# Para "añadir" un elemento, concatenamos para crear una nueva tupla
tupla_nueva = tupla_vieja + (4,) # Concatenar con otra tupla
print(tupla_nueva) # Salida: (1, 2, 3, 4)
print(tupla_vieja) # Salida: (1, 2, 3) (la original no cambió)
```

### Métodos de Tuplas
Debido a su inmutabilidad, las tuplas tienen muy pocos métodos. Los dos principales son:

*   `.count(valor)`: Devuelve el número de veces que `valor` aparece en la tupla.
*   `.index(valor)`: Devuelve el índice de la primera ocurrencia de `valor`. Causa `ValueError` si no se encuentra.
```python
numeros = (1, 2, 5, 2, 3, 2)
print(numeros.count(2)) # Salida: 3
print(numeros.index(5)) # Salida: 2
```

### Desempaquetado de Tuplas (Tuple Unpacking)
Esta es una característica muy poderosa y común en Python. Te permite asignar los elementos de una tupla a múltiples variables en una sola línea.
```python
# Asignación de coordenadas a variables x e y
coordenadas = (100, 250)
x, y = coordenadas

print(f"La coordenada x es: {x}") # Salida: La coordenada x es: 100
print(f"La coordenada y es: {y}") # Salida: La coordenada y es: 250
```
El número de variables a la izquierda debe coincidir con el número de elementos en la tupla. El desempaquetado es muy útil, por ejemplo, cuando una función devuelve múltiples valores (generalmente como una tupla).

### Conversión entre Listas y Tuplas
Puedes convertir fácilmente entre estas dos estructuras de datos usando las funciones `list()` y `tuple()`.
```python
mi_lista = [1, 2, 3]
mi_tupla_desde_lista = tuple(mi_lista)
print(mi_tupla_desde_lista) # Salida: (1, 2, 3)

mi_tupla = ('a', 'b', 'c')
mi_lista_desde_tupla = list(mi_tupla)
print(mi_lista_desde_tupla) # Salida: ['a', 'b', 'c']
```
Este es un patrón común: si necesitas modificar una tupla, puedes convertirla a una lista, hacer los cambios, y luego convertirla de nuevo a una tupla.

Las tuplas son una parte esencial del ecosistema de Python, proporcionando una forma segura y eficiente de manejar colecciones de datos que no deben cambiar.

---

## Ejercicios del Módulo 8

Estos ejercicios te ayudarán a practicar la creación, uso y comprensión de las tuplas y su diferencia clave con las listas: la inmutabilidad.

1.  **Crear y Acceder a una Tupla** (Dificultad 1.28): [m8-ejercicio1-1.md](m8-ejercicio1-1.md)
2.  **Intento de Modificación de una Tupla** (Dificultad 2.56): [m8-ejercicio2-2.md](m8-ejercicio2-2.md)
3.  **Desempaquetado de Tuplas** (Dificultad 3.84): [m8-ejercicio3-3.md](m8-ejercicio3-3.md)
4.  **Tupla con un Solo Elemento** (Dificultad 5.12): [m8-ejercicio4-4.md](m8-ejercicio4-4.md)
5.  **Iterar sobre una Tupla** (Dificultad 6.4): [m8-ejercicio5-5.md](m8-ejercicio5-5.md)
6.  **Métodos de Tupla (`.count()` y `.index()`)** (Dificultad 7.68): [m8-ejercicio6-6.md](m8-ejercicio6-6.md)
7.  **Concatenar Tuplas para "Añadir" un Elemento** (Dificultad 8.96): [m8-ejercicio7-7.md](m8-ejercicio7-7.md)
8.  **Conversión entre Lista y Tupla para Modificar** (Dificultad 10.24): [m8-ejercicio8-8.md](m8-ejercicio8-8.md)
9.  **Uso de Tuplas para Devolver Múltiples Valores de una "Función Simulada"** (Dificultad 11.52): [m8-ejercicio9-9.md](m8-ejercicio9-9.md)
10. **Tuplas Anidadas (Coordenadas de un Triángulo)** (Dificultad 12.8): [m8-ejercicio10-10.md](m8-ejercicio10-10.md)
