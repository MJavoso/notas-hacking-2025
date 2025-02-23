My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/70/challenge.zip)

Hints:
- `git branch -a` will let you see available branches
- How can file 'diffs' be brought to the main branch? Don't forget to `git config`!
- Merge conflicts can be tricky! Try a text editor like nano, emacs, or vim.

## Solución
Hay que hacer un `git merge feature/part-x` e ir resolviendo los conflictos de merge con un editor de texto. Al juntar las tres partes, ejecutar `python3 flag.py`

`picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_7ffa0077}`