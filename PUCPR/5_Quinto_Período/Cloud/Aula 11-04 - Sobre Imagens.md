Docker cliente é apenas uma interface de interação com o Dockerd (daemon).

Para criar uma imagem derivativa de um outro container, podemos executar:
``` cmd
docker commit
```
Essa "nova" imagem, apenas armazena somente as modificações realizadas em cima de uma imagem, e aponta a imagem utilizada.

Mas para criarmos uma nova imagem via script:
```dockerfile
FROM <nome_imagem>
ADD <nome_de_um_arquivo_no_host>
RUN <comando linux>
CMD <comando via cmd>
```
E para construir a imagem prevista no script:
``` powershell
docker build --no-cache --tag=<nome_imagem_a_ser_criada> <diretório>
```


Para executar comandos em um container temporário:
``` powershell
docker run -it --name=<nome_container> -rm <nome_da_imagem> 
```
