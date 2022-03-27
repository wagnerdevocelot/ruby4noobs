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

``

# O valor nil
Em casos onde o valor é nulo, ou `nil` em ruby, existe um método que facilita
sua verificação:

5. `.nil?` Retorna `true` ou `false`. Tudo que estiver no lado esquerdo recebe a
   chamada ao método que verifica o valor contido na variavel.

```ruby
irb :001 > var = {}
irb :002 > var.nil? # verifica o valor atribuído a variavel de nome var
irb :003 > false # var possui uma hash vazia dentro dele
irb :004 > var2 = nil
irb :005 > var2.nil? # verifica o valor atribuído a variavel de nome var2
irb :006 > true

```

Um outro exemplo onde precisamos que a variavel tenha algum nome atribuído a ela, caso contrário não mostrará a mensagem

```ruby
irb :001 > nome = nil
irb :002 > puts "Bem vindo à He4rt, primo #{nome}" unless nome.nil? # não retorna nada no
console, já que o nome está nulo
irb :003 > nil
```
