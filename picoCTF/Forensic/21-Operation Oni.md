Download this disk image, find the key and log into the remote machine.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

Additional details will be available after launching your challenge instance.

Hints: no hay

## Solución
Con `mmls` se obtiene que la partición a buscar es `206848`. Hay que acceder a la carpeta root con `fls`, y ahí se encuentran 2 archivos para ssh. Hay que extraer la clave privada con `icat disk.img -o 206848 2345 > key_file`, y luego ejecutar el comando `ssh -i key_file -p puerto ctf-player@saturn.picoctf.net`. La flag está apenas entrar en flag.txt

`picoCTF{k3y_5l3u7h_339601ed}`