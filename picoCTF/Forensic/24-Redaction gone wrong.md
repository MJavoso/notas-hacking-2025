Now you DON’T see me.This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?

Hints:
- How can you be sure of the redaction?

## Solución
Algunas partes son rectángulos en negro. El documento fue hecho en microsoft word. Lo que pasa en realidad es que solo pusieron el fondo de los rectángulos en negro, al igual que el texto. Si se selecciona con el mouse, se puede ver lo que esconde. De no ser así, se puede copiar y pegar en un editor de texto plano.

`picoCTF{C4n_Y0u_S33_m3_fully}`