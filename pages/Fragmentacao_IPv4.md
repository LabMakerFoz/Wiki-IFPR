# Fragmentação do IPv4

Referências: [^1], [^2].

A **fragmentação de um datagrama IP** pode ocorrer quando um datagrama chega em um enlace de entrada de um roteador e precisa ser enviado através de um enlace de saída cuja **MTU** (*maximum transfer unit*) não permite acomodar todos os bytes do datagrama. Neste caso, o datagrama deverá ser fragmentado em dois ou mais fragmentos (datagramas de menor tamanho) antes de ser enviado através do enlace de saída.

Os fragmentos precisam ser remontados antes de serem entregues a camada transporte no destino, uma vez que tanto o TCP quanto o UDP aguardam um datagrama completo. A solução adotada pelos projetistas do IPv4 foi fragmentar os datagramas nos roteadores intermediários e somente remontá-los no destino final. Para permitir a remontagem do datagrama são utilizados três campos do cabeçalho IP: ***Identification***, ***flags*** e ***Fragment Offset***. Quando um datagrama é criado o emissor o identifica com um número de identificação (*Identification*), assim como um endereço IP de origem e destino. Para cada novo datagrama criado o emissor gera uma nova identificação incrementando o valor deste campo. Quando um datagrama é fragmentado cada fragmento recebe o número de identificação, endereço IP de origem e destino iguais aos do datagrama original. Uma vez fragmentado o datagrama, cada fragmento será transmitido de forma independente, podendo inclusive chegarem no destino fora de ordem. Para a remontagem, a fim de identificar a posição de cada fragmento dentro do datagrama original, o campo *Fragment Offset* é utilizado. O último fragmento é reconhecido através do *flag*, que é definido como 0 (zero), ficando para os demais fragmentos o *flag* definido como 1 (um).

A figura ilustra um exemplo, apresentado por [^3], no qual um datagrama de 4000 bytes (20 bytes de cabeçalho IP mais 3980 bytes de dados) chega a um roteador e deve ser reenviado por um enlace com MTU de 1500 bytes. Para isto, os 3980 bytes de dados devem ser alocados em três fragmentos, todos identificados com o mesmo número de identificação.

A tabela abaixo ilustra os valores dos campos ***Identification***, ***Fragment Offset*** e ***Flag*** para os três fragmentos. O terceiro fragmento carrega somente 1020 bytes de dados (=3980-1480-1480). O campo *Offset* do primeiro fragmento é 0, significando que os dados devem ser inseridos a partir da posição 0 byte do datagrama a ser remontado. Para o segundo fragmento o *Offset* é 185, significando deve ser inserido na posição 1480 bytes (note que 185 . 8=1480). Para o terceiro fragmento o *Offset* é 370, significando deve ser inserido na posição 2960 bytes (note que 370 . 8 =2960).

`Fragmento Bytes Identification Offset Flag`  
`       1o  1480            777      0    1  `  
`       2o  1480            777    185    1  `  
`       3o  1020            777    370    0`

<a href="Arquivo:Fragmentacao.gif" class="wikilink" title="500px">500px</a> [^4]

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 14h14min de 12 de maio de 2020 (-03)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: KUROSE, J.F; ROSS K. W. Redes de Computadores e a Internet: Uma abordagem *top-down*, São Paulo: Pearson, 2010.

[^2]: <http://www.rfc-editor.org/info/rfc791>

[^3]:

[^4]:
