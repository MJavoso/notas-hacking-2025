Do you know how to use the web inspector?

Additional details will be available after launching your challenge instance.

Hints:
- Use the web inspector on other files included by the web page.
- The flag may or may not be encoded

## Solución
La flag se encuentra en la sección de About. Está en un elemento HTML con el modificador `notify_true`. Hay que decodificarla de Base64.

`picoCTF{web_succ3ssfully_d3c0ded_07b91c79}`