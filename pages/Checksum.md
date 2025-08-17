# *Checksum*

O mecanismo de ***checksum*** permite a **detecção de erros** nos dados transmitidos em um **enlace de comunicação**.

Para implementar este mecanismo o TCP e o UDP possuem em seu cabeçalho um campo de 16 bits, chamado *checksum*. Para determinar o valor do campo *checksum*, o emissor faz o complemento de 1 da soma de todos as palavras de 16 bits do segmento e coloca o resultado no campo *cheksum* [^1].

Por exemplo, suponha que temos três palavras de 16 bits sendo transmitidas:

` 0110011001100110`  
` 0101010101010101`  
` 0000111100001111`

A soma será

` 0110011001100110`  
` 0101010101010101`  
`+________________`  
` 1011101110111011`

Adicionando a terceira palavra a esta soma

` 1011101110111011`  
` 0000111100001111`  
`+________________`  
` 1100101011001010`

O **complemento de 1** é obtido invertendo cada bit 1 por 0 e vice-versa. Desta forma o complemento da soma será 0011010100110101 o qual será o cheksum. No lado do receptor, todas as palavras de 16 bits recebidas são adicionadas, incluindo o *cheksum*. Se não houve erros na transmissão, a soma será 1111111111111111. Se um dos bits for 0, então é sabido que houve erros.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h33min de 12 de junho de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: KUROSE, J.F; ROSS K. W. Redes de Computadores e a Internet: Uma abordagem *top-down*, São Paulo: Pearson, 2010.
