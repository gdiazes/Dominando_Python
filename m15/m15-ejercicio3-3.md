# Módulo 15: Ejercicio 3 (Dificultad 5/10) - Crear una Clase con Métodos (CuentaBancaria)

## Enunciado del Problema

1.  Define una clase `CuentaBancaria`.
2.  El constructor `__init__` debe aceptar un `titular` y un `saldo_inicial` (con valor por defecto 0).
3.  Define un método `depositar(monto)` que añada el `monto` al saldo.
4.  Define un método `retirar(monto)` que reste el `monto` del saldo, pero solo si hay fondos suficientes. Si no hay fondos, debe imprimir un mensaje de advertencia.
5.  Define un método `consultar_saldo()` que imprima el saldo actual.
6.  Crea un objeto, deposita, intenta retirar más de lo que tienes, retira una cantidad válida y consulta el saldo.

## Código con Errores

```python
# Ejercicio: Crear una clase con métodos

class CuentaBancaria:
    def __init__(self, titular, saldo_inicial=0):
        self.titular = titular
        self.saldo = saldo_inicial
    
    def depositar(monto): # Error 1
        saldo += monto
        print(f"Depósito exitoso. Nuevo saldo: {self.saldo}")

    def retirar(self, monto):
        if monto <= self.saldo:
            self.saldo -= monto
            print(f"Retiro exitoso. Nuevo saldo: {self.saldo}")
        else:
            print("Fondos insuficientes.")
            
    def consultar_saldo(self):
        print(f"Saldo actual: {self.saldo}")

mi_cuenta = CuentaBancaria("Ana")
mi_cuenta.depositar(100)
mi_cuenta.retirar(150) # Intento de sobregiro
mi_cuenta.retirar(50)
consultar_saldo(mi_cuenta) # Error 2

# Error 3: Intento de acceder a un atributo privado (convención), o simplemente de forma incorrecta
# print(mi_cuenta._saldo)
```
