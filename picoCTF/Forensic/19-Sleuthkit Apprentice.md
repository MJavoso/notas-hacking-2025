Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/137/disk.flag.img.gz)

Hints: no hay

## Solución
Al descomprimir la imagen, se usa el comando `mmls imagen` para listar las particiones. La salida es la siguiente:

```
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000360447   0000153600   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000360448   0000614399   0000253952   Linux (0x83)
```

Se puede buscar en la partición 360448. Con el comando:

`fls imagen -o 360448`

Se obtienen los archivos de la ruta raíz:

```
d/d 451:        home
d/d 11: lost+found
d/d 12: boot
d/d 1985:       etc
d/d 1986:       proc
d/d 1987:       dev
d/d 1988:       tmp
d/d 1989:       lib
d/d 1990:       var
d/d 3969:       usr
d/d 3970:       bin
d/d 1991:       sbin
d/d 1992:       media
d/d 1993:       mnt
d/d 1994:       opt
d/d 1995:       root
d/d 1996:       run
d/d 1997:       srv
d/d 1998:       sys
d/d 2358:       swap
V/V 31745:      $OrphanFiles
```

Al ejecutar el comando:

`fls imagen -o 360448 -r` obtiene todos los archivos de manera recursiva, y si además, le agregamos `| grep flag`, se obtiene la siguiente información:

```
++ r/r * 2082(realloc): flag.txt
++ r/r 2371:    flag.uni.txt
```

El archivo "flag.txt" indica que fue eliminado, por lo tanto se intentará buscar en el archivo "flag.uni.txt".

Con el comando `icat imagen -o 360448 2371` se obtiene el contenido del archivo. El número se refiere al id del archivo dentro de la imagen, ya que no se puede usar el nombre del archivo.

`picoCTF{by73_5urf3r_adac6cb4}`