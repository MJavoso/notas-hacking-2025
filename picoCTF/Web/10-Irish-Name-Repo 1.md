There is a website running at `https://jupiter.challenges.picoctf.org/problem/33850/` ([link](https://jupiter.challenges.picoctf.org/problem/33850/)) or http://jupiter.challenges.picoctf.org:33850. Do you think you can log us in? Try to see if you can login!

Hints:
- There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?
- Try to think about how the website verifies your login.

## Solución
Hay que escribir `' OR 1=1;--` ya que no hace un filtrado de texto.

`picoCTF{s0m3_SQL_f8adf3fb}`