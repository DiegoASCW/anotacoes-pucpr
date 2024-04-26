Todo código em assembling têm extensão .asm ou .s . No caso do HTB será usado **.s**.

Para podermos compilar um código em assembling, usamos a ferramenta ***nasm***, e a partir dela precisamos criar um objeto:

```bash
nasm -f elf64 nomeDoArquivo.s
```

Agora temos um arquivo .o . No entanto, precisamos converter para um executável, e em linux usamos o seguinte comando para poder criar um Executable and Linkable Format:
```bash
ld -o helloWorld helloWorld.o
```

E por fim podemos executar o arquivo gerado.

Ou você pode usar esse script aqui ó:
```bash
#!/bin/bash

fileName="${1%%.*}" # remove .s extension

nasm -f elf64 ${fileName}".s"
ld ${fileName}".o" -o ${fileName}
[ "$2" == "-g" ] && gdb -q ${fileName} || ./${fileName}
```


Para reverter o processo temos de usar:
```bash
objdump -M intel -d nomeDoArquivo
```
E caso não queiramos ver a linguagem de máquina, somente o código, usamos com esses argumentos:
```bash
objdump -M intel --no-show-raw-insn --no-addresses -d helloWorld
```

Para obter somente string presentes no código:
```bash
objdump -sj .data nomeDoArquivo
```

