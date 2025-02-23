I accidentally wrote the flag down. Good thing I deleted it!You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/75/challenge.zip)

Hints:
- Version control can help you recover files if you change or lose them!
- Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control)
- You can 'checkout' commits to see the files inside them

## Solución
Al descomprimir el archivo, hay que entrar en la carpeta drop-in y usar el comando `git log`. Hay 2 commits: el principal y el anterior. Copiar el hash del commit anterior  y usar `git checkout <hash>` y hacerle un `cat message.txt`

`picoCTF{s@n1t1z3_9539be6b}`
