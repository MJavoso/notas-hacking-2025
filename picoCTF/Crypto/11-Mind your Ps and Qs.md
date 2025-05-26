In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/2604f8b51a5cc62d38a3736938f19cef/values)

Hints:
- Bits are expensive, I used only a little bit over 100 to save money

## Solución
Se nos proporciona n, e y c.

Debido a que n es muy pequeño, se le puede buscar sus factores. En páginas como [factordb](https://factordb.com) se pueden calcular. Los dos números que salgan, son p y q. Teniendo estos números, se debe calcular tn así: `tn = (p - 1) * (q - 1)`. Después, se calcula d con: `d = pow(e, -1, tn)`, y finalmente el mensaje se obtiene con: `m = pow(c, d, n)`.

Para imprimirlo, se usa:
`bytes.fromhex(hex(m)[2:])`

`picoCTF{sma11_N_n0_g0od_13686679}`