Additional details will be available after launching your challenge instance.

Hints:
- Try using burpsuite to intercept request to capture the flag.
- Try mangling the request, maybe their server-side code doesn't handle malformed requests very well.

## Solución
Hay que usar burpsuite para interceptar las peticiones. Hay que registrarse normalmente, pero cuando se llega a la sección de OTP, hay que cambiar el contenido de la petición. En este ejercicio, se reemplazó la clave `otp` por `potp` y funcionó.

`picoCTF{#0TP_Bypvss_SuCc3$S_9090d63c}`