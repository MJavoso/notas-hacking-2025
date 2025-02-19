Can you make sense of this file?Download the file [here](https://artifacts.picoctf.net/c/477/enc_flag).

Hints:
- Multiple decoding is always good.

## Solución
```
MarCode-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/477/enc_flag

MarCode-picoctf@webshell:~$ ls
README.txt  enc_flag  textos
MarCode-picoctf@webshell:~$ cat enc_flag 
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbHBWV0VKVVZGWmFWMDVHV2tkYVNHUlZDazFyY0ZkVWJGWlhZVlpLU0dWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==
```
Hay que decodificar base64 varias veces hasta obtener la flag.

`picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_de523f49}`