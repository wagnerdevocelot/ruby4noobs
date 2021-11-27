## Estruturas de Condição

O conceito de estruturas de condição é bem simples, é tudo que envolve controlar o fluxo do seu código. Imagine que você tem algum bloco de código se pode ser executado em determinada situação, dessa forma você precisa de um jeito que seu computador entenda se essas condições foram encontradas.

Os condicionais são definidos usando uma combinação de declarações `if` com comparações e operadores de lógica como `(<, >, <=, >=, ==, !=, &&, ||)` . Eles são as estruturas básicas de condições em Ruby e as palavras reservadas para os condicionais são `if, else, elsif, end`.

Condicionais são encontradas em todo e qualquer lugar que você pode imaginar. Você já marcou de ir jogar bola com os amigos e só iria se estivesse fazendo sol?

```ruby
if sunny_day == true
  "Vou jogar bola com os amigos"
end
```

Em código ruby essa condição ficaria assim. Usando um exemplo parecido, da para se aprofundar ainda mais nas condições e na logica, de modo que seu código seja executado somente quando uma condição específica for acionada.

```ruby
nota = gets.chomp.to_i

if nota == 10
  "Férias na disney!"
elsif nota >= 5 && nota < 10
  "Férias em casa"
else
  "Aulas de reforço"
end
```

No bloco de código acima você já deve ter percebido que se trata de uma estrutura de controle condicional, e abordamos uma situação onde você só irá tirar suas queridas férias na disney se tirar uma nota 10 e se tirar menos que 5 terá aulas de reforço! Observando o código, primeiro recebemos algum valor e atribuímos à variavel `nota`. Em seguida fazemos a seguinte comparação: É `nota` igual a `10`? A resposta aqui sempre irá retornar verdadeiro ou falso. 

## Comparações

Com certeza você viu no exemplo acima as comparações entre a variavel `nota` e algum valor númerico. Mas o que são comparações em ruby? Operadores de compração ou operadores lógicos, na maioria das linguagens de programação, servem para definir se alguma condição é verdadeira ou falsa e rodar um bloco de código específico. É sempre retornado um valor booleano `true` ou `false`, nada mais. 

`As expressões ou valores que um operador usa são seus operandos. Em comparações, as expressões à esquerda e à direita do operador são os operandos.`

### Operadores

1. `==` Operador de igualdade. Tudo que estiver no lado esquerdo do símbolo é exatamente igual ao que está do lado direito. Nós usamos esse operador quando comparamos `nota` com o valor `10`.
```ruby
irb :001 > 5 == 5
=> true
irb :002 > 5 == 6
=> false
irb :003 > 'abc' == 'abc'
=> true
irb :004 > 'abc' == 'abcd'
=> false
irb :005 > 'abc' == 'aBc'
=> false
irb :006 > '5' == '5'
=> true
irb :007 > '5' == '6'
=> false
irb :008 > '5' == 5
=> false
```
Perceba que podemos comparar duas strings igualmente, contanto que elas tenham exatamente o mesmo valor, se tiver alguma diferença, as strings não serão iguais.

2. `!=` Operador de não-igualdade ou diferença. Tudo que estiver no lado esquerdo do símbolo é diferente ao que está do lado direito. 
```ruby
irb :001 > 4 != 5
=> true
# 4 é diferente de 5, o que retorna verdadeiro
irb :002 > 'abc' != 'aBc'
=> true
irb :003 > '4noobs' != '4noobs'
=> false
```
Assim como no operador de igualdade a comparação é bem simples, basta que ambos os valores tenham a mínima diferença para retornar `true`

3. `<` Operador "menor que". Tudo que estiver no lado esquerdo do símbolo é menor do que o que está do lado direito.
4. `>` Operador "maior que". Tudo que estiver no lado esquerdo do símbolo é maior do que o que está do lado direito.

```ruby
irb :001 > 4 < 5
=> true
irb :002 > 4 > 5
=> false
irb :003 > "4" < "5"
=> true
irb :004 > "4" > "5"
=> false
```










