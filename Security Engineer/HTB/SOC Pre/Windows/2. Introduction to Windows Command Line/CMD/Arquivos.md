Para ler arquivos, temos 2 formas mais conhecidas, sendo elas: ***more***, e ***type***.


### type
Podemos também redirecionar a saída do programa com: ***type  arquivo.txt>> nomeDoArquivo***

### fsutils
O comando ***fsutils*** é muito útil, e uma de suas atribuições é criar arquivo:
``` cmd
fsutil file c reateNew for-sure.txt 222
```

### Ren(ame)
Para renomear um arquivo, podemos utilizar o comando:
```cmd
ren arquivoAntes.txt arquivoDepois.txt
```

---

## I/O

Por mais que até então só utilizamos Input/Output, precisamos falar dos operadores de inserção, sendo eles: ***>  >>  <  |  &&***

- > substitui todo o conteúdo de um arquivo;
- >> agrega ao final do arquivo um conteúdo;
-  < utiliza de entrada o conteúdo de um arquivo, para um comando;
- | a saída do comando anterior servirá como entrada do próximo;
- & executa um comando a seguir, após a conclusão do atual.

#### Mas como encontrar algo específico dentro de um arquivo ou saída?
Em linux temos diversas opções de filtro e captura. Enquanto lá temos o "grep", aqui temos o "***find***".

Por exemplo, para encontrar só número com 4, em um ping:
```cmd
ping 8.8.8.8 | find /i "4"
```
(confira seu manual, é curto eu juro)

### Eu esqueci de uma coisa
E se eu precisar que o comando anterior seja bem sucedido para que o próximo de certo? Podemos usar o operador ***&&*** .
Caso contrário, caso esperamos que ele dê errado: ***||*** .

---

## Deletar
Para deletar arquivos é tão fácil quanto, basta usar:
``` cmd
del nomeDoarquivo.txt
```

Mas também podemos apagar arquivos com base em suas permissões, usando o argumento ***/A***, assim como veremos a seguir:
```
del /A:R #apagamos somente arquivos de leitura
```


---
## Encontrar

Para encontrar arquivos dentro do sistema, temos que usar o comando ***where***, como segue o exemplo:
```cmd
where nomeDoArquivo.txt
```

Mas assim ele só irá procurar em pastas padrões do sistema, então para definir um ponto de início, e fazer buscas forma recursiva, usamos o argumento ***/R***:
```
where /R C:\caminho\específico nomeDoArquivo.txt
```

Mas vamos supor que estamos procurando por algo específico dentro de umm arquivo, podemos usar o "***find***" e o "***findstr***"