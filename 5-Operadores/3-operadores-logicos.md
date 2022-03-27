## Operadores Lógicos

Toda linguagem que se preza tem esses caras aqui, afinal a lógica por trás dos
computadores bebem bastante dessa fonte. Mas o que são os operadores logicos? 

Os operadores lógicos são usados para juntar/combinar duas ou mais expressões
logicas, e seu retorno é sempre `true` ou `false`.

Esse operadores normalmente são usados para tomadas de decisões, por exemplo,
dada uma variavel `a = 11`:

```
if (a == b) || a > 10
  puts 'Retorna alguma coisa'
end

```

1. `or` Operador lógico que verifica se um dos 2 operandos é verdadeiro, então
   ele retorna `true`

2. `||` A mesma coisa do 1, mas é usado com mais frequência e similar ao de
   outras linguagens.

3. `and` Operador lógico que verifica se os 2 operandos são verdadeiros, se sim
   retorna `true`

4. `&&` A mesma coisa do 3º, mas é usado com mais frequência e similar ao de
   outras linguagens.

5. `not` Operador de negação. Inverte uma expressão anterior `true`, tornando-a
   um retorno de boolean `false`.

6. `!` Mesma coisa do 5º, mas é usado com mais frequência e similar ao de outras
   linguagens.
