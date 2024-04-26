"Alias" está presente em todo o mundo da tecnologia, e significa em outras palavras, criar um novo nome de apresentação, por exemplo em MySQL:
```
SELECT detection_time as Timestamp from logs;
```

No caso do PS, podemos listar todos os Alias presentes da seguinte forma:
```
get-alias
```

E criar novos:
```powershell-session
New-Alias -Name "NovoNome" <cmdlet>
```

### Execution Policies
São regras que definem a execução de scripts, para poder prevenir contra scripts maliciosos. As políticas variam entre:

|   |   |
|---|---|
|`AllSigned`|All scripts can run, but a trusted publisher must sign scripts and configuration files. This includes both remote and local scripts. We receive a prompt before running scripts signed by publishers that we have not yet listed as either trusted or untrusted.|
|`Bypass`|No scripts or configuration files are blocked, and the user receives no warnings or prompts.|
|`Default`|This sets the default execution policy, `Restricted` for Windows desktop machines and `RemoteSigned` for Windows servers.|
|`RemoteSigned`|Scripts can run but requires a digital signature on scripts that are downloaded from the internet. Digital signatures are not required for scripts that are written locally.|
|`Restricted`|This allows individual commands but does not allow scripts to be run. All script file types, including configuration files (`.ps1xml`), module script files (`.psm1`), and PowerShell profiles (`.ps1`) are blocked.|
|`Undefined`|No execution policy is set for the current scope. If the execution policy for ALL scopes is set to undefined, then the default execution policy of `Restricted` will be used.|
|`Unrestricted`|This is the default execution policy for non-Windows computers, and it cannot be changed. This policy allows for unsigned scripts to be run but warns the user before running scripts that are not from the local intranet zone.|


