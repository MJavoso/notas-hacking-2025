Can you abuse the banner?

Additional details will be available after launching your challenge instance.

Hints:
- Do you know about symlinks?
- Maybe some small password cracking or guessing

## Solución
El reto provee 2 links. Hay que conectarse a ellos a través de netcat. El primero provee la contraseña para entrar al segundo link.

En el segundo link, hay que ingresar la contraseña, y además hay que responder 2 preguntas:
```
What is the top cyber security conference in the world?
DEF CON
the first hacker ever was known for phreaking(making free phone calls), who was it?
john draper
```

Al responderlas, se obtendrá acceso al servidor. La bandera está en `/root/flag.txt`, sin embargo, no se puede leer.

Lo que hay que hacer es crear un link simbólico al archivo con la bandera:
`ln -s link /root/flag.txt`
Y en el directorio principal del usuario, hay que eliminar el archivo `banner` por defecto, y reemplazarlo por el link que se acaba de crear:
```
rm banner
mv link banner
```

Hay que desconectarse y volverse a conectar con netcat.

`picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_8126c9b0}`