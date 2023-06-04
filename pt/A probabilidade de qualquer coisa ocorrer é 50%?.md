Vez ou outra, é comum ouvirmos que não faz sentido dizer que a probabilidade de algo ocorrer é, digamos, 0,00625%: só há a probabilidade do evento ocorrer ou não. São os únicos cenários possíveis.
Mas será que essa afirmação é realmente correta? Vamos descobrir.

## Parte 1: o que é a probabilidade de algo?
Um dos conceitos fundamentais da chamada probabilidade clássica é o que chamamos de *ponto amostral*. Um ponto amostral nada mais é do que o resultado *possível* e *único* de um experimento aleatório.
Por exemplo, vamos imaginar que temos um dado de seis faces. Nesse caso, temos exatamente seis resultados possíveis: 1, 2, 3, 4, 5, 6. Cada um desses números é um **ponto amostral**.

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
- um evento `x` ocorrer, dado que esse evento ocorre em média `λ` vezes
