No windows temos 2 tipos de interação de login: Interativo, e Não Interativo.
- Interativo:
	O usuário precisa colocar suas credenciais de acesso para entrar, seja fisicamente, ou remotamente.

Não Interativo:
	No windows só é executado serviços a partir de um usuário na máquina, então existem diversos usuários de serviço, que seu único papel é executar serviços e manter tudo em ordem na casa. E por mais que pareça contra intuitivo do ponto de vista de segurança, eles não precisam de senha para poderem logar no sistema.

Entretanto, temos 3 níveis de acesso no Windows, como já vimos em outras sessões, como:

|   |   |
|---|---|
|Local System Account|Also known as the `NT AUTHORITY\SYSTEM` account, this is the most powerful account in Windows systems. It is used for a variety of OS-related tasks, such as starting Windows services. This account is more powerful than accounts in the local administrators group.|
|Local Service Account|Known as the `NT AUTHORITY\LocalService` account, this is a less privileged version of the SYSTEM account and has similar privileges to a local user account. It is granted limited functionality and can start some services.|
|Network Service Account|This is known as the `NT AUTHORITY\NetworkService` account and is similar to a standard domain user account. It has similar privileges to the Local Service Account on the local machine. It can establish authenticated sessions for certain network services.|

