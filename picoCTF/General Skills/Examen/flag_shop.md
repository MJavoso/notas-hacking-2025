There's a flag shop selling stuff, can you buy a flag? [Source](https://jupiter.challenges.picoctf.org/static/253c4651d852ac6342752ff222cf2a83/store.c). Connect with `nc jupiter.challenges.picoctf.org 9745`.

Hints:
- Two's compliment can do some weird things when numbers get really big!

## Solución
Lo que hay que hacer es comprar las banderas normales en la opción 1 tras haber seleccionado `Buy flags`. Hay que ingresar una cantidad grande de banderas para que al realizar el cálculo, el número sea más grande que el límite que soportan 32 bits con complemento a 2 y se desborde, causando que en vez de restar saldo, sume.

`picoCTF{m0n3y_bag5_65d67a74}`