I made a cool website where you can announce whatever you want! Try it out!

Additional details will be available after launching your challenge instance.

Hints:
- Server Side Template Injection

## Solución
En el input, se probó el payload {{ 7\*7 }} y devolvió 49, por lo tanto, es vulnerable a la inyección de código de templates, como el que se usa en Flask o Django.

Con este payload: 
`{{self._TemplateReference__context.cycler.__init__.__globals__.os.popen('id').read() }}`

Se pueden ejecutar comandos.
Primero se ejecutó `ls /root` para averiguar si se puede acceder, pero no se pudo. Luego, se intentó `sudo -l`, pero tampoco se obtuvo nada. Después se ejecutó `pwd` para averiguar en que carpeta se encontraba por defecto, y devolvió `/challenge`. Con esto, se ejecutó `ls` y se descubrió el archivo `flag`, y finalmente con el comando `cat flag` se obtuvo la bandera.

`picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_bd4cfc64}`