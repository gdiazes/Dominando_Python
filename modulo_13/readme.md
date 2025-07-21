# Módulo 13: Organizando Proyectos: Módulos y Paquetes en Python

## Laboratorio 13 - Guía Paso a Paso

¡Bienvenido al Laboratorio 13! A medida que tus programas crecen, se vuelve impráctico mantener todo tu código en un solo archivo. Los **módulos** y **paquetes** son la forma en que Python nos permite organizar el código en diferentes archivos y directorios, haciendo nuestros proyectos más limpios, mantenibles y reutilizables.

### ¿Qué es un Módulo?
Un **módulo** es simplemente un archivo de Python con la extensión `.py`. Este archivo puede contener definiciones de funciones, clases y variables que puedes usar en otros archivos de Python.

**Beneficios de usar Módulos:**
*   **Organización:** Divide un programa grande en archivos más pequeños y manejables.
*   **Reutilización:** Puedes importar el mismo módulo en múltiples proyectos para reutilizar su funcionalidad.
*   **Espacios de Nombres (Namespaces):** Ayuda a evitar conflictos de nombres. Una función `sumar` en tu módulo `calculos.py` no chocará con una función `sumar` de otro módulo.

**Creación de un Módulo Propio:**
1.  Crea un nuevo archivo de Python. Llamémoslo `matematicas_utiles.py`.
2.  Dentro de `matematicas_utiles.py`, define algunas funciones:
    ```python
    # archivo: matematicas_utiles.py
    PI = 3.14159

    def sumar(a, b):
        """Devuelve la suma de dos números."""
        return a + b

    def area_circulo(radio):
        """Calcula el área de un círculo."""
        return PI * (radio ** 2)
    ```

### Importación de Módulos
Para usar la funcionalidad de un módulo en otro archivo (por ejemplo, en tu script principal `main.py`), debes **importarlo**.

**Forma 1: `import modulo`**
Esta es la forma más común y recomendada. Importa el módulo completo. Para acceder a sus funciones o variables, debes usar la sintaxis `nombre_del_modulo.nombre_del_elemento`.
```python
# archivo: main.py
import matematicas_utiles

resultado_suma = matematicas_utiles.sumar(10, 5)
resultado_area = matematicas_utiles.area_circulo(3)
PI_valor = matematicas_utiles.PI

print(f"Suma: {resultado_suma}")
print(f"Área: {resultado_area}")
print(f"Valor de PI: {PI_valor}")
```

**Forma 2: `from modulo import elemento`**
Puedes importar elementos específicos de un módulo. Esto te permite usarlos directamente sin el prefijo del nombre del módulo.
```python
# archivo: main.py
from matematicas_utiles import sumar, area_circulo

resultado_suma = sumar(10, 5) # Se usa directamente, sin 'matematicas_utiles.'
resultado_area = area_circulo(3)

print(f"Suma: {resultado_suma}")
print(f"Área: {resultado_area}")
```
También puedes importar todo con `from matematicas_utiles import *`, pero **no se recomienda** porque puede causar conflictos de nombres y hace el código menos legible.

**Forma 3: `import modulo as alias`**
Puedes darle un alias (un nombre más corto) a un módulo importado. Esto es muy común con módulos de nombres largos como `matplotlib.pyplot` (alias `plt`) o `pandas` (alias `pd`).
```python
# archivo: main.py
import matematicas_utiles as mu

resultado = mu.sumar(100, 200)
print(f"Resultado con alias: {resultado}")
```

### Módulos de la Biblioteca Estándar de Python
Python viene con una vasta **biblioteca estándar** llena de módulos listos para usar. No necesitas instalar nada extra. Algunos de los más útiles son:

*   `math`: Para funciones matemáticas avanzadas (seno, coseno, raíz cuadrada, constantes como pi y e).
    ```python
    import math
    print(math.sqrt(16)) # Raíz cuadrada. Salida: 4.0
    print(math.pi)       # Constante pi con más precisión.
    ```
*   `random`: Para generar números aleatorios.
    ```python
    import random
    print(random.randint(1, 10)) # Un entero aleatorio entre 1 y 10
    print(random.choice(["cara", "cruz"])) # Elige un elemento aleatorio de una lista
    ```
*   `datetime`: Para trabajar con fechas y horas (como vimos en el módulo anterior).
*   `os`: Para interactuar con el sistema operativo (manejar archivos, directorios, etc.).
    ```python
    import os
    print(os.getcwd()) # Obtiene el directorio de trabajo actual
    ```

### La Variable `__name__` y el Script Principal
Cada módulo en Python tiene una variable especial llamada `__name__`.
*   Si ejecutas el archivo del módulo directamente, el valor de `__name__` para ese archivo será `"__main__"`.
*   Si importas el módulo desde otro archivo, el valor de `__name__` será el nombre del archivo del módulo (ej: `"matematicas_utiles"`).

Esto nos permite escribir código dentro de un módulo que solo se ejecutará cuando el archivo se ejecute directamente, pero no cuando se importe. Es la forma estándar de crear un punto de entrada para un programa o de incluir pruebas para el módulo.

```python
# archivo: matematicas_utiles.py

# ... (definiciones de PI, sumar, area_circulo) ...

# Este bloque solo se ejecuta si corremos 'matematicas_utiles.py' directamente
if __name__ == "__main__":
    print("Ejecutando el módulo directamente como script principal.")
    print("Realizando algunas pruebas...")
    # Prueba de la función sumar
    assert sumar(2, 2) == 4
    # Prueba de la función area_circulo
    assert area_circulo(1) == PI
    print("¡Pruebas pasadas exitosamente!")

# Si importas este módulo en main.py, este bloque no se ejecuta.
```

### ¿Qué son los Paquetes?
Cuando tu proyecto crece aún más, puedes organizar tus módulos en directorios. Un **paquete** es simplemente un directorio que contiene módulos de Python y un archivo especial (a menudo vacío) llamado `__init__.py`. Este archivo le indica a Python que el directorio debe ser tratado como un paquete.

**Estructura de un paquete simple:**
```
mi_proyecto/
├── main.py
└── mi_paquete/
    ├── __init__.py
    ├── modulo_a.py
    └── modulo_b.py
```
Para importar desde un paquete, usas la notación de punto:
```python
# En main.py
from mi_paquete import modulo_a
from mi_paquete.modulo_b import alguna_funcion
```

Aprender a organizar tu código en módulos y paquetes es un paso crucial para convertirte en un desarrollador de Python competente y escribir software robusto y escalable.

---

## Ejercicios del Módulo 13

Estos ejercicios se centrarán en la creación de módulos propios, la importación de funcionalidades y el uso de algunos módulos útiles de la biblioteca estándar de Python.

1.  **Crear y Usar un Módulo Simple** (Dificultad 1.63): [m13-ejercicio1-1.md](m13-ejercicio1-1.md)
2.  **Importar Funciones Específicas de un Módulo** (Dificultad 3.26): [m13-ejercicio2-2.md](m13-ejercicio2-2.md)
3.  **Uso de un Módulo con Alias** (Dificultad 4.89): [m13-ejercicio3-3.md](m13-ejercicio3-3.md)
4.  **Uso del Módulo `math`** (Dificultad 6.51): [m13-ejercicio4-4.md](m13-ejercicio4-4.md)
5.  **Uso del Módulo `random`** (Dificultad 8.14): [m13-ejercicio5-5.md](m13-ejercicio5-5.md)
6.  **Estructura de Módulo con `if __name__ == "__main__"`** (Dificultad 9.77): [m13-ejercicio6-6.md](m13-ejercicio6-6.md)
7.  **Mover Funcionalidad a Múltiples Módulos** (Dificultad 11.4): [m13-ejercicio7-7.md](m13-ejercicio7-7.md)
8.  **Importación Circular (Error Conceptual)** (Dificultad 13.03): [m13-ejercicio8-8.md](m13-ejercicio8-8.md)
9.  **Crear y Usar un Paquete Simple** (Dificultad 14.66): [m13-ejercicio9-9.md](m13-ejercicio9-9.md)
10. **Utilizar un Módulo de Terceros (Simulación)** (Dificultad 16.29): [m13-ejercicio10-10.md](m13-ejercicio10-10.md)

