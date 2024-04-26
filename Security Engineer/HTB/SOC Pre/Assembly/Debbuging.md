Em uma linguagem de alto nível, usamos break points durante um código para poder saber seu estado naquele momento. A nível de binário, usamos o mesmo, mas decretando uma pausa diretamente na memória.
Mas para poder fazer isso, usaremos uma ferramenta muito popular, dentre diversas, que é o **GNU Debugger** ou **GDB**, juntamente com uma ferramenta muito poderosa para engenharia reversa e exploração de binário, que é a **GNU Enhaced Features** ou **GEF**.

---
### Invoke
Podemos chamar a ferramenta por meio de:
```
gdb -q ./helloWorld
# ou no script
./script nomeDoBinário -g
```

Mas por meio dele podemos ser muito precisos com relação ao que procuramos, e como, por meio de comandos como o **info**:
```gdb
help info
info functions
info variables
```

Ou até mesmo realizar o disassembling de um programa, por meio de:
```gdb
disas _start
```

---
### Breakpoints
Para podermos criar breakpoints em nosso programa, usamos o seguinte comando:
```gdb
break  # or b
```

Note-se que podemos passar o endereço relativo de memória (0x401000) , ou sua linha de execução (\*\_start+10).
