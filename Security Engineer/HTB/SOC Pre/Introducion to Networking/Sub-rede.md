### Calculando CIDR e Redes
Sub-rede é a capacidade de quebrar um rede em redes menores, ainda dentro do escopo oficial da originária.

Para isso vamos nos aprofundar em como calcular a rede:

Por definição temos que dividir os 255 IPs possíveis em 8 números (os OCTETOS!):

128 - 64 - 32 - 16 - 8 - 4 - 2 - 1

E cada trecho de um IPv4 tem este octeto, ou seja a rede: 192.168.10.0, também pode ser definida por:

1100 0000 . 1010 1100 . 0000 1010 . 0000 0000

Onde 1 aponta qual número está ativo e deve ser somado com outros ativos.


Cada trecho do IP pode ser definido também como:

192 . 168 . 10 . 0
  8/   16/  24/  32/

Onde se eu te falar 192.168.10.0/27, você já sabe que no último trecho tenho: 1110 0000, ou seja a máscara de sub-rede será: 255.255.255.224, e por fim, o range do ip será 192.168.10.0-31.

---
### Quebrando redes
Quebrar redes nesse contexto não se trata sobre pedir para o estagiário configurar uma, mas sim sobre como criar novas redes dentro da original.

Peguemos o exemplo da rede anterior: 192.168.10.0/27 .
Temos nela o escopo de 32 possíveis hosts.

Se quisermos dividir em 4 novas redes, precisamos pegar o número total de hosts possíveis, e dividir pelo número requerido (caso a divisão não seja exata, apela pro de baixo, sempre). Então no nosso caso teremos 4 novas redes:

1. 192.168.10.0-7
2. 192.168.10.8-15
3. 192.168.10.16-23
4. 192.168.10.23-31