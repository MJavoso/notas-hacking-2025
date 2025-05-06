We found this [file](https://mercury.picoctf.net/static/06a5e4ab22ba52cd66a038d51a6cc07b/tunn3l_v1s10n). Recover the flag.

Hints:
- Weird that it won't display right...

## Solución
Con el comando `xxd -l 100 tunn3l_v1s10n` se obtienen los primeros 100 bytes.
Con `exiftool imagen` se obtienen los metadatos.
Los datos del renglón 0 que están como `BAD0` hay que cambiarlos por `280`. Y los bytes del rengón 10 hay que cambiar `32 01` por `40 03`.

`picoCTF{qu1t3_a_v13w_2020}`