# Módulo 12: Trabajando con el Tiempo: Fechas y Horas en Python

## Laboratorio 12 - Guía Paso a Paso

¡Bienvenido al Laboratorio 12! En casi cualquier aplicación, desde un blog hasta un sistema de reservas o un análisis de datos, es fundamental manejar fechas y horas. Python nos proporciona un módulo muy potente en su biblioteca estándar para este propósito: `datetime`.

### El Módulo `datetime`
El módulo `datetime` contiene clases para manipular fechas y horas. Las más importantes son:
*   `datetime.date`: Para trabajar solo con fechas (año, mes, día).
*   `datetime.time`: Para trabajar solo con horas (hora, minuto, segundo, microsegundo).
*   `datetime.datetime`: Para trabajar con fechas y horas combinadas.
*   `datetime.timedelta`: Para representar una duración o diferencia entre dos fechas u horas.

Para empezar a usarlo, primero debemos importarlo:
```python
import datetime
```

### `datetime.datetime`: La Clase Principal
La clase `datetime.datetime` es la que más usarás, ya que combina información de fecha y hora.

**Obtener la Fecha y Hora Actual:**
El método `.now()` te da la fecha y hora actual del sistema.
```python
ahora = datetime.datetime.now()
print(f"Fecha y hora actual: {ahora}")
# Salida (ejemplo): Fecha y hora actual: 2023-10-27 10:30:55.123456
```
Puedes acceder a sus componentes individuales:
```python
print(f"Año: {ahora.year}")
print(f"Mes: {ahora.month}")
print(f"Día: {ahora.day}")
print(f"Hora: {ahora.hour}")
print(f"Minuto: {ahora.minute}")
print(f"Segundo: {ahora.second}")
```

**Crear un Objeto `datetime` Específico:**
Puedes crear un objeto `datetime` para una fecha y hora concretas.
```python
fecha_especifica = datetime.datetime(2025, 1, 31, 15, 45, 0) # Año, mes, día, hora, minuto, segundo
print(f"Fecha específica: {fecha_especifica}")
# Salida: Fecha específica: 2025-01-31 15:45:00
```

### Formateo de Fechas y Horas: `strftime()`
A menudo, querrás mostrar una fecha en un formato más legible para el usuario (ej: "27 de Octubre de 2023"). El método `.strftime()` (string format time) convierte un objeto `datetime` a una cadena de texto formateada.
Utiliza códigos de formato especiales que comienzan con `%`.

**Códigos de formato comunes:**
*   `%Y`: Año con 4 dígitos (ej: 2023)
*   `%y`: Año con 2 dígitos (ej: 23)
*   `%m`: Mes como número (01-12)
*   `%B`: Nombre completo del mes (ej: "October")
*   `%b`: Nombre abreviado del mes (ej: "Oct")
*   `%d`: Día del mes como número (01-31)
*   `%A`: Nombre completo del día de la semana (ej: "Friday")
*   `%a`: Nombre abreviado del día de la semana (ej: "Fri")
*   `%H`: Hora en formato 24h (00-23)
*   `%I`: Hora en formato 12h (01-12)
*   `%p`: AM o PM
*   `%M`: Minuto (00-59)
*   `%S`: Segundo (00-59)

```python
ahora = datetime.datetime.now()

# Formateo personalizado
formato_latino = ahora.strftime("%d/%m/%Y %H:%M:%S")
print(f"Formato latino: {formato_latino}") # Salida: 27/10/2023 10:30:55

formato_legible = ahora.strftime("Hoy es %A, %d de %B de %Y")
print(f"Formato legible: {formato_legible}") # Salida: Hoy es Friday, 27 de October de 2023
# Nota: los nombres de meses/días salen en inglés por defecto. Para otros idiomas se requiere configuración adicional (locale).
```

### Convertir Cadenas a `datetime`: `strptime()`
El proceso inverso, convertir una cadena de texto a un objeto `datetime`, se hace con `datetime.strptime()` (string parse time). Debes indicarle a la función el formato exacto en que viene la cadena de texto, usando los mismos códigos de formato.

```python
cadena_fecha = "31-01-2025 15:45"
formato_de_cadena = "%d-%m-%Y %H:%M"

fecha_objeto = datetime.datetime.strptime(cadena_fecha, formato_de_cadena)
print(f"Objeto datetime creado: {fecha_objeto}")
print(f"Año del objeto: {fecha_objeto.year}")
# Salida:
# Objeto datetime creado: 2025-01-31 15:45:00
# Año del objeto: 2025
```
Si la cadena no coincide con el formato especificado, se producirá un `ValueError`.

### Cálculos con Fechas y Horas: `timedelta`
Para realizar cálculos como "qué fecha será dentro de 10 días" o "cuántos días han pasado entre dos fechas", se usa la clase `datetime.timedelta`. Un objeto `timedelta` representa una duración.

**Crear un `timedelta`:**
```python
duracion_una_semana = datetime.timedelta(days=7)
duracion_dos_horas_media = datetime.timedelta(hours=2, minutes=30)
```

**Sumar y Restar `timedelta` a un `datetime`:**
```python
ahora = datetime.datetime.now()
print(f"Ahora: {ahora}")

hace_tres_dias = ahora - datetime.timedelta(days=3)
print(f"Hace 3 días: {hace_tres_dias}")

dentro_de_5_horas = ahora + datetime.timedelta(hours=5)
print(f"Dentro de 5 horas: {dentro_de_5_horas}")
```

**Diferencia entre dos `datetime`:**
Restar dos objetos `datetime` da como resultado un objeto `timedelta`.
```python
fecha_inicio = datetime.datetime(2023, 1, 1)
fecha_fin = datetime.datetime(2023, 1, 31)

diferencia = fecha_fin - fecha_inicio
print(f"Diferencia: {diferencia}") # Salida: Diferencia: 30 days, 0:00:00

print(f"Días de diferencia: {diferencia.days}") # Salida: 30
print(f"Segundos totales de diferencia: {diferencia.total_seconds()}") # Salida: 2592000.0
```
El módulo `datetime` es esencial para cualquier programador Python. Te permite manejar el tiempo con precisión, una habilidad crucial para una amplia gama de aplicaciones.

---

## Ejercicios del Módulo 12

Estos ejercicios te ayudarán a familiarizarte con la creación de objetos `datetime`, su formateo a cadenas (`strftime`), la conversión de cadenas a `datetime` (`strptime`), y la realización de cálculos temporales con `timedelta`.

1.  **Mostrar Fecha y Hora Actual** (Dificultad 1.55): [m12-ejercicio1-1.md](m12-ejercicio1-1.md)
2.  **Crear una Fecha Específica y Formatearla** (Dificultad 3.11): [m12-ejercicio2-2.md](m12-ejercicio2-2.md)
3.  **Convertir una Cadena a `datetime`** (Dificultad 4.66): [m12-ejercicio3-3.md](m12-ejercicio3-3.md)
4.  **Calcular una Fecha Futura con `timedelta`** (Dificultad 6.22): [m12-ejercicio4-4.md](m12-ejercicio4-4.md)
5.  **Calcular Días Vividos** (Dificultad 7.77): [m12-ejercicio5-5.md](m12-ejercicio5-5.md)
6.  **Extraer Componentes de una Fecha** (Dificultad 9.33): [m12-ejercicio6-6.md](m12-ejercicio6-6.md)
7.  **Temporizador de Cuenta Regresiva Simple** (Dificultad 10.88): [m12-ejercicio7-7.md](m12-ejercicio7-7.md)
8.  **Validador de Formato de Fecha** (Dificultad 12.44): [m12-ejercicio8-8.md](m12-ejercicio8-8.md) (PC3 Integrada)
9.  **Calcular Edad Exacta (Años, Meses, Días)** (Dificultad 13.99): [m12-ejercicio9-9.md](m12-ejercicio9-9.md) (PC3 Integrada)
10. **Agenda de Eventos Simple: ¿Cuánto falta?** (Dificultad 15.54): [m12-ejercicio10-10.md](m12-ejercicio10-10.md) (PC3 Integrada)
