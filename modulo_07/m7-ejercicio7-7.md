
# Módulo 7: Ejercicio 7 (Dificultad 8.51/10) - Contar Ocurrencias de un Elemento en una Lista

## Enunciado del Problema

1.  Crea una lista de cadenas de texto llamada `respuestas_encuesta` que contenga varias respuestas, algunas repetidas (por ejemplo, "si", "no", "quizas").
2.  Solicita al usuario una respuesta específica que desea contar (por ejemplo, "si").
3.  Convierte la entrada del usuario y los elementos de la lista a un caso consistente (por ejemplo, minúsculas) para un conteo insensible a mayúsculas/minúsculas.
4.  Cuenta cuántas veces aparece esa respuesta específica en la lista.
5.  Imprime el resultado.

## Código con Errores

```python
# Ejercicio: Contar ocurrencias de un elemento en una lista

respuestas_encuesta = ["Si", "No", "si", "Quizas", "SI", "no", "Si"]

respuesta_a_contar = input("¿Qué respuesta quieres contar? (ej: si): ")
respuesta_a_contar_lower = respuesta_a_contar.lower

contador = 0
for respuesta in respuestas_encuesta:
    if respuesta.lower() = respuesta_a_contar_lower: # Error 1
        contador++ # Error 2

print(f"La respuesta '{respuesta_a_contar}' aparece {contador} veces.")
# Error 3: Si respuesta_a_contar_lower no se genera correctamente (por no llamar al método),
# la comparación y el conteo serán incorrectos.
