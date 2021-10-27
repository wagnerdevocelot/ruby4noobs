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

* Algo para você lembrar é que variavel ela não é "alguma coisa", ela é apenas o nome para alguma coisa, no caso um objeto, seja string, número, um array ou qualquer outro objeto em ruby.


### Como nomear variaveis?

Lembre-se que variavel é uma referência, então seja sempre sucinto e esclarecedor sobre o que a sua variavel faz. Observe o seguinte:

```ruby
a = 2
b = 3
c = 2 * (a + b)
```
Se te perguntarem o que esse código cálculo você dificlmente entenderia, poderia até tentar resolver o calculo e falar que ele faz a multiplicação da soma de dois valores, mas para qual finalidade? 

Agora o mesmo exemplo com as variaveis nomeadas de um jeito mais adequado

```ruby
base = 2
altura = 3
perimetro = 2 * (a + b)
```

Pronto! Não precisa pensar muito pra entender que está calculando o perimetro de alguma coisa que tem base o valor 2 e uma altura de valor 3. Nesse caso específico é o perímetro de um retângulo. Bem melhor para entender, né? 

Entretanto, sempre tenha em mente que nomear variaveis de forma clara e sucinta é sempre uma tarefa dificil, então procure sempre encontrar alguma que descreva bem que tipo de objeto ela guarda. Só lembrar do exemplo da caixa, como você encontraria uma caixa com dvds antigos guardados dentro dela?

