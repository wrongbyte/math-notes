# Teorema de Bayes: pensando com estatística

Dado que tenhamos um dado de seis faces e o jogamos, sabemos que temos 6 possíveis resultados, e sabemos também que cada um desses resultados possui a mesma chance de ocorrer. 

Por exemplo, a probabilidade de obtermos o número 6 é igual a $$\frac{1}{6}$$.
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
Vamos jogar um jogo de advinhação.

Supondo que jogamos o dado uma vez, e o resultado foi **um número par**, qual a probabilidade desse número ser 2?
A primeira etapa lógica para resolver esse exercício é reduzir nosso espaco amostral de 
```math
S = \left\{ 1,2,3,4,5,6\right\} 
```
para
```math
S = \left\{ 2,4,6\right\} 
```

Ou seja, sabemos que dos seis números iniciais, apenas três são pares. Portanto, calculamos nossa probabilidade com base nessa informacão, obtendo o resultado $$\frac{1}{3}$$.

## Probabilidade condicional
Note que no último exemplo, o fato de reduzirmos os resultados possíveis a _apenas os números pares_ influenciou diretamente na probabilidade de obtermos o número 2. Ela dobrou!
Temos nesse caso um exemplo de **probabilidade condicional**.

```math
P(A \mid B) = \frac{P(A \cap B)}{P(B)}
```
> :bulb: PS: a notacão $$P(A \mid B)$$ significa **a probabilidade de A dado B**. Por exemplo, a probabilidade de termos tirarmos o número 2 **dado que** o número que tiramos é par.

Observe a fórmula acima. Ela nos indica que a probabilidade de A, dado B, é igual a probabilidade da ocorrência de **A e B** sobre a probabilidade da ocorrência de B. Nessa equacão, **assumimos que o evento B ocorreu**, ou seja, nosso espaço amostral se torna reduzido. Como no último exemplo, se antes tínhamos 6 números possíveis, agora passamos a ter apenas 3, porque **sabemos que o número tirado é um número par.** Podemos dizer que essa é uma _probabilidade a posteriori_, ou seja, uma probabilidade calculada após sabermos novas informacões.

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
A fórmula da probabilidade condicional que vimos possui uma propriedade interessante. Ao colocarmos a probabilidade da ocorrência de A e B em evidência:
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

## Utilizando o teorema de Bayes na prática
TODO

### Referências
https://byjus.com/maths/multiplication-rule-probability/#:~:text=What%20is%20the%20Multiplication%20Rule,given%20that%20event%20B%20occurs.

https://www.hep.upenn.edu/~johnda/Papers/Bayes.pdf
