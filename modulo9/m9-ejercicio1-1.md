# Módulo 9: Ejercicio 1 (Dificultad 1.34/10) - Crear y Acceder a un Diccionario

## Enunciado del Problema

1.  Crea un diccionario llamado `pelicula_favorita` para almacenar información sobre una película. Debe tener las siguientes claves: "titulo", "director" y "anio". Asígnale valores apropiados.
2.  Imprime el diccionario completo.
3.  Accede e imprime el valor asociado con la clave "director".
4.  Accede e imprime el año de lanzamiento de la película.

## Código con Errores

```python
# Ejercicio: Crear y acceder a un diccionario

pelicula_favorita = {
    "titulo": "Inception",
    director: "Christopher Nolan", # Error 1
    "anio": 2010
}

print(f"Diccionario completo: {pelicula_favorita}")

director_pelicula = pelicula_favorita["Director"] # Error 2
anio_pelicula = pelicula_favorita[anio] # Error 3

print(f"Director: {director_pelicula}")
print(f"Año de lanzamiento: {anio_pelicula}")
```
