Para poder pedir ajuda no PS, usamos:
```powershell
Get-Help comando
```

No entanto, sempre devemos estar com o nosso menu de ajuda sempre atualizado, então para atualizar devemos usar:
```powershell
Update-Help
```

---
### Capturar Comandos

Mas vamos supor que você não lembre exatamente o nome de um comando, você pode usar:
```powershell
Get-Command
```
Entretanto, você só se lembra do verbo do cmdlet:
```powershell
Get-Command -verb get
```
Ou só do noun:
```powershell
Get-Command -noun windows*  
```

---
### Alias
Temos diversos alias nativos do Windows, e para poder verificar quais são, podemos usar:
```powershell
Get-Alias
```

E todos nós sabemos que usar "Get-Location" a todo momento é muito demorado, por isso podemos nós mesmos criar nossos alias, usando:
```powershell
Set-Alias -Name aliasASerUsado -Value comandoASerResumido
```

