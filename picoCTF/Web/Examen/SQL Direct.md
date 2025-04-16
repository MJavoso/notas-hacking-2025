Connect to this PostgreSQL server and find the flag!

Additional details will be available after launching your challenge instance.

Hints:
- What does a SQL database contain?

## Solución
Al conectarse a la base de datos, se puede usar el comando `\dt` para mostrar todas las tablas que contiene la base de datos. Nótese que hay que estar en la base de datos `pico`. Si no, se pueden listar todas las bases de datos con el comando `\list` y cambiar a la base de datos `pico`.

Hay que seleccionar los datos de la tabla `flags` con el comando:
`SELECT * FROM flags;`

`picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}`