## Visão Geral
Coletor é uma peça chave na construção do ambiente de monitoramento, dado que ele têm o poder de centralizar o envio de logs. Em outras palavras, é uma máquina dedicada ao recebimento, tratamento, e envio dos logs à nuvem da Rapid7.
Todos os agentes Insight, têm por padrão a configuração de enviarem direto para a nuvem seus logs. Mas podem ser configurados com um proxy para enviar ao coletor.

Entretanto, o coletor é único porquê é ele quem acessa servidores AD, Domain Controller, e afins, com um usuário somente de leitura, e busca estes logs para ele, e então os formata e envia à nuvem.

O coletor deve ser posicionado o mais próximo possível da origem dos logs (data sources), para evitar fluxo intenso desnecessário em diversos pontos da rede, e por conta da velocidade de resposta que teremos com um envio rápido à nuvem.


## Requisitos e Usos do sistema
Antes de entrar em tabelas, vale lembrar que: o Coletor têm o limite de 600 agentes por CPU, então 4 CPU's = 2,400 agentes. Portanto, quanto mais event sources, mais RAM deve-se provisionar, mas caso o Coletor não consiga enviar imediatamente os logs para a nuvem, este armazenará os logs em seu disco, para envio em estrutura de fila.

### Tabela de requisitos
Segue abaixo tabela com a recomendação oficial da Rapid7, sobre o hardware:

|Collector Location Size|Number of Endpoints/Agents|Number of Event Sources on the Collector|Recommended Minimum CPU|Recommended Minimum RAM|Recommended Minimum Disk Space|
|---|---|---|---|---|---|
|Small|Up to 500|1 - 10|4|8 GB|60 GB|
|Medium|Up to 2,400|10 - 50|4|8 GB|80 GB|
|Large|Up to 600 per CPU core|50 - 80*|4+|16 GB|100 GB|
OBS: Podemos agregar mais de 80 event sources no mesmo Coletor, mas o recomendado é que ao atingir essa marca, provisionemos um novo Coletor para balancear a carga. 

### Requisitos mínimos
- 4 cores de CPU, com ao menos 2GHz em cada;
- 8 GB RAM
- 60 GB de disco;
- FQDN (ex: idrcollector.taskti.com);
- 100Mbps network .


## Regras de firewall
As portas mencionadas devem estar desabilitadas do firewall local, bem como malware detection, e anti virus.
### Outbound (obrigatório):

Para envio dos logs à plataforma:
- 443/TCP - URL: \*.endpoint.ingress.rapid7.com (data.insight.rapid7.com (US-1) , us2.data.insight.rapid7.com (US-2), us3.data.insight.rapid7.com (US-3), eu.data.insight.rapid7.com (EMEA), ca.data.insight.rapid7.com (CA), au.data.insight.rapid7.com (AU), ap.data.insight.rapid7.com (AP) )

Envio dos logs para armazenamento em nuvem
- 443/TCP - URL: s3.amazonaws.com (US-1), s3.us-east-2.amazonaws.com (US-2), s3.us-west-2.amazonaws.com (US-3), s3.eu-central-1.amazonaws.com (EMEA), s3.ca-central-1.amazonaws.com (CA), s3.ap-southeast-2.amazonaws.com (AU), s3.ap-northeast-1.amazonaws.com (AP)

Domain Controller como event source de LDAP
- 636/TCP UDP ou 
	LDAPS: 389/TCP UDP

Domain Controller por padrão:
- 135, 139, 445/TCP UDP

Mais portas disponíveis [aqui](Firewall-Rules%20-%20Collector.md)

### Outbound & Inbound (caso receba logs de Agentes):

Comunicação com o Agente:
- 5508/TCP , 8037/TCP UDP

Upgrade agent data path for the Insight Agent:
- 6608/TCP

Comunicação entre o Coletor e o Endpoint Monitor
- 20,000 - 30,000/TCP


## Capacidades
### Integração Microsoft
##### Office 365


Para mais detalhes, verifique a documentação [oficial](https://docs.rapid7.com/insightidr/microsoft-office-365/)


#### Azure AD

Para mais detalhes, verifique a documentação [oficial](https://docs.rapid7.com/insightidr/microsoft-azure/)

### Sophos


## Troubleshooting
Caminho completo do diretório de instalação:
- Linux: /opt/rapid7/collector
- Windows: C:\\Program Files\\Rapid7\\Collector

Chave do Coletor:
- Linux: /opt/rapid7/collector/agent-key/Agent_Key.html
- Windows: C:\\Program Files\\Rapid7\\Collector\\agent-key\\Agent_Key.html

Logs:
- Linux: /opt/rapid7/collector/logs
- Windows: C:\\Program Files\\Rapid7\\Collector\\logs

Favor visitar [site oficial](https://docs.rapid7.com/insightidr/collector-troubleshooting)


---
Links de referência:
[Collector Requirements](https://docs.rapid7.com/insightidr/collector-requirements)
[Troubleshooting](https://docs.rapid7.com/insightidr/collector-troubleshooting)
