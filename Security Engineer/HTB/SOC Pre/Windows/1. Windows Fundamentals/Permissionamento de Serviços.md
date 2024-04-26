Imagine que você têm um único técnico de redes em sua empresa, e que por não saber das boas práticas, este associou todos os serviços de rede à sua conta. Até que um dia Bob sai da empresa, e como é esperado, seu usuário é excluído dos sistemas. No entanto, serviços como o DHCP para de rodar, por conta que estavam todos associados ao usuário de Bob.
Isso tudo gera uma enorme dor de cabeça, e para evitar esse tipo de evento, criamos usuários de serviço para justamente isso, ou seja, contas individuais somente para rodar serviços críticos de rede.

### Verificando permissões de serviços
Para poder verificar as permissões de serviços, usamos essencialmente um GUI chamado "*services.msc*", ou *serviços* em windows pt-br

Temos então a presença de alguns usuários, como:
- LocalService
- NetworkService  
- LocalSystem
Sendo o LocalSystem o nível mais alto de usuário para um serviço.

É de costume de um SysAdmin verificar os permissionamentos, por conta que softwares baixados podem alterar essas regras.


