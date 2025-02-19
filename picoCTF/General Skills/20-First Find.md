Unzip this archive and find the file named 'uber-secret.txt'

- [Download zip file](https://artifacts.picoctf.net/c/500/files.zip)

Hints: no hay

## Solución
```
MarCode-picoctf@webshell:~/comprimido$ find . -name uber-secret.txt
./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
MarCode-picoctf@webshell:~/comprimido$ cat $_
cat: uber-secret.txt: No such file or directory
MarCode-picoctf@webshell:~/comprimido$ cd files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/
MarCode-picoctf@webshell:~/comprimido/files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets$ cat uber-secret.txt 
picoCTF{f1nd_15_f457_ab443fd1}
MarCode-picoctf@webshell:~/comprimido/files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets$ 
```
`picoCTF{f1nd_15_f457_ab443fd1}`