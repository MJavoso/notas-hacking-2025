Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/13/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/13/level2.flag.txt.enc) in the same directory too.

Hints:
- Does that encoding look familiar?
- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
Hay que entrar al script `level2.py` y buscar la función `level_2_pw_check`. La contraseña está armada por caracteres armados a través de su valor hexadecimal. Hay que convertir a letras a partir de esos hexadecimales.

```
MarCode-picoctf@webshell:~/PW Cracker/level2$ nano level2.py 
MarCode-picoctf@webshell:~/PW Cracker/level2$ python3 level2.py 
Please enter correct password for flag: de76
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_489dea9a}
MarCode-picoctf@webshell:~/PW Cracker/level2$ 

picoCTF{tr45h_51ng1ng_489dea9a}
```