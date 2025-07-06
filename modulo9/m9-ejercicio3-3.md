# Módulo 9: Ejercicio 3 (Dificultad 4.03/10) - Acceso Seguro con `.get()`

## Enunciado del Problema

1.  Crea un diccionario `configuracion` con algunas claves como "tema" (valor: "oscuro") y "idioma" (valor: "español").
2.  Solicita al usuario una clave que desea consultar.
3.  Usa el método `.get()` para obtener el valor de la clave ingresada por el usuario. Si la clave no existe, debe devolver el mensaje "Clave no encontrada".
4.  Imprime el resultado obtenido.

## Código con Errores

```python
# Ejercicio: Acceso seguro con .get()

configuracion = {
    "tema": "oscuro",
    "idioma": "español",
    "notificaciones": True
}

clave_a_buscar = input("¿Qué clave de configuración quieres consultar? ")

valor = configuracion.get(clave_a_buscar, "Clave no encontrada".) # Error 1
valor_tema = configuracion.get[tema] # Error 2

print(f"El valor para '{clave_a_buscar}' es: {valor}")

# Error 3: Intento de usar .get() para asignar un valor
configuracion.get("fuente", "Arial") = "Calibri"
```
