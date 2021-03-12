## 1. - Dígitos invertidos
<div id="digitos_invertidos"></div>

Autor: <font color = "blue">Desconhecido</font>

Resolva este problema: [Hackerrank][hackerrank-e]{:target="_blank"}

O problema fornece um inteiro <b>x</b> de 32 bits e solicita que seja impresso o valor de <b>x</b> com os seus dígitos invertidos.
O único ponto que requer atenção nesse problema está na descrição da saída: "Imprima como saída o valor inteiro <b>x</b> com os seus dígitos invertidos. **A saída também deve ser um inteiro**". Por exemplo, suponha o valor <b>10000</b> como entrada e a saída deverá ser um inteiro que represente <b>10000</b> com os dígitos invertidos, ou seja, o valor inteiro <b>1</b> e não <b>00001</b>. Dessa forma, se a leitura de <b>x</b> for feita como string a inversão simples da mesma não é será uma solução 100% aceita.
Existem várias formas de resolver. Uma delas segue abaixo:

{% gist wellvolks/981f7d8e781a9ac7a7a83cf569405eb6 welton_digitos_invertidos.cpp %}

[hackerrank-e]: https://www.hackerrank.com/contests/gogeo-problemas-ja-utilizados-em-avaliacoes/challenges/digitos-invertidos
