## 8 - Produto máximo
<div id="produto_maximo"></div>

Autor: <font color = "blue">Desconhecido</font>

Resolva este problema: [Hackerrank][hackerrank-i]{:target="_blank"}

Para todas as possibilidades de dividir **n** queremos encontrar a que tem o maior produto entre os números nessa divisão. A quantidade de possibilidades de dividir **n** é muito grande. Uma forma de verificar todas essas possibilidade de forma rápida é através da utilização da [programação dinâmica](https://www.ime.usp.br/~pf/analise_de_algoritmos/aulas/dynamic-programming.html). 

Para todo valor **n** devemos verificar todas as possibilidades de divisão de **n** em valores cuja a soma dê extamente **n** e a multiplicação desses valores seja o máximo possível. Por exemplo, em uma iteração podemos dividir **n** em  **1 + (n - 1)**, **2 + (n - 2)**, ... , **i + (n - i)**, com **1** ⩽ **i** < **n**. Da mesma forma, podemos pegar o valor de **(n-i)** e dividi-lo. O caso base então será quando **n** chegar ao valor **1**, não sendo mais possível dividi-lo. Para qualquer possibilidade que testarmos devemos multiplicar a resposta dessa divisão por **i** já que **i** está sendo considerado na divisão de **n**. Desejamos, dentre todas as possibilidades de divisão, o maior valor possível. Assim, temos que **divisao\[n\] = max(divisao\[n\], divisao[n - i] * i) para 1** $\leqslant$ **i** < **n**.

Um exemplo de implementação segue abaixo:

{% gist wellvolks/1d8d8ba4ca27bdadb9fd9f3e4cbda19f welton_produto_maximo.cpp %}

[hackerrank-i]: https://www.hackerrank.com/contests/gogeo-problemas-ja-utilizados-em-avaliacoes/challenges/produto-maximo
