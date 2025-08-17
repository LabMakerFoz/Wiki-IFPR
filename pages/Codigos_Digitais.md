# Outros códigos binários utilizados na informática e eletrônica digital[^1]

## Código BCD

Vimos que um número decimal pode ser representado por um binário equivalente, por exemplo, o decimal 13<sub>10</sub> pode ser representado pelo binário 1101<sub>2</sub>. Isto é chamado **codificação em binário puro**.

Em alguns casos é interessante representar cada digito decimal pelo seu binário equivalente, o resultado será um código denominado **decimal codificado em binário** (BCD - binary coded decimal).

|         |      |      |      |      |      |      |      |      |      |      |
|---------|------|------|------|------|------|------|------|------|------|------|
| Decimal | 0    | 1    | 2    | 3    | 4    | 5    | 6    | 7    | 8    | 9    |
| BCD     | 0000 | 0001 | 0010 | 0011 | 0100 | 0101 | 0110 | 0111 | 1000 | 1001 |

Um dos usos do código BCD é quando precisamos enviar cada digito digital para ser mostrado em um *display* de 7 segmentos, utilizando um CI chamado conversor BCD para 7 segmentos. Note que para representar números decimais de 2 dígitos, precisamos de 2 *displays* e 4 bits para a entrada do código BCD em cada um dos *displays*.

<a href="Arquivo:7segmentos.gif" class="wikilink" title="Arquivo:7segmentos.gif">Arquivo:7segmentos.gif</a>

<a href="Arquivo:7segmentos.gif" class="wikilink" title="Arquivo:7segmentos.gif">Arquivo:7segmentos.gif</a>

## Código Gray

O [**código Gray**](http://pt.wikipedia.org/wiki/C%C3%B3digo_de_Gray) permite representar sequências de números de forma que apenas um bit muda entre dois números sucessivos.

Exemplo de aplicação  
O **código Gray** pode utilizado em sensores de posição angular, por exemplo, para verificar a posição angular de um motor de passo.

A figura mostra um leitor binário de posição angular de 3 bits:

<a href="Arquivo:CodigoGray.gif" class="wikilink" title="Arquivo:CodigoGray.gif">Arquivo:CodigoGray.gif</a>

  
Usando o **código Gray** não há risco de haver uma leitura "falsa" entre dois estados, já que apenas um bit é alterado entre cada leitura. Caso dois bits fossem alterados ao mesmo tempo, qualquer diferença entre as mudanças de cada bit poderia gerar uma leitura falsa.

## Código ASCII

O [**código ASCII**](http://pt.wikipedia.org/wiki/ASCII) é um código alfanumérico, utilizado como padrão para a troca de informações entre a CPU de um computador e dispositivos como teclado, monitores e impressoras, por exemplo.

No código ASCII cada caractere é codificado em 7 bits, existindo, portanto, 2<sup>7</sup> = 128 representações codificadas.

[Conversor de texto ASCII em binário](http://nickciske.com/tools/binary.php)

### Exercícios:

1.  Codifique os números decimais a seguir em BCD:
    - 47,
    - 962,
    - 6727;
2.  Quantos bits são necessários para representar os números decimais na faixa de 0 a 999 usando:
    - Binário puro;
    - BCD.
3.  Represente a expressão entre aspas "X = 3 \* Y" em código ASCII (hexadecimal).
4.  Os Bytes a seguir (mostrados em hexadecimal) representam o nome de uma pessoa am ASCII. Determine o nome da pessoa:
    - 43 61 54 61 52 61 54 61 53

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h45min de 12 de junho de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Sistemas_Digitais" class="wikilink" title="Categoria:Sistemas Digitais">Categoria:Sistemas Digitais</a>

[^1]: TOCCI, R.J.; WIDMER, N.S.; MOSS, G.L. Sistemas Digitais: princípios e aplicações, São Paulo: Pearson, 2011.
