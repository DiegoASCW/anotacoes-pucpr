4. Get-ChildItem -Path C:\Users\user4\Documents -Recurse -Force | ? {$_.Length -ne 0} | ? {$_.Name -Match "flag.txt"}
5. net user
7. Conectar no alvo, ssh do DC. Get-Module -ListAvailable | ? {$_.Name -Match "flag"} .
8. Get-ADUser -Filter *
9. 