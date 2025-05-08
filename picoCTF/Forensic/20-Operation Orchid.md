Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/213/disk.flag.img.gz)

Hints: no hay

## Solución
Se usa el comando `mmls imagen` para obtener las particiones de la imagen. La partición objetivo es `411648`. Listando la carpeta root, se obtiene que existe un archivo llamado `flag.txt.enc`. Si se hace un `icat` al archivo, se obtiene que está encriptado. Se puede hacer también un `icat` al archivo `.ash_history`, y se obtiene el proceso que se hizo para codificar la bandera. El comando usado fue:

`openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567`

Entonces para hacer el proceso inverso, primero hay que extraer el archivo a nuestro sistema de archivos con `icat > flag.txt.enc` y el comando:

`openssl aes256 -salt -d -in flag.txt.enc -out flag.txt -k unbreakablepassword1234567`

`picoCTF{h4un71ng_p457_5113beab}`