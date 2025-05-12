I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/15/challenge.zip)

Additional details will be available after launching your challenge instance.

Hints:
- QR codes are a way of encoding data. While they're most known for storing URLs, they can store other things too.
- Mobile phones have included native QR code scanners in their cameras since version 8 (Oreo) and iOS 11
- If you don't have access to a phone, you can also use zbar-tools to convert an image to text

## Solución
Al descomprimir el archivo, hay que ubicarse en la ruta `home/ctf-player` y abrir la imagen con `open flag.png`. Es un QR, y solo hay que escanearlo.

`picoCTF{p33k_@_b00_19eccd10}`