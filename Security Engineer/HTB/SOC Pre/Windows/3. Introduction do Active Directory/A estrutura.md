Active Directory é uma estrutura de diretórios hierárquica, que se preocupa em gerir da melhor forma políticas em cima de usuários e computadores.

O active directory têm 4 principais elementos em sua forma principal:
- Floresta;
- Árvore;
- Diretório;
- Raiz;

A Floresta é um conjunto de árvores, que por sua vez é um conjunto de domínios, e estes são gerados pelo mesmo controle administrativo, até que seja requisitado de outra árvore.

Cada grupo, usuário, computador, dispositivo, GPO, arquivo compartilhado, têm seu próprio schema, que é compartilhado somente entre a mesma floresta, que é basicamente os campos a serem preenchidos sobre o objeto, por exemplo: Nome, Senha, Andar*, Departamento*...
*Pode variar

Em um caso real: Temos a Exxon Mobil (Floresta), com a parte de Chemicals (Árvore) e TI (Árvore), e na parte de TI temos uma unidade em Houston (Domínio), e outra em Curitiba (Domínio), com setores como RH (OU/Unidade Organizacional), e Janitor (OU).

OBS: OU são de extrema importância para uma qualificada a administração de AD, dado que com elas podemos criar GPO's mais precisas, e definir mais micro administradores para cada caso.

OBS2: quem cuida respectivamente da autenticação dos usuários, é o DC, ou Domain Controller.
