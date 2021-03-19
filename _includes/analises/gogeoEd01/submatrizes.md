## 7 - Submatrizes
<div id="submatrizes"></div>

Autor: <font color = "blue">Desconhecido</font>

Resolva este problema: [Hackerrank][hackerrank-i]{:target="_blank"}

Dada uma matriz **M** e um inteiro **k** pede-se para que seja informado a quantidade de submatrizes de **M** cuja a soma dos valores contidos dentro delas deem extamente um valor **k**. Uma primeira abordagem seria tentar uma força bruta varrendo todas as submatrizes e computando a soma dos valores. No entanto, tal abordagem não será aceita uma vez que a complexidade ficará **L * C * L * C * L * C**, como **L** e **C**, no pior caso, tendo valor **100** a  complexidade ficará O(**1000000**). Essa solução não será aceita. A sacada aqui é perceber que podemos remover um **L * C** da complexidade simplismente  pré-computando as somas das submatrizes de **M**. Suponha uma matriz **M**:

<img src="https://github.com/wellvolks/wellvolks.github.io/raw/main/_includes/analises/gogeoEd01/imagens/mat_M.png" width="200" height="200" />

Para cada posição **i**,**j** de **M**, com **i** ⩽ **L** e **j** ⩽ **C**, mantenha a soma de todos os valores de **M\[1]\[1]** até **M\[i]\[j]**. Uma forma de realizar essa soma em **O(L * C * L * C**) é percorrer as colunas depois as linhas, ou sea, primeiro as células **M\[1]\[1]**, **M\[1]\[2]**, ... , **M\[1]\[C]** depois as células **M\[2]\[1]**, **M\[2]\[2]**, ... , **M\[2]\[C]** e assim por diante até **M\[L]\[C]**. Dessa forma, ao chegar na célula **M\[i]\[j]**  já teremos computado a soma dos valores de **M\[1]\[1]** até **M\[i]\[j-1]**, **M\[1]\[1]** até **M\[i-1]\[j]** e  **M\[1]\[1]** até **M\[i-1]\[j-1]**. Desta forma, a soma de **M\[1]\[1]** até **M\[i]\[j]** pode ser obtida como segue: **M\[i]\[j]** = **M\[i]\[j-1]** + **M\[i-1]\[j]** +  **M\[i]\[j]**. Note que ao somar os acumulados em **M\[i-1]\[j]** com os de **M\[i]\[j-1]** estaremos computando o acumulado de **M\[i-1]\[j-1]** duas vezes, assim, devemos subtrai-lo para que tenhamos o acumulado correto:  **M\[i]\[j]** = **M\[i]\[j-1]** + **M\[i-1]\[j]** +  **M\[i]\[j]** - **M\[i-1]\[j-1]** como mostrado nas figuras abaixo:

<img src="https://github.com/wellvolks/wellvolks.github.io/raw/main/_includes/analises/gogeoEd01/imagens/mat_pre.png"  width="200" height="200" />
<img src="https://github.com/wellvolks/wellvolks.github.io/raw/main/_includes/analises/gogeoEd01/imagens/mat_pre2.png" width="200" height="200" />
<img src="https://github.com/wellvolks/wellvolks.github.io/raw/main/_includes/analises/gogeoEd01/imagens/mat_pre3.png" width="200" height="200" />

Agora, para toda submatriz (**i**,**j**, **k**,**w**), com **i** ⩽ **k** e **j** ⩽ **w**, pode-se encontrar a soma dos valores dessa submatriz em **O(1)**. A célula **M\[k]\[w]**, como definido anteriormente, terá a soma de todas as células da submatriz (**1**,**1**, **k**, **w**), no entanto, devemos olhar todas as submatrizes. Dessa forma, precisamos descobrir o acumulado para uma submatriz generica (**i**,**j**, **k**,**w**). Suponha a seguinte submatriz **m** de **M**:

<img src="https://github.com/wellvolks/wellvolks.github.io/raw/main/_includes/analises/gogeoEd01/imagens/mat_sub.png"  width="200" height="200" />

Nota-se que essa submatriz tem o acumulado de duas outras submatrizes, **m'** e **m''**:

<img src="https://github.com/wellvolks/wellvolks.github.io/raw/main/_includes/analises/gogeoEd01/imagens/mat_mm.png"  width="600" height="200" />

Ao desconsiderar essas duas submatrizes teremos o valor correto para a submatriz que desejamos. No entanto, estaremos subtraindo a submatriz (**1**,**1**, **i-1**,**i-1**) duas vezes. Portanto, para que tenhamos realmente o acumulado correto para a submatriz **m** devemos adicionar o acumulado de **M\[i-1]\[i-1]** na resposta:

<img src="https://github.com/wellvolks/wellvolks.github.io/raw/main/_includes/analises/gogeoEd01/imagens/mat_calc.png" width="316.47" height="200" />

Assim, de forma geral, para encontrar o acumulado de qualquer submatriz (**i**,**j**, **k**,**w**) em **O(1)** basta computar da seguinte forma **soma_submat = (**i**,**j**, **k**,**w**) - ((**1**,**1**, **i-1**,**j**) + (**1**,**1**, **i**,**j-1**)) + (**1**,**1**, **i-1**,**i-1**). Por fim, para resolver o problema devemos percorrer todas as sumatrizes e contar a quantidade de vezes que **soma_submat** é igual a **k**. 

Um exemplo de implementação segue abaixo:

{% gist wellvolks/83f0af8c89e085074868b5193618e78e welton_submatrizes.cpp %}

[hackerrank-i]: https://www.hackerrank.com/contests/gogeo-problemas-ja-utilizados-em-avaliacoes/challenges/submatrizes
