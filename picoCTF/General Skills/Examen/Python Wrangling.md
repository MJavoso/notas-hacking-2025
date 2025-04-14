Python scripts are invoked kind of like programs in the Terminal... Can you run [this Python script](https://mercury.picoctf.net/static/0bf545252b5120845e3b568b9ad0277e/ende.py) using [this password](https://mercury.picoctf.net/static/0bf545252b5120845e3b568b9ad0277e/pw.txt) to get [the flag](https://mercury.picoctf.net/static/0bf545252b5120845e3b568b9ad0277e/flag.txt.en)?

Hints:
- Get the Python script accessible in your shell by entering the following command in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/0bf545252b5120845e3b568b9ad0277e/ende.py`
- `$ man python
## Solución
Hay que descargar los 3 archivos de las url de la descripción del reto. Luego, hay que copiar la contraseña del archivo `pw.txt`. Y para ejecutar el script se hace de la siguiente manera:
`python ende.py -d flag.txt.en`
Cuando solicite la contraseña, pegas la contraseña del archivo antes mencionado.

`picoCTF{4p0110_1n_7h3_h0us3_6008014f}`