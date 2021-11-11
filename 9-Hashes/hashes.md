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

Agora que aprendemos a acessar os valores, vamos progredir, `Adicionando` e `Editando` os dados:

```ruby
> puts hash
> "{"Prato n° 1"=>"Macarrão", "Prato n° 2"=>"Salada", "Prato n° 3"=>"Bife"}"

#Adicionando
> hash["Prato n° 4"] = "Feijoada"

> puts hash
> "{"Prato n° 1"=>"Macarrão", "Prato n° 2"=>"Salada", "Prato n° 3"=>"Bife", "Prato n° 4" =>"Feijoada"}"

#Editando
> hash["Prato n° 1"] = "Camarão"

> puts hash 
> "{"Prato n° 1"=>"Camarão", "Prato n° 2"=>"Salada", "Prato n° 3"=>"Bife", "Prato n° 4" =>"Feijoada"}"

#Excluindo
> hash.delete("Prato n° 4")

> puts hash
> "{"Prato n° 1"=>"Camarão", "Prato n° 2"=>"Salada", "Prato n° 3"=>"Bife"}"
```

Desse modo, vimos que é possível adicionar, deletar e editar os dados de uma `Hash` por meio de códigos.
