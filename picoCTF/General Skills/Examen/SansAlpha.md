The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols.

Additional details will be available after launching your challenge instance.

Hints:
- Where can you get some letters?

## Solución
La shell solo reconoce símbolos y números. No permite letras ni el carácter '\\'.
Hay que usar los wildcards de linux. Primero se intento `./*`, y se obtuvo que hay una carpeta `blargh`. Luego se intentó `./*/*`, y se encontró el archivo `flag.txt`.
Aplicando el símbolo '?' con el payload inicial `/????`, descubrimos el nombre del usuario actual `ctf-player`, y por lo tanto, la ruta absoluta de la bandera es `/home/ctf-player/blargh/flag.txt`.

Ahora el problema es leer el archivo.
Al intentar usar el comando `cat` ubicado en `/bin/cat`, no se puede, ya que hay varios comandos con tres letras.
Se debe de usar el comando `/bin/base64` para obtener la bandera, el posible payload sería `/???/??????`, pero hay otro comando que causa conflicto, ya que existe `base58` y `base32`.
Por lo tanto, otra alternativa sería `/???/????64`, pero hay otro comando que existe llamado `x86_64`. Finalmente, se llegó a la conclusión de que hay que aplicar una exclusión del símbolo '\_' para que agarre el comando deseado, siendo el payload final `/???/???[!_]64`, y el comando final quedaría así: `/???/???[!_]64 /????/??????????/??????/????????`. El segundo argumento representa la ruta de la bandera, pero como no se puede usar letras, hay que usar wildcards.

El comando regresará un  texto en base64, y hay que decodificarlo con CyberChef.

> [!NOTE]
> Si el comando no regresa un texto de una sola línea, hay que aplicar varias veces el comando.

`picoCTF{7h15_mu171v3r53_15_m4dn355_36a674c0}`