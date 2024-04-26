
Proxy, por definição, é um intermediador de uma comunicação, que têm poderes de inspecionar o pacote trafegado. Em contramão, se o proxy somente redirecionasse o pacote, substituindo seu ip de origem, este seria então um roteador.

Um proxy vai atuar na camada 7 (OSI, aplicação), pois têm a habilidade de facilmente inspecionar o conteúdo do pacote trafegado. Entretanto, este não consegue inspecionar pacotes que usem protocolos com criptografia, por exemplo: HTTPS, e outros derivados do SSL.
A única forma de de inspecionar pacotes criptografados, é se o servidor proxy tiver a chave.

Proxies têm diversos usos, sendo eles:
- Proxy Foward: Media a conexão, mas está mais ao lado do cliente. Muito útil para bloquear sites, ou conteúdos específicos, além de ter controle sobre o que está sendo pesquisado;
- Proxy reverso: Utilizado mais ao lado do servidor, este intercepta as requisições de clientes, e pode encaminhar para firewalls, ou até realizar balanceamento de carga entre servidores;

No entanto, entre os proxies, temos ainda outras duas variações destes:
- Transparente: O cliente não têm ciência de que há um proxy no caminho;
- Não-Transparente: O cliente sabe que há um proxy no caminho, e este ao receber a requisição do cliente, modifica os dados do pacote. 