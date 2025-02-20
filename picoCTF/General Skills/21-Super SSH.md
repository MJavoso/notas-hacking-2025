Using a Secure Shell (SSH) is going to be pretty important.

Additional details will be available after launching your challenge instance.

Details:
Can you `ssh` as `ctf-player` to `titan.picoctf.net` at port `50642` to get the flag?You'll also need the password `6dd28e9b`. If asked, accept the fingerprint with `yes`.If your device doesn't have a shell, you can use: [https://webshell.picoctf.org](https://webshell.picoctf.org/)If you're not sure what a shell is, check out our Primer: [https://primer.picoctf.com/#_the_shell](https://primer.picoctf.com/#_the_shell)

Hints:
- [https://linux.die.net/man/1/ssh](https://linux.die.net/man/1/ssh)
- You can try logging in 'as' someone with `<user>`@titan.picoctf.net
- How could you specify the port?
- Remember, passwords are hidden when typed into the shell

## Solución

```
MarCode-picoctf@webshell:~$ ssh ctf-player@titan.picoctf.net -p 50642
The authenticity of host '[titan.picoctf.net]:50642 ([3.139.174.234]:50642)' can't be established.
ED25519 key fingerprint is SHA256:4S9EbTSSRZm32I+cdM5TyzthpQryv5kudRP9PIKT7XQ.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[titan.picoctf.net]:50642' (ED25519) to the list of known hosts.
ctf-player@titan.picoctf.net's password: Ingresar contraseña proporcionada en el reto
Welcome ctf-player, here's your flag: picoCTF{s3cur3_c0nn3ct10n_5d09a462}
Connection to titan.picoctf.net closed.

picoCTF{s3cur3_c0nn3ct10n_5d09a462}
```