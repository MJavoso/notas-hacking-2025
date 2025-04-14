The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee?Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz).

Hints:
- [Referencia](https://doc.rust-lang.org/book/ch04-02-references-and-borrowing.html)

## Solución
El problema está en que no se pueden modificar referencias por defecto en Rust.
Para hacerlo, hay que crear referencias mutables.
En la función:
`fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &String){`
Hay que agregar la palabra reservada `mut` al lado del &, que le permite ser modificable. De tal manera que quede así:
`fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mut String){`

Y al llamar a la función:
`decrypt(encrypted_buffer, &party_foul);`
También hay que agregar `mut`. Por lo tanto, queda así:
`decrypt(encrypted_buffer, &mut party_foul);`

`picoCTF{4r3_y0u_h4v1n5_fun_y31?}`