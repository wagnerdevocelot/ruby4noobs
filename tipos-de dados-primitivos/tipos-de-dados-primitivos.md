## Tipos de dados primitivos

Ruby é uma linguagem fortemente orientada a objetos, então todos dados até o mais primitivos são objetos. Um objeto é um conjunto de dados e métodos, que podem ser acessados e manipulados. Os dados vamos falar agora sobre alguns deles e os metodos vamos falar futuramente mas entenda nesse momento que metodos são como adicionar comportamento a um objeto.

A questão aqui é que como os dados primitivos sao objetos eles podem ser manipulados como qualquer outro objeto? A resposta é sim!

<small>É desejável que para todos os exemplos através desse artigo você rode os comando no 'irb' para ver as saídas.</small>


### Números

Os tipos numéricos são utilizados para representar os mesmos dados que usamos na matemática. Então podemos fazer expressões matemáticas com eles.

```ruby
    # Soma
    1 + 1 # => 2

    # Subtração
    10 - 5 # => 5

    # Multiplicação
    2 * 2 # => 4

    # Divisão
    10 / 5 # => 2

    # Expoente
    10 ** 2 # => 100

    # Módulo (resto da divisão)
    8 % 2 # => 0 ( 8 / 2 = 4 sem resto)
    10 % 4 # => 2 ( 10 / 4 = 2 com resto 2)
```

Existem dois tipos de dados numéricos principais: Integer e Float.
Integer é um tipo de dados que representa um número inteiro, como 1, 2, 3, 4, 5, 6, 7, 8, 9, 10
Float é um tipo de dados que representa um número real, como 1.0, 2.0, 3.0, 4.0, 5.0, 6.0, 7.0, 8.0, 9.0, 10.0

Quando estivermos fazendo operações com Integer, o resultado será sempre um Integer.

```ruby
    17 / 5 # => 3, e não 3.4
```

Se você quiser um resultado exato você pode trocar um dos tipos de dados por Float.

```ruby
    17 / 5.0 # => 3.4
```

### Strings

String são uma coleção de caracteres, repare que disse caractere e não letras. Geralmente números que não precisam passar por uma expressão matemática são usados como string.
Um exemplo é o CPF, que é um número de 11 dígitos. O CPF é usado como um identificador e em nenhum momento você precisaria passar um CPF por uma expressão matemática, nesses casos é possivel usar numeros como string.

#### Aspas simples e aspas duplas

Strings podem ser escritas com aspas simples ou aspas duplas. Você pode usar aspas duplas quando for precisar de interpolação de strings e scape de caracteres especiais. Já falaremos sobre isso daqui a pouco.

#### Concatenação

Existem maneiras simples de concatenar strings em ruby.

```ruby
    # Usando sinal de +
    "Hello" + " " + "World" # => "Hello World"

    # Usando o operador de desvio a esquerda
    "Hello" << " " << "World" # => "Hello World"

    # Usando o metodo concat
    "Hello".concat(" ").concat("World") # => "Hello World"
```

#### Substrings

Strings são uma coleção de caracteres, então podemos pegar partes deles.

```ruby
    "Hello"[0] # => "H"

    "Hello"[0..1] # => "He"

    "Hello"[0, 4] # => "Hell"

    "Hello"[-1] # => "o"
```

#### Escape de caracteres

Escape de caracteres permitem que você escreva dentro de strings de aspas duplas caracteres especiais como aspas, barras, crases, etc.

```ruby
    \\ # => \
    \b # => Backspace
    \r # => Carriage Return
    \n # => Newline
    \t # => Tab
    \" # => Double Quote
    \' # => Single Quote
```

#### Interpolação

Interpolação é a forma de escrever strings com variáveis. É como se você estivesse escrevendo um convite de uma festa por exemplo, você precisaria de uma parte do convite escrita por padrao que seria igual para todo mundo e outra parte que seria diferente para cada pessoa.
Por exemplo:

    Olá PESSOA, dia 28/12 é meu aniversário! Conto com a sua presença!

Nesse exemplo eu não poderia manda um email pra pessoa com o a palavra "PESSOA" e colocar o nome de cada um seria cansativo.
A interpolação permite que eu defina em uma variável uma lista com o nome dos convidados e depois eu posso usar essa variável para substituir a palavra "PESSOA" no meu convite.

```ruby
    # Variável
    PESSOA = "João"

    # Interpolação
    "Olá #{PESSOA}, dia 28/12 é meu aniversário! Conto com a sua presença!" # => "Olá João, dia 28/12 é meu aniversário! Conto com a sua presença!"
```

#### Symbol

Symbols em ruby são similares a strings, mas são úteis quando você precisa de um identificador único. Mesmo que eu tenha uma string igual a "João" e definir outra identica o ruby vai guardar essa nova string em outro lugar da memória. Um symbol é guardado na memória apenas uma vez e não pode ser alterado.

```ruby
    "João" == "João" # => true

    "João".object_id == "João".object_id # => false (não é o mesmo objeto)

    :João == :João # => true (são o mesmo objeto)
```

#### Booleans

Em ruby booleanos são `true` ou `false`. nos exemplos de código acima temos comentários com o retorno de alguns códigos e geralmente eles são utilizados para retornar uma resposta sobre uma expressão como saber se duas strings são iguais ou se um número é maior que outro. São representacoes de valores falsos ou verdadeiros.

#### Nil

No ruby o nil representa a inexistência de valor. Tudo no ruby retorna um valor então quando não há valor retornado, o ruby retorna nil.
Um dos exemplos que você vai encontrar muito é quando você tenta usar um método em um objeto que não existe, o famoso:

```text
Undefined method `nome' for nil:NilClass (NoMethodError)
```

O que o Ruby está tentando te avisar aqui é que você está tentando usar um método pra um objeto que não existe e como todos os tipos de dados em ruby são objetos ele se refere a esse valor nil como nil:NilClass.


#### Dicas

Como tudo no ruby é um objeto, você pode tentar acessar os tipos e procurar os métodos que eles possuem existem uma série de maneiras de manipular dados primitivos em ruby e isso vai ajudar você a entender melhor o que está acontecendo.

Abra o irb no console do ruby e defina variaveis e coloque tipos de dados dentro delas.

```ruby
    nome = "João"
```

Agora você tem um tipo de dado definido dentro de uma variável e pra provar que os tipos de dados são objetos, você pode usar o método `class` e ver se o tipo de dado é um objeto.

```ruby
    nome.class # => String
    nome.class.superclass # => Object
    nome.class.superclass.superclass # => BasicObject
```

Se você usar o metodo `methods` você pode ver todos os métodos que o tipo de dado tem.

```ruby
    nome.methods # => [:to_s, :to_str, :to_i, :to_f, :to_a, :to_ary, :to_c, :to_r, :to_sym, :to_proc, :to_h, :to_json, :to_set, :to_enum, :to_a, :to_ary, :to_c, :to_r, :to_sym, :to_proc, :to_h, :to_json, :to_set, :to_enum, :to_a, :to_ary, :to_c, :to_r, :to_sym, :to_proc, :to_h, :to_json, :to_set, :to_enum, :to_a, :to_ary, :to_c, :to_r, :to_sym, :to_proc, :to_h, :to_json, :to_set, :to_enum, :to_a, :to_ary, :to_c, :to_r, :to_sym, :to_proc, :to_h, :to_json, :to_set, :to_enum, :to_a, :to_ary, :to_c, :to_r, :to_sym, :to_proc, :to_h, :to_json, :to_set, :to_enum, :to_a, :to_ary, :to_c, :to_r, :to_sym, :to_proc, :to_h, :to_json, :to_set, :to_enum, :to_a, :to_ary, :to_c, :to_r, :to_sym, :to_proc, :to_h, :to_json, :to_set, :to_enum, :to_a, :to_ary, :to_c, :to_r, :to_sym, :to_proc, :to_h, :to_json, :to_set, :to_enum, :to_a, :to_ary, :to_c, :to_r, :to_sym, :to_proc
```

Todos esses são métodos que o tipo string possui e que você pode usar para manipular seus dados.
São muitos métodos e você nao vai precisar decorar isso, existem alguns que você vai acabar utilizando mais durante o processo e ai naturalmente você vai acabar decorando.
E para saber o que cada método faz você pode consultar a documentação do ruby no proprio terminal.

Pra isso você precisa sair do `irb` e digitar `ri` ( isso só funciona se tiver instalado o ruby com a documentação, por padrão ele já instala a não ser que você tenha instalado o ruby
usando o comando `--no-ri --no-rdoc`).

Dentro do `ri` você pode escrever o nome do método e ele vai te trazer a referência de como ele é implementado e uma breve explicação sobre como ele funciona.

```text
    to_s # => (retorna a documentação do método)
```

Essa é uma opção de consulta rápida mas muita gente pode considerar visualmente ruim já que é no console, então visitar a documentação do ruby no site [ruby-doc.org](https://ruby-doc.org/) é uma outra boa opção.
