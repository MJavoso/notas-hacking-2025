We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.

Hints:
- Try using a tool like Wireshark.
- How can you decrypt the TLS stream?

## Solución
Hay que usar `wireshark` para abrir el archivo de paquetes. Abrir el menú Edición > Preferencias > Protocolo y buscar TLS. En el menú de RSA agregar la key descargada. Aplicar y con eso se obtiene. La bandera está en el paquete 32. Con `Ctrl + F` se puede buscar la cadena 'picoCTF'.

`picoCTF{nongshim.shrimp.crackers}`