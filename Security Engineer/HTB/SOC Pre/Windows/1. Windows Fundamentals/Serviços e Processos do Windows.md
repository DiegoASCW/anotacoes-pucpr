Para podermos ver quais  processos temos ativo no Windows, abra o powershell e execute esta linha
```powershell-session
Get-Service | ? {$_.Status -eq "Running"} | select -First 2 |fl
```

No windows temos apenas 3 categorias de serviço, sendo elas: Serviço Local, Serviço de Rede, Serviços do Sistema.
Entretanto, temos um serviço muito importante, que gerencia apenas o ato de Logon, e Logoff, sendo o Local Security Authority Subsystem Service (LSASS).


### Exercício
Para podermos encontrar um serviço de Update, que não é padrão do Windows, vamos usar o comando *Get-Service* para poder pegar todos os serviços do Windows:
```
Get-Service
```

Para sabermos quais serviços estão rodando:
```
Get-Service | ? {$_.Status -eq 'Running'}
```
Break Down:
-  | : pega a saída do último comando e usa de entrada para o atual;
-  ? : alias para Where-Object, ou seja, define que o objeto de entrada neste comando (o de saída do outro) será tratado da forma a seguir nas chaves;
- {$\_}: variável especial que declara que o objeto a ser tratado é o de saída do comando anterior;
- -eq : mesmo sentido de "igual a";

Com isso ele trará uma lista de serviços do Windows, mas queremos um do Windows que não é padrão e que seja de Update, então vamos filtrar pelo nome do serviço para que tenha "Update":
```
Get-Service | ? {$_.Status -eq "Running"} | ? {$_.DisplayName -Match "Update"}
```

Por fim, só jogar no google os serviços retornados e ver quais deles não são padrões do Windows, e ir ao Monitor de Recursos para procurar qual o nome do executável, a partir do DisplayName do serviço