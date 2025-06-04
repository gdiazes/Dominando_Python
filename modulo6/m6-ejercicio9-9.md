# Módulo 6: Ejercicio 9 (Dificultad 10.4/10) - Encontrar el MCD (Máximo Común Divisor) de Dos Números usando `while` (Algoritmo de Euclides)

## Enunciado del Problema

Solicita al usuario dos números enteros positivos, `a` y `b`.
Calcula y muestra el Máximo Común Divisor (MCD) de `a` y `b` utilizando el algoritmo de Euclides basado en restas sucesivas o el método del módulo.

**Algoritmo de Euclides (método del módulo, más eficiente):**
1.  Mientras `b` no sea 0:
    a.  Guarda temporalmente el valor de `b`.
    b.  Actualiza `b` para que sea el resto de `a` dividido por `b` (`a % b`).
    c.  Actualiza `a` para que sea el valor temporal de `b` (el valor original de `b`).
2.  El MCD es el valor final de `a`.

Ejemplo: MCD(48, 18)
1. a=48, b=18. temp_b=18. b = 48 % 18 = 12. a = 18. (Ahora a=18, b=12)
2. a=18, b=12. temp_b=12. b = 18 % 12 = 6.  a = 12. (Ahora a=12, b=6)
3. a=12, b=6.  temp_b=6.  b = 12 % 6 = 0.   a = 6.  (Ahora a=6, b=0)
4. b es 0, el bucle termina. El MCD es a = 6.

## Código con Errores

```python
# Ejercicio: MCD usando Algoritmo de Euclides con while

a_str = input("Ingresa el primer número entero positivo (a): ")
a = int(a_str)
b_str = input("Ingresa el segundo número entero positivo (b): ")
b = int(b_str)

# Guardar los originales para el mensaje final
original_a = a
original_b = b

if a <= 0 or b <= 0:
    print("Ambos números deben ser enteros positivos.")
else
    while b != 0 
        temp_b = b
        b = a % b
        a = temp_b 
    
    mcd = b
    print(f"El MCD de {original_a} y {original_b} es: {mcd}")

```

