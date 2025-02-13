There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 35652`, but it doesn't speak English...

Hints:
1. You can practice using netcat with this picoGym problem: [what's a netcat?](https://play.picoctf.org/practice/challenge/34)
2. You can practice reading and writing ASCII with this picoGym problem: [Let's Warm Up](https://play.picoctf.org/practice/challenge/22)

## Solucion 1
- Primero ejecutar el comando:
```
MarCode-picoctf@webshell:~$ nc mercury.picoctf.net 35652 > ascii
^C
```

- Luego, irse al cyberchef
```

Cyberchef:
Input:
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
57 
98 
51 
98 
55 
51 
57 
50 
125 
10
Recipe: From Decimal
Output: picoCTF{g00d_k1tty!_n1c3_k1tty!_9b3b7392}
```

## Solucion 2
Python:
- Primero obtener los códigos del servidor

```
MarCode-picoctf@webshell:~$ cat ascii | tr '\n' ','
112 ,105 ,99 ,111 ,67 ,84 ,70 ,123 ,103 ,48 ,48 ,100 ,95 ,107 ,49 ,116 ,116 ,121 ,33 ,95 ,110 ,49 ,99 ,51 ,95 ,107 ,49 ,116 ,116 ,121 ,33 ,95 ,57 ,98 ,51 ,98 ,55 ,51 ,57 ,50 ,125 ,10 ,MarCode-picoctf@webshell:~$ python
Python 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> codigos = "112 ,105 ,99 ,111 ,67 ,84 ,70 ,123 ,103 ,48 ,48 ,100 ,95 ,107 ,49 ,116 ,116 ,121 ,33 ,95 ,110 ,49 ,99 ,51 ,95 ,107 ,49 ,116 ,116 ,121 ,33 ,95 ,57 ,98 ,51 ,98 ,55 ,51 ,57 ,50 ,125".replace(" ", "")
>>> numeros = [
... int(codigo) for codigo in codigos.split(",")]
>>> codigos
'112,105,99,111,67,84,70,123,103,48,48,100,95,107,49,116,116,121,33,95,110,49,99,51,95,107,49,116,116,121,33,95,57,98,51,98,55,51,57,50,125'
>>> numeros
[112, 105, 99, 111, 67, 84, 70, 123, 103, 48, 48, 100, 95, 107, 49, 116, 116, 121, 33, 95, 110, 49, 99, 51, 95, 107, 49, 116, 116, 121, 33, 95, 57, 98, 51, 98, 55, 51, 57, 50, 125]
>>> flag = ''
>>> for numero in numeros:
...     flag += chr(numero)
... 
>>> flag
'picoCTF{g00d_k1tty!_n1c3_k1tty!_9b3b7392}'
>>>
```