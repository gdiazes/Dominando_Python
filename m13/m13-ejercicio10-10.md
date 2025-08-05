# Módulo 13: Ejercicio 10 (Dificultad 16.29/10) - Utilizar un Módulo de Terceros (Simulación)

## Enunciado del Problema

Imagina que has instalado una biblioteca de terceros muy popular llamada `requests` para hacer peticiones web.
El objetivo de este ejercicio es simular el uso de esta biblioteca.
1.  Importa la biblioteca `requests`.
2.  Simula una petición GET a una URL (por ejemplo, "https://api.github.com").
3.  El resultado de una petición con `requests` suele ser un objeto "Response" que tiene un atributo `.status_code` (un número) y un método `.json()` (que convierte la respuesta a un diccionario si es JSON).
4.  Verifica si el `status_code` es 200 (que significa "OK"). Si lo es, "convierte" la respuesta a JSON e imprime alguna parte de ella. Si no, imprime un mensaje de error.

*Nota: No necesitas instalar `requests` para este ejercicio. Crearemos un objeto "falso" que simule la respuesta para probar la lógica.*

## Código con Errores

```python
# Ejercicio: Utilizar un módulo de terceros (simulación)

import requests # Error 1: Si no está instalado, esto falla. Lo simularemos.

# --- SIMULACIÓN ---
class RespuestaFalsa:
    def __init__(self, status, contenido_json):
        self.status_code = status
        self._contenido_json = contenido_json
    def json(self):
        return self._contenido_json

# respuesta = requests.get("https://api.github.com") # Línea real que simularemos
respuesta = RespuestaFalsa(200, {"message": "API rate limit exceeded"}) # Simulación de respuesta real
# --- FIN SIMULACIÓN ---


if respuesta.status_code = 200: # Error 2
    datos = respuesta.json
    print("Petición exitosa.")
    print(f"Mensaje de la API: {datos['message']}")
else
    print(f"Error en la petición. Código de estado: {respuesta.status_code}") # Error 3
