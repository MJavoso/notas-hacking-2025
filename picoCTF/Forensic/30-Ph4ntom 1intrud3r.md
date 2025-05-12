A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag.

To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder!

Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.picoctf.net/c_verbal_sleep/b6fbb3a5560749f838cdc6db4950985767c4691db3a7b34a220e5654ee39e700/myNetworkTraffic.pcap) and try to get the flag.

Hints:
- Filter your packets to narrow down your search.
- Attacks were done in timely manner.
- Time is essential

## Solución
Hay que abrir el archivo con wireshark. Después, hay que analizar los paquetes que tengan un tamaño de 12 o 4. Sin embargo, debido a que el ataque fue realizado en base al tiempo, hay que organizar cada paquete conforme al tiempo, desde el más negativo hasta el más positivo.

`picoCTF{1t_w4snt_th4t_34sy_tbh_4r_36f4a666}`