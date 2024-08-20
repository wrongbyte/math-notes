#TODO: introdução

O argumento da diagonalização de Georg Cantor funciona através de uma prova por **contradição**. Isso significa que, para provar nosso objetivo, iniciamos a prova assumindo **o oposto do que queremos provar**. No nosso caso, queremos provar que reais não são enumeráveis. Portanto, nossa prova começa assumindo que os reais **são enumeráveis.**

A definição de algo contável - ou enumerável - é um conjunto que tenha correspondência 1:1 com os números naturais. Ou seja, existe uma função **bijetora** que mapeia de um para o outro. Ou seja, para que os reais sejam enumeráveis precisamos de uma função N ↦ R.
### Construindo nossa função
Uma função pode ser definida como um conjunto de pares ordenados. Para cada x, temos um valor y correspondente, por exemplo se tivermos $f(x) = x^{2}$, nosso conjunto de pares será (1, 1), (2, 4), (3, 9) ...
Vamos definir então como seriam os pares ordenados de uma função cujo **domínio** (valores de x) corresponde aos números **naturais** e a **imagem** corresponde aos números **reais**.

**Definição de cada elemento do domínio**
```math
{x\in N}
```
Para gerarmos um valor de x, é simples: o único requerimento é que ele pertença aos números naturais.

**Definição de cada elemento da imagem**
```math
{y_{x} = \sum_{i=1}^{\infty}(0.1)^{i}y_{xi}}
```
Nossa equação representa uma [série infinita](https://edisciplinas.usp.br/pluginfile.php/3597252/mod_resource/content/1/11.2%20S%C3%A9ries.pdf).
A equação descreve a soma de uma série infinita onde cada termo (ou seja, cada valor $y_{x}$ é um dígito aleatório multiplicado por uma potência decrescente de 10. Essencialmente, isso significa que yxyx​ representa um número real com uma sequência infinita de dígitos decimais​. A convenção por trás dessa notação decimal é que **todo número pode ser escrito como uma soma infinita.**
![exemplo pi](https://github.com/user-attachments/assets/e45a5172-243e-4c44-b990-634aa12aff82)

### Nossa função realmente gera números únicos?
Para que nossa função geradora seja válida para que possamos continuar a prova por contradição de que reais são incontáveis, precisamos que essa função gere **valores únicos** (ou seja, cada valor x deve ter um y diferente - isso faz que nossa função seja injetora, um pré-requisito para que ela seja bijetora).

É trivial ver que não possuíremos valores idênticos para valores diferentes de x. Dado que tenhamos dois valores x, por exemplo $x = a$ e $x = b$, supondo que $a$ e $b$ tenham uma quantidade $k$ de dígitos, a probabilidade que essas duas séries de dígitos sejam iguais é:
```math
P(y_{a} = y_{b}) = \frac{1}{10^{k}}
```
Com isso, podemos ver que $\lim_{k \to \infty}  \frac{1}{10^{k}} = 0$, logo, dado que nossa sequência de dígitos seja infinita, a probabilidade de gerarmos dois números repetidos é nula.

#TODO

### referências
[Real numbers and decimal representations](https://personal.math.ubc.ca/~cass/courses/m220/999.pdf)
