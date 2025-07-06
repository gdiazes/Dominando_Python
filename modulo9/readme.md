# Módulo 9: Pares Clave-Valor: Diccionarios en Python

## Laboratorio 9 - Guía Paso a Paso

¡Bienvenido al Laboratorio 9! Ya hemos visto cómo organizar datos en secuencias ordenadas con listas y tuplas. Ahora, exploraremos una estructura de datos completamente diferente y extremadamente poderosa: los **diccionarios**. Los diccionarios no se basan en un orden secuencial (índices numéricos), sino en un sistema de **pares clave-valor**.

### ¿Qué son los Diccionarios?
Un **diccionario** en Python es una colección no ordenada (aunque desde Python 3.7 mantienen el orden de inserción), mutable y que almacena datos en pares **clave-valor**.
*   **No ordenada (históricamente):** No accedes a los elementos por su posición (como `[0]`), sino por su `clave`.
*   **Mutable:** Puedes añadir, modificar y eliminar pares clave-valor después de crear el diccionario.
*   **Clave-Valor:** Cada elemento del diccionario consta de una `clave` única y su `valor` asociado. Piensa en un diccionario real: la "palabra" es la clave y la "definición" es el valor.

**Características de las Claves:**
*   Las claves deben ser **únicas** dentro de un diccionario. Si intentas usar la misma clave dos veces, el último valor asignado sobrescribirá al anterior.
*   Las claves deben ser de un tipo de dato **inmutable** (como cadenas, números o tuplas). No puedes usar listas como claves.

**Creación de Diccionarios:**
Los diccionarios se crean encerrando los pares clave-valor entre llaves `{}`. Cada par se define como `clave: valor`, y los pares se separan por comas.
```python
# Diccionario vacío
diccionario_vacio = {}
print(diccionario_vacio) # Salida: {}

# Diccionario simple
persona = {
    "nombre": "Ana",
    "edad": 28,
    "ciudad": "Barcelona"
}
print(persona) # Salida: {'nombre': 'Ana', 'edad': 28, 'ciudad': 'Barcelona'}

# Usando el constructor dict()
coche = dict(marca="Ford", modelo="Mustang", anio=1964)
print(coche) # Salida: {'marca': 'Ford', 'modelo': 'Mustang', 'anio': 1964}
```

### Acceso a Valores
Para acceder a un valor, usas su clave correspondiente entre corchetes `[]`.
```python
print(persona["nombre"]) # Salida: Ana
print(persona["edad"])   # Salida: 28
```
Si intentas acceder a una clave que no existe, Python generará un error (`KeyError`).

**Acceso seguro con `.get()`:**
El método `.get(clave, valor_por_defecto)` es una forma más segura de acceder a los valores.
*   Devuelve el valor de la clave si existe.
*   Si la clave no existe, devuelve `None` por defecto, en lugar de un error.
*   Puedes proporcionar un segundo argumento para especificar un valor por defecto diferente.
```python
profesion = persona.get("profesion")
print(profesion) # Salida: None

profesion = persona.get("profesion", "No especificada")
print(profesion) # Salida: No especificada
```

### Modificación de Diccionarios
Como los diccionarios son mutables, puedes cambiarlos después de su creación.

**Añadir o Actualizar un par clave-valor:**
Si la clave ya existe, su valor se actualiza. Si no existe, se crea un nuevo par clave-valor.
```python
persona["edad"] = 29 # Actualizar valor de clave existente
print(persona) # {'nombre': 'Ana', 'edad': 29, 'ciudad': 'Barcelona'}

persona["profesion"] = "Ingeniera" # Añadir nuevo par clave-valor
print(persona) # {'nombre': 'Ana', 'edad': 29, 'ciudad': 'Barcelona', 'profesion': 'Ingeniera'}
```
**El método `.update()`:**
Permite fusionar un diccionario con otro, o añadir múltiples pares clave-valor.
```python
info_adicional = {"email": "ana@correo.com", "telefono": "123456789"}
persona.update(info_adicional)
print(persona) # El diccionario 'persona' ahora incluye email y telefono
```

**Eliminar un par clave-valor:**
*   `del diccionario[clave]`: Elimina el par clave-valor. Causa `KeyError` si la clave no existe.
    ```python
    del persona["telefono"]
    print(persona)
    ```
*   `.pop(clave, valor_por_defecto)`: Elimina el par y **devuelve** su valor. Causa `KeyError` si la clave no existe y no se proporciona un valor por defecto.
    ```python
    ciudad_eliminada = persona.pop("ciudad")
    print(f"Ciudad eliminada: {ciudad_eliminada}") # Salida: Ciudad eliminada: Barcelona
    print(persona)
    ```

### Iteración sobre Diccionarios
Puedes iterar sobre un diccionario de varias maneras.

**Iterar sobre las claves (comportamiento por defecto):**
```python
for clave in persona:
    print(f"Clave: {clave}, Valor: {persona[clave]}")
```

**Iterar sobre los valores usando `.values()`:**
```python
for valor in persona.values():
    print(f"Valor: {valor}")
```

**Iterar sobre los pares clave-valor usando `.items()` (la forma más común):**
El método `.items()` devuelve una vista de los pares (clave, valor) del diccionario, que puedes desempaquetar en dos variables.
```python
for clave, valor in persona.items():
    print(f"La clave '{clave}' tiene el valor '{valor}'")
```

### Métodos y Operadores Útiles
*   `len(diccionario)`: Devuelve el número de pares clave-valor.
*   `clave in diccionario`: Devuelve `True` si la `clave` existe en el diccionario.
*   `.keys()`: Devuelve una vista de todas las claves.
*   `.values()`: Devuelve una vista de todos los valores.
*   `.items()`: Devuelve una vista de todos los pares (clave, valor).
*   `.clear()`: Elimina todos los elementos del diccionario.

```python
print(len(persona))          # Imprime el número de pares
print("nombre" in persona)   # Salida: True
print("apellido" in persona) # Salida: False

print(list(persona.keys()))  # Convertir la vista a una lista para ver las claves
```

Los diccionarios son increíblemente útiles para modelar objetos del mundo real (como una persona, un producto, una configuración) y para búsquedas rápidas de datos.

---

## Ejercicios del Módulo 9

Estos ejercicios están diseñados para que practiques todos los aspectos de los diccionarios: creación, acceso, modificación, iteración y uso de sus métodos principales.

1.  **Crear y Acceder a un Diccionario** (Dificultad 1.34): [m9-ejercicio1-1.md](m9-ejercicio1-1.md)
2.  **Añadir y Modificar Elementos de un Diccionario** (Dificultad 2.69): [m9-ejercicio2-2.md](m9-ejercicio2-2.md)
3.  **Acceso Seguro con `.get()`** (Dificultad 4.03): [m9-ejercicio3-3.md](m9-ejercicio3-3.md)
4.  **Eliminar Elementos de un Diccionario** (Dificultad 5.38): [m9-ejercicio4-4.md](m9-ejercicio4-4.md)
5.  **Iterar sobre Claves, Valores e Ítems** (Dificultad 6.72): [m9-ejercicio5-5.md](m9-ejercicio5-5.md)
6.  **Verificar si una Clave Existe** (Dificultad 8.07): [m9-ejercicio6-6.md](m9-ejercicio6-6.md)
7.  **Contador de Frecuencia de Palabras** (Dificultad 9.41): [m9-ejercicio7-7.md](m9-ejercicio7-7.md)
8.  **Combinar Dos Diccionarios** (Dificultad 10.76): [m9-ejercicio8-8.md](m9-ejercicio8-8.md)
9.  **Diccionario Anidado (Información de Múltiples Usuarios)** (Dificultad 12.1): [m9-ejercicio9-9.md](m9-ejercicio9-9.md)
10. **Traductor Simple usando un Diccionario** (Dificultad 13.44): [m9-ejercicio10-10.md](m9-ejercicio10-10.md)

```
