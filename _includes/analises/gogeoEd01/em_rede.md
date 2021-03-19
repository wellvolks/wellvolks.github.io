## 11 - Em rede
<div id="em_rede"></div>

Autor: <font color = "blue">Welton Cardoso</font>

Resolva este problema: [Hackerrank][hackerrank-i]{:target="_blank"}

Dois computadores estão diretamente conectados se o ID de um deles é prefixo do outro ID. Deseja-se descobrir se dois computadores estão na mesma rede e o tamanho da rede em que estão conectados. Uma rede pode ser vista como um conjunto. Dois computadores estão conectados se pertencerem ao mesmo conjunto. O tamanho da rede é o tamanho do conjunto. Nesse sentido, podemos resolver esse problema com uma estrutura de dados chamada [Union-Find](https://www.geeksforgeeks.org/union-find/). Para verificar de forma rápida se um computador tem seu ID como prefixo de outro computador pordemos utilizar uma árvore chamada [Trie](https://www.geeksforgeeks.org/trie-insert-and-search/). Na Trie podemos manter em cada nó que prepresenta um final de string a qual conjunto esse ID pertence. Assim, ao adicionar um novo ID na Trie, basta adicionar esse computador nos conjuntos ao longo dos nós que compartilham os mesmos caracteres do seu ID.

Ao inserir um ID na Trie basta adicionar esse computador no conjunto 

Um exemplo de implementação segue abaixo:

{% gist wellvolks/18489592dd06032015f137a46ad3d321 welton_em_rede.cpp %}

[hackerrank-i]: https://www.hackerrank.com/contests/gogeo-problemas-ja-utilizados-em-avaliacoes/challenges/em-rede
