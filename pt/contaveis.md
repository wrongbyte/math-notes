Antes de falar de matemática, suponha que você tenha uma array, em Javascript.

> :warning: **Para esse post, vamos fingir que nossa array não possa ter elementos repetidos**. Em JS, temos um tipo de dado exclusivo para este fim: [Sets](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set). Contudo, a API de um `Set` não possui nativamente meios de acessar um elemento pelo seu índice, portanto para fins de simplicidade, vamos utilizar arrays partindo do pressuposto que elas **não contenham nenhum elemento repetido.**

## Infinitos contáveis
```js
const myArray = [1, 2, 3, 4, 5]
```
Essa array possui 5 elementos; todos números entre 1 e 5. Caso você queira acessar o número 3, podemos acessá-lo pelo índice 2.

```js
const myNumber = myArray[2]
console.log(myNumber) // 3
```
Nossa array `myArray`, assim como todas as arrays, possui _índices_, que são basicamente labels atreladas a cada elemento. Esse índice começa do zero e vai até a quantidade de elementos da array - 1.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/m53vm6rw1x2bfy8bpvwq.png)



Agora suponha o seguinte cenário: temos um computador com memória infinita. Nele, resolvemos criar uma array que contém _todos os números existentes_, começando a partir de 1. **Lembre-se que nossa array não contém nenhum número repetido**.

```js
const myInfiniteArray = [1, 2, 3, ...] //array infinita!
```

Veja que nossa array, _teoricamente_, é infinita, afinal a quantidade de números existentes é infinita. Mas ainda assim, **cada elemento terá seu índice correspondente**. Nossa array é **contável**.

### um pouco de matemática
Vamos traduzir nossa array de JS para a linguagem matemática. 
Podemos pensar em `myArray` como um **conjunto**. Então, em vez de 
```js
const myArray = [1, 2, 3, 4, 5]
```
teremos
```
S = {1, 2, 3, 4, 5}
```

onde S é o nome do nosso conjunto, e {1, 2, 3, 4, 5} são os elementos dele. Quando dizemos que podemos _atribuir um índice_ aos elementos da nossa array, o que estamos dizendo é que **existe uma bijeção entre S e N** (conjunto dos números naturais).

### O que é uma bijeção?
![tipos de funcoes](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/64616vv3fv6oyxn9evvu.png)
Imagine uma função simples f(x) = y.
Na matemática, dividimos funções com base em propriedades que elas possuem. Quando acessamos os itens da nossa array, usamos o índice do elemento para encontrar o elemento em si. Isso é uma função!
//imagem funcao

Porém, temos algumas restrições para nossa função.
- Não podemos ter mais de um índice igual. Índices são uma maneira de contar nossos elementos, logo, não faria sentido contar "1, 2, 3, 3, 4..."
- Cada índice corresponde a exatamente um elemento. Se tentarmos acessar `myArray[10]` em uma array com 5 elementos, receberemos um erro, afinal o índice 10 não corresponde a nenhum elemento. Da mesma forma, ao acessar `myArray[1]`, temos apenas **um elemento** que possui esse índice correspondente.
- Os índices são números **inteiros positivos**. Ou seja, não temos um índice 0.5 ou um índice -2.

As propriedades acima nos levam ao determinado modelo:

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1vlfo2l0m2pjze6rf28r.png)

onde X é o _conjunto_ que contém os elementos da nossa array e Y é o _conjunto_ de todos os índices possíveis para a nossa array. Essa é uma função **bijetiva** (injetiva e sobrejetiva), ou seja, uma correspondência de 1 para 1.

![set](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/mdk1vhg2e1p3jseet0ds.png)
Isso, em palavras simples, significa que podemos _contar_ os elementos da nossa array, mesmo que a quantidade de elementos que ela possui seja infinita. Nossa array é um **conjunto infinito contável.**

> :bulb: Veja que o conceito de "contar" se refere à **atribuir um índice a um elemento**, tal como fazemos na vida real (exemplo: quando contamos de 1 a 10, basicamente listamos os números de 1 a 10). Matematicamente, poder contar os elementos de um conjunto **não é o mesmo** que saber o **tamanho** do conjunto. Por isso, podemos contar infinitos, mesmo que o número total de elementos de um conjunto infinito não corresponda a um número natural. A **quantidade** de elementos em um conjunto, ou tamanho do conjunto, é chamada de [cardinalidade](https://pt.wikipedia.org/wiki/Cardinalidade). Vamos entender um pouco mais desse conceito em seguida.

### Outros infinitos contáveis
Atendendo à condição de que nossa array infinita não tivesse elementos repetidos, poderíamos criar as seguintes arrays infinitas, onde N representa o índice de cada elemento:
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ugzamiel1yvo9cuj6h4o.png)
Do ponto de vista matemático, cada um desses conjuntos é um conjunto infinito contável, porque temos uma correspondência 1-1 entre cada elemento do conjunto e um número natural (o equivalente ao índice da array). 

### Infinitos maiores que outros
É possível que um infinito seja maior que outro? 
Pense na seguinte questão: temos um conjunto contendo todos os números naturais, e outro conjunto contendo todos os _quadrados_ de números naturais. Alguns números são quadrados: 
1² = 1, 2² = 4, 3² = 9
Porém, se pensarmos em uma lista com todos os números inteiros, vemos que _a maioria deles não são quadrados de outros números._ Logo, podemos dizer que a _cardinalidade_ do conjunto de quadrados de números inteiros é menor do que a do conjunto dos números inteiros. Contudo, se tivermos uma função no formato `x -> x²`, ambos os conjuntos aparentam ter a mesma quantidade de membros:
![paradoxo galileu](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/n2brcl95d36qtc513g5i.png)
Essa aparente contradição foi descoberta por Galileo Galilei e é chamada de [paradoxo de Galileo](https://en.wikipedia.org/wiki/Galileo%27s_paradox). Na verdade, o que isso demonstra é que o conjunto contendo todos os x² é contável, ou seja, possui uma bijeção com os naturais. Portanto, apesar de soar contraditório, o conjunto x e o conjunto x² _possuem o mesmo tamanho_: ℵ0. Este número é chamado de [álefe-nulo](https://simple.wikipedia.org/wiki/Aleph_null)) e representa a <u>cardinalidade</u> do conjunto dos naturais. Todo conjunto infinito contável possui a cardinalidade ℵ0, por ter uma bijeção com o conjunto dos naturais.
> :bulb: ℵ0 é a cardinalidade dos números naturais, e considerado o "menor infinito" (ou seja, nenhum conjunto infinito tem cardinalidade menor que ℵ0).

## Infinitos incontáveis
Contudo, nem todos os conjuntos infinitos são contáveis.
Imagine que queremos enumerar **todos os números reais** existentes no intervalo entre 0 e 1. Isso é possível?
A resposta é **não.** Não existe uma correspondência 1-1 entre todos os números no intervalo [0,1] e o conjunto dos naturais, porque **existem mais números reais do que números naturais**. Portanto, entre 0 e 1 existem _infinitos_ números, mas não podemos contá-los. Esse é um exemplo de **infinito incontável.**

## Por que existem mais números reais do que números naturais?
### A reta numérica dos naturais
Os conjunto dos números naturais é composto por números **inteiros e positivos**. Ou seja, -1 não é um número natural, 1.45 e 1.99999... também não o são. Podemos listar os números naturais em uma reta:
![reta naturais](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/d74hivred1dcz10otmzn.png)
Veja que entre cada número, temos um espaço. Sabemos que existem números entre `n` e `n + 1`, porém eles não são números naturais, ou seja, ao colocar os números naturais em uma linha, temos um "gap" entre um número e o seu sucessor.

### A reta numérica dos reais
Contudo, se fizermos o mesmo com os números reais, o resultado é diferente, porque _todos_ os números entre `n` e `n + 1` **são números reais**. Vamos listar todos os números reais entre 1 e 2:
![real line](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/c4ethpl2cdv1jwzr4mal.png)
Podemos começar incrementando 0.10 entre cada número:
![numeros entre 1 e 2](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/dfrktqzbzn0fdean8pdb.png)
Contudo, entre cada um dos números, existem outros números:
![entre 1.10 e 1.20](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/fxmkohnepfvemx34xi4t.png)
E ainda mais números:

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ng14e21vi0v4on7drjke.png)
E assim por diante. Podemos dividir um número real infinitamente, e continuaremos encontrando novos números entre cada um deles, [porque não existem "espaços" entre um número e outro](https://en.wikipedia.org/wiki/Completeness_of_the_real_numbers). Essa é uma propriedade fundamental do conjunto dos números reais.

// TODO: improve?
Com isso podemos ver que o conjunto dos números naturais é um _subconjunto próprio_ dos números reais, porque todo número natural é um número real, porém nem todo número real é um número natural. Na imagem abaixo, B representa o conjunto R e A o conjunto N.
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/0zjiuy4k9qdrono9aw35.png)
> :bulb: Um subconjunto A de um conjunto B é considerado um subconjunto próprio se todos os elementos de A estão em B, mas existe pelo menos um elemento em B que não está em A.
Você talvez lembre-se de ter visto a imagem abaixo em alguma aula de matemática na escola. Ela traz a relação entre os conjuntos numéricos:
![conjuntos numericos](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/v5ibzp0g0hdc5onkst6i.png)

Por essa definição, sabemos que R contém mais elementos do que N. Mas como provar isso?
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/v3mj4cih281x4b21kc84.png)

## O teorema de Cantor
A prova mais conhecida que nos mostra que não podemos enumerar os números reais é o [argumento de diagonalização de Cantor](https://pt.wikipedia.org/wiki/Argumento_de_diagonaliza%C3%A7%C3%A3o_de_Cantor). A ideia principal dessa prova é mostrar que sempre que criarmos uma lista com os números reais (ou seja, enumerarmos os reais), haverá algum número real que **não está nessa lista**. Em termos matemáticos, **não existe uma sobrejeção de N para R**.

Podemos ver esse argumento em ação, utilizando o **teorema de Cantor**:
> Para cada conjunto S, o conjunto das partes de S, ou seja, o conjunto de todos os subconjuntos de S (aqui escrito como P(S)), tem uma cardinalidade maior do que o próprio S.
Vamos supor que tenhamos um conjunto A:

```math
A = \left\{  1, 2, 3, 4, 5  \right\}
```
Vamos considerar um conjunto arbitrário de A (por exemplo, {1, 3}) e chamá-lo de B, e assumir (por contradição) que exista uma função que mapeie elementos de B para A (ou seja, de um subconjunto de A para A).


```math
f: B \to A
```

Para que essa função possa existir, precisamos que _todos os elementos de B estejam em A_, afinal de contas, B é um subconjunto de A. Logo, se A contém os números 1, 2, 3, 4 e 5, qualquer elemento do conjunto B deve ser, obrigatoriamente, um dos números de A.

### Powersets: conjunto das partes
O conjunto A possui 32 subconjuntos ($2^{5}$). Vamos criar um conjunto que contenha todos esses subconjuntos e tentar fazer o mesmo que fizemos acima. Vamos supor que exista uma função que mapeie de elementos de A para subconjuntos de A.

Isso implicaria que, _para cada **subconjunto** de A, temos um **elemento** em A correspondente_, e vice-versa.
Logo, podemos imaginar os seguinte cenários:
Podemos ter alguns cenários possíveis, como por exemplo:
```math
f(1) = \left\{  1, 2, 3  \right\}
```
ou
```math
f(3) = \left\{  5, 2  \right\}
```
Veja que há uma diferença fundamental nos dois casos: no primeiro, o número 1 está também no conjunto para o qual f(1) mapeia. No segundo caso, o número 3 não está no conjunto para o qual f(3) mapeia.
Vamos tentar listar todos os conjuntos similares ao segundo caso. Vamos tentar montar um conjunto X:

```math
X = \left\{ x \in A: x \notin f(x)\right\}
```

A definição de X é: cada elemento x deve estar em A, mas não deve estar em f(x). Tal como 3 não está em f(3) no exemplo que vimos.

### Quais elementos de A estão em X?
Vamos assumir que $f: A \to B$ é bijetiva. Se nossa função de A para P(A) é bijetiva, todo subconjunto de A corresponde a um elemento de A e todo elemento de A corresponde a um subconjunto de A.
Contudo,



// TODO

Referências 
https://jlmartin.ku.edu/~jlmartin/courses/math410-S09/cantor.pdf
https://www.mathpages.com/home/kmath371/kmath371.htm
https://mathcs.org/analysis/reals/infinity/countble.html
http://www.people.vcu.edu/~rhammack/BookOfProof/Main.pdf#page=281
https://www.reddit.com/r/learnmath/comments/11b28dj/can_someone_explain_why_cantors_diagonal_argument/?chainedPosts=t3_193e0hw
https://math.vanderbilt.edu/schectex/courses/infinity.pdf
http://legacy.earlham.edu/~peters/writing/infapp.htm
