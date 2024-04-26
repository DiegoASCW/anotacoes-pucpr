## Visão Geral

Todos os dados adquiridos pelos agentes, coletores, api's, são prontamente entregues ao "*Insight Collector*", que por sua vez entrega à Cloud da Rapid7, e por fim nos dá acesso aos dados pelo InsightIDR
![[Pasted image 20231123132556.png]]


## Coletores
Os coletores centralizam o envio de logs, recebendo estes dos meios já ditos acima. E portanto, ele deve ser posicionado o quão próximo possível dos pontos de eventos.

Pode-se utilizar um ou mais, dependendo do seu ambiente.

Para saber dos requisitos de sistema para comportar um coletor, acesse [aqui](https://docs.rapid7.com/insightidr/collector-requirements/).


## Network Sensor
Pode-se instalar agentes em sensores de rede, isto é, dispositivos que enforcam a rede para si antes de passarem para fora, ou que estão em promiscuidade, e recebem todos os pacotes circulates

Os dados coletados são:
- IDS (Suricata);
- DHCP;
- DNS;
- ENTA: Network Flow.
	Não se refere a Sniff de pacotes, mas aos seus metadados, em 2 modos:
	- East-West: Comunicação entre hosts na mesma rede;
	- Norte-Sul: Informação que trafega entre a rede e para fora dela.

Pode ser tanto um servidor físico, máquina virtual, ou EC2 no caso de AWS Cloud.

Por ser um dispositivo que deve estar na rede, este pode ser, ou não, um equipamento apenas local, e com isso quero dizer que, para fazer novas configurações deve-se ir presencialmente neste dispositivo e aplicar as mudanças.

## Plataforma InsightIDR
É onde todos os dados são analisados, e transformados.

- Cada cliente têm sua própria instância na nuvem;
- Todos os logs são padronizados em formato JSON;
- Realiza a análise de comportamento de usuário e atacante.

## Console InsightIDR
Interface WEB usada para acessar a Plataforma Insight.

Para entrar, clique aqui [insight.rapid7.com](https://insight.rapid7.com).

