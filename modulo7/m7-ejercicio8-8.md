# Módulo 7: Ejercicio 8 (Dificultad 9.72/10) - Ordenar una Lista e Invertirla

## Enunciado del Problema

1.  Crea una lista de al menos 6 números desordenados llamada `calificaciones_desordenadas`.
2.  Ordena la lista en orden ascendente *modificando la lista original*. Imprime la lista ordenada.
3.  Luego, invierte el orden de la lista ordenada (para que quede en orden descendente) *modificando la lista original*. Imprime la lista invertida.
4.  Crea una copia de la lista `calificaciones_desordenadas` original. Ordena esta copia para obtener una *nueva lista* ordenada en ascendente, sin modificar la copia original (la que se está ordenando). Imprime tanto la nueva lista ordenada como la copia que debería permanecer desordenada.

## Código con Errores

```python
# Ejercicio: Ordenar una lista e invertirla

calificaciones_desordenadas = [88, 75, 92, 60, 95, 80]
print(f"Original: {calificaciones_desordenadas}")

# Ordenar modificando la original
calificaciones_desordenadas.sort # Error 1
print(f"Ordenada ascendente: {calificaciones_desordenadas}")

# Invertir la lista ya ordenada
calificaciones_desordenadas.reverse()
print(f"Invertida (descendente): {calificaciones_desordenadas}") # Esta parte estaría bien si la anterior funcionó

# Copia y ordenamiento sin modificar la copia original que se ordena
copia_calificaciones = calificaciones_desordenadas.copy() # Correcto
# Queremos que 'copia_calificaciones' siga desordenada (o como estaba antes de este bloque)
# Pero calificaciones_desordenadas ya está modificada. Usemos la original.
copia_para_ordenar = [88, 75, 92, 60, 95, 80] # Reiniciamos para el ejemplo
nueva_lista_ordenada = sorted(copia_para_ordenar, reverse=False) # Correcto
copia_para_ordenar.sort(descending=True) # Error 2 (parámetro incorrecto para sort)

print(f"Copia original (debería estar desordenada o como al inicio de este bloque): {copia_para_ordenar}")
print(f"Nueva lista ordenada (de la copia): {nueva_lista_ordenada}")
# Error 3: El estado de 'copia_para_ordenar' se ve afectado por .sort() in-situ.
# La idea es mostrar que sorted() no la afecta, pero .sort() sí.
# La pista para el error 3 es sobre el entendimiento de la mutabilidad.
