Play this short game to get familiar with terminal applications and some of the most important rules in scope for picoCTF.Connect to the program with netcat:`$ nc verbal-sleep.picoctf.net 55716`

Hints:
- When a choice is presented like [a/b/c], choose one, for example: `c` and then press Enter.

## Solución
Hay que conectarse a través de netcat a la url y puerto solicitados. Solo es una breve historia donde hay que presionar enter e ingresar a/b/c cuando se te pida.
Cuando te pregunten:
```
Options:
A) *Play the game*
B) *Search the Ether for the flag*
[a/b] >
```
Hay que ingresar la a.

`picoCTF{m1113n1um_3d1710n_fc649bc5}`