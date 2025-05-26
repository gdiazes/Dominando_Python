# Módulo 4: Tomando Decisiones: Estructuras Condicionales en Python

## Laboratorio 4 - Guía Paso a Paso

¡Bienvenido al Laboratorio 4! Hasta ahora, nuestros programas han seguido una secuencia lineal de instrucciones. Sin embargo, la verdadera potencia de la programación reside en la capacidad de tomar decisiones y ejecutar diferentes bloques de código según se cumplan ciertas **condiciones**. En este laboratorio, exploraremos las **estructuras condicionales** en Python: `if`, `elif` y `else`.

### Operadores de Comparación (Relacionales)
Antes de tomar decisiones, necesitamos comparar valores. Python ofrece los siguientes operadores de comparación, que siempre devuelven un valor booleano (`True` o `False`):

| Operador | Descripción              | Ejemplo (si x=5, y=10) | Resultado |
| :------- | :----------------------- | :--------------------- | :-------- |
| `==`     | Igual a                  | `x == y`               | `False`   |
| `!=`     | No igual a (diferente de)| `x != y`               | `True`    |
| `>`      | Mayor que                | `x > y`                | `False`   |
| `<`      | Menor que                | `x < y`                | `True`    |
| `>=`     | Mayor o igual que        | `x >= 5`               | `True`    |
| `<=`     | Menor o igual que        | `y <= 10`              | `True`    |

```python
edad_usuario = 18
MAYORIA_EDAD = 18

print(edad_usuario == MAYORIA_EDAD)  # Salida: True
print(edad_usuario > MAYORIA_EDAD)   # Salida: False
print(edad_usuario != 20)          # Salida: True
```

### Operadores Lógicos
Los operadores lógicos nos permiten combinar múltiples condiciones booleanas:

1.  **`and` (Y lógico):** Devuelve `True` si **ambas** condiciones son verdaderas.
    ```python
    temperatura = 25
    hay_sol = True
    # ¿Es un buen día para ir a la playa?
    buen_dia_playa = temperatura > 20 and hay_sol
    print(buen_dia_playa) # Salida: True
    ```

2.  **`or` (O lógico):** Devuelve `True` si **al menos una** de las condiciones es verdadera.
    ```python
    es_fin_de_semana = False
    es_feriado = True
    # ¿Tengo día libre?
    dia_libre = es_fin_de_semana or es_feriado
    print(dia_libre) # Salida: True
    ```

3.  **`not` (NO lógico):** Invierte el valor booleano de una condición. Devuelve `True` si la condición es `False`, y `False` si es `True`.
    ```python
    esta_lloviendo = False
    necesito_paraguas = not esta_lloviendo
    print(f"¿Necesito paraguas? {not esta_lloviendo}") # Salida: ¿Necesito paraguas? True
    ```

**Tabla de Verdad:**
| A     | B     | A `and` B | A `or` B | `not` A |
| :---- | :---- | :-------- | :------- | :------ |
| True  | True  | True      | True     | False   |
| True  | False | False     | True     | False   |
| False | True  | False     | True     | True    |
| False | False | False     | False    | True    |

### La Estructura `if`
La estructura `if` (si) permite ejecutar un bloque de código solo si una condición es verdadera.
La sintaxis requiere dos puntos (`:`) al final de la línea del `if` y que el bloque de código subsiguiente esté **indentado** (generalmente 4 espacios).

```python
edad = 20
if edad >= 18:
    print("Eres mayor de edad.") # Esta línea está indentada, pertenece al if
    print("Puedes votar.")       # Esta también
print("Esta línea se ejecuta siempre, fuera del if.")
```
Si `edad` fuera `15`, las dos líneas indentadas no se ejecutarían.

### La Estructura `if-else`
La estructura `if-else` (si-sino) permite ejecutar un bloque de código si la condición es verdadera, y un bloque de código diferente si la condición es falsa.

```python
puntuacion = 75
if puntuacion >= 60:
    print("¡Felicidades, has aprobado!")
else: # else también termina con dos puntos (:) y su bloque va indentado
    print("Lo siento, necesitas estudiar más.")
```

### La Estructura `if-elif-else`
La estructura `if-elif-else` (si-sino si-sino) permite encadenar múltiples condiciones. Python evalúa las condiciones en orden:
1.  Si la condición del `if` es verdadera, ejecuta su bloque y salta el resto.
2.  Si no, comprueba la condición del primer `elif`. Si es verdadera, ejecuta su bloque y salta el resto.
3.  Puedes tener tantos `elif` como necesites.
4.  Si ninguna condición anterior es verdadera, se ejecuta el bloque del `else` (que es opcional).

```python
nota = 88

if nota >= 90:
    calificacion = "Sobresaliente (A)"
elif nota >= 80: # Se ejecuta si nota no es >= 90, PERO SÍ es >= 80
    calificacion = "Notable (B)"
elif nota >= 70:
    calificacion = "Bien (C)"
elif nota >= 60:
    calificacion = "Suficiente (D)"
else:
    calificacion = "Insuficiente (F)"

print(f"Tu calificación es: {calificacion}") # Salida: Tu calificación es: Notable (B)
```

### Condicionales Anidados
Puedes poner estructuras `if` (y sus variantes) dentro de otras estructuras `if`. Esto se llama anidamiento.

```python
tiene_entrada = True
edad = 15

if tiene_entrada:
    print("Bienvenido al cine.")
    if edad >= 12:
        print("Puedes ver la película clasificada para mayores de 12.")
    else:
        print("Lo siento, esta película no es adecuada para tu edad.")
else:
    print("Necesitas una entrada para acceder.")
```
El anidamiento excesivo puede hacer el código difícil de leer, así que úsalo con prudencia.

Las estructuras condicionales son fundamentales para escribir programas que puedan reaccionar de manera diferente a diversas situaciones y entradas. ¡Vamos a dominarlas!

---

## Ejercicios del Módulo 4

Estos ejercicios te ayudarán a practicar el uso de operadores de comparación, operadores lógicos y las estructuras `if`, `elif` y `else` para controlar el flujo de tus programas.

1.  **Verificar Mayoría de Edad** (Dificultad 1.05): [m4-ejercicio1-1.md](m4-ejercicio1-1.md)
2.  **Número Positivo, Negativo o Cero** (Dificultad 2.1): [m4-ejercicio2-2.md](m4-ejercicio2-2.md)
3.  **Acceso a Club con Doble Condición** (Dificultad 3.15): [m4-ejercicio3-3.md](m4-ejercicio3-3.md)
4.  **Calculadora de Descuento Simple** (Dificultad 4.2): [m4-ejercicio4-4.md](m4-ejercicio4-4.md)
5.  **Clasificación de Triángulos (por lados)** (Dificultad 5.25): [m4-ejercicio5-5.md](m4-ejercicio5-5.md)
6.  **Horóscopo Básico (por mes de nacimiento)** (Dificultad 6.3): [m4-ejercicio6-6.md](m4-ejercicio6-6.md)
7.  **Validador de Contraseña Simple** (Dificultad 7.35): [m4-ejercicio7-7.md](m4-ejercicio7-7.md)
8.  **Juego de Adivinar Número (con pistas)** (Dificultad 8.4): [m4-ejercicio8-8.md](m4-ejercicio8-8.md) (PC1 Integrada)
9.  **Conversor de Calificaciones Numéricas a Letras** (Dificultad 9.45): [m4-ejercicio9-9.md](m4-ejercicio9-9.md) (PC1 Integrada)
10. **Cajero Automático Básico (Menú y Operaciones)** (Dificultad 10.5): [m4-ejercicio10-10.md](m4-ejercicio10-10.md) (PC1 Integrada)
