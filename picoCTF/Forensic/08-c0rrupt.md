We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

Hints:
- Try fixing the file header

## Solución
El archivo está corrupto.
Primero se intenta obtener el tipo del archivo con el comando `file`, y se obtiene que es de tipo `data`. El archivo es una imagen corrupta. Para empezar, se agrega al principio los bytes magicos que identifican un png:
`89 50 4E 47  0D 0A 1A 0A   00 00 00 0D  49 48 44 52`
Hay que instalar el paquete `pngcheck` para verificar que errores tiene: `pngcheck -v mystery`.

Mostrará que los errores los tiene en las líneas hexadecimales `40` y `50`. Para corregir el archivo corrupto, debe quedar de la siguiente manera:
```
00000040: 0009 7048 5973 0000 1625 0000 1625 0149
00000050: 5224 f000 00ff a549 4441 5478 5eec bd3f
```
Y finalmente, se puede abrir con `open mystery` para obtener la bandera.

`picoCTF{c0rrupt10n_1847995}`