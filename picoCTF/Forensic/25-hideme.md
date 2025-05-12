Every file gets a flag.The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://artifacts.picoctf.net/c/262/flag.png).

Hints: no hay


## Solución
Se puede usar la herramienta `binwalk` para analizar el contenido binario dentro de una imagen, como si se tratase de un zip. Al ejecutar el comando `binwalk flag.png`, se observa que al final hay 2 rutas interesantes. 'secret/UT' y 'secret/flag.pngUT'.

Con el comando `binwalk -e flag.png`, se extrae todo el contenido en una carpeta llamada `_flag.png.extracted`. La bandera se encuentra en la carpeta secret como otra imagen.

`picoCTF{Hiddinng_An_imag3_within_@n_ima9e_82101824}`