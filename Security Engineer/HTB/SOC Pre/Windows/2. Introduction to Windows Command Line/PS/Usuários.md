Para podermos listar todos os usuários presentes na máquina por meio do comando:
```powershell
Get-LocalUser
```


Para CRIAR novos usuários via PS podemos usar o comando:
```powershell
New-LocalUser -Name "Nome" -NoPassword
```

Para poder MODIFICAR um usuário, e neste contexto, colocar uma senha:
```
$Password = Read-Host -AsSecureString #criamos uma senha segura
Set-LocalUser -Name "JLawrence" -Password $Password -Description "CEO EagleFang"
```

---
## Grupos

Para poder listar todos os grupos presentes na máquina:
```
Get-LocalGroup
```

Para poder listar todos os membros de um grupo. usamos:
```
Get-LocalGroupMember -Name "Users"
```

No entanto, para poder adicionar o usuário a um grupo
