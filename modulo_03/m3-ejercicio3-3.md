# Módulo 3: Ejercicio 3 (Dificultad 3.3/10) - Información Personal con f-strings

## Enunciado del Problema

Solicita al usuario su nombre, edad (como número) y ciudad de residencia.
Luego, utilizando una f-string, muestra un mensaje que combine esta información en una sola frase coherente. Adicionalmente, calcula y muestra cuántos años tendrá el usuario el próximo año.

Ejemplo de salida (si el usuario ingresa "Lucía", 32, "Madrid"):
```
Hola, Lucía. Vives en Madrid y tienes 32 años. El próximo año tendrás 33 años.
```

## Código con Errores

```python
# Ejercicio: Mostrar información personal usando f-strings y calcular edad futura

nombre = input("¿Cuál es tu nombre? ")
edad_str = input("¿Cuántos años tienes? ")
ciudad = Input("¿En qué ciudad vives? ") # Pista 1

edad_actual = edad_str # Pista 2
edad_proximo_anno = edad_actual + 1

print(f'Hola, {nombre}. Vives en {ciudad} y tienes {edad_actual} años.')
print(f'El próximo año tendrás {Edad_Proximo_Anno} años.') # Pista 3
```

## Pistas para Corregir los Errores

*   **Pista 1:** Python es sensible a mayúsculas y minúsculas. Revisa el nombre de la función para obtener entradas del usuario.
*   **Pista 2:** La edad ingresada por el usuario es una cadena. Para realizar cálculos matemáticos (como sumarle 1), ¿en qué tipo de dato necesitas convertirla primero?
*   **Pista 3:** Los nombres de las variables dentro de las f-strings también deben coincidir exactamente (incluyendo mayúsculas/minúsculas) con cómo fueron definidas.

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Mostrar información personal usando f-strings y calcular edad futura

nombre = input("¿Cuál es tu nombre? ")
edad_str = input("¿Cuántos años tienes? ")
ciudad = input("¿En qué ciudad vives? ") # Corregir 'Input' a 'input'

# Convertir edad_str a entero para cálculos
edad_actual = int(edad_str)
edad_proximo_anno = edad_actual + 1

print(f"Hola, {nombre}. Vives en {ciudad} y tienes {edad_actual} años.")
# Corregir el nombre de la variable en la f-string
print(f"El próximo año tendrás {edad_proximo_anno} años.")
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio combina la obtención de múltiples datos del usuario, la conversión de tipos, el cálculo simple y el formateo de salida con f-strings.

*   **Error 1 Corrección (Nombre de función incorrecto):**
    *   El código original era `ciudad = Input("¿En qué ciudad vives? ")`.
    *   La función para obtener la entrada del usuario es `input()` (todo en minúsculas), no `Input()`. Esto causaría un `NameError`.
    *   **Solución:** `ciudad = input("¿En qué ciudad vives? ")`

*   **Error 2 Corrección (Falta de conversión de tipo para la edad):**
    *   El código original tenía `edad_actual = edad_str` y luego `edad_proximo_anno = edad_actual + 1`.
    *   Si `edad_str` es una cadena (por ejemplo, `"32"`), entonces `edad_actual` también será una cadena. Intentar sumar `edad_actual` (cadena) con `1` (entero) resultará en un `TypeError`.
    *   Es necesario convertir `edad_str` (o `edad_actual` después de la asignación inicial) a un entero usando `int()` antes de realizar la suma.
    *   **Solución:** `edad_actual = int(edad_str)` (y luego `edad_proximo_anno = edad_actual + 1` funcionará).

*   **Error 3 Corrección (Nombre de variable incorrecto en f-string):**
    *   El código original era `print(f'El próximo año tendrás {Edad_Proximo_Anno} años.')`.
    *   La variable que almacena la edad del próximo año se definió como `edad_proximo_anno` (todo en minúsculas y con guiones bajos). Usar `Edad_Proximo_Anno` (con mayúsculas y sin guiones bajos) en la f-string causaría un `NameError`.
    *   **Solución:** `print(f'El próximo año tendrás {edad_proximo_anno} años.')`

El programa corregido solicita correctamente todos los datos, convierte la edad a un entero para poder calcular la edad del próximo año, y luego presenta toda la información de manera clara utilizando f-strings con los nombres de variable correctos.
</details>
