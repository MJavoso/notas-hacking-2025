We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

Hints:
- Try using a tool like Wireshark
- What are streams?

## Solución
Hay que usar la herramienta Wireshark y escribir el comando `wireshark archivo` para abrirlo. Darle click derecho a cualquier paquete UDP y darle al menú "Seguir/Follow", usar el menú UDP  Streams. Buscar en los primeros 10 paquetes.

`picoCTF{StaT31355_636f6e6e}`