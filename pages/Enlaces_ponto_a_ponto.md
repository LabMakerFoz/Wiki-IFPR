# Enlaces ponto a ponto[^1]

<a href="Arquivo:RedePonto-a-ponto.png" class="wikilink" title=" 200px"> 200px</a>

Um **enlace ponto a ponto** consiste de um simples emissor em uma extremidade de um enlace e um simples receptor na outra ponta. São exemplos de protocolos ponto a ponto o **PPP** (*Point to Point Protocol*) e o **HDLC** (*High-level Data Link Control*).

## Protocolo PPP

O **PPP** (*Point to Point Protocol*), padronizado pela RFC 1661 é um protocolo bastante utilizado em enlaces ponto a ponto entre roteadores.

Formato do **quadro** PPP:

- Sempre inicia e termina com 01111110 (chamado de ***flag***), o segundo Byte é sempre 11111111 (chamado de **endereço**) e o terceiro byte é sempre 00000011 (chamado de **controle**).
- ***Protocol***: indica qual o protocolo da camada superior que está encapsulado no quadro, por exemplo, o hexadecimal 21 indica que o quadro leva um datagrama IP.
- **Dados**: leva a informação sendo transmitida, contendo um número inteiro de Bytes, podendo ter no máximo 1500 Bytes.
- ***<a href="Checksum" class="wikilink" title="Checksum">Checksum</a>***: é usado para detectar erros nos bits do quadro transmitido e normalmente implementado através de 2 Bytes (como o TCP ou UDP).

<a href="Arquivo:PPP.png" class="wikilink" title="Arquivo:PPP.png">Arquivo:PPP.png</a>

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h37min de 12 de junho de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: KUROSE, J.F; ROSS K. W. Redes de Computadores e a Internet: Uma abordagem *top-down*, São Paulo: Pearson, 2010.
