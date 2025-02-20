Find the flag in the Python script! [Download Python script](https://artifacts.picoctf.net/c/35/serpentine.py)

Hints:
- Try running the script and see what happens
- In the webshell, try examining the script with a text editor like `nano`
- To exit `nano`, press Ctrl and x and follow the on-screen prompts.
- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución

Hay que entrar al script `serpentine.py` y buscar el ciclo que itera para el menú interactivo. Hay que reemplazar el print en la opción b por la llamada a la función `print_flag`

`picoCTF{7h3_r04d_l355_7r4v3l3d_ae0b80bd}`