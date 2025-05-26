In RSA d is a lot bigger than e, why don't we use d to encrypt instead of e? Connect with `nc jupiter.challenges.picoctf.org 19566`.

Hints:
- What is e generally?

## Solución
Se nos da c, e y n.

e es demasiado grande, por lo que se reemplaza por su valor más común: 65537.

Debido a que utilizo e para encriptar, se puede usar también para desencriptar:
`m = pow(c, e, n)`

`picoCTF{bad_1d3a5_2438125}`