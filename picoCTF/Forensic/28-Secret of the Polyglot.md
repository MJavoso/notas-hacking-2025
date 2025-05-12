The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/99/flag2of2-final.pdf).

Hints:
- This problem can be solved by just opening the file in different ways

## Solución
Al apenas abrir el pdf descargado, te da la segunda parte de la bandera. Hay que buscar la primera parte.

Con `exiftool pdf`, se puede observar que en realidad, el archivo es una imagen. Al renombrarla a un archivo con extensión png, se obtiene la primera parte: `picoCTF{f1u3n7_`.

`picoCTF{f1u3n7_1n_pn9_&_pdf_2a6a1ea8}`