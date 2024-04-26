Em assembly temos diversos registradores, cada qual com sua devida capacidade de armazenamento (isso será muito importante).
E para poder associar dados a um registrador podemos usar 3 comandos:

```
mov
lea
xchg
```

### mov
Movimentar um dado é simples:
```
mov rax, 1
```

### lea
Carregar um dado é muito útil, pois costumeiramente associamos o local da memória a uma variável.
A var rsp armazena estes ponteiros.

Para carregar seu valor:
```
mov rax, [rsp]
```

Para carregar seu endereço:
```
mov rax, rsp
```


### xchg
xchg (Exchange) realiza a troca de valores entre variáveis
```
xchg rax, rbx
```