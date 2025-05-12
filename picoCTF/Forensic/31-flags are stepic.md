A group of underground hackers might be using this legit site to communicate. Use your forensic techniques to uncover their message

Additional details will be available after launching your challenge instance.

Hints:
- In the country that doesn't exist, the flag persists

## Solución
En el sitio web que se arranca con el reto hay varias banderas. Entre todas, hay una rara que tiene una imágen que no pareciese un país, llamado 'Upanzi, Republic The'. Hay que inspeccionar este elemento para obtener su url y descargarlo.

Con la herramienta `stepic`, se pueden obtener datos de la imagen. Usando `stepic -d -i imagen` se obtiene la bandera. 

`picoCTF{fl4g_h45_fl4g6f5548ea}`