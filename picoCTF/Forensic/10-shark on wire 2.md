We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

Hints: no hay

## Solución
Hay que usar la herramienta wireshark para analizar el archivo. `wireshark archivo`.
Hay que seguir los paquetes UDP dandoles click derecho y dar en la opción "Seguir/Follow". Sin embargo, la bandera está incompleta. En el paquete 32, el texto dice "start", y en el "60", end.  Por lo tanto, la bandera puede estar en ese rango. Además, este rango de paquetes usa el puerto 22.

La bandera se obtiene haciendo un filtrado de los paquetes que sean UDP y que usen el puerto 22. Hay que restarle 5000 al caracter del paquete para obtener un fragmento de la bandera. Se puede hacer mediante el siguiente script:

```
from scapy.all import *
 
 packages = rdpcap('capture.pcap')
 
 flag=""
 for p in packages:
     if UDP in p and p[UDP].dport == 22:
         if p[UDP].sport > 5000:
             flag += chr(p[UDP].sport - 5000)
 
 print(flag)
```

Y esto es lo que imprime:
`picoCTF{p1LLf3r3d_data_v1a_st3g0}`