Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:45028/](http://mercury.picoctf.net:45028/)

Hints:
- Maybe you have more than 2 choices
- Check out tools like Burpsuite to modify your requests and look at the responses

## Solución
Hay que interceptar la petición y usar el método HEAD en lugar del GET o POST.

`picoCTF{r3j3ct_th3_du4l1ty_775f2530}`