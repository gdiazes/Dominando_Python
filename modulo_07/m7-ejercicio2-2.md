
# Módulo 7: Ejercicio 2 (Dificultad 2.43/10) - Acceder y Modificar Elementos de una Lista

## Enunciado del Problema

1.  Crea una lista llamada `planetas` con los nombres: "Mercurio", "Venus", "Tierra", "Marte".
2.  Imprime el segundo planeta de la lista.
3.  Modifica el cuarto planeta para que sea "Jupiter" en lugar de "Marte".
4.  Imprime la lista completa después de la modificación.
5.  Intenta acceder al quinto planeta (índice 4) y observa qué sucede (esto generará un error intencionalmente si no se maneja, pero el código con errores se centrará en los otros puntos).

## Código con Errores

```python
# Ejercicio: Acceder y modificar elementos de una lista

planetas = ["Mercurio", "Venus", "Tierra", "Marte"]

print("Segundo planeta:", planetas[2]) # Error 1

planetas[4] = "Jupiter" # Error 2
print("Lista modificada:", planetas)

# print("Quinto planeta:", planetas[4]) # Error 3 (Comentado para evitar que el script se detenga por completo aquí)
# El error 3 estará en la lógica del anterior o en cómo se interpretaría el acceso.
# Para el código con errores, nos enfocaremos en los dos primeros y el conceptual.
# Si el código se ejecutara tal cual, planetas[4] ya daría error.
# Así que el tercer error será más sutil.
planetas.add("Saturno") # Error 3 (forma incorrecta de añadir)
