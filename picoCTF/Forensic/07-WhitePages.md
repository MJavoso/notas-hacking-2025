I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitepages.txt) is all blank!

Hints: no hay

## Solución
El archivo contiene caracteres que no tienen una representación en caracteres normales, pero están ahí. Si se usa una herramienta como `xxd`, se podrá ver que existen.
Hay que instalar (o usar) el módulo `pwn` de python, y hacer el siguiente script:
```
from pwn import *
 
file = open('whitepages.txt', 'rb')
data = bytearray(file.read())
data = data.replace(b'\xe2\x80\x83', b'0')
data = data.replace(b'\x20', b'1')

data = data.decode('ascii')
data = unbits(data)

print(data)
```

`picoCTF{not_all_spaces_are_created_equal_c54f27cd05c2189f8147cc6f5deb2e56}`