Host enumeration, ou levantamento de informações sobre o sistema, é fundamentalmente útil tanto para SysAdmin quanto para PenTesters.

Mas para isso, precisamos responder perfeitamente a 3 perguntas:
- Quais informações eu posso pegar do Host?
- Por que precisamos dessa informação, e qual a importância do levantamento?
- Como pegamos essas informações via prompt de comando, e qual a metodologia geral que devemos seguir?

---
## Quais?

Se eu te perguntasse "Qual informação estamos procurando?" em um teste, você provavelmente ficaria confuso, dado que não sabemos o que procurar, enquanto não sabermos o quê existe.
Portanto, temos aqui uma interessante, e básica ramificação de informações que podemos encontrar:
![[Pasted image 20231212135612.png]]


Então para sempre nos mantermos na rota ideal do que QUEREMOS buscar, devemos ter sempre em mente algumas perguntas, dentre elas:
- Quais informações do sistema conseguimos detectar a partir do nosso host?
- Quais outros sistemas o nosso alvo está se comunicando na rede?
- Quais usuários temos acesso? E que informação é acessível a partir dessa conta?

Refletir sobre perguntas como essa, é essencial para podermos desenvolver uma metodologia de busca, e saber o que definitivamente queremos buscar.

---

## Por que?

Capturar informações do ambiente é necessário para entender onde estamos e o que conseguimos fazer com o que temos. Em um caso mais prático, vamos supor que você está fazendo um teste de invasão, e de repente você conseguiu acesso a uma conta sem privilégios, mas dentro do sistema, e agora sua missão é conseguir escalar seus privilégios. Assim que você entrar, pode até tentar procurar por CVE's presentes no sistema, mas o SysAdmin garantiu que tudo estivsse devidamente atualizado... e agora? Devemos olhar para erros humanos de configuração, e assim sendo precisamos nos atentar em algumas coisas que nos permitam atingir um nível maior de privilégio, como:
- Quais permissões meu usuário têm?
- A qual grupo pertence? Quais as permissões do grupo?
- Quais processos estão rodando embaixo do meu usuário?
- Quais recursos tenho acesso na rede?

Com essas perguntas, você já consegue estar devidamente ambientado na rede, e no sistema, para só assim, adquirir uma escala de privilégios.

---

## Como?

Para conseguir as informações classificadas em ***"Quais"***, precisamos usar comandos diretamente no CMD, então vamos lá:

#### Informações do sistema
Sempre é preferível que usemos a menor quantidade possível de comandos, justamente para evitar de sermos detectados enquanto realizamos o levantamento, portanto, um comando que nos traz todas as informações necessárias sobre o sistema e seu hardware, é:
```cmd
systeminfo
```
Mas justamente por ser um comando tão poderoso, por vezes haverá monitoramento de quem, e quando o utiliza, e então precisamos fazer algumas voltas para conseguir seus dados. Para saber qual o nome do dispositivo:
```cmd
hostname
```

E para saber qual sua versão de OS:
```cmd
ver
```

#### Informações da rede
Informações da rede são extremamente relevantes para um atacante, dado que com elas podemos executar, entre tantas outras coisas, movimentação lateral. E para identificar dados sobre o adaptador, IP, gateway padrão, máscara, sub-redes, e afins, usamos:
```cmd
ipconfig
```
E caso queiramos trazer mais dados ainda, podemos usar o argumento ***/all***:
```cmd
ipconfig /all
```

No entanto, como dito acima, precisamos saber também quais são os dispositivos que nosso alvo se comunica, ou já se comunicou anteriormente, a partir do cache da tabela ARP: 
```cmd
arp /a
```

### Informações do usuário e grupos

```
whoami
```

```
whoami /priv
```

```cmd
whoami /groups
```

```cmd
net user
```
```cmd
net group # em caso de ser DC
```
```cmd
net localgroup
```