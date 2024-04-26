InsightVM é um dos módulos da linha Insight. No entanto, este não pode utilizar o mesmo agente já instalado nos dispositivos, pelo InsightIDR, na verdade, este deve ser apenas um host dedicado.
Explicando melhor, InsightVM deve ser um host dedicado, que têm seu próprio banco de dados (PostgreSQL), e executa Scan de vulnerabilidades em cima de outros dispositivos na rede previamente definidos.

Por executar scans de vulnerabilidades, não é interessante deixar apenas um único host realizar múltiplos scans e milhares de máquinas, na realidade você pode deixar diversas engines de scan espalhadas pela rede, e cada uma delas irá executar independentemente scans, e enviar para o host principal.
Entretanto, caso você precise monitorar um dispositivo importante, e que nem sempre está na rede da empresa, ou que nem sempre está em alguma rede, você pode sim se utilizar de scan mais básicos providos pelos agentes do InsightIDR e do InsightOps, mas os resultados não são tão satisfatórios quanto.

A conexão do host com a plataforma em nuvem da Rapid7, é unicamente pela porta 443, e para atualizações e suporte, também a 443 com o sites "**update.rapid7.com**" e "**support.rapid7.com**"

Para fins de melhor visualização:
![[Pasted image 20231124152242.png]]

Entretanto, o console

[[InsightVM]]