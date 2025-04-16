# Nombre original: Java Code Analysis!?!
BookShelf Pico, my premium online book-reading service.I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!

Additional details will be available after launching your challenge instance.

Hints:
- Maybe try to find the JWT Signing Key ("secret key") in the source code? Maybe it's hardcoded somewhere? Or maybe try to crack it?
- The 'role' and 'userId' fields in the JWT can be of interest to you!
- The 'controllers', 'services' and 'security' java packages in the given source code might need your attention. We've provided a README.md file that contains some documentation.
- Upgrade your 'role' with the _new_ (cracked) JWT. And re-login for the new role to get reflected in browser's localStorage.

## Solución
Primero hay que descargar el código para analizar el servidor completo. Los paquetes que importan son los de `configs`, `services`, `security` y `controllers`.

Las clases que importan en el paquete de `security` es la de `JwtService`. Ahí se observa que se obtiene la clave secreta de una clase llamada `SecretGenerator`, la cual se encuentra en el mismo paquete. En esa clase se descubre que la clave secreta es el valor literal '1234'.

Con esto, se puede obtener el token JWT que está guardado en el LocalStorage del navegador. Para acceder a el, es desde la consola de desarrollador en la pestaña `Application`. Se copia el token y hay que buscar una [herramienta](https://jwt.io) para ver el contenido del token.

La clave del json que realmente importa es la de `role`, ya que por defecto tiene el valor de `Free`, y para poder acceder al sistema, tiene que tener el valor de `Admin`. Se hizo un script en python para crear un nuevo token:
```
import jwt
from jwt.jwk import OctetJWK

# Clave secreta para firmar el token
SECRET_KEY = OctetJWK(key=b"1234")

def generar_jwt(datos):
    """
    Genera un token JWT a partir de un diccionario.

    :param datos: Diccionario con los datos a incluir en el token.
    :return: Token JWT como cadena.
    """
    global SECRET_KEY
    # Generar el token
    token = jwt.JWT().encode(datos, SECRET_KEY, alg="HS256")
    return token

if __name__ == "__main__":
    datos = {"role": "Admin", "iss": "bookshelf", "exp": 1745362755, "iat": 1744757955, "userId": 6, "email": "ctfplayer@gmail.com"}
    token = generar_jwt(datos)
    print("Token JWT generado:", token)
```

Con el token generado, hay que pegarlo en el lugar del token original en el LocalStorage. Además, hay que reemplazar también la clave `role` en el json de `json_payload`, si no no funcionará. Con esto, al refrescar la página y darle click a la foto de perfil se debería desbloquear una opción llamada 'Admin Dashboard'. Al entrar, se verán los libros disponibles y los usuarios. Si se intenta cambiar el rol del usuario propio no funcionará. Sin embargo, se le puede cambiar el rol al usuario `user`. Si se inspecciona el paquete `configs`, se encontrará la clase `UserDataPaths.java`, la cual es mencionada en el README del reto, ya que se crean 2 usuarios por defecto con sus respectivos permisos. Hay que checar la contraseña, la cual es `user`. Una vez asignado el rol 'Admin' al usuario 'user', hay que cerrar sesión y volver a ingresar con el usuario administrador. Finalmente hay que darle click al libro `Flag`.

`picoCTF{w34k_jwt_n0t_g00d_d7c2e335}`