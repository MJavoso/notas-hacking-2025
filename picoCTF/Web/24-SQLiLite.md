Can you login to this website?

Additional details will be available after launching your challenge instance.

Hints:
- `admin` is the user you want to login as.

## Solución
Hay que hacer una inyección SQL. El payload que funcionó fue este:
`' OR 1=1;--`. Luego, hay que inspeccionar el HTML porque la bandera está escondida.

`picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}`