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

```math
P = \frac{1}{6} + \frac{1}{6} = \frac{2}{3}
```

## Fazendo perguntas mais complexas



### Referências
https://byjus.com/maths/multiplication-rule-probability/#:~:text=What%20is%20the%20Multiplication%20Rule,given%20that%20event%20B%20occurs.
