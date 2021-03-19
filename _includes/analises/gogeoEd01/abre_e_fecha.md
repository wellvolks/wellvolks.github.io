## 6 - Abre e fecha
<div id="abre_e_fecha"></div>

Autor: <font color = "blue">Desconhecido</font>

Resolva este problema: [Hackerrank][hackerrank-i]{:target="_blank"}

Este problema pode ser resolvido de forma simples com o auxílio de uma [pilha](https://www.ime.usp.br/~pf/algoritmos/aulas/pilha.html). Para cada caractere do tipo abre "**(**, **\[**, **{**" devemos empilhar. Para cada caractere do tipo fecha "**)**, **]**, **}**" devemos verificar se o caractere que se encontra no topo da pilha é exatamente um caractere do tipo abre e que combine com o que está fechando, ou seja, "**(** com **)**, **\[** com **]** e **{** com **}**". No final, basta verificar se a pilha está vazia, se tiver então quer dizer que conseguimos satisfazer as condições apresentadas no enunciado e, portanto, deve-se imprimir "valida" ou invalida caso contrário.

Um exemplo de implementação segue abaixo:

{% gist wellvolks/6a1cf3fb6d74936ba33435d2475ee33a welton_abre_e_fecha.cpp %}

[hackerrank-i]: https://www.hackerrank.com/contests/gogeo-problemas-ja-utilizados-em-avaliacoes/challenges/abre-e-fecha
