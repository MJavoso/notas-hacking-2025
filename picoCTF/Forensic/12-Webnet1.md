We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

Hints:
- Try using a tool like Wireshark.
- How can you decrypt the TLS stream?

## Solución
Hay que usar `wireshark` para abrir el archivo de paquetes. Hay que obtener el paquete 91 ya que se descarga una imagen. En Archivo > Exportar objetos, hay que exportar el http. Al guardar la imagen, hay que hacer `strings imagen | grep picoCTF`.

`picoCTF{honey.roasted.peanuts}`