# Módulo 15: Introducción a la Programación Orientada a Objetos (POO) en Python

## Laboratorio 15 - Guía Paso a Paso

¡Bienvenido al Laboratorio 15! Hasta ahora, hemos practicado la programación procedural (secuencias de instrucciones, funciones). Ahora, daremos un paso hacia uno de los paradigmas de programación más influyentes: la **Programación Orientada a Objetos (POO)**. La POO nos permite estructurar nuestro código modelando objetos del mundo real (como un coche, una persona, un producto), con sus propias propiedades y comportamientos.

### Conceptos Fundamentales de la POO
*   **Clase (Class):** Es la "plantilla" o "plano" para crear objetos. Define un conjunto de atributos (propiedades) y métodos (comportamientos) que tendrán los objetos de esa clase. Por ejemplo, una clase `Coche` definiría que todos los coches tienen un color, una marca y pueden acelerar o frenar.
*   **Objeto (Object) / Instancia (Instance):** Es una creación concreta a partir de una clase. Si `Coche` es la clase, un coche rojo de marca Ford sería un objeto o una instancia de esa clase. Puedes crear muchos objetos de la misma clase.
*   **Atributo (Attribute):** Es una variable asociada a un objeto o a una clase. Representa una propiedad o un dato del objeto. Para un objeto `Coche`, los atributos podrían ser `color`, `marca`, `velocidad_actual`.
*   **Método (Method):** Es una función asociada a un objeto o a una clase. Representa un comportamiento o una acción que el objeto puede realizar. Para un objeto `Coche`, los métodos podrían ser `acelerar()`, `frenar()`, `encender()`.

### Definición de una Clase: `class`
Para definir una clase en Python, usamos la palabra clave `class`, seguida del nombre de la clase (por convención, en `CamelCase` o `PascalCase`).
```python
class Coche:
    # Atributos y métodos de la clase irán aquí
    pass # 'pass' es un marcador de posición para un bloque vacío
```

### El Constructor: `__init__()`
El método `__init__()` es un método especial llamado **constructor**. Se ejecuta automáticamente cada vez que se crea un nuevo objeto (instancia) de la clase. Se usa para inicializar los atributos del objeto.

El primer parámetro de `__init__` (y de casi todos los métodos de instancia) es siempre `self`. `self` es una referencia al objeto que se está creando. Python lo pasa automáticamente.
```python
class Coche:
    # Este es el constructor
    def __init__(self, marca, modelo, color):
        # Asignamos los valores recibidos a los atributos del objeto (self)
        self.marca = marca
        self.modelo = modelo
        self.color = color
        self.velocidad_actual = 0 # Atributo inicializado con un valor fijo
        print(f"¡Se ha creado un {self.marca} {self.modelo} de color {self.color}!")
```

### Creación de Objetos (Instanciación)
Para crear un objeto (una instancia) de una clase, "llamas" a la clase como si fuera una función, pasándole los argumentos que el método `__init__` espera (sin contar `self`).
```python
# Creamos dos objetos de la clase Coche
mi_coche = Coche("Ford", "Mustang", "rojo")
coche_de_ana = Coche("Tesla", "Model S", "blanco")
```
Cada objeto (`mi_coche`, `coche_de_ana`) es una entidad independiente con sus propios atributos.

### Acceso a Atributos y Llamada a Métodos
Para acceder a los atributos de un objeto o llamar a sus métodos, se usa la **notación de punto (`.`)**.

**Acceder a atributos:**
```python
print(f"La marca de mi coche es: {mi_coche.marca}") # Salida: Ford
print(f"El color del coche de Ana es: {coche_de_ana.color}") # Salida: blanco
```

**Definir y llamar a métodos:**
Los métodos son funciones definidas dentro de la clase. También reciben `self` como su primer parámetro.
```python
class Coche:
    def __init__(self, marca, modelo):
        self.marca = marca
        self.modelo = modelo
        self.velocidad_actual = 0
        self.encendido = False
    
    # Método para encender el coche
    def encender(self):
        if not self.encendido:
            self.encendido = True
            print(f"El {self.marca} {self.modelo} se ha encendido.")
        else:
            print("El coche ya estaba encendido.")
            
    # Método para acelerar
    def acelerar(self, cantidad):
        if self.encendido:
            self.velocidad_actual += cantidad
            print(f"Acelerando... Velocidad actual: {self.velocidad_actual} km/h")
        else:
            print("No puedes acelerar, el coche está apagado.")

# Creamos un objeto
mi_coche_nuevo = Coche("Toyota", "Corolla")

# Llamamos a sus métodos
mi_coche_nuevo.acelerar(20) # Salida: No puedes acelerar, el coche está apagado.
mi_coche_nuevo.encender()   # Salida: El Toyota Corolla se ha encendido.
mi_coche_nuevo.acelerar(20) # Salida: Acelerando... Velocidad actual: 20 km/h
```

### Herencia (Introducción)
La **herencia** es un pilar de la POO que permite crear una nueva clase (llamada **clase hija** o subclase) que hereda los atributos y métodos de una clase existente (la **clase padre** o superclase). Esto promueve la reutilización de código.

```python
# Coche es la clase padre
class CocheElectrico(Coche): # Hereda de Coche
    # Añadimos un constructor para la clase hija
    def __init__(self, marca, modelo, capacidad_bateria):
        # Llamamos al constructor de la clase padre para inicializar sus atributos
        super().__init__(marca, modelo)
        # Añadimos un atributo específico para CocheElectrico
        self.capacidad_bateria = capacidad_bateria
        
    # Podemos añadir métodos nuevos o sobrescribir los del padre
    def cargar_bateria(self):
        print(f"Cargando la batería de {self.capacidad_bateria} kWh...")

# Creamos un objeto de la clase hija
mi_tesla = CocheElectrico("Tesla", "Model 3", 75)
mi_tesla.encender()       # Método heredado de Coche
mi_tesla.acelerar(50)     # Método heredado de Coche
mi_tesla.cargar_bateria() # Método propio de CocheElectrico
```

La POO es un tema extenso (incluye conceptos como encapsulamiento y polimorfismo que veremos más superficialmente). Sin embargo, dominar las clases, objetos, atributos y métodos es el primer y más importante paso para escribir código Python de alta calidad y bien estructurado.

---

## Ejercicios del Módulo 15

Estos ejercicios te guiarán en la creación de tus primeras clases y objetos, ayudándote a entender los conceptos básicos de la Programación Orientada a Objetos.

1.  **Definir una Clase Simple (Perro)** (Dificultad 1.79): [m15-ejercicio1-1.md](m15-ejercicio1-1.md)
2.  **Crear una Clase con Constructor `__init__()` (Libro)** (Dificultad 3.59): [m15-ejercicio2-2.md](m15-ejercicio2-2.md)
3.  **Crear una Clase con Métodos (CuentaBancaria)** (Dificultad 5.38): [m15-ejercicio3-3.md](m15-ejercicio3-3.md)
4.  **Crear Múltiples Objetos de una Clase (Estudiante)** (Dificultad 7.18): [m15-ejercicio4-4.md](m15-ejercicio4-4.md)
5.  **Modificar Atributos de un Objeto (Producto)** (Dificultad 8.97): [m15-ejercicio5-5.md](m15-ejercicio5-5.md)
6.  **Usar un Objeto como Atributo de Otro (Composición)** (Dificultad 10.77): [m15-ejercicio6-6.md](m15-ejercicio6-6.md)
7.  **Herencia Simple (Vehículo y Coche)** (Dificultad 12.56): [m15-ejercicio7-7.md](m15-ejercicio7-7.md)
8.  **Llamar al Constructor del Padre con `super()`** (Dificultad 14.36): [m15-ejercicio8-8.md](m15-ejercicio8-8.md)
9.  **Sobrescribir un Método del Padre** (Dificultad 16.15): [m15-ejercicio9-9.md](m15-ejercicio9-9.md)
10. **Mini-Proyecto POO: Figuras Geométricas** (Dificultad 17.95): [m15-ejercicio10-10.md](m15-ejercicio10-10.md)

