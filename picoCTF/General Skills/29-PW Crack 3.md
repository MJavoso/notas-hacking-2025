Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/17/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/17/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/17/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

Hints:
- To view the level3.hash.bin file in the webshell, do: `$ bvi level3.hash.bin`
- To exit `bvi` type `:q` and press enter.
- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
Hay que entrar al archivo `level3.py` e irse al final del script. Hay una lista de posibles contraseñas, sin embargo, solo una es correcta. Intentar hasta acertar.

```
MarCode-picoctf@webshell:~/PW Cracker/level3$ ls
level3.flag.txt.enc  level3.hash.bin  level3.py
MarCode-picoctf@webshell:~/PW Cracker/level3$ nano level3.py 
MarCode-picoctf@webshell:~/PW Cracker/level3$ bvi level3.hash.bin 

bvi version 1.4.0 Copyright (C) 1996-2014 by Gerhard Buergmann
MarCode-picoctf@webshell:~/PW Cracker/level3$ bvi level3.hash.bin 

bvi version 1.4.0 Copyright (C) 1996-2014 by Gerhard Buergmann
MarCode-picoctf@webshell:~/PW Cracker/level3$ nano level3.py
MarCode-picoctf@webshell:~/PW Cracker/level3$ python3 level3.py 
Please enter correct password for flag: f09e
That password is incorrect
MarCode-picoctf@webshell:~/PW Cracker/level3$ python3 level3.py 
Please enter correct password for flag: 4dcf
That password is incorrect
MarCode-picoctf@webshell:~/PW Cracker/level3$ python3 level3.py 
Please enter correct password for flag: 87ab
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_cd6ed2eb}
MarCode-picoctf@webshell:~/PW Cracker/level3$ 

picoCTF{m45h_fl1ng1ng_cd6ed2eb}
```