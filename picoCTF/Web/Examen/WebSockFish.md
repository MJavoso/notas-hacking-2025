Can you win in a convincing manner against this chess bot? He won't go easy on you!You can find the challenge [here](http://verbal-sleep.picoctf.net:57518/).

Hints:
- Try understanding the code and how the websocket client is interacting with the server

## Solución
Hay que usar burpsuite para interceptar los datos que se intercambian en el websocket. Cada que se realiza un movimiento, se manda `eval n` o `eval -n`, y el servidor responde con un mensaje. Si n es más grande, ya sea positivo o negativo, mandará un mensaje de asombro. Por lo cual, si le mandamos un número muy grande, nos dará la bandera. `eval 10000000`

`picoCTF{c1i3nt_s1d3_w3b_s0ck3t5_c0789e29}`