Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/a614a27d4cb251d04c7d2f3f3f76a965/cat.jpg)

Hints:
- Look at the details of the file
- Make sure to submit the flag as picoCTF{XXXXX}

## Solución
Con el comando `exiftool cat.jpg`, se obtienen los metadatos de la imagen.

```
ExifTool Version Number         : 13.10
File Name                       : cat.jpg
Directory                       : .
File Size                       : 878 kB
File Modification Date/Time     : 2021:03:15 12:24:46-06:00
File Access Date/Time           : 2025:05:12 16:12:42-06:00
File Inode Change Date/Time     : 2025:05:12 16:12:39-06:00
File Permissions                : -rw-rw-r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1
```

El atributo `License` pareciera tener el formato de base 64. Al copiarlo, se puede ejecutar el comando `echo texto | base64 -d`. Con eso se obtiene la bandera.

`picoCTF{the_m3tadata_1s_modified}`