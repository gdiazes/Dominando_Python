# Módulo 6: Ejercicio 5 (Dificultad 5.78/10) - Imprimir Números Pares Omitiendo Múltiplos de Especifico (con `while` y `continue`)

## Enunciado del Problema

Escribe un programa que utilice un bucle `while` para imprimir números pares desde 2 hasta un `limite_superior` (inclusive) ingresado por el usuario.
Sin embargo, el programa debe *omitir* (no imprimir) aquellos números pares que también sean múltiplos de un segundo número ingresado por el usuario, `omitir_multiplos_de`.
Usa la instrucción `continue` para omitir la impresión.

Ejemplo: Si `limite_superior` es 10 y `omitir_multiplos_de` es 4:
Salida esperada:
2
6
10
(Se omite 4 y 8 porque son múltiplos de 4)

## Código con Errores

```python
# Ejercicio: Imprimir pares omitiendo múltiplos específicos

limite_str = input("Ingrese el límite superior (entero >= 2): ")
limite_superior = int(limite_str)

omitir_str = input("Ingrese el número cuyos múltiplos pares se omitirán: ")
omitir_multiplos_de = int(omitir_str)

contador = 1 # Pista 1

while contador <= limite_superior:
    contador += 1 # Moveremos esta actualización para una lógica más clara
    if contador % 2 == 0: # Es par
        if contador % omitir_multiplos_de == 0:
            continue # Pista 2 (Esta parte está bien, pero ¿la lógica general es la mejor?)
        print(contador) 
    # Pista 3: ¿Qué pasa si 'contador' se incrementa al inicio y luego 'continue' salta la impresión? 
    # ¿Se imprimen los números correctos o se salta alguno que no debería?
    # ¿O la actualización del contador está en el lugar óptimo?
```

## Pistas para Corregir los Errores

*   **Pista 1:** Si el primer número par a considerar es 2, y el `contador` se incrementa *antes* de cualquier verificación o impresión dentro del bucle, ¿cuál debería ser el valor inicial de `contador` para que el primer número evaluado sea potencialmente 2?
*   **Pista 2:** La instrucción `continue` está bien usada para saltar la impresión. La pregunta es si las condiciones que llevan al `continue` y la actualización del contador están coordinadas para producir la secuencia correcta.
*   **Pista 3:** El orden de actualización del `contador`, la verificación de si es par, y la verificación de si es múltiplo de `omitir_multiplos_de` es crucial. Si `contador` se incrementa al inicio del bucle, el primer valor que `contador` toma *dentro* del bucle es 1 (si empezó en 0) o 2 (si empezó en 1). ¿Esto se alinea con querer empezar a verificar desde el número 2?

<details>
<summary>Mostrar Solución Correcta</summary>

```python
# Ejercicio: Imprimir pares omitiendo múltiplos específicos

limite_str = input("Ingrese el límite superior (entero >= 2): ")
limite_superior = int(limite_str)

omitir_str = input("Ingrese el número cuyos múltiplos pares se omitirán (mayor que 0): ")
omitir_multiplos_de = int(omitir_str)

if limite_superior < 2 or omitir_multiplos_de <= 0:
    print("Entrada inválida. El límite debe ser >= 2 y el divisor > 0.")
else:
    contador = 2 # Empezar directamente desde el primer número par a considerar

    while contador <= limite_superior:
        # Verificar primero si es un múltiplo a omitir ANTES de imprimir
        # Esta condición solo aplica si el número ya es par (lo cual está implícito si
        # incrementamos de 2 en 2, o verificamos paridad antes)
        
        # Lógica actual: iterar por todos los números y seleccionar pares
        # luego de los pares, omitir los que son múltiplos de omitir_multiplos_de
        
        es_par = (contador % 2 == 0)
        es_multiplo_a_omitir = (contador % omitir_multiplos_de == 0)

        if es_par:
            if es_multiplo_a_omitir:
                # Es par Y es múltiplo a omitir, entonces no hacer nada (o explícitamente continue si hubiera más código después)
                # Para que el continue tenga efecto, debe haber algo después que saltar.
                # En este caso, el 'else' del 'if es_multiplo_a_omitir' maneja la impresión.
                pass # No imprimir, pasamos al incremento del contador
            else:
                print(contador) # Es par y NO es múltiplo a omitir
        
        contador += 1 # Incrementar el contador para la siguiente iteración

    # --- Alternativa con incremento de 2 en 2 (más eficiente si solo interesan pares) ---
    # print("\nAlternativa (incrementando de 2 en 2):")
    # contador_alt = 2
    # while contador_alt <= limite_superior:
    #     if contador_alt % omitir_multiplos_de == 0:
    #         contador_alt += 2 # Incrementar ANTES de continue para no quedar atascado
    #         continue
    #     print(contador_alt)
    #     contador_alt += 2
```
**Solución más directa y fiel a la estructura del error original, corregida:**
```python
limite_str = input("Ingrese el límite superior (entero >= 2): ")
limite_superior = int(limite_str)

omitir_str = input("Ingrese el número cuyos múltiplos pares se omitirán (mayor que 0): ")
omitir_multiplos_de = int(omitir_str)

if limite_superior < 2 or omitir_multiplos_de <= 0:
    print("Entrada inválida. El límite debe ser >= 2 y el divisor > 0.")
else:
    contador = 1 # Iniciar en 1 para que el primer incremento lo lleve a 2

    while contador < limite_superior: # Iterar hasta un número antes del límite para que el incremento no lo pase sin evaluar
        contador += 1 # Incrementar al inicio de la iteración
        
        if contador % 2 == 0: # Es par
            if contador % omitir_multiplos_de == 0: # Es par Y múltiplo a omitir
                continue # Saltar la impresión para este número
            print(contador) # Es par y NO es múltiplo a omitir
        # Si no es par, no se hace nada y el bucle continúa
```

</details>

<details>
<summary>Mostrar Explicación de la Solución</summary>

Este ejercicio requiere un bucle `while`, condiciones anidadas y el uso de `continue`. El orden de las operaciones (incrementar contador, verificar condiciones, imprimir) es clave.

*   **Error 1 Corrección (Valor inicial de `contador` y estrategia de incremento):**
    *   El código original tenía `contador = 1` y luego `contador += 1` al inicio del bucle. Esto significa que el primer valor de `contador` *evaluado dentro de las condiciones* sería 2. Esto es correcto si queremos empezar a verificar desde 2. La condición del `while` `contador <= limite_superior` también necesita considerar este incremento. Si `contador` llega a ser `limite_superior` y luego se incrementa a `limite_superior + 1` al inicio de la siguiente iteración, la condición `while` debe ser tal que no se pase. Una forma común es `while contador < limite_superior` si se incrementa al inicio, o `while contador <= limite_superior` si se incrementa al final.
    *   **Solución (en la "Solución más directa..."):** `contador = 1` y `while contador < limite_superior:`, con `contador += 1` al inicio del bucle. Esto asegura que `contador` tome valores desde 2 hasta `limite_superior` dentro de las verificaciones.

*   **Error 2 Corrección (Efecto del `continue`):**
    *   La Pista 2 indica que el `continue` está bien usado. Si un número es par Y es múltiplo de `omitir_multiplos_de`, el `continue` salta la parte de `print(contador)` y va a la siguiente iteración del bucle `while`. Esto es correcto.

*   **Error 3 Corrección (Lógica general y flujo con `continue`):**
    *   El problema principal en la lógica original era la interacción entre dónde se incrementaba `contador` y el efecto del `continue`. Si `contador` se incrementaba, luego se cumplía la condición para `continue`, la impresión se saltaba, pero el `contador` ya se había incrementado para la *siguiente* posible iteración.
    *   **Solución (en la "Solución más directa...")**:
        1.  Inicializar `contador = 1`.
        2.  Condición del bucle: `while contador < limite_superior:`. (Iterará mientras `contador` pueda llegar a ser `limite_superior` después del incremento).
        3.  `contador += 1`: Incrementar `contador` al inicio de cada iteración. Ahora `contador` tiene el valor actual a evaluar (desde 2 hasta `limite_superior`).
        4.  `if contador % 2 == 0:`: Verificar si es par.
            *   `if contador % omitir_multiplos_de == 0:`: Si también es múltiplo a omitir.
                *   `continue`: Saltar la impresión y el resto del cuerpo del bucle actual, ir al inicio del `while` para la siguiente iteración.
            *   `print(contador)`: Si es par pero NO es múltiplo a omitir, imprimirlo.
    *   Esta estructura asegura que el `contador` se incremente siempre, y que `continue` solo salte la impresión del número actual si cumple ambas condiciones de omisión, sin afectar el flujo general de iteración sobre todos los números hasta el límite.

**Validación de Entrada:**
La solución también añade una validación inicial para `limite_superior` y `omitir_multiplos_de` para asegurar que tengan sentido para el problema (límite >= 2, divisor > 0).

La "Alternativa con incremento de 2 en 2" en los comentarios de la solución muestra un enfoque más eficiente si solo nos interesan los números pares desde el principio, ya que reduce el número de iteraciones y verificaciones de paridad. Sin embargo, la solución principal se adhiere más a corregir la estructura del error original iterando por todos los números.
</details>
