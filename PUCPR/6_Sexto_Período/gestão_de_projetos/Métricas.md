Vamos calcular as métricas Lead Time, Fluxo de Trabalho (WIP) e Throughput para os itens fornecidos.

### Dados Fornecidos:

- **Itens:** US-1, US-2, US-3, US-4, US-5, US-6, US-7
- **Semana de Entrega:** 1, 1, 1, 2, 2, 3, 3
- **Dias de Trabalho:** 1, 1, 1, 2, 2, 2, 2
- **Dias de Espera:** 3, 2, 3, 6, 8, 10, 12

### Cálculo do Lead Time:

O Lead Time é a soma dos Dias de Trabalho e Dias de Espera.

Para cada item:

- **US-1:** 1 (Dias de Trabalho) + 3 (Dias de Espera) = 4 dias
- **US-2:** 1 (Dias de Trabalho) + 2 (Dias de Espera) = 3 dias
- **US-3:** 1 (Dias de Trabalho) + 3 (Dias de Espera) = 4 dias
- **US-4:** 2 (Dias de Trabalho) + 6 (Dias de Espera) = 8 dias
- **US-5:** 2 (Dias de Trabalho) + 8 (Dias de Espera) = 10 dias
- **US-6:** 2 (Dias de Trabalho) + 10 (Dias de Espera) = 12 dias
- **US-7:** 2 (Dias de Trabalho) + 12 (Dias de Espera) = 14 dias

### Cálculo do Throughput:

O Throughput é o número de itens entregues por semana.

Contagem de itens entregues por semana:

- **Semana 1:** US-1, US-2, US-3 (total de 3 itens)
- **Semana 2:** US-4, US-5 (total de 2 itens)
- **Semana 3:** US-6, US-7 (total de 2 itens)

O Throughput semanal é:

- **Semana 1:** 3 itens/semana
- **Semana 2:** 2 itens/semana
- **Semana 3:** 2 itens/semana

### Fluxo de Trabalho (WIP):

Para calcular o WIP, precisamos estimar o número de itens em progresso em um determinado momento. Vamos considerar o fluxo de trabalho na última semana.

**Semana 1:**

- Itens entregues: US-1, US-2, US-3
- Itens em progresso: Nenhum, todos foram concluídos na semana 1.

**Semana 2:**

- Itens entregues: US-4, US-5
- Itens em progresso ao final da semana: Os itens que começaram antes e ainda estavam em andamento até o início da semana 2 (US-4, US-5).

**Semana 3:**

- Itens entregues: US-6, US-7
- Itens em progresso ao final da semana: Nenhum, já que todos os itens entregues foram concluídos.

Para o WIP máximo em cada semana, consideramos que o WIP pode ser maior se o tempo de espera entre as semanas se acumula. Por exemplo:

- **Semana 1:** WIP pode ser considerado até 3 itens (se todos começaram na semana 1 e foram entregues no mesmo período).
- **Semana 2:** Para o início da semana, o WIP é 2 (US-4 e US-5), assumindo que o trabalho começou nas semanas anteriores e continuou.
- **Semana 3:** Para o início da semana, o WIP é 2 (US-6 e US-7).

### Reflexão sobre os Objetivos das Métricas:

- **Lead Time:** Reflete o tempo total para completar um item desde o início até a entrega. Reduzir o Lead Time é fundamental para melhorar a eficiência e a satisfação do cliente. Um Lead Time mais baixo geralmente indica um processo mais ágil.
    
- **Throughput:** Mede a capacidade de entrega de itens por unidade de tempo. Aumentar o Throughput é essencial para atender à demanda e melhorar a performance do processo. Um Throughput mais alto indica uma capacidade de entrega mais eficiente.
    
- **Fluxo de Trabalho (WIP):** Ajuda a entender a quantidade de trabalho em progresso. Monitorar o WIP é crucial para identificar gargalos e ajustar o fluxo de trabalho. Um WIP equilibrado ajuda a manter a eficiência sem sobrecarregar os recursos.
    

Essas métricas ajudam a avaliar e melhorar o desempenho do fluxo de trabalho, otimizando processos e garantindo que os objetivos de entrega sejam atendidos de forma eficiente.


WIP: Médio 33.57%
Throughput: 2.33

## Épicos
Épico é um conjunto de estórias menores, 

Exercício:

Épico: Eu como cliente da consultoria de segurança, gostaria de saber a análise do impacto do ataque.

- Eu como Gerente T.I, quero Identificar rastro de contaminação para identificar os potenciais danos causados, e a quem:
	- Identificar paciente zero
	-  Criar imagem do paciente
	- Verificar topologia lógica de rede para identificar possíveis ativos contaminados
	- Verificar integridade dos ativos envolvidos
	- Montar mapa de caminho percorrido pela ameaça
	
- Eu como Coordenador de Infraestrutura, quero verificar integridade dos serviços de operação para verificar a viabilidade do negócio:
	- Mapear serviços esperados
	- Avaliar comportamento dos sistemas com base no seu desempenho anterior
	- Validar configurações dos serviços de acordo com sua baseline
	- Criar relatório com os serviços analisados e seu hardening aplicado

- Eu como Analista de Seg. da Informação, quero Identificar as TTP utilizadas para aprimorar a segurança a longo prazo:
	- Identificar vetor de ataque inicial
	- Identificar artefatos maliciosos presentes nos ativos
	- Se houver, aplicar malware em ambiente sandbox
	- Produzir documento de post-mortem
	- Produzir documento de planejamento de ações futuras