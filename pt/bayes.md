# Teorema de Bayes: pensando com estatística 🐈‍⬛

Suponha que tenhamos um dado de seis faces e o jogamos. 
Como temos 6 possíveis resultados, e cada um desses resultados possui a mesma chance de ocorrer, a probabilidade de obtermos o número 6 é igual a $\frac{1}{6}$.

Contudo, podemos fazer outras perguntas com base nas informações que temos. Qual é a probabilidade de jogarmos nosso dado **duas vezes** e obtermos o número 6 **nas duas vezes**?
### Regras básicas: adição e multiplicação
Para resolver o problema acima, podemos utilizar de duas regras básicas de probabilidade, que envolvem a _adicão_ de probabilidades e a _soma_ de probabilidades.
Quando temos interesse na probabilidade de dois eventos **independentes** ocorrerem, ou seja, A e B, multiplicamos a probabilidade de ocorrência de cada um desses eventos:
```math
 P\left ( A\cap B \right ) = P\left ( A \right ) P\left ( B \right )
```

> :bulb: Note que dois eventos são independentes quando a probabilidade da ocorrência de um não afeta a probabilidade de ocorrência do outro. Falaremos mais sobre em seguida.

Logo, a probabilidade de tirarmos o número seis duas vezes é igual a:
```math
P = \frac{1}{6} \cdot \frac{1}{6} = \frac{1}{36}
```

Ou seja, a chance de tirarmos o número 6 duas vezes é 1 em 36. Porém, podemos mudar de ideia e nos perguntar: qual é a probabilidade de jogarmos nosso dado duas vezes e obtermos o **número 6 ou o número 2**?

Note que temos uma diferença fundamental: na primeira pergunta, estávamos buscando a **probabilidade da ocorrência de dois eventos.** Aqui estamos buscando a probabilidade de **um evento ou outro**, que nesse caso é dada pela fórmula:
```math
 P\left ( A\cup  B \right ) = P\left ( A \right ) + P\left ( B \right ) - P\left ( A  \cap  B \right )
```

Então vamos calcular a probabilidade de ocorrência de $$A\cup  B$$:

```math
P = \frac{1}{6} + \frac{1}{6} - \frac{1}{36}
```
Mas espere: ao jogar o dado uma vez, podemos ter o número 6 **ou** o número 2, sem a possibilidade de obtermos dois números **ao mesmo tempo.** Isso, na prática, significa que nossos dois eventos são **mutuamente exclusivos** e portanto não podemos ter a ocorrência de ambos ao mesmo tempo. Em suma, isso significa que $$P\left ( A  \cap  B \right ) = 0$$.
Ou seja:

```math
P = \frac{1}{6} + \frac{1}{6} = \frac{2}{3}
```
A probabilidade de tirarmos 2 ou 6 no nosso dado é $$\frac{2}{3}$$.

## Fazendo perguntas mais complexas
Suponha que agora temos dois dados. Jogamos o primeiro dado e ele nos dá um número par.
Agora, jogamos o segundo dado e ele nos dá o número 2. Qual a probabilidade dessa situacão ocorrer?

### Probabilidade condicional
Note que no último exemplo, o fato de reduzirmos os resultados possíveis a _apenas os números pares_ influenciou diretamente na probabilidade de obtermos o número 2. Ela dobrou!
Temos nesse caso um exemplo de **probabilidade condicional**. A fórmula para encontrarmos a probabilidade $P(A \mid B)$ é a seguinte:

```math
P(A \mid B) = \frac{P(A \cap B)}{P(B)}
```
> :bulb: PS: a notacão $$P(A \mid B)$$ significa **a probabilidade de A dado B**. Por exemplo, a probabilidade de termos tirarmos o número 2 **dado que** o número que tiramos no primeiro dado é par.

Observe a fórmula acima. Ela nos indica que a probabilidade de A, dado B, é igual a probabilidade da ocorrência de **A e B** sobre a probabilidade da ocorrência de B. Nessa equacão, **assumimos que o evento B ocorreu**, ou seja, nosso espaço amostral se torna reduzido. Podemos dizer que essa é uma _probabilidade a posteriori_, ou seja, uma probabilidade calculada após sabermos novas informacões.

### Usando a fórmula para calcular um caso simples
Vamos imaginar mais um cenário com nosso dado de seis faces. 
Agora, vamos definir dois eventos.

Vamos definir P(A) como sendo a probabilidade de obtermos algum número que pertenca ao conjunto A:
```math
A = \left\{ 1,2,3,4,5\right\} 
```
Podemos seguir a mesma lógica com o conjunto B:
```math
B = \left\{3,4,5,6\right\} 
```
Agora vamos nos perguntar: qual o valor de $P(A \mid B)$?

Você pode ter percebido que esse é um caso tão simples que não necessita que usemos a fórmula da probabilidade condicional, afinal se o evento B ocorreu, sabemos que nosso número está no conjunto B, podendo ser 3,4,5 ou 6.
Nosso espaco amostral então se reduz ao conjunto B. Para calcular a probabilidade do evento A nesse cenário, devemos considerar que só os números {3,4,5} aparecem em B. Portanto, usando esse raciocínio chegamos no resultado:
```math
P(A \mid B) = \frac{3}{4}
```
O que fizemos, indiretamente, foi seguir o mesmo passo a passo da fórmula da probabilidade condicional:
```math
P(A \cap B) = \frac{3}{6}
```

```math
P(A \mid B) = \frac{P(A \cap B)}{P(B)} = \frac{\frac{3}{6}}{\frac{4}{6}} = \frac{3}{4}
```

## O teorema de Bayes
A fórmula da probabilidade condicional que vimos possui uma propriedade interessante. Ao colocarmos a probabilidade da ocorrência de A e B em evidência [(regra da cadeia)](https://github.com/wrongbyte/math-notes/blob/main/pt/chain-rule.md):
```math
P(A \cap B) = P(B) \cdot P(A \mid B)
```
[Notamos que](https://www.hep.upenn.edu/~johnda/Papers/Bayes.pdf):
```math
P(B) \cdot P(A \mid B) = P(A) \cdot P(B \mid A)
```
e com isso chegamos na seguinte igualdade, também chamada de **teorema de Bayes**:
```math
P(A \mid B) = \frac{P(A) \cdot P(B \mid A)}{P(B)}
```

Essa fórmula é equivalente a fórmula da probabilidade condicional, e ambas são usadas para calcularmos a probabilidade da ocorrência de um evento quando sabemos da ocorrência de outro evento. A diferenca fundamental é que a fórmula de Bayes nos dá uma relacão que utiliza de outra probabilidade condicional. Parece muito abstrato? Vamos ver a aplicacão em alguns exemplos.

## Antes de prosseguir: a poção da probabilidade total 🔮🪄
Agora que já sabemos o que é probabilidade condicional e como calculá-la, é hora de imaginar um cenário curioso: suponhamos que exista uma "poção mágica da verdade". Essa poção é usada para descobrir quem é culpado de algum crime;

![potion](https://community.akamai.steamstatic.com/economy/image/a5HYp9Sw61Iks7TiNF57DFqT7uTUsBt13CvwcWpsxqwUkg/360fx360f)

Contudo, esta poção tem um funcionamento específico: **ela funciona 90% das vezes quando aplicada em uma pessoa culpada e 99% das vezes quando aplicada em uma pessoa inocente**. Um suspeito é retirado de um grupo de pessoas, onde 95% jamais cometeram qualquer crime.

Dito isso, temos duas perguntas a responder:

**1 - Qual é a probabilidade de a poção nos dar a resposta certa?**

**2 - Se a poção indica “culpado”, qual é a probabilidade de o suspeito ser
inocente?**


Nesse cenário, temos os seguintes eventos possíveis:

- $C$ = "suspeito culpado"
- $\bar{C}$ = "suspeito inocente"
- $V$ = "poção indicou que o suspeito é culpado"
- $\bar{V}$ = "poção indicou que o suspeito é inocente"

> :bulb: A notacão $\bar{A}$ significa o *complementar* do evento $A$, que é basicamente o evento "não A". Por exemplo, se definirmos $A$ como obter cara no lançamento de uma moeda, $\bar{A}$ seria obter coroa. Note que isso implica que os eventos $A$ e $\bar{A}$ são **mutuamente exclusivos**.

Vamos começar representando os eventos acima em uma árvore:

![árvore das probabilidades](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/bq4v7gy3mtv0atliwh0c.png)

Os cenários onde a pocão nos dá as respostas certas são os destacados em amarelo:

![image](https://github.com/user-attachments/assets/c8481beb-2aa4-4357-9882-e917074de807)

Ou seja, a probabilidade total de termos o resultado correto é a soma da probabilidade dos dois caminhos acima (pois são caminhos mutuamente exclusivos).

```math
P(A) = P(C \cap V) \cup P(\overline{C} \cap \overline{V})
```

Sabemos que a probabilidade da pocão funcionar em um suspeito inocente - $P(\overline{C} \mid \overline{V})$ - é de 99%, e a probabilidade de funcionar em um suspeito culpado - $P(C \mid V)$ - é de 99%. Veja que temos as probabilidades _condicionais_, mas não temos as probabilidades $P(C \cap V)$ e $P(\overline{C} \cap \overline{V})$. Como encontrá-las?

### Regra da cadeia
Dado a fórmula da probabilidade condicional,
```math
P(A \mid B) = \frac{P(A \cap B)}{P(B)}
```
temos a seguinte igualdade:
```math
P(A \cap B) = P(B) \cdot P(A \mid B)
```

Ou seja, 
```math
P(V \cap C) = P(C) \cdot P(V \mid C) = 0.05 \cdot 0.90 = 0.045
```
Outra forma de visualizar isso é transformando nossa árvore de decisão em um grafo ponderado:

![image](https://github.com/user-attachments/assets/c450057a-4326-480b-b996-4970430804cc)

Para sabermos a probabilidade $P(C \cap V)$ multiplicamos os valores de suas arestas, ou seja, $0.05 \cdot 0.90$, que é o equivalente a termos usado a regra da cadeia.
Fazendo o mesmo para $P(\overline{C} \cap \overline{V})$:
```math
P(\overline{V} \cap \overline{C}) = P(\overline{C}) \cdot P(\overline{V} \mid \overline{C}) = 0.95 \cdot 0.99 = 0.9405
```

Somando ambas as probabilidades, obtemos $0.9855$. Ou seja, temos 98,5% de chance de obter o resultado correto com a nossa pocão.

### Lei da probabilidade total
A regra da cadeia é extremamente útil na **lei da probabilidade total**.
Com as informacoes que temos, podemos nos perguntar: **qual a probabilidade da nossa pocao apontar que um suspeito é culpado**? 
Veja que só sabemos as probabilidades condicionais: os valores 90% e 99% são de eventos _condicionados_, ou seja, dependem da probabilidade _a priori_, que é o suspeito ser culpado ou não. Porém, aqui queremos saber a probabilidade **sem saber se o suspeito é culpado ou não**. Como encontrar esse número?

Considerando P(V) como a probabilidade da pocao apontar que o suspeito é culpado:
```math
P(V) = P(C) \cdot P(V \mid C) + P(\overline{C}) \cdot P(V \mid \overline{C})
```
```math
P(V) = 0.05 \cdot 0.90 + 0.95 \cdot 0.01 = 0.0545
```
ou seja, temos 5,45% de chance da nossa pocão indicar que algum suspeito é culpado.
Esse cálculo é a base da **lei da probabilidade total**:
```math
P(A) = P(A\cap B) + P(A \cap \overline{B})
```
utilizando a regra de cadeia:
```math
P(A) = P(B) \cdot P(A\mid B) + P(\overline{B}) \cdot P(A \mid \overline{B})
```

que pode ser generalizado para:
```math
P(A) = \sum_{i=1}^{n} P(A \mid B_i) \cdot P(B_i)
```

## Exemplos práticos com o Teorema de Bayes
Pense no seguinte problema:
> Uma pessoa usa seu carro 30% do tempo, anda a pé 30% do tempo e pega o ônibus 40% do tempo para ir ao trabalho. Ele se atrasa 10% das vezes quando anda a pé; ele se atrasa 3% das vezes quando dirige; e se atrasa 7% das vezes que pega o ônibus.

1 - Qual é a probabilidade de que ele tenha pego o ônibus, dado que se atrasou?

2 - Qual é a probabilidade de que ele tenha andado a pé, dado que chegou no horário?

<hr>
Vamos definir os **eventos**:

- W: a pessoa foi ao trabalho andando
- C: a pessoa foi ao trabalho de carro
- B: a pessoa foi ao trabalho de ônibus
- L: a pessoa se atrasou
- $\overline{L}$: a pessoa chegou no horário

Probabilidades **conhecidas**:

- P(W) = 0,3: 30% das vezes ele vai andando.
- P(C) = 0,3: 30% das vezes ele vai de carro.
- P(B) = 0,4: 40% das vezes ele vai de ônibus.
- P(L|W) = 0,1: Ele se atrasa 10% das vezes que vai andando.
- P(L|C) = 0,03: Ele se atrasa 3% das vezes que vai de carro.
- P(L|B) = 0,07: Ele se atrasa 7% das vezes que vai de ônibus.


1. Qual é a probabilidade de que ele tenha pego o ônibus, dado que se atrasou?
Queremos encontrar P(B∣L).

Pelo Teorema de Bayes:
```math
P(B|L) = \frac{P(L|B) \cdot P(B)}{P(L)}
```

Primeiro, precisamos encontrar P(L), a probabilidade de que ele se atrase. Esta é a probabilidade total de ele se atrasar, considerando todas as formas de transporte:

```math
P(L) = P(L|W) \cdot P(W) + P(L|C) \cdot P(C) + P(L|B) \cdot P(B)
```

Substituindo os valores:

```math
P(L) = (0,1 \cdot 0,3) + (0,03 \cdot 0,3) + (0,07 \cdot 0,4)
```
```math
P(L) = 0,03 + 0,009 + 0,028 = 0,067
```
Agora, substituímos na fórmula de Bayes para encontrar P(B∣L):

```math
P(B|L) = \frac{P(L|B) \cdot P(B)}{P(L)}
```
```math
P(B|L) = \frac{0,07 \cdot 0,4}{0,067}
```
```math
P(B|L) \approx \frac{0,028}{0,067} \approx 0,418
```

Portanto, a probabilidade de que ele tenha pego o ônibus, dado que se atrasou, é aproximadamente 41,8%.
A segunda questão fica como exercício para o leitor.

### Referências
[Lista de exercícios na íntegra](https://mathcenter.oxford.emory.edu/site/math117/probSetBayesTheorem/)

https://byjus.com/maths/multiplication-rule-probability/#:~:text=What%20is%20the%20Multiplication%20Rule,given%20that%20event%20B%20occurs.

https://www.hep.upenn.edu/~johnda/Papers/Bayes.pdf

https://cesad.ufs.br/ORBI/public/uploadCatalago/10161710102012Probabilidade_e_Estatistica_aula_9.pdf
