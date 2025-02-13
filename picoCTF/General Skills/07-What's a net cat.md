Using netcat (nc) is going to be pretty important. Can you connect to `jupiter.challenges.picoctf.org` at port `25103` to get the flag?

Hints:
1. nc [tutorial](https://linux.die.net/man/1/nc)

## Solucion
```
MarCode-picoctf@webshell:~$ ls
README.txt  flag  textos
MarCode-picoctf@webshell:~$ which nc
/usr/bin/nc
MarCode-picoctf@webshell:~$ man nc
MarCode-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 25103
You're on your way to becoming the net cat master
picoCTF{nEtCat_Mast3ry_d0c64587}

picoCTF{nEtCat_Mast3ry_d0c64587}
```