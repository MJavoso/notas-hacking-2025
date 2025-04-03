Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/00efdf2961da1e21470ffc0d496c3cc2/pico_img.png).

Hints:
- What does meta mean in the context of files?
- Ever heard of metadata?

## Solución
Hay que obtener los metadatos de la imagen. La bandera se encuentra en el artista. La manera usada  aquí fue `zsteg -a pico_img.png`. `zsteg` se descarga con `sudo gem install zsteg`. `gem` es el instalador de paquetes de Ruby.

`picoCTF{s0_m3ta_fec06741}`