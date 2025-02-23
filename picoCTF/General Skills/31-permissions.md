Can you read files in the root file?

Additional details will be available after launching your challenge instance.

The system admin has provisioned an account for you on the main server:`ssh -p 50955 picoplayer@saturn.picoctf.net`Password: `UYiOazkqY2`Can you login and read the root file?

Hints:
- What permissions do you have?
## Solución

Primero hay que ejecutar el comando `sudo -l` para obtener los permisos del usuario actual. Ahí te provee información de que puedes ejecutar vi, editor de texto. Al ejecutarlo como sudo, se debe escribir dentro de  vi el comando `:!/bin/bash` para acceder al root.

> [!WARNING]
> No se puede acceder a la carpeta de root usando `sudo ls` `sudo su` ni ningún otro comando. Debe ser a través de vi.

Al acceder al root, se debe de cambiar a la carpeta `/root` y ejecutar `cat .flag.txt`.

> [!NOTE]
> El archivo está oculto, se debe usar `ls -la`

`picoCTF{uS1ng_v1m_3dit0r_89e9cf1a}`