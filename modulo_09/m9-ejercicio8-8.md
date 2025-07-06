# Módulo 9: Ejercicio 8 (Dificultad 10.76/10) - Combinar Dos Diccionarios

## Enunciado del Problema

1.  Crea un diccionario `perfil_basico` con claves como "nombre" y "edad".
2.  Crea otro diccionario `perfil_social` con claves como "email" y "red_social".
3.  Crea un tercer diccionario `perfil_completo` que sea la combinación de los dos anteriores. Utiliza un método de diccionario para lograrlo.
4.  Imprime el `perfil_completo`.
5.  Crea un cuarto diccionario `actualizacion_perfil` con una clave que ya exista en `perfil_completo` (ej: "edad") con un nuevo valor, y una clave nueva (ej: "ciudad").
6.  Actualiza `perfil_completo` con `actualizacion_perfil` e imprime el resultado final.

## Código con Errores

```python
# Ejercicio: Combinar dos diccionarios

perfil_basico = {"nombre": "David", "edad": 42}
perfil_social = {"email": "david@example.com", "red_social": "@david_py"}

# Combinar diccionarios
perfil_completo = perfil_basico + perfil_social # Error 1

print(f"Perfil combinado inicial: {perfil_completo}")

actualizacion_perfil = {"edad": 43, "ciudad": "Nueva York"}

# Actualizar el perfil completo
perfil_completo.update[actualizacion_perfil] # Error 2

print(f"Perfil final actualizado: {perfil_completo}")

# Error 3: Otra forma incorrecta de intentar combinar
# perfil_final_alt = {perfil_basico, perfil_social}
# print(perfil_final_alt)
```
