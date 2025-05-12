Download this image and find the flag.

- [Download image](https://artifacts.picoctf.net/c/216/pico.flag.png)

Hints:
- We know the end sequence of the message will be `$t3g0`.

## Solución
Se descarga una herramienta llamada [Image Stego Tool](https://github.com/djrobin17/image-stego-tool). Se ejecuta con `python stego.py`. Al ejecutarse, preguntará si se desea codificar o decodificar. Se selecciona decodificar y se pone la ruta donde se descargó la imagen del reto. Al pedir la contraseña, se coloca `$t3g0`, que es la pista que nos da el reto.

`picoCTF{7h3r3_15_n0_5p00n_a1062667}`