## Nombre Original: Disk, disk, sleuth!
Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image: [dds1-alpine.flag.img.gz](https://mercury.picoctf.net/static/920731987787c93839776ce457d5ecd6/dds1-alpine.flag.img.gz)

Hints:
- Have you ever used `file` to determine what a file was?
- Relevant terminal-fu in picoGym: https://play.picoctf.org/practice/challenge/85
- Mastering this terminal-fu would enable you to find the flag in a single command: https://play.picoctf.org/practice/challenge/48
- Using your own computer, you could use qemu to boot from this disk!

## Solución
Descomprimir el archivo gz con el comando `gzip -d archivo.gz`. Usando el comando `srch_strings archivo.img | grep pico` se obtiene la bandera.

 `picoCTF{f0r3ns1c4t0r_n30phyt3_564ff1a0}`