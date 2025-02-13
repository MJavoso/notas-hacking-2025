Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 7480`.

Hints:
1. Remember the flag format is picoCTF{XXXX}
2. What's a pipe? No not that kind of pipe... This [kind](http://www.linfo.org/pipes.html)

## Solucion 1
```
MarCode-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 7480 > datos
^C
MarCode-picoctf@webshell:~$ cat datos | grep pico
picoCTF{digital_plumb3r_06e9d954}
MarCode-picoctf@webshell:~$

picoCTF{digital_plumb3r_06e9d954}
```

## Solucion 2
```
MarCode-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 7480 | grep pico
picoCTF{digital_plumb3r_06e9d954}
^C
MarCode-picoctf@webshell:~$

picoCTF{digital_plumb3r_06e9d954}
```
