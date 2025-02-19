Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `481e7b14`

Additional details will be available after launching your challenge instance.

`ssh ctf-player@venus.picoctf.net -p 53030`
Hints:
- Finding a cheatsheet for bash would be really helpful!

## Solución
Es una flag compuesta, no se encuentra en un solo archivo
```
MarCode-picoctf@webshell:~$ ssh ctf-player@venus.picoctf.net -p 53030
ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt
ctf-player@pico-chall$ less instructions-to-2of3.txt 
-bash: less: command not found
ctf-player@pico-chall$ nano instructions-to-2of3.txt 
-bash: nano: command not found
ctf-player@pico-chall$ cat instructions-to-2of3.txt 
Next, go to the root of all things, more succinctly `/`
ctf-player@pico-chall$ cat 1of3.flag.txt 
picoCTF{xxsh_
ctf-player@pico-chall$ cd /
ctf-player@pico-chall$ ls
2of3.flag.txt  bin  boot  dev  etc  home  instructions-to-3of3.txt  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
ctf-player@pico-chall$ cat 2of3.flag.txt 
0ut_0f_\/\/4t3r_
ctf-player@pico-chall$ cat instructions-to-3of3.txt 
Lastly, ctf-player, go home... more succinctly `~`
ctf-player@pico-chall$ cd ~
ctf-player@pico-chall$ ls
3of3.flag.txt  drop-in
ctf-player@pico-chall$ cat 3of3.flag.txt 
1118a9a4}
```
`picoCTF{xxsh_0ut_0f_\/\/4t3r_1118a9a4}`
