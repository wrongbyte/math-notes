## O que é "probabilidade condicional" e qual sua utilidade? 🎲

Probabilidade condicional se refere à **probabilidade da ocorrência de um evento A**, dado que **sabemos que um evento B ocorreu**. Um exemplo simples é quando temos um dado de seis faces e nos perguntamos qual a probabilidade de tirarmos o número 2. Bom, se temos 6 números igualmente possíveis e queremos saber a probabilidade de tirarmos um deles (o número 2), logo nossa probabilidade é de $\frac{1}{6}$. 

Porém o que acontece se adicionarmos uma nova informacão ao problema? Vamos supor que agora temos dois dados. Alguém jogou o primeiro dado e nos disse que o resultado foi *um número par*.
**Qual a probabilidade de obtermos o número 2 ao jogar o segundo dado após obter um número par no primeiro dado?** Note que ambos os eventos são *independentes*, ou seja, não interferem um no outro, mas como agora temos uma combinacão de resultados, é trivial imaginar que a probabilidade dessa combinacão vai ser menor do que a probabilidade de um ou outro evento separado. 

> [!TIP]  
> Ainda que contraditório, é comum que as pessoas imaginem que a probabilidade de dois eventos A e B ocorrerem é maior do que a probabilidade de somente A ou somente B. Veja: [Conjunction Fallacy](https://en.wikipedia.org/wiki/Conjunction_fallacy)

### Como encontrar a probabilidade condicional?
Para situacões desse tipo, temos uma equacão extremamente útil:
```math
P(A \mid B) = \frac{P(A \cap B)}{P(B)}
```
A probabilidade de A dado B é igual a probabilidade de A e B sobre a probabilidade de B.
Substituindo os valores com o nosso exemplo do dado, obtemos:

> B = probabilidade de tirar um número par no primeiro dado
> 
> A = probabilidade de tirar o número 2 no segundo dado

```math
P(A \mid B) = \frac{P(\frac{1}{6} \cdot \frac{1}{2})}{P(\frac{1}{2})} = \frac{1}{6}
```

### Qual a diferenca entre a probabilidade de A e B, ou P(A,B) e a probabilidade de A dado B, ou P(A|B)?
![image](https://github.com/user-attachments/assets/d36db160-ad59-465f-b08d-a4f45c633e54) 

Na imagem[¹](https://chrispiech.github.io/probabilityForComputerScientists/en/part1/cond_prob/) acima, temos 50 hexágonos no total. Esse é o nosso _espaco amostral_, ou seja, todas as possibilidades existentes. A chance de termos E **e** F é de $\frac{3}{50}$, se considerarmos _todos os 50 hexágonos_:
```math
P(E \cap F) = \frac{3}{50}
```
Contudo, quando queremos calcular a probabilidade de um evento acontecer **dado que outro evento já aconteceu**, nosso espaco amostral se torna reduzido: consideramos apenas o universo onde o primeiro evento ocorreu. Isso, no exemplo da imagem, significa que se quisermos calcular $P(E \mid F)$ estamos calculando a probabilidade de B dado que F ocorre:
```math
P(A \mid B) = \frac{P(\frac{3}{50})}{P(\frac{14}{50})} = \frac{3}{14} 
```
Ou seja, podemos pensar que a probabilidade condicional P(A|B) é basicamente a probabilidade P(A,B) reduzida para o espaco amostral de B.

### Regra da cadeia

A fórmula que vimos acima é uma igualdade, ou seja, podemos obter a relacao abaixo a partir dela:
```math
P(B) \cdot P(A \mid B) = P(A \cap B)
```
Agora conseguimos encontrar a probabilidade de A e B ocorrerem se soubermos a probabilidade P(A | B)! Isso se torna extremamente útil quando falamos sobre a [lei da probabilidade total](https://en.wikipedia.org/wiki/Law_of_total_probability). Podemos visualizar como a fórmula acima funciona utilizando árvores de decisão:

![decision tree](https://github.com/user-attachments/assets/8005a326-0a8b-4bed-8cce-00f80e48f1d7)

No exemplo acima[²](https://www.youtube.com/watch?v=7t9jyikrG7w), temos três máquinas, e sabemos a probabilidade delas serem defeituosas. Por exemplo, sabemos que a chance da máquina 1 ser defeituosa é 0.7. Isso seria equivalente a $P(D|M_{1}) = 0.7$. 
Dado que temos a probabilidade de a máquina 1 ser defeituosa, e sabemos a probabilidade de usar a máquina 1 ($P(M_{1}) = 0.6$), podemos multiplicar as probabilidades e obtemos 
```math
P(D \cap M_{1}) = P(M{1}) \cdot P(D \mid M_{1}) = 0.7 \cdot 0.5 = 0.35
```

### Referências
1 - https://chrispiech.github.io/probabilityForComputerScientists/en/part1/cond_prob/

2 - https://www.youtube.com/watch?v=7t9jyikrG7w
