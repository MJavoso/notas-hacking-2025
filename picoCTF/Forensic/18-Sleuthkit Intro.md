Download the disk image and use `mmls` on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.[Download disk image](https://artifacts.picoctf.net/c/164/disk.img.gz)

Additional details will be available after launching your challenge instance.

Hints: no hay

## Solución
Hay que descomprimir el archivo descargado con `gzip -d archivo`.

Con el comando `mmls disk.img` te mostrará la información de las particiones. Al conectarse al servidor, te preguntará cuanto mide la partición de linux. Al ingresar el tamaño correcto, devuelve la bandera.

`picoCTF{mm15_f7w!}`