Para poder criar os seus próprios decoders, vá para:
<p style="text-align:center; font-weight:bold;" > vim /var/ossec/etc/decoders/local_decoder.xml  </p>
Neste arquivo podemos criar os nossos Decoders personalizados.


### Parents
Ao invés de fazer com que cada decoder seja testado, podemos criar ***pais***, que quando estes dão "match" com o registro analisado, habilita a verificação de todos os decoders ***filhos***.

Podemos definir da seguinte forma:
``` html 
<!-- Decoder PAI -->
<decoder name="decoderPai">
        <prematch>^Medium:</prematch>
</decoder>

<!-- Decoder FILHO -->
<decoder name="decoderFilho">
        <parent>decoderPai</parent>
        <regex offset="after_parent">^\s(\.+) is an awesome company, check them out at (https://\.+)</regex>
        <order>company,website</order>
</decoder>
```

Podemos observar a tag "parent" no filho, que permite associar a qual pai estamos nos referenciando.

Podemos usar os pais de outros arquivos, no campo "parent" do nosso.

### Testes
Para poder testar os seus decoders, execute:
<p style="text-align:center; font-weight:bold;" > /var/ossec/bin/wazuh-logtest </p>
Neste arquivo podemos testar entradas de supostos logs que recebemos, e testar se nosso decoder está capturando devidamente o log.

**IMPORTANTE: você só pode inserir textos em uma única linha. Então execute o comando acima, e em seguida já insira no terminal o log a ser analisado.**

Teste a seguinte entrada:
*Medium: SOCFortress is an awesome company, check them out at https://www.socfortress.co*

E por fim, para saber se o seu decoder está no padrão aceito, você pode:

- CLI:
<p style="text-align:center; font-weight:bold;" > /var/ossec/bin/wazuh-regex 'seu regex aqui'</p>

- GUI
<p style="text-align:center; font-weight:bold;" > Wazuh > Management > Administration - Decoders > Manage Decoders Files > (última página) local_decoder.xml </p> 
No GUI você pode criar novos decoders, assim como testar eles, exatamente como você faria no CLI.


### Cuidados
O regex que estamos acostumados a usar, é levemente diferente do que usamos no Wazuh. Na verdade, é o mesmo, mas com algumas diferenças de sintaxe, sendo elas:

- Ao invés de declarar '.+' para pegar tudo, usa-se '\\.+' ;
- Para declarar um caractere especial ( *()*+,-.:;<=>?[]!"'#$%&|{}* ), não se usa '\\{' ou '\\?', usa-se '\\p' para todos.
- O Wazuh não reconhece distância de caracteres, então ao invés de usar, por exemplo "\\d{1,3}", use "\\d+". Sim, eu sei que parece contraproducente.


Dado a ótima performance que o Regex têm, não precisa se preocupar com "Otimização a todo custo", o ideal é que seu padrão seja o mais preciso e fácil de entender possível, por exemplo: não precisa substituir " " por "\\s" todas as vezes, dado que isso polui muito a visibilidade, como é o caso do seguinte log:

>Apr 14 19:28:21 gori123lla protocoloaleatorio \[31274]: Connection closed by 192.168.1.33
>
>> 1- ^\\w{1,3} \\d{1,2} \\d{1,2}:\\d{1,2}:\\d{1,2} \\w+ protocoloaleatorio
>> 2- ^\\w{1,3}\\s\\d{1,2}\\s\\d{1,2}:\\d{1,2}:\\d{1,2}\\s\\w+\\sprotocoloaleatorio

Ambos os padrões estão corretos, mas a visibilidade que temos do primeiro é superior a do segundo.




---
Referências:
[SOCFortress](https://socfortress.medium.com/understanding-wazuh-decoders-4093e8fc242c)
[Sintaxe do Regex no Wazuh](https://documentation.wazuh.com/current/user-manual/ruleset/ruleset-xml-syntax/regex.html)


