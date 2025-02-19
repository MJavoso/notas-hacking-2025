To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29221`.

Hints:
- I hear python can convert things.
- It might help to have multiple windows open.

## Solución 1
Primero te pedirá la palabra formada en un binario, después en octal, y por último en hexadecimal.

Python
```
from sys import exit

BINARIO = 'b'
DECIMAL = 'd'
HEXADECIMAL = 'h'
OCTAL = 'o'

numero_base = input("Ingresa el número: ")

base = input("Ingresa la base del número: ")

if base == BINARIO:
    numero_base = numero_base.split(" ")
    numero = [int(i, 2) for i in numero_base]
elif base == DECIMAL:
    numero_base = numero_base.split(" ")
    numero = [int(i) for i in numero_base]
elif base == HEXADECIMAL:
    numero_base = [numero_base[i:i+2] for i in range(0, len(numero_base), 2)]
    numero = [int(i, 16) for i in numero_base]
elif base == OCTAL:
    numero_base = numero_base.split(" ")
    numero = [int(i, 8) for i in numero_base]
else:
    print("Base no válida")
    exit(0)

palabra = "".join([chr(i) for i in numero])
print(palabra)
```
El formato será:
- Binario: 01010011 10010101 (espacio por cada letra)
- Octal: 155 141 170 (espacio por cada letra)
- Hexadecimal: e4563e14 (letra por cada 2 caracteres del hexadecimal)
`picoCTF{learning_about_converting_values_00a975ff}`