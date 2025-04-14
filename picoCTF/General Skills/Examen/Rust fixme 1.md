Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz).

Hints:
- Cargo is Rust's package manager and will make your life easier. See the getting started page [here](https://doc.rust-lang.org/book/ch01-03-hello-cargo.html)
- [println!](https://doc.rust-lang.org/std/macro.println.html)
- Rust has some pretty great compiler error messages. Read them maybe?

## Solución
Todos los problemas están en la función main.
1. En la declaración de la variable `key`, se debe terminar con ;
2. En la línea `if res.is_err()`, está escrito `ret;`, pero debe ser `return;`
3. Para imprimir una variable con `println!`, debe ser `"{}, variable"`

Una vez realizado los cambios, hay que ejecutar el comando `cargo build`. El ejecutable estára en la carpeta `target/debug` y el archivo se llama `rust_proj`

`picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}`