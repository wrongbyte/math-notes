# A probabilidade de qualquer coisa ocorrer é 50%?
Vez ou outra, é comum ouvirmos que não faz sentido dizer que a probabilidade de algo ocorrer é, digamos, 0,00625%: só há a probabilidade do evento ocorrer ou não. São os únicos cenários possíveis.
Mas será que essa afirmação é realmente correta? Vamos descobrir.

## O que é a probabilidade de algo?
Um dos conceitos fundamentais da chamada probabilidade clássica é o que chamamos de *ponto amostral*. Um ponto amostral nada mais é do que o resultado *possível* e *único* de um experimento aleatório.

Por exemplo, vamos imaginar que temos um dado de seis faces. Nesse caso, temos exatamente seis resultados possíveis: 1, 2, 3, 4, 5, 6. Cada um desses números é um **ponto amostral**.
Matematicamente, um ponto amostral é um item do **espaço amostral**, que é um **conjunto** que agrupa *todos os resultados possíveis* de um experimento aleatório.

```
Ω = {1, 2, 3, 4, 5, 6} -> espaço amostral
```

O que acontece, então, caso nosso intuito seja descobrir qual é a chance do nosso dado nos dar o número 2? Vamos por partes.

Nesse cenário hipotético, do conjunto acima, o número 2 é especial porque ele nos mostra qual nosso "resultado desejado". Logo, ele não é somente um ponto amostral qualquer, ele é um *ponto amostral favorável*. Logo, do nosso conjunto de resultados possíveis (espaço amostral), temos exatamente **um ponto amostral favorável**. 

A probabilidade da ocorrência de um evento se dá pela **razão entre a quantidade de pontos amostrais favoráveis e a quantidade total de pontos amostrais**. 
Ou seja, a probabilidade de tirarmos o número 2 é, como você imaginou, 1/6.

Porém, esse é um dos casos mais simples quando se trata de probabilidade. No mundo real, eventos dificilmente ocorrem de forma isolada - e muitas vezes queremos saber as chances de:
- um evento `x` ocorrer juntamente a um evento `y`
- um evento X ocorrer `n` vezes em `r` tentativas
- um evento `x` ocorrer, dado que esse evento ocorre em média `λ` vezes em um dado intervalo

Portanto, calcular a probabilidade de algo acontecer isoladamente já não se torna mais tão adequado.  E é daí que voltamos à questão do título.

## 50% de chance de se obter o número 2?
No cenário anterior, nossa questão analisava a probabilidade de se obter o número 2 jogando um dado de seis faces. Apesar de já sabermos que a real probabilidade desse evento é 1/6, ainda podemos voltar à questão do título e aplicar a mesma lógica à situação que temos: **se há apenas "dois" resultados possíveis (obter-se 2 ou não), porque a probabilidade é 1/6 e não 50%?**

Para entendermos a reposta, é preciso ir por partes.

Vamos separar os possíveis resultados do nosso experimento em duas categorias distintas: *sucesso* e *falha*. Cada uma dessas categorias define um conjunto disjunto e a união desses conjuntos resulta no nosso espaço amostral.
Logo, o sucesso é definido por
S ={2}
e a falha é definida por:
F ={1, 3, 4, 5, 6}

A afirmação de que a chance de algo ocorrer é 50% presume algumas coisas:
- a probabilidade de sucesso é 50%
- a probabilidade de falha é 50%

Agora, imagine que vamos jogar o dado e ver qual número obtemos a partir dessa tentativa.
Embora temos duas *categorias* possíveis de resultados (sucesso ou falha), **temos apenas 1 maneira de se obter um "sucesso" e cinco maneiras de se obter uma "falha".** Portanto, pela diferença de pontos amostrais favoráveis, **suas probabilidades não são iguais.** Ou seja, temos 1/6 de chance de sucesso e 5/6 de chance de falha.

![image](https://github.com/wrongbyte/statistics-notes/assets/57643375/926185c3-3af4-48fa-ba8c-c9df20ca288b)

Portanto, assumir que o resultado de um experimento é um "sucesso" ou "falha" faz sentido, pois podemos de fato dividir os resultados nas duas categorias. Contudo, assumir que ter apenas duas espécies de resultado implica em ter chances iguais para sucesso e falha é um erro.

## Definindo sucesso e falha matematicamente: tentativas de Bernoulli
O conceito de ter uma tentativa com conjuntos de resultados divididos entre sucesso e falha tem um nome no campo das probabilidades: *tentativa de Bernoulli*.

> Uma tentativa de Bernoulli é uma tentativa na qual temos dois possíveis resultados: sucesso e falha. A probabilidade de sucesso é representada por `p` e a probabilidade de falha é representada por `q`. A soma de ambas deve ser sempre igual a 1.

O conceito de tentativa de Bernoulli é especialmente importante quando falamos de distribuições de probabilidade como a *distribuição binomial*. Apesar do nome complicado, a distribuição binomial representa um conceito simples, apoiado no que vimos até agora sobre tentativa e falha: ela permite calcular a probabilidade de cenários hipotéticos que **combinam x sucessos e y falhas em r tentativas.**
Vamos ver um exemplo prático, reformulando nossa questão inicial:

> "Se rolarmos nosso dado de seis faces *três* vezes, qual a probabilidade de obtermos o número 2 *duas vezes*?"

Passamos do cenário de uma única tentativa para três tentativas, das quais sabemos que em duas queremos obter sucesso e em uma queremos obter falha. Como calcular a probabilidade de um cenário assim? Veremos a seguir:

## Distribuição binomial
Temos os mesmos conjuntos para sucesso e falha que tínhamos anteriormente:

S ={2}

F ={1, 3, 4, 5, 6}

além do mesmo espaço amostral:

Ω = {1, 2, 3, 4, 5, 6}

Além disso, sabemos que a probabilidade de sucesso em uma tentativa isolada é igual a 1/6 (e, consequentemente, a probabilidade de falha é 5/6).
Podemos então, a partir daqui, utilizar as regras básicas que definem a união de eventos:


> A probabilidade de termos um evento **e** outro evento é igual ao **produto** de suas probabilidades.
> 
> A probabilidade de termos um evento **ou** outro evento é igual a **soma** de suas probabilidades.
> 

No nosso cenário hipotético, queremos que os eventos ocorram conjuntamente. Portanto, queremos um sucesso **e** outro sucesso **e** uma falha. Isso nos dá:

```math
\frac{1}{6}\cdot\frac{1}{6}\cdot\frac{5}{6}= \frac{5}{216}
```
Que é a probabilidade de termos exatamente dois sucessos e uma falha, dada uma tentativa.

Contudo, esse número por si só não leva em consideração que esse resultado pode ocorrer em várias ordens diferentes, sendo cada combinação um resultado possível para o experimento, que possui o seguinte espaço amostral (S = sucesso, F = falha):

Ω={ SSS, SSF, SFS, SFF, FSS, FSF, FFS, FFF }

Dos quais apenas os seguintes resultados atendem nossas condições:

S={ SSF, SFS, FSS }

Portanto, temos apenas três combinações possíveis. A probabilidade da ocorrência de uma delas - dado que são mutuamente exclusivas - é igual à **soma** de suas probabilidades (que são de 5/216 para cada uma das combinações), nos dando:
```math
3\cdot\frac{5}{216}=0.06944..
```
O processo que fizemos, bem como cada um dos cálculos, pode ser abstraído na **fórmula da distribuição binomial**, que possui a seguinte estrutura:
```math
\binom{n}{x}p^{x}q^{n-x}
```
onde:
- n é a quantidade de tentativas
- x é a quantidade de sucessos
- p é a probabilidade de sucesso em uma tentativa
- q é a probabilidade de falha em uma tentativa

<hr>

O estudo de probabilidade nos dá ferramentas interessantes para calcular a chance de ocorrência de diversos tipos de eventos ou combinações de eventos. As fórmulas de algumas distribuições, como a de Poisson, usam informações como a média de ocorrências de um evento ao longo de um intervalo no seu cálculo. 

Portanto, é possível ver que uma questão aparentemente simples como a do título é capaz de abrir inúmeros caminhos para que possamos descobrir como conceitos simples se entrelaçam formando as bases de inúmeros modelos matemáticos do campo das probabilidades.


