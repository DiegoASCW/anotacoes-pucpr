Todo código em Assembly têm a seguinte estrutura: Diretiva, .data, .text .

- Diretiva: são comandos da linguagem assembly, que facilitam o manejo do programa, mas que não fazem parte da ISA. Por exemplo, é o caso do "\_start" que define que o programa deve processar todas as informações a partir da chamada desse comando, ou seja, o programa roda a partir dele.
- .data: pedaço do código onde as variáveis são definidas. Uma variável pode ser definida da seguinte maneira:
``` assembly
db # bytes list
dw # word list
dd # digit list

db 0x0a #new line
message db 0x41, 0x42, 0x43, 0x0a #abc
message db "Hello World!", 0x0a #Hello World
```

- .text: seção mais importante de um código, dado que aqui que é de fato escrito um código. Por convenção se chama a diretiva "\_start" no início do bloco.

### Você percebeu?
A existência de um trecho de código só para declarar varíaveis (read/write), e outro só para código (read only), é necessário para mitigar ataques como buffer overflow e binary exploitation.
Temos então que todo espaço de memória é devidamente alocado para as variáveis, assim que ".text" é chamado.

### Na prática
Vamos aplicar o que sabemos em um código que apenas retorna "Hello World":
```assembly
	global _start ;diretiva

	section .data ;declamos variáveis
message db "Hello world"

	section .text ;código de fato
_start:
	
		mov     rax, 1
        mov     rdi, 1
        mov     rsi, message
        mov     rdx, 18
        syscall

        mov     rax, 60
        mov     rdi, 0
        syscall
```

