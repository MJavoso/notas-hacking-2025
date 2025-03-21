Can you break into this super secure portal?
`https://jupiter.challenges.picoctf.org/problem/29835/` ([link](https://jupiter.challenges.picoctf.org/problem/29835/)) or http://jupiter.challenges.picoctf.org:29835

Hints:
- Never trust the client

## Solución
Entrar al inspector de la página web y entrar en la sección 'Sources'. Ir a la sección de script de html y estará la bandera fragmentada.
Hay que armar la bandera en base a la variable split, ya que define cada cuantos caracteres se divide el string, Empieza en 0 y termina en split, a partir de ahí va multiplicando split por n.

`picoCTF{no_clients_plz_7723ce}`