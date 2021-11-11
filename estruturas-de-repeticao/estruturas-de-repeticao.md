## Estruturas de repetição

Repetição é uma estrutura de controle que nos permite executar um bloco de código várias vezes tornando tarefas repetitivas em algo simples.
Um exemplo é um servidor web, geralmente quando estamos desenvolvendo aplicativos para a web temos que servir páginas html em uma porta específica.

Exemplo de um servidor http Ruby:

```ruby
require 'socket'

server = TCPServer.new('localhost', 3000)
loop do
  client = server.accept

  request_line = client.gets
  puts request_line

  client.puts "HTTP/1.1 200 OK\r\n\r\n"
  client.puts "<html><body><h1>Olá rubysta!</h1></body></html>"

  client.close
end
```

Esse servidor recebe uma requisição e responde com uma página html com a mensagem 'Olá rubysta!'
A palavra reservada **loop** é justamente o que abre a repetição, dentro dele passamos várias instrições que ficarão a espera de uma requisição e quando receber essa requisição executamos o bloco de código e só depois disso ele termina o server.

Caso a porta 3000 nunca seja acessada nosso loop irá rodar para sempre. Fora do contexto de servidores loops infinitos são algo bom então sempre deve existir condições para que seu loop seja terminado.

Geralmente em loops usamos a palavra reservada **break** em conjunto com alguma condição para que o loop seja interrompido.

Esse tipo de repetição é não costuma ser muito usada no Ruby pois temos algumas alternativas mais interessantes.

### while

O while é um opção interessante pois antes mesmo de executar o bloco de código definimos o **break** implicitamente.

while em português é **"enquanto"**, o Ruby tem uma sintaxe bastante declarativa o que faz com que possamos ler isso como sentenças em inglês.

```ruby
idade = 1
while idade < 10 do
 puts "idade é #{idade}"
 idade += 1
end
# => idade é 1
# => idade é 2
# => idade é 3
# => idade é 4
# => idade é 5
# => idade é 6
# => idade é 7
# => idade é 8
# => idade é 9
```

Em uma tradução literal pra português isso seria:

```
enquanto idade for menor que 10 faça...
```

Quando dizemos `enquanto idade for menor que 10` fica muito claro que isso é uma condição verdadeira então o while irá rodar até que a condição seja falsa, assim definindo um break de forma implicita.

### until

O until é exatamente o oposto do while, ele é executado até que a condição seja verdadeira.

```ruby
idade = 1
until idade > 10 do
 puts "idade é #{idade}"
 idade += 1
end
# => idade é 1
# => idade é 2
# => idade é 3
# => idade é 4
# => idade é 5
# => idade é 6
# => idade é 7
# => idade é 8
# => idade é 9
# => idade é 10
```

A traducão de until em português é **"até que"**.
Esse bloco em português seria:

```
até que idade seja maior que 10 faça...
```

### range

O range é uma forma de repetir um bloco quando sabemos o início e o fim da repetição, então sabemos extamente a quantidade de vezes que o bloco deve ser executado.

```ruby
('a'..'e') #=> a, b, c, d, e
(1..5) #=> 1, 2, 3, 4, 5
```

Isso acaba sendo lido como, a partir do `a` até o `e` e a partir do `1` até o `5`.



### for

O for pode ser usado em conjunto com range ou com uma lista para fazer as repetições através dos itens dessa lista ou do incio ao final de um range.

```ruby
for item in ('a'..'e') do
 puts item
end
#=> a
#=> b
#=> c
#=> d
#=> e
```

### times

Se precisarmos repetir um bloco de código várias vezes, podemos usar a palavra reservada **times** que nos ajuda a especificar quantas vezes o bloco deve ser executado.

```ruby
5.times do
 puts "Ruby!"
end
# => Ruby!
# => Ruby!
# => Ruby!
# => Ruby!
# => Ruby!
```
