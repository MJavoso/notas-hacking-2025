Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/26/fixme1.py)

Hints:
- Indentation is very meaningful in Python
- To view the file in the webshell, do: `$ nano fixme1.py`
- To exit `nano`, press Ctrl and x and follow the on-screen prompts.
- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
Hay  que abrir el script y corregir las últimas líneas, en específico, la línea que imprime la bandera:
```
MarCode-picoctf@webshell:~/fixme$ nano fixme1.py 
MarCode-picoctf@webshell:~/fixme$ python3 fixme1.py 
  File "/home/MarCode-picoctf/fixme/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
MarCode-picoctf@webshell:~/fixme$ nano fixme1.py 
MarCode-picoctf@webshell:~/fixme$ python3 fixme1.py 
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_09ee727a}
MarCode-picoctf@webshell:~/fixme$ 
```

`picoCTF{1nd3nt1ty_cr1515_09ee727a}`