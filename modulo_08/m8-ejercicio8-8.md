# Módulo 8: Ejercicio 8 (Dificultad 10.24/10) - Conversión entre Lista y Tupla para Modificar

## Enunciado del Problema

1.  Se te da una tupla de `invitados = ("Ana", "Luis", "Carlos", "Eva")`.
2.  Imprime la lista de invitados original.
3.  Resulta que "Carlos" no puede venir y en su lugar vendrá "Marta". Como no puedes modificar la tupla directamente, conviértela a una lista.
4.  En la nueva lista, busca el índice de "Carlos" y reemplázalo por "Marta".
5.  Convierte la lista modificada de nuevo a una tupla llamada `invitados_actualizados`.
6.  Imprime la nueva tupla de invitados.

## Código con Errores

```python
# Ejercicio: Conversión entre lista y tupla para modificar

invitados = ("Ana", "Luis", "Carlos", "Eva")
print(f"Invitados originales: {invitados}")

# Convertir a lista para modificar
lista_invitados = list(invitados) # Esta línea es correcta

# Encontrar y reemplazar
indice_a_reemplazar = lista_invitados.index("carlos") # Error 1
lista_invitados[indice_a_reemplazar] = "Marta"

# Convertir de nuevo a tupla
invitados_actualizados = tuple(Lista_Invitados) # Error 2

print(f"Invitados actualizados: {invitados_actualizados}")
invitados[2] = "Marta" # Error 3 (Intento de modificar la tupla original para mostrar el error)
```
