# MÉTODOS BÁSICOS DE ENUMERAÇÃO

**Enumerações** são um conjunto de métodos de construção em ruby, e são includas tanto em ***Arrays*** como também em ***Hashes***. Existem alguns padrões de iteração que você conhecerá com o tempo, mas isso só acontecerá conforme estuda a linguagem.

As enumerações foram criadas buscando facilitar a implementação desses padrões de iteração, deixando a vida do dev muito, mas muito mais fácil.

Aqui será citado apenas alguns métodos mais conhecidos, caso queira estudar mais a fundo, a documentação oficial do [Ruby](https://ruby-doc.org/core-2.6/) é sempre bem vinda, principalmente o [Módulo de enumeração](https://ruby-doc.org/core-2.6.1/Enumerable.html).

## Métodos que você aprenderá nessa seção:

  - Funcionamento do método **each**.

  - Funcionamento do método **map**.

  - Funcionamento do método **select**.

  - Funcionamento do método **reduce**.

  - Métodos **"bang!"** e o porquê de não serem considerados boas práticas.

## A vida antes das enumerações:


Suponhamos que você fará uma festinha da [He4rtDevs™](https://github.com/he4rt) com um array de **devs**, mas não quer chamar o Daniel por ele gostar de PHP, sempre evangelizando a linguagem por aí... Nesse caso, você faria algo assim:

```ruby
devs = ['VaporDev', 'EduRFS', 'DanielHe4rt', 'Nadachi', 'Cyytrus']

lista_de_convidados = []

for dev in devs do
  if dev != 'DanielHe4rt'
    lista_de_convidados.push(dev)
  end
end

lista_de_convidados #=> ["VaporDev", "EduRFS", "Nadachi", "Cyytrus"]
```
  - ***Aviso:*** O  **do** é opcional para um loop em Ruby e pode causar problemas se usado no **irb**.

Não é muito difícil, mas imagina que horrível ter que ficar fazendo esse tipo de coisa sempre que fizer uma festa, seria muito mais fácil parar de interagir com o Daniel.

Utilizando o método **select**, você proderia transformar o código nisso:

```ruby
devs = ['VaporDev', 'EduRFS', 'DanielHe4rt', 'Nadachi', 'Cyytrus']

devs.select { |dev| dev != 'DanielHe4rt' }
  #=> ["VaporDev", "EduRFS", "Nadachi", "Cyytrus"]
```

Ou mais explícito ainda:

```ruby
devs = ['VaporDev', 'EduRFS', 'DanielHe4rt', 'Nadachi', 'Cyytrus']

devs.reject { |dev| dev == 'DanielHe4rt' }
  #=> ["VaporDev", "EduRFS", "Nadachi", "Cyytrus"]
```

Você acabou de transformar um programa que antes possuia 8 linhas em um programa de 2 linhas, está orgulhoso? Não? Pois eu sim!

## O método each:

**each** é o vovô dos métodos de enumeração. Ele simplesmente faz de tudo, mas não é por isso que você vai usar apenas ele, né seu porra? Ele faz de tudo mas não tem só ele não.

Chamando o **each** em um array você fará uma iteração com cada componente do array, ligando-os cada um com um bloco de código:

```ruby
devs  = ['VaporDev', 'EduRFS', 'DanielHe4rt', 'Nadachi', 'Cyytrus']

devs.each { |dev| puts "Salve, " + friend }

  #=> Salve, VaporDev
  #=> Salve, EduRFS
  #=> Salve, DanielHe4rt
  #=> Salve, Nadachi
  #=> Salve, Cyytrus

  #=>  ["VaporDev", "EduRFS", "DanielHe4rt",  "Nadachi", "Cyytrus"]
```

### Detalhando a sintaxe:

  1. **devs** é o array que contém as strings com o nome dos devs.

  2. **each** é o método de enumeração que você está chamando no seu array de **devs**.

  3. **{ |dev| puts "Salve, " + friend }** é o ***bloco*** com o código dentro,  sendo percorrido com cada elemento do seu array, ou melhor, com cada dev da sua lista de devs, esse bloco rodará 5 vezes, cada vez com o nome de cada dev na lista.

  4. Dentro do bloco, nós temos **|dev|**, que é chamado de ***variável de bloco***. Esse é o elemento do seu array que estará iterando com o bloco de código. você pode usar qualquer nome de variável, nomes como **|x|**, **|y|**, dentro outros. No entanto, para melhor leitura e visualização, o método comumente adotado é escrever o nome do array no singular, se possível. Dessa forma, os valores de **|dev|** serão ***'VaporDev***, ***'EduRFS'*** e em diante até o fim do array.

E se o bloco que você decide passar o método precisar de mais argumentos do que você consegue escrever em uma linha? O código vai começar a ficar feio, porco e fedido, né? Dito isso, adotaram um consenso, ou melhor, uma boa prática para esse tipo de situação, alterando a sintaxe e urilizando **do...end** ao invés de **{...}**:

```ruby
array = [1, 2]

array.each do |num|
  num *= 2
  puts "O novo número é #{num}"
end

  #=> O novo número é 2.
  #=> O novo número é 4.

  #=> [1, 2]
```

**each** também funciona com hashes, deixando-as mais funcionais. Por padrão, cada iteração vai jogar na tela ambas chaves e valores, juntos ou separados (como em um array) no bloco, dependendo apenas de como você define sua variável de bloco.

```ruby
hash = { "um" => 1, "dois" => 2 }

hash.each { |key, value| puts "#{key} é #{value}"}

um é 1
dois é 2

  #=> { "um" => 1, "two" => 2}
```
**each** retorna o array ou hash independente do que aconteça dentro do bloco de código e é muito bom manter isso em mente.

Veja o exemplo a seguir:

```ruby
devs  = ['VaporDev', 'EduRFS', 'DanielHe4rt', 'Nadachi', 'Cyytrus']

devs.each { |dev| dev.upcase }

  #=> ['VaporDev', 'EduRFS', 'DanielHe4rt', 'Nadachi', 'Cyytrus']
```
Você esperava que isso retornasse tudo em CAPS? É amigo, infelizmente n vai dar certo não, isso retornará apenas o array original.

## O método map:

No exemplo acima, tentamos colocar todo o array de devs em CAPSLOCK, certo? Mas como pudemos observar, o método **each** retornou o array original. Dessa forma, para melhor otimização do código utilizaremos o método **map**.

### Afinal, o quê é o método map?

O método **map**, também chamado de **collect**, transforma cada elemento de um array de acordo com o que vai rodar no seu bloco de código, você passa o método e ele retornará um novo array com os elementos modificados. O **map** parece meio confuso no início, mas é só no início, ok? 

Primeiramente, vamos usar o **map** para otimizar nosso código anterior, fazendo-o funcionar como deveria, colocando o nome dos devs em CAPSLOCK.

```ruby
devs = ['VaporDev', 'EduRFS', 'DanielHe4rt', 'Nadachi', 'Cyytrus']

devs.map { |dev| dev.upcase }

  #=> `['VAPORDEV', 'EDURFS', 'DANIELHE4RT', 'NADACHI', 'CYYTRUS']`
```

É isso, agora conseguimos o nosso tão sonhado CAPSLOCK, bonitinho, né?

Agora em outro exemplo, vamos mexer com dinheiro, para deixar nossas economias daquele jeitão brabo.

  - Suponhamos que você tenha que pagar seu cartão de crédito todos os meses, mas isso só depois de pagar outras contas de casa, ou seja, você pagará o cartão apenas com o que sobra do seu salário.

  ```ruby
  salarios = [1200, 1500, 1100, 1800]

  salarios.map { |salario| salario - 700}

  #=> [500, 800, 400, 1100]
  ```
Desse modo, fizemos um pequeno loop utilizando o método **map**, em que diminuímos o "valor do cartão" de cada salário no array.

Então, sempre que quisermos criar um novo array, alterando os valores do nosso array atual, utilizamos o método **map**.

## O método select:

Já vimos o método **select** bem no começo desse tópico, quando queríamos tirar o Daniel da lista de convidados por conta da evangelização constante do PHP. Vamos relembrar?

```ruby
devs = ['VaporDev', 'EduRFS', 'DanielHe4rt', 'Nadachi', 'Cyytrus']

devs.select { |dev| dev != 'DanielHe4rt' }
  #=> ["VaporDev", "EduRFS", "Nadachi", "Cyytrus"]
```
O método **select** (também chamado de **filter**) passa todos os itens de um array para o bloco de código, e retorna um novo array **COM APENAS** os itens nomeados no bloco de código.

E já que tiramos o Daniel, vamos ver quem irá na nossa festinha, utilizando o **select** para retornar o **nome** e a **resposta** de cada dev:

```ruby
respostas = {'VaporDev' => 'sim', 'EduRFS' => 'nao', 'Nadachi' => 'nao', 'Cyytrus' => 'sim'}

respostas.select { |dev, resposta| resposta == 'sim' }

  #=> { "VaporDev" => "sim", "Cyytrus" => "sim" }
```

Parece que apenas Cyytrus e Vapor irão à festa, não é mesmo?

## Métodos BANG!

Lá em cima você aprendeu que os métodos **map** e **select** retornam novos arrays ao invés de modificarem o array original, certo? Isso é feito para não modificarmos o conteúdo original por acidente, evitando problemas futuros.

Por exemplo, se os métodos modificassem o array original, quando usamos **select** para verificar as respostas da festa da [He4rtDevs™](https://github.com/he4rt), apenas o Vapor e o Cyytrus iriam na festa, apenas eles... ***PARA SEMPRE***. Isso seria um pouco esquisito né? Pois é...

Dessa forma, podemos ver como mudar um array permanentemente em prática:

Voltando na brincadeira do CAPS:

```ruby
devs  = ['VaporDev', 'EduRFS', 'DanielHe4rt', 'Nadachi', 'Cyytrus']

devs.map { |dev| dev.upcase }

  #=> ['VAPORDEV', 'EDURFS', 'DANIELHE4RT', 'NADACHI', 'CYYTRUS']

devs

  #=> ['VaporDev', 'EduRFS', 'DanielHe4rt', 'Nadachi', 'Cyytrus']
```
Como vc pôde observar, ao requisitar a lista de devs, ela permanece inalterada

Caso queira mudar ***PERMANENTEMENTE*** isso, utilizamos o método bang **map!**

```ruby
devs = ['VaporDev', 'EduRFS', 'DanielHe4rt', 'Nadachi', 'Cyytrus']

devs.map! { |dev| dev.upcase }

  #=> ['VAPORDEV', 'EDURFS', 'DANIELHE4RT', 'NADACHI', 'CYYTRUS']

devs

  #=> ['VAPORDEV', 'EDURFS', 'DANIELHE4RT', 'NADACHI', 'CYYTRUS']
```
Perigoso né? Conseguimos mudar o array de forma permanente com o **map!**

Caso você já tenha lido a explicação de métodos, sabe que os métodos **bang!** podem ser identificados pelo seu sinal gritante (ba dum tss) de exclamação *(!)*,. Todos os métodos bang são ***destrutivos*** e modificam o objeto original quando chamados.

A boa prática é evitar esses métodos o máximo possível, você como um bom dev deve esperar que, ao criar um código, futuramente um psicopata maluco vai manter ele para você, pois é, lembra desse cara quando cogitar utilizar os métodos **bang!**
