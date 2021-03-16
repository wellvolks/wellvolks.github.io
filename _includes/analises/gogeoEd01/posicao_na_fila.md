## 9. - Posição na fila
<div id="posicao_na_fila"></div>

Autor: <font color = "blue">Welton Cardoso</font>

Resolva este problema: [Hackerrank][hackerrank-i]{:target="_blank"}

O problema, à primeira vista, parece ser complicado, no entanto a soluço é bem direta, basta simular os eventos na fila como descrito. Uma observação, que não impossibilita a resolução, mas que simplifica é observar o seguinte trecho do enunciado: *\[...\] é garantido que na entrada não tenha eventos do tipo ID CONSULTA para IDs de clientes preferenciais*. O fato de não ter esse tipo de evento para os clientes preferenciais facilita no sentido de não ter que se preocupar com esses clientes ao longo da simulação, basta manter um contador com a quantidade de clientes preferenciais e, quando for solicitado uma consulta do tipo ID CONSULTA, imprimir a quantidade de clientes não preferenciais até a posição do cliente ID na fila + esse contador (uma vez que os preferenciais sempre ficam na frente).  

Um exemplo de implementação segue abaixo:

{% gist wellvolks/a2a492edf2c20442bfff05cf6c06b799 welton_posicao_na_fila.cpp %}

[hackerrank-i]: https://www.hackerrank.com/contests/gogeo-problemas-ja-utilizados-em-avaliacoes/challenges/posicao-na-fila
