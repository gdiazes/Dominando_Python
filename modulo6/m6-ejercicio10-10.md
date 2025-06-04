# Módulo 6: Ejercicio 10 (Dificultad 11.55/10) - Simulación de Batalla por Turnos Simple con Bucles `while` Anidados

## Enunciado del Problema

Simula una batalla por turnos entre un Héroe y un Monstruo.
*   Héroe: Empieza con 100 de Vida (HP) y hace 10 de Daño por ataque.
*   Monstruo: Empieza con 80 de Vida (HP) y hace 8 de Daño por ataque.

El combate sigue estas reglas:
1.  El Héroe ataca primero.
2.  Luego el Monstruo ataca (si sigue vivo).
3.  Esto se repite hasta que uno de los dos tenga 0 o menos HP.
4.  El programa debe anunciar cada ataque y la vida restante del objetivo.
5.  Al final, anunciar quién ganó.

Usa un bucle `while` principal para controlar la batalla (mientras ambos estén vivos) y puedes usar lógica condicional para los turnos o simplemente alternarlos.

## Código con Errores

```python
# Ejercicio: Simulación de batalla por turnos

hp_heroe = 100
dano_heroe = 10
hp_monstruo = 80
dano_monstruo = 8

turno = 1
print("¡Comienza la batalla!")
print(f"Héroe HP: {hp_heroe}, Monstruo HP: {hp_monstruo}")

while hp_heroe > 0 and hp_monstruo > 0:
    print(f"\n--- Turno {turno} ---")

    # Turno del Héroe
    if hp_heroe > 0: # Héroe solo ataca si está vivo (ya cubierto por el while principal)
        print(f"Héroe ataca al Monstruo por {dano_heroe} de daño.")
        hp_monstruo -= dano_heroe
        print(f"Monstruo HP restante: {hp_monstruo}")
    
    
    
    # Turno del Monstruo
    if hp_monstruo > 0 
        print(f"Monstruo ataca al Héroe por {dano_monstruo} de daño.")
        hp_heroe -= dano_monstruo
        print(f"Héroe HP restante: {hp_heroe}")

    turno += 1
    

# Anunciar ganador
if hp_heroe <= 0:
    print("\n¡El Monstruo ha ganado!")
elif hp_monstruo <= 0:
    print("\n¡El Héroe ha ganado!")
else: # Caso improbable si el bucle termina correctamente
    print("\n¡La batalla terminó en empate técnico o error!")
```
