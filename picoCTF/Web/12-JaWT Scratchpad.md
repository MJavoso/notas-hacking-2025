Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/58210/` or http://jupiter.challenges.picoctf.org:58210

Hints:
- What is that cookie?
- Have you heard of JWT?

## Solución
Hay que obtener el token jwt de las cookies, y mandarlo a un decodificador de jwt. Cambiar el atributo `user` del payload por `admin`, y con la herramienta `john`, buscar la contraseña que devuelve un positivo, indicando que la contraseña realiza la misma firma.

`picoCTF{jawt_was_just_what_you_thought_44c752f5}`