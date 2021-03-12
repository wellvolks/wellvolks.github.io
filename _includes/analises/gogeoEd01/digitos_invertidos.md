## 1. - Dígitos invertidos
<div id="digitos_invertidos"></div>

Autor: <font color = "blue">Desconhecido</font>

Resolva este problema: [Hackerrank][hackerrank-e]{:target="_blank"}

O problema fornece um inteiro <code> x </code> de 32 bits e solicita que seja impresso o valor de <code>x</code> com os seus dígitos invertidos.
O único ponto que requer atenção nesse problema está na descrição da saída: "Imprima como saída o valor inteiro x com os seus dígitos invertidos. **A saída também deve ser um inteiro.**". Portanto, se a entrada for <code>10000</code> a saída deve ser um inteiro, ou seja, o valor inteiro <code>1</code> e não <code>00001</code>.
Existem várias formas de resolver. Uma delas segue abaixo:

{% gist wellvolks/981f7d8e781a9ac7a7a83cf569405eb6 welton_digitos_invertidos.cpp %}

[hackerrank-e]: https://www.hackerrank.com/contests/gogeo-problemas-ja-utilizados-em-avaliacoes/challenges/digitos-invertidos
