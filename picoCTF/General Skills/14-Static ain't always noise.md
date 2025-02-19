Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/static)? This [BASH script](https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/ltdis.sh) might help!

Hints: no hay

## Solución
Obtener los archivos con wget
```
MarCode-picoctf@webshell:~/noise$ chmod 744 ltdis.sh 
MarCode-picoctf@webshell:~/noise$ ./ltdis.sh 
Attempting disassembly of  ...
objdump: 'a.out': No such file
objdump: section '.text' mentioned in a -j option, but not found in any input file
Disassembly failed!
Usage: ltdis.sh <program-file>
Bye!
MarCode-picoctf@webshell:~/noise$ ./ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
MarCode-picoctf@webshell:~/noise$ ls
ltdis.sh  static  static.ltdis.strings.txt  static.ltdis.x86_64.txt
MarCode-picoctf@webshell:~/noise$ nano static.ltdis.strings.txt 
MarCode-picoctf@webshell:~/noise$ cat static.ltdis.strings.txt | grep pico
   1020 picoCTF{d15a5m_t34s3r_1e6a7731}
MarCode-picoctf@webshell:~/noise$ 
```
`picoCTF{d15a5m_t34s3r_1e6a7731}`