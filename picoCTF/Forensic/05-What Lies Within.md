There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?

Hints:
- There is data encoded somewhere... there might be an online decoder.

## Solución
Hay que usar la herramienta `zsteg` para buscar datos en los bytes.
`zsteg -a imagen.png`. Se instala con `sudo gem install zsteg`

`picoCTF{h1d1ng_1n_th3_b1t5}`