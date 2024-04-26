<p style="color: red"> !!! TÓPICO IMPORTANTE PARA O RESTO DO CONTEÚDO !!!</p>

O endereçamento de sub-rede, é sempre orquestrado pelo DHCP (servidor dentro do seu gateway), e é ele que lhe trará um IP para chamar de seu.

Temos 3 componentes internos extremamente essenciais: Máscara de rede, Gateway padrão, e Endereço IP.

Vamos nos atentar nos 2 primeiros, dado que o endereço é apenas a resultante de ambos.

---
#### Máscara:
A máscara é quem define a variação da rede, ou seja, quais números do seu IP são fixos, e quais podem variar. Mas sua sintaxe é um pouco diferente: **255.255.255.0**.

Para a máscara, 255 é FIXO, e 0 pode variar.

---
#### Gateway Padrão:
Gateway Padrão é por obrigação o IP de número 1 da rede, e é ele quem é sua internet.

---
## Juntando as pontas

Em um IP privado: 192.168.1.0, com máscara 255.255.255.0, os números 192.168.1 SERÃO SEMPRE ESTÁTICOS, e SOMENTE O ÚLTIMO PODE MUDAR, então o seu computador reconhece que só pode pegar um ip entre **192.168.1.2** até **192.168.1.254** .

 
---
[IP Address](https://www.youtube.com/watch?v=5WfiTHiU4x8)
