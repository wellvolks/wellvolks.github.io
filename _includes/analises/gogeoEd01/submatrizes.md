## 7 - Submatrizes
<div id="submatrizes"></div>

Autor: <font color = "blue">Desconhecido</font>

Resolva este problema: [Hackerrank][hackerrank-i]{:target="_blank"}

Dada uma matriz **M** e um inteiro **k** pede-se para que seja informado a quantidade de submatrizes de **M** cuja a soma dos valores contidos dentro dela dá extamente o valor **k**. Uma primeira abordagem seria tentar uma força bruta varrendo todas as submatrizes e computando a soma dos valores. No entanto, tal abordagem não será aceita uma vez que a complexidade ficará **L**x**C**x**L**x**C**x**L**x**C**, como **L** e **C**, no pior caso, podem ter valor **100**, então teremos, no pior caso, complexidade **$100^6$**. Essa solução será aceita. A sacada aqui é perceber que podemos remover um **L**x**C** da complexidade simplismente  pré-computando as somas das submatrizes de **M**. Suponha uma matriz **M**:


Para cada posição **i**,**j** de **M**, com **i** $leqslant$ **L** e **j** $leqslant$ **C**, mantenha a soma de todos os valores de **M\[1]\[1]** até **M\[i]\[j]**. Uma forma de realizar essa soma em **O(L**x**C**x**L**x**C**) é perceber que, apesar de não sabermos a soma de todos os valores de  **M\[1]\[1]** até **M\[i]\[j]**, sabemos de **M\[1]\[1]** até **M\[i]\[j-1]**, **M\[1]\[1]** até **M\[i-1]\[j]** e  **M\[1]\[1]** até **M\[i-1]\[j-1]**. Desta forma, a soma de **M\[1]\[1]** até **M\[i]\[j]** pode ser obtida como segue: **M\[i]\[j]** = **M\[i]\[j-1]** + **M\[i-1]\[j]** +  **M\[i]\[j]**. Note que ao somar os acumulados em **M\[i-1]\[j]** com os em **M\[i]\[j-1]** estaremos computando o acumulado em **M\[i-1]\[j-1]** duas vezes, assim, devemos subtrai-lo:  **M\[i]\[j]** = **M\[i]\[j-1]** + **M\[i-1]\[j]** +  **M\[i]\[j]** - **M\[i-1]\[j-1]** como mostrado na figura abaixo:

Agora, para toda submatriz (**i**,**j**, **k**,**w**), com **i** $leqslant$ **k** e **j** $leqslant$ **w**, pode-se encontrar a soma dos valores dessa submatriz em **O(1)**. A célula **M\[k]\[w]**, como definido anteriormente, terá a soma de todas as células da submatriz (**1**,**1**, **k**, **w**), no entanto, queremos a soma da submatriz (**i**,**j**, **k**,**w**). , ou seja, teriamos que desconsiderar as seguintes submatrizes na soma:

Ao desconsiderar essas duas submatrizes estaremos subtraindo a submatriz (**1**,**1**, **i-1**,**i-1**) duas vezes, entretanto, desejamos desconsiderá-la apenas uma única vez. Assim, devemos somar o acumulado em **M\[i-1]\[i-1]** na resposta. 

Resumindo, para encontrar a soma dos valores de qualquer submatriz (**i**,**j**, **k**,**w**) em **O(1)** basta fazer **soma_submat = (**i**,**j**, **k**,**w**) - ((**1**,**1**, **i-1**,**j**) + (**1**,**1**, **i**,**j-1**)) + (**1**,**1**, **i-1**,**i-1**). Por fim, para resolver o problema devemos percorrer todas as sumatrizes e contar as vezes que **soma_submat** é igual a **k**. 

Um exemplo de implementação segue abaixo:

{% gist wellvolks/83f0af8c89e085074868b5193618e78e welton_submatrizes.cpp %}

[hackerrank-i]: https://www.hackerrank.com/contests/gogeo-problemas-ja-utilizados-em-avaliacoes/challenges/submatrizes
