RED, RED, RED, RED

Download the image: [red.png](https://challenge-files.picoctf.net/c_verbal_sleep/831307718b34193b288dde31e557484876fb84978b5818e2627e453a54aa9ba6/red.png)

Hints:
 - The picture seems pure, but is it though?
 - Red?Ged?Bed?Aed?
 - Check whatever Facebook is called now.

## Solución
Al realizar un `exiftool red.png`, solo se obtiene un poema extraño.

Se puede usar `zsteg red.png` de las librerías de Ruby para intentar obtener información extra. Al ejecutarlo, se puede observar que debajo del poema hay un texto codificado. Pareciera base64, entonces al realizar `echo texto | base64 -d`, se observa que la bandera está repetida 3 veces

`picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}`