Fix the syntax error in the Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/5/fixme2.py)

Hints:
- Are equality and assignment the same symbol?
- To view the file in the webshell, do: `$ nano fixme1.py`
- To exit `nano`, press Ctrl and x and follow the on-screen prompts.
- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
El error está en que al verificar si el string está vacío, está usando un igual (=), que sirve para asignar, en vez de usar 2 iguales (\==) que sirve para comparar.

```
MarCode-picoctf@webshell:~/fixme$ nano fixme2.py 
MarCode-picoctf@webshell:~/fixme$ python3 fixme2.py 
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}
MarCode-picoctf@webshell:~/fixme$ 

picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}
```