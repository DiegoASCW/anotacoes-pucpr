Docker cliente é apenas uma interface de interação com o Dockerd (daemon).

Para criar uma imagem derivativa de um outro container, podemos executar:
``` cmd
docker commit
```
Essa "nova" imagem, apenas armazena somente as modificações realizadas em cima de uma imagem, e aponta a imagem utilizada.

