# Hashes

## O que são Hashes?

As `hashes` são arrays indexados, com `Chaves` e `Valores`, que podem ser quaisquer tipos de objetos. Caso você seja familiarizado com outras linguagens, as hashes assemelham-se muito aos `Objetos` do JavaScript e `Dicionários` do Python.

## Arrays vs Hashes

Entendendo o que são Arrays e Hashes, vamos entrar mais a fundo nas diferenças entre cada uma:

Suponhamos que você esteja com muita fome e tenha duas opções: Ir ao mercado ou ir a um restaurante, no mercado, você verá diversas prateleiras com os produtos alinhados nas mesmas, certo? Imagine isso como um `Array`, a prateleira é um `Array` e os produtos são os `Valores` dentro dela. Já no restaurante, você precisará olhar um cardápio para pedir o seu prato, isto é, você estará olhando para um bocado de `Chaves` de uma `Hash`, e ao escolher sua `Chave`, o prato ou `Valor` chegará até você.

```ruby
hash = {"Prato n° 1" => "Macarrão",
        "Prato n° 2" => "Salada",
        "Prato n° 3" => "Bife"        
        }
```

Ou de outra forma:

```ruby
hash = {"Prato n° 1" => "Macarrão", "Prato n° 2" => "Salada", "Prato n° 3" => "Bife"}
```

E Para vermos se funcionou, vamos jogar na tela a nossa hash:

```ruby
> puts hash
> "{"Prato n° 1"=>"Macarrão", "Prato n° 2"=>"Salada", "Prato n° 3"=>"Bife"}"
```
Dessa forma, podemos acessar uma `Chave` específica a fim de retornarmos seu `Valor`, da mesma forma que fazemos com `Arrays`:

```ruby
> puts hash["Prato n° 1"]
> puts hash["Prato n° 2"]
> puts hash["Prato n° 3"]
> "Macarrão"
> "Salada"
> "Bife"
```

Agora que aprendemos a acessar os valores, vamos progredir, `Adicionando` , `Editando`, `Excluindo` e `Fundindo` os dados:

```ruby
> puts hash
> "{"Prato n° 1"=>"Macarrão", "Prato n° 2"=>"Salada", "Prato n° 3"=>"Bife"}"
```

### Adicionando:
```ruby 
> hash["Prato n° 4"] = "Feijoada"

> puts hash
> "{"Prato n° 1"=>"Macarrão", "Prato n° 2"=>"Salada", "Prato n° 3"=>"Bife", "Prato n° 4" =>"Feijoada"}"
```

### Editando:
```ruby
> hash["Prato n° 1"] = "Camarão"

> puts hash 
> "{"Prato n° 1"=>"Camarão", "Prato n° 2"=>"Salada", "Prato n° 3"=>"Bife", "Prato n° 4" =>"Feijoada"}"
```

### Excluindo:

```ruby
> hash.delete("Prato n° 4")

> puts hash
> "{"Prato n° 1"=>"Camarão", "Prato n° 2"=>"Salada", "Prato n° 3"=>"Bife"}"
```

### Fundindo:

```ruby
> cardapio1 = {"Prato n° 1"=>"Camarão", "Prato n° 2"=>"Salada", "Prato n° 3"=>"Bife"}
> cardapio2 = {"Prato n° 1"=>"Peixe", "Prato n° 4"=>"Churrasco"}

> cardapio3 = cardapio1.merge(cardapio2)

> puts cardapio3

> {"Prato n° 1"=>"Peixe", "Prato n° 2"=>"Salada", "Prato n° 3"=>"Bife", "Prato n° 4"=>"Churrasco"}
```

## Símbolos como chaves de hashes

Nos exemplos acima, foi usario em sua maioridade as strings como chaves, no entanto, usualmente o consenso é a utilização de `Símbolos` como chaves. Isso acontece devido aos símbolos serem mais performáticos do que as strings em Ruby, além disso o código fica bem mais bonito, convenhamos:

```ruby
american_cars = { 
                  :chevrolet => "Corvette",
                  :ford => "Mustang", 
                  :dodge => "Ram" 
                }

japanese_cars = { 
                  honda: "Accord", 
                  toyota: "Corolla", 
                  nissan: "Altima" 
                }
```

Muito mais bonito, não? E o melhor de tudo, performático! No entanto, vale ressaltar algumas coisas:

  - Mesmo mudando as chaves, o método de chamada da `Hash` continua o mesmo:

  ```ruby
  american_cars[:ford]    #=> "Mustang"
  japanese_cars[:honda]   #=> "Accord"
  ```

Desse modo, aprendemos sobre as Hashes, utilizando métodos básicos para adicionar, editar, excluir e fundir. 
