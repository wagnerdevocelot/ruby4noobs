## Operadores Matemáticos

É certo que toda linguagem de programação possui operadores matemáticos, pois
são necessários para realização de cálculos e expressões matemáticas desde as
mais básicas até as mais avançadas. Porém a maioria dos operadores em Ruby são
apenas chamadas de métodos.
Como assim?

Por exemplo, o expressão a+b é interpretada como a+(b). Onde o `+` é o método do
objeto `a` que recebe o argumento `b`. E em Ruby, você verá mais para frente(dando um spoiler aqui) que não é preciso colocar os parenteses nas chamadas de metodos

Sabendo disso, é hora de mostrar quais são os operadores matemáticos em Ruby:

1. `+`. Operador de adição. Soma-se tudo que estiver de ambos os lados do
   operador.

2. `-`. Operador de subtração. Substrae-se(ah vá!) tudo que estiver de ambos os
   lados do operador.

3. `*` Operador de multiplicação. Você sabe o que uma multiplicação faz... Não
   sabe? Deveria.

4. `/` Operador de divisão. Divide o operando da esquerda pelo operando da
   direita.

5. `%` Módulo. Este operador divide o operando da esquerda pelo operador da
   direita e retorna o resto da divisão.

6. `**` Operador Exponencial. Performa calculo exponencial do operando da
esquerda, pelo que está na direita. 

Bom, agora que você já sabe quais são os operadores ariméticos, resta saber que
para cada um deles há uma forma reduzida de atribuição, onde `a = a+b` vira `a += b`

`(+=, /= ,**= %=, etc...)`


Ir para: [5.2 Operadores-Comparacao](2-operadores-comparacao.md)
