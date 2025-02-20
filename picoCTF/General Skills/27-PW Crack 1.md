Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/10/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/10/level1.flag.txt.enc) in the same directory too.

Hints:
- To view the file in the webshell, do: `$ nano level1.py`
- To exit `nano`, press Ctrl and x and follow the on-screen prompts.
- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
Hay que entrar al archivo level1.py y  buscar la contraseña en la función `level_1_pw_check`, está en el if después del input.

```
MarCode-picoctf@webshell:~/PW Cracker$ ls   
level1.flag.txt.enc  level1.py
MarCode-picoctf@webshell:~/PW Cracker$ nano level1.py 
MarCode-picoctf@webshell:~/PW Cracker$ python3 level1.py 
Please enter correct password for flag: 691d
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_56891419}
MarCode-picoctf@webshell:~/PW Cracker$ 

picoCTF{545h_r1ng1ng_56891419}
```