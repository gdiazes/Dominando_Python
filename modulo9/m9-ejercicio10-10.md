# Módulo 9: Ejercicio 10 (Dificultad 13.44/10) - Traductor Simple usando un Diccionario

## Enunciado del Problema

1.  Crea un diccionario llamado `traductor_es_en` que sirva como un traductor simple de español a inglés. Incluye al menos 5 pares de palabras (ej: "casa": "house", "gato": "cat").
2.  Solicita al usuario que ingrese una frase en español.
3.  Divide la frase del usuario en una lista de palabras.
4.  Itera sobre la lista de palabras. Para cada palabra:
    *   Búscala en el diccionario `traductor_es_en`.
    *   Si la encuentras, añade su traducción a una nueva lista de palabras traducidas.
    *   Si no la encuentras, añade la palabra original (sin traducir) a la lista.
5.  Une las palabras de la lista traducida para formar una frase final y muéstrala.

## Código con Errores

```python
# Ejercicio: Traductor simple usando un diccionario

traductor_es_en = {
    "casa": "house",
    "gato": "cat",
    "perro": "dog",
    "árbol": "tree",
    "libro": "book",
}

frase_es = input("Ingresa una frase en español para traducir: ").lower()
palabras_es = frase_es.split()

palabras_traducidas_lista = []
for palabra in palabras_es:
    traduccion = traductor_es_en(palabra) # Error 1
    palabras_traducidas_lista.append(traduccion)

frase_final_en = " ".join(palabras_traducidas_lista)
print(f"Frase traducida: {frase_final_en}")

# Error 2 (lógico): El código fallará si una palabra no está en el diccionario.
# Error 3: Al dividir, la puntuación puede quedar pegada a las palabras (ej: "casa.").
# El código actual no maneja esto. ¿Cómo se podría limpiar la palabra antes de buscarla?
# Por ejemplo:
palabra_con_punto = "casa."
# traductor_es_en[palabra_con_punto] daría un KeyError.
```
