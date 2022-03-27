## Operadores de Comparação

Muito bem, você provavelmente acabou de ver os operadores aritméticos para
aprender a fazer cálculos em Ruby. E como você faz para descobrir se um numero é
maior do que o outro? 

Bom, para isso, jovem gafanhoto, é que existem os Operadores de Comparação.
Mas o que são comparações em ruby? Operadores de comparação na maioria das linguagens de programação, servem para definir se alguma condição é verdadeira ou falsa e rodar um bloco de código específico. É sempre retornado um valor booleano `true` ou `false`, nada mais. 

Sabendo disso, é hora de mostrar quais são os operadores de comparação em Ruby:

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

5. `<=` Operador "menor ou igual à".Tudo que estiver no lado esquerdo do símbolo
   é menor ou igual do que o que está do lado direito.

6. `>=` Operador "maior ou igual à". Tudo que estiver no lado esquerdo do
   símbolo é maior ou igual do que o que está do lado direito.

7. `eql?` Este métoddo retorna `true` se o número a esquerda for exatamente igual ao da
   direita.

Legal, né? Esses são alguns operadores de comparação, ao menos os mais usados e
com certeza é bom aprendê-los pela frequencia que você vai utilizar.

Ir para: [5.3_Operadores-Logicos](3-operadores-logicos.md)
