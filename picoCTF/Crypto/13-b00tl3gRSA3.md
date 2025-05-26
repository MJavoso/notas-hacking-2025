Why use p and q when I can use more? Connect with `nc jupiter.challenges.picoctf.org 4557`.

Hints:
- There's more prime factors than p and q, finding d is going to be different.
## Solución
Se nos proporciona c, n y e.

Se busca factorizar n en [factordb](https://factordb.com), sin embargo, se descubre que no tiene solo 2 factores, si no que varios. Se puede usar la siguiente [calculadora](https://www.alpertron.com.ar/ECMC.HTM) para factorizar el número, pero además, permite calcular `tn`, en la página se llama Phi de euler.

A partir de ahí es calcular:
- `d = pow(e, -1, tn)`
- `m = pow(c, d, n)`
- `bytes.fromhex(hex(m)[2:])`

`picoCTF{too_many_fact0rs_4025135}`