IDR = Incidente Detection and Response


Podemos definir logs da seguinte forma:
- Evento: logs que tenham algum valor investigativo;
- Adversidade: logs que indicam alguma situação adversa (exemplo: algum agente foi desconectado);
- Incidente: quando alguma Adversidade gera uma violação de segurança ou política;
- Quebra: quando um ato é assumidamente malicioso.


Para tal, precisamos entender perfeitamente as fases de resposta a um incidente:
![[Pasted image 20231123111208.png]]

- Preparação:
	Preparação assume que um incidente alguma hora irá acontecer, portanto precisamos de capacidade de resposta, e isso surge com um time, um plano, reconhecimento claro do terreno que estamos atuando, e planos para caso isso ocorra. Além claro de aplicar segurança passiva, como antivirus, softwares atualizados, e afins.

	Ainda no campo da Preparação, deve-se atentar a:
	- Clara comunicação entre os pares;
	- Ter cadeia clara e objetiva de responsabilidades entre os membros;
	- Plano.
	Quando citamos plano, nos referimos à:
	- Metas de curto e longo prazo sobre o incidente;
	- Métricas claras de como medir cada meta;
	- Passos para responder à incidentes.


- Detecção e Análise:
	Detecção é fundamental para o sucesso de uma operação de Resposta, e este pode vir por:
	- Detecção automática (SIEM e afins);
	- Denúncias de usuários.
	E para tal, voltamos a necessidade de ter clara visibilidade sobre o ambiente, mas mais precisamente sobre seus vetores de ataque.

	Aqui vale salientar que nem todo alerta é um incidente, mas todo incidente surge de um alerta, então para definir o que é um incidente, e para investigar tal, usa-se:
	- Baseline de comportamento (linha esperada de comportamento em tempos normais);
	- Correlação de eventos;
	- Retenção de logs;

	Caso se confirme como incidente, algumas tarefas importantes:
	- Documentação sobre o ocorrido;
	- Priorização de esforços;
	- Notifique as pessoas necessárias, a depender da proporção do ocorrido.

	Vetores de ataque:
		Para tal, aconselho os artigos da [Fortinet](https://www.fortinet.com/resources/cyberglossary/attack-vector) e da [CloudFlare](https://www.cloudflare.com/pt-br/learning/security/glossary/attack-vector/)

- Contenção, Erradicação e Recuperação dos sistemas:
	- Contenção:
		Trata-se sobre quais decisões tomar e executar em cima de um sistema suspeito, ou confirmado de infecção, dentre elas:
		- Desligar o sistema;
		- Desconectar da rede;
		- Desabilitar funções;
		- Matar processos maliciosos.
		Essas são algumas decisões de grande impacto, e para isso deve-se ter claro qual a estratégia adotada para responder o incidente, e qual o apetite de risco/risco tolerado da empresa.

	- Erradicação:
		Trata-se de eliminar aquilo que é malicioso, ou pode ocasionar na volta.

	- Recuperação:
		- Confirmar as funções normais do sistemas;
		- Remediar as vulnerabilidades.

	O mais importante de tudo, é que todas as fases supracitadas, devem preservar as evidências do ocorrido, para fins de aprendizado e pós-mortem.

- Pós incidente / Pós-mortem:
	Essa é fase que sucede após concluir totalmente a reposta, e nela podemos aprender o que funcionou, como corrigir o que deu errado, e como se prevenir de um novo incidente igual.

