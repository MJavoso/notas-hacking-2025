Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings) without running it?

Hints:
- [strings](https://linux.die.net/man/1/strings)

## Solución
Ejecutar el comando `strings` de Linux, ya que es un archivo binario al leerlo como texto.
```
MarCode-picoctf@webshell:~$ strings strings | grep pico
picoCTF{5tRIng5_1T_d66c7bb7}
```
`picoCTF{5tRIng5_1T_d66c7bb7}`