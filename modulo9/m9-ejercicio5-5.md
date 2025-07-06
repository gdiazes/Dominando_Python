# Módulo 9: Ejercicio 5 (Dificultad 6.72/10) - Iterar sobre Claves, Valores e Ítems

## Enunciado del Problema

1.  Crea un diccionario `capitales` que mapee algunos países a sus capitales (ej: "España": "Madrid", "Francia": "París", "Italia": "Roma").
2.  Usando un bucle `for`, imprime solo las claves (países).
3.  Usando un bucle `for` y el método `.values()`, imprime solo los valores (capitales).
4.  Usando un bucle `for` y el método `.items()`, imprime los pares clave-valor en el formato "La capital de [País] es [Capital]".

## Código con Errores

```python
# Ejercicio: Iterar sobre claves, valores e ítems

capitales = {
    "España": "Madrid",
    "Francia": "París",
    "Italia": "Roma"
}

print("Países (claves):")
for pais in capitales.keys: # Error 1
    print(pais)

print("\nCapitales (valores):")
for capital in capitales.values():
    print(capital)

print("\nRelación completa:")
for pais, capital in capitales: # Error 2
    print(f"La capital de {pais} es {capital}")

# Error 3 (conceptual): ¿Qué imprimiría el siguiente código?
# for item in capitales.items():
#     print(item[1])
```
