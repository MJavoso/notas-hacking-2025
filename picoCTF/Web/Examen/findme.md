Help us test the form by submiting the username as `test` and password as `test!`

Additional details will be available after launching your challenge instance.

Hints:
- any redirections?

## Solución
Hay que ingresar al sitio web con el usuario `test` y la contraseña `test!`.

Antes de hacerlo hay que abrir la pestaña de network en la consola de desarrollador. Hay una redirección, y hay que buscar la cabecera `Referer`, donde habrá un link apuntando a `next-page/id=`. El texto del id hay que copiarlo y desencriptarlo de base64. Sin embargo, la bandera está incompleta. Hay que repetir el proceso las veces que sean necesarias hasta completar la bandera.

`picoCTF{proxies_all_the_way_a0fe074f}`