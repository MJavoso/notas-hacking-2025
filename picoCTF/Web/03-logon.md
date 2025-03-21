The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/44573/` ([link](https://jupiter.challenges.picoctf.org/problem/44573/)) or http://jupiter.challenges.picoctf.org:44573

Hints:
- Hmm it doesn't seem to check anyone's password, except for Joe's?

## Solución
Hay que cambiar la cabecera `Cookie`, modificando la variable 'admin' a 'True'. Hay que enviar de todos modos las cookies 'username' y 'password' con cualquier valor.

`picoCTF{th3_c0nsp1r4cy_l1v3s_0c98aacc}`