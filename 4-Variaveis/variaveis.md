# Variáveis

## O que é uma variável?

Variáveis são informações guardadas para serem referenciadas e manipuladas em programação de computador. Ok, mas o que isso significa? 

## A caixa

Imagina uma variavel como um caixa onde você guarda alguma coisa lá dentro, e depois marca essa caixa com uma etiqueta com um nome. Como nesse exemplo:

![variavel-caixa](https://i.imgur.com/IEBFo0a.png)

Pode não ser um bom exemplo, mas é suficiente para entender. A variável é uma caixa que você guarda algum valor e dá um nome para identificar o que é que está guardado.

Uma variável, em Ruby, pode se referir a qualquer conceito relacionado a valor que a linguagem entenda, como números, textos, listas ou qualquer outra estrutura de dados. 

### Atribuindo Valores à uma Variável

```ruby
first_name = "João"
```
Depois de declarar (criar) uma variavel chamada `first_name`, foi atribuida à ela a string `"João"`. Para atribuir algum valor à uma variável, é utilizado o símbolo `=`, onde o nome da variável ficará na esquerda e o valor na direita.

* Atenção: Apesar do símbolo de igual (`=`) ser bastante conhecido e ter um significado bem estabelecido, na programação acontece um pouco diferente. O símbolo de igual (`=`) é o símbolo de atribuir, e a leitura de uma variavel é entendível da direita para esquerda, como no exemplo: A string `"João"` foi atribuida a variável `first_name`

Agora, se quisermos referenciar(chamar) essa variável, basta escrever o nome da variavel, assim:
```ruby
> first_name
> "João"
```

O que acontece aqui é que agora salvamos a string `"João"` na memória do computador para ser usada depois quando chamar a variavel `first_name`.

Você também pode atribuir resultados de expressões em alguma variável

```ruby
> soma = 5 + 4 #=> Salvamos a expressão de soma de dois valores
> soma #=> A variável agora armaezena o resultado da expressão, 
> 9 #=> e quando é chamada retorna o numero 9
```