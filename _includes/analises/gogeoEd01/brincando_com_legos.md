## 10 - Brincando com LEGOs
<div id="brincando_com_legos"></div>

Autor: <font color = "blue">Welton Cardoso</font>

Resolva este problema: [Hackerrank][hackerrank-i]{:target="_blank"}

A parte mais complicada desse problema é conseguir imaginar a escultura que Fulano e Beltrano construíram. Um exemplo de uma escultura segue abaixo:

<img src="https://github.com/wellvolks/wellvolks.github.io/raw/main/_includes/analises/gogeoEd01/imagens/escultura_ok.png" width="200" height="200" />

Uma outra observação importante é que a água pode vazar nas diagonais:

<img src="https://github.com/wellvolks/wellvolks.github.io/raw/main/_includes/analises/gogeoEd01/imagens/escultura_fail.png" width="200" height="200" />

Para cada célula da matriz **A** devemos descobrir qual a maior quantidade (nível) de água que essa célula comporta sem que a água, ao ir preenchendo as deamis células, saía (derrame) de **A**. Uma primeira solução seria, para cada célula de **A**, ir acrecentando água e simulando o preenchimento das demais células de forma que o maior nível que conseguimos alcaçar sem que derrame será o maior nível (altura) possível que essa célula comporta. Somando as alturas em cada célula menos suas alturas iniciais teremos a quantidade de água total que a escultura suporta. No entanto, essa solução apresenta complexidade muito alta O(100*100*100*100*1000000). No entanto, perceba que se é possível chegar a uma altura **x** de água na célula então é possível chegar a uma altura **x-1**, de forma análoga, se não for possível chegar a uma altura **x** então não será possível chegar a uma algura **x+1**. Ou seja, existe um valor limite. Para encontrar esse valor podemos utilizar uma busca binária. Para simular a água percorrendo as demais céluas podemos utilizar uma [busca em largura][https://www.ime.usp.br/~pf/algoritmos_para_grafos/aulas/bfs.html] ou uma [busca em produndidade][https://www.ime.usp.br/~pf/algoritmos_para_grafos/aulas/dfs.html] de forma que se for possível sair de **A** com um nível **mid** então esse nível não pode ser alcançado na célula em  análise. 

Um exemplo de implementação segue abaixo:

{% gist wellvolks/507f5c7c92167262eacad8374b165e3b brincando_com_legos.cpp %}

[hackerrank-i]: https://www.hackerrank.com/contests/gogeo-problemas-ja-utilizados-em-avaliacoes/challenges/submatrizes
