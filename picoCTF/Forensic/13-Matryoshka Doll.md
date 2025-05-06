Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/5ef2e9103d55972d975437f68175b9ab/dolls.jpg)

Hints:
- Wait, you can hide files inside files? But how do you find them?
- Make sure to submit the flag as picoCTF{XXXXX}

## Solución
A la imagen descargada se le aplica un `binwalk imagen`. Con eso se obtiene que la imagen en realidad es un zip. Hay que hacer un `unzip imagen` hasta obtener el archivo 'flag.txt'.

`picoCTF{e3f378fe6c1ea7f6bc5ac2c3d6801c1f}`