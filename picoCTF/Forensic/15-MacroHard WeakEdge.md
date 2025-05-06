I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/d3dd8cd51524d9fafcccd1b7d55f85e7/Forensics%20is%20fun.pptm)

Hints: no hay

## Solución
Debido a que todas las presentaciones son en realidad un zip, se puede descomprimir y buscar la bandera.

De todos los archivos descomprimidos, hay un archivo curioso ubicado en `ppt/slideMasters/hidden`. Si le aplicamos un `cat`, salen letras con espacios. Para quitarlos hay que aplicar `cat archivo | tr -d ' '`. La salida produce una cadena que pareciera estar codificada en base 64. Al agregar `| base64 -d` al comando, obtenemos la bandera.

`picoCTF{D1d_u_kn0w_ppts_r_z1p5}`