How about some hide and seek?Download this file [here](https://artifacts.picoctf.net/c_titan/131/unknown.zip).

Hints:
- How can you view the information about the picture?
- If something isn't in the expected form, maybe it deserves attention?

## Solución
Se extrae el zip con `unzip archivo.zip`. Se obtiene una imagen. Abrirla no aporta información.

Al usar `exiftool imagen`, se obtienen los metadatos de la imagen, y se puede ver un atributo llamado `Attribution URL` con lo que parece ser codificación base 64. Con el comando `echo texto | base64 -d` se obtiene la bandera. 

`picoCTF{ME74D47A_HIDD3N_d8c381fd}`