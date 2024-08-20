#TODO: introdução

O argumento da diagonalização de Georg Cantor funciona através de uma prova por **contradição**. Isso significa que, para provar nosso objetivo, iniciamos a prova assumindo **o oposto do que queremos provar**. No nosso caso, queremos provar que reais não são enumeráveis. Portanto, nossa prova começa assumindo que os reais **são enumeráveis.**

A definição de algo contável - ou enumerável - é um conjunto que tenha correspondência 1:1 com os números naturais. Ou seja, existe uma função **bijetora** que mapeia de um para o outro. Ou seja, para que os reais sejam enumeráveis precisamos de uma função N ↦ R.
### Construindo nossa função
Uma função pode ser definida como um conjunto de pares ordenados. Para cada x, temos um valor y correspondente, por exemplo se tivermos f(x) = x^2, nosso conjunto de pares será (1, 1), (2, 4), (3, 9) ...
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
Em suma, para cada valor x, definimos o valor y correspondente como
