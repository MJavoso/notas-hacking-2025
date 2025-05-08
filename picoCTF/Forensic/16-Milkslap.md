[🥛](http://mercury.picoctf.net:29522/)

Hints:
- Look at the problem category

## Solución
Al abrir el link, nos muestra una imagen, pero no se podrá encontrar en el html. Lo que se puede hacer es entrar en la psetaña de Network, y buscar el png. Luego, copiar el url de donde se obtuvo y descargar.

Con la herramienta `zsteg`, se puede analizar imágenes en busca de datos. Al ejecutar `zsteg -a imagen.png`, nos saldrá el siguiente error:
```
/var/lib/gems/3.1.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:303:in `upto': stack level too deep (SystemStackError)
        from /var/lib/gems/3.1.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:303:in `decoded_bytes'
        from /var/lib/gems/3.1.0/gems/zpng-0.4.5/lib/zpng/scan_line/mixins.rb:17:in `prev_scanline_byte'
        from /var/lib/gems/3.1.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:377:in `prev_scanline_byte'
        from /var/lib/gems/3.1.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
        from /var/lib/gems/3.1.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:318:in `upto'
        from /var/lib/gems/3.1.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:318:in `decoded_bytes'
        from /var/lib/gems/3.1.0/gems/zpng-0.4.5/lib/zpng/scan_line/mixins.rb:17:in `prev_scanline_byte'
        from /var/lib/gems/3.1.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:377:in `prev_scanline_byte'
         ... 9483 levels...
        from /var/lib/gems/3.1.0/gems/zsteg-0.2.13/lib/zsteg.rb:26:in `run'
        from /var/lib/gems/3.1.0/gems/zsteg-0.2.13/bin/zsteg:8:in `<top (required)>'
        from /usr/local/bin/zsteg:25:in `load'
        from /usr/local/bin/zsteg:25:in `<main>'
```

Con el comando `export RUBY_THREAD_VM_STACK_SIZE=500000000`, se puede expandir el stack del programa. Con esto, se obtiene la bandera.

`picoCTF{imag3_m4n1pul4t10n_sl4p5}`