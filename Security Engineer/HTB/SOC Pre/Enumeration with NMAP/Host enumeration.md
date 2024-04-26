Para somente verificar se o host está ativo, usa-se:
nmap -sn [ipv4]

Entretanto, o nmap assume diversas configurações se não as definirmos, como é o caso de somente verificar se um host está ativo enviando ARP ping e esperar receber um ARP reply. Para isso podemos utilizar o argumento -PE para utilizar ICMP request como método.

---
Entre tantas coisas que o nmap assume para si, o SYN scan (-sS) é definido por padrão em caso de ausência de usuário root, mas se assim for, este criará pacotes TCP (-sT) por padrão.

Por padrão, o nmap só verifica as 1000 primeiras portas de um host, caso queiramos verificar dentro de um escopo, podemos usar -p min-max   ou   -p 1,2,3,4,5   ou   -p-65535 .

Quando utilizamos a opção *-sT*, sinalizamos que queremos usar o **Connect Scan**, ou seja, só vamos definir se a porta está aberta, se conseguirmos nos conectar a ela. Esse é um scan muito furtivo, e com propriedade de fazer bypass pelo firewall e IDS, dado que não enviamos um pacote apenas, mas queremos legitimamente realizar a conexão para com ele.
No entanto, este pode demorar.

UDP: -sU

