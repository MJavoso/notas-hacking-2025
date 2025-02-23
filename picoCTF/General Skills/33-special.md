Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)Start your instance to see connection details.

Additional details will be available after launching your challenge instance.

`ssh -p 63220 ctf-player@saturn.picoctf.net`The password is `af86add3`

Hints:
- Experiment with different shell syntax

## Solución
Lo que hay que hacer es escribir `${parameter=comando}` debido a que la línea de comandos está en python. Primero hay que hacer un ls, luego ejecutar `cat < ruta/flag.txt`.

`picoCTF{5p311ch3ck_15_7h3_w0r57_6a2763f6}`