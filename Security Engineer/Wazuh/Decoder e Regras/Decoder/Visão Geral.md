Temos 2as maneiras de monitorar o comportamento das informações, sejam elas pacotes de redes, ou até mesmo eventos de logon em uma máquina, nós registramos todos as ações envolvidas nesse processo.
Existe uma diferença de categoria entre monitoramento de rede, e de endpoints, cujo qual não me lembro exatamente. Entretanto, para analisar e monitorar as atividades/ações feitas em endpoints, precisamos ler os logs armazenados, pois neles moram todo o histórico de ação daquele dispositivo.

Cada ação tem um conteúdo diferente, mas via de regra, o mesmo esqueleto. Mas aplicações diferentes têm esqueletos diferentes. E é aqui que entra a necessidade de um Decoder, ou para fazer mais sentido, um decodificador.

Por padrão, para analisarmos um log, usamos OS_Regex, mas podemos usar sregex, e pcre2