## Visão Geral
O Agente, também conhecido como Insight Agent, é um dos principais braços da Rapid7 para monitoramento dos endpoints, dado que há um agente em cada endpoint de sua escolha.

O Insight Agent têm este nome pois é o mesmo agente utilizado para a ferramenta InsightIDR, e a InsightVM.

O Agente têm preferência para enviar os logs diretamente para a nuvem, mas pode ser configurado para enviar diretamente para um coletor, por meio de uma configuração [proxy](https://docs.rapid7.com/insight-agent/proxy-configuration/) durante a instalação.

### Uso médio

| InsightVM & InsightIDR | Linux | Mac | Windows |
| ---- | ---- | ---- | ---- |
| Rede (diário) | < 5MB | < 5MB | < 70MB |
| Footprint | < 500MB | < 500MB | < 500MB |
| RAM | < 200MB | < 200MB | < 400MB |
| CPU | 6% - 8% | 6% - 8% | 6% - 8% |

### Proteção contra exclusão
Alguns softwares de proteção de endpoint podem excluir o Agente, portanto certifique-se de há uma regra de proteção de exclusão para o caminho ( e seus subdiretórios ):
- Linux: /opt/rapid7/ir_agent/
- Windows: C:\\Program Files\\Rapid7\\Insight Agent\

## Regras de Firewall
As portas mencionadas devem estar desabilitadas no firewall local, bem como malware detection, e anti virus.
### Outbound (obrigatório)

Envio dos logs à nuvem:
- 443/TCP - URL: \*endpoint.ingress.rapid7.com  &  \*.insight.rapid7.com (13.58.19.32,3.131.127.126,3.139.243.230)

### Outbound & Inbound (para proxy com coletor)

Comunicação com o coletor:
- 5508, 8037/TCP

Atualização e file upload:
- 6608/TCP


## Capacidades
### Asset Quarantine
O Insight Agent permite que o asset seja posto em quarentena durante uma investigação, ou seja, tal dispositivo é isolado de toda a rede, exceto para a nuvem da Rapid7, e serviços confiáveis, como DHCP, por exemplo.

Para isso é necessário realizar algumas configurações:
#### Linux & Mac
Habilitar iptables

#### Windows
Para Windows, deve-se verificar se o serviço de Firewall local não foi desabilitado pela GPO, se sim, siga este [roteiro](https://docs.rapid7.com/insight-agent/quarantine-action-configuration#windows-operating-systems)

### Excluir Código de Eventos
Por vezes, o ambiente que o Agente está inserido pode estar mal configurado, ou não seguindo as boa práticas, o que resulta em diversos disparos de alertas e logs falsos e/ou sem valor algum. Portanto, podemos excluir alguns ID's de eventos em ambientes Windows, através destes passos:
1. Pare o serviço do Agente;
2. Como administrador abra C:\\Program Files\\Rapid7\\Insight Agent\config\\agent.jobs.windows.ui_realtime.json ;
3. Adicione o JSON a seguir, modificando à sua necessidade:
```JSON
{
    "EventLogMonitor": {
        "excludes": {
            "application": [
                1033,
                1034,
                11707,
                11708,
                11724,
                11725
            ],
            "applicationWithSource": {
                "EMET": [
                    2
                ]
            },
            "security": [
                1102,
                4624,
                4625,
                4648,
                4720,
                4697
            ],
            "securityWithSource": {
                "Microsoft-Windows-Security-Auditing": [
                    5145
                ]
            },
            "system": [
                7045
            ],
            "systemWithSource": {
                "Service Control Manager": [
                    7045
                ]
            }
        }
    }
}
```
Obs: caso deseje excluir mais eventos, certifique-se de incluir o nome do log (ex: securityWithSource), e seu nome de origem (ex: Microsoft-Windows-Security-Auditing).


## Update
Todo agente contém um componente que gerencia a versão do software, que ao detectar uma nova versão, tenta atualizar, mas caso não consiga em um primeiro momento, forçará novas tentativas até obter sucesso na atualização.
A ordem de prioridade de como irá conseguir o arquivo de atualização é:
1. Pelo Coletor mais próximo;
2. Pelo Proxy (se configurado);
3. Diretamente da plataforma Insight .

Podemos verificar a versão do agente diretamente pela plataforma.

Obs: por padrão o número máximo de agentes que podem ser atualizados simultaneamente corresponde a 25% dos agentes.

## Troubleshooting
Caminho completo da instalação:
- Linux: /opt/rapid7/ir_agent/
- Windows: C:\\Program Files\\Rapid7\\Insight Agent\

Logs do agente:
- Linux: /opt/rapid7/ir_agent/components/insight_agent/common/agent.log
- Windows: C:\\Program Files\\Rapid7\\Insight Agent\\components\\insight_agent\\common\\agent.log

Favor verificar documentação [oficial](https://docs.rapid7.com/insight-agent/troubleshoot)


---
Links de referência:
[Agent Requirements](https://docs.rapid7.com/insight-agent/requirements/)
[Sistemas Operacionais com, e sem, suporte](https://docs.rapid7.com/insight-agent/operating-system/)
[Coletor como Proxy](https://docs.rapid7.com/insight-agent/proxy-configuration/)
[Requisitos de Rede](https://docs.rapid7.com/insight-agent/network-traffic-and-connectivity-requirements/)
[Como funciona?](https://docs.rapid7.com/insight-agent/data-collected)
[Asset Quarantine](https://docs.rapid7.com/insight-agent/quarantine-action-configuration)
[Update](https://docs.rapid7.com/insight-agent/how-the-insight-agent-software-updates/)
[Troubleshooting](https://docs.rapid7.com/insight-agent/troubleshoot)
