Decode this [message](https://jupiter.challenges.picoctf.org/static/fc1edf07742e98a480c6aff7d2546107/message.wav) from the moon.

Hints:
- How did pictures from the moon landing get sent back to Earth?
- What is the CMU mascot?, that might help select a RX option

## Solución
El mensaje es un archivo de audio. No se encontrará la flag en ese formato. Hay que convertir a una imagen, ya que así se enviaron las fotos de la luna a la tierra. La herramienta a usar para convertir de audio a imagen es `sstv decoder`. Se tiene que descargar desde el [repositiorio](https://github.com/colaclanth/sstv) e instalar con: `python setup.py install`.
Se transforma el audio con:
`sstv -d ../message.wav -o resultado.png`

`picoCTF{beep_boop_im_in_space}`