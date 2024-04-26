Para criar e apagar diretórios podemos usar os mesmos comandos do Linux: ***mkdir***, e ***rmdir***.

Entretanto para apagar recursivamente todo um diretório, usamos: ***rmdir /S***. No entanto, você pode usar a versão simplificada do comando, sendo: ***rd***.

---

Para copiar arquivos, temos diversas formas, e ferramentas, sendo as mais usadas:
- ***xcopy*** para itens individuais, ou em pequenas quantidades;
- ***ROBOCOPY*** para altas cargas de cópia.

Ambos copiam arquivos, mesmo que só tenham permissão de leitura do mesmo, e reiniciam as permissões.

### xcopy
Para copiar um arquivo em específico, use:
``` cmd
xcopy C:/caminho/do/arquivo C:/caminho/do/destino 
```

E para copiar todos os arquivos e subdiretórios de um diretório:
``` cmd
xcopy /S C:/caminho/do/diretório C:/caminho/do/destino 
```

Robocopy mesma coisa.

---

Para lermos o conteúdo de um diretório, basta usar *dir*, ou para saber toda sua extensão: ***tree /F*** (/F para listar arquivos também).

