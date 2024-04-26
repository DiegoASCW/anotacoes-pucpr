---
aliases:
---
---
### Switch Case
```bash
case $var in 
	"valor") comando ;;
	"valor") comando ;;
	"valor") comando ;;
esac
```

---
### I/O
Para inserirmos dados a uma variável usamos o comando ***read***:
```Shell
read $var
# ou
read -p "Algum texto" $var
```

Entretanto, por mais que já vimos redirecionamento de saída de erro (2), normal (1), no entanto, podemos adicionar todas as saídas a um documento, por meio do ***tee***:
```Shell
ping -c 10 8.8.8.8 | tee -a saídasPing.txt
```

---
## Loop

#### While:
Loop While, assim como em todas as linguagens, foca-se em realizar algo, enquanto algo for verdadeiro. E podemos aplicar da seguinte forma:

```Shell
numero=1

while [ numero == 1 ];
do
	comando
done
```


#### For
Loop for, diferente de While, somente é utilizado quando seu fim é definido, ou seja, que já existe uma quantidade de vezes já definida para seu uso.

Loop For "Range":
``` Shell
for numero in {1..40};
do
	echo $numero
done
```

Loop For em lista:
```Shell
lista=(8.8.8.8 3.3.3.3 1.1.1.1)

for ip in ${lista[@]};
do
	echo $ip
done
```
Neste caso, a variável lista é usada com ${lista[@]}, pois "[@]" indica que queremos entrar em cada um dos seus valores. Se quiséssemos operar em cima dos seus índices, usaríamos: ${!lista[@]}.

---
## Contagem de caracteres
Para contagem de caracteres, o ideal é que seja utilizado o comando: ***${#var}***, entretanto, se você está fazendo exercícios do HTB, você deve usar o método incorreto: 
***$( echo $var | wc -c)***. Este método é incorreto, dado que ele considera as quebras de linha como sendo caracteres válidos.

---

## Função
Podemos declarar função de 2as formas diferentes:
```Shell
function nome{
...
}
```
Ou
```Shell
nome(){
	echo $1 $2 $3
}

nome Ola Novo Mundo
```

