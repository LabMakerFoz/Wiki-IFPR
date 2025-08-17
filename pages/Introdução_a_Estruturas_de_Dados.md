# Introdução a Estruturas de Dados

O estudo de **Estruturas de Dados** inclui o exame da organização, manipulação e utilização das informações manipuladas por um computador.

## Conceitos fundamentais

bit  
É a menor unidade de informação manipulada pelo computador, podendo assumir dois valores, **0** ou **1**.

O termo bit é a contração de *binary digit*.

<!-- -->

Palavra binária  
**n bits** formam uma palavra binária, a qual pode representar 2<sup>n</sup> valores diferentes.

<!-- -->

Byte  
É o termo clássico utilizado para uma **palavra binária de 8 bits**, o qual pode representar 2<sup>8</sup> = 256 combinações diferentes.

## Sistemas Numéricos e Aritmética Binária

Os <a href="Sistemas_Numericos" class="wikilink" title=" Sistemas Numéricos"> <strong>Sistemas Numéricos</strong></a> são utilizados para representar valores numéricos.

Os sistemas numéricos mais utilizados na informática são o decimal, binário, octal e hexadecimal:

- O **sistema decimal**, com 10 digitos, é o método que utilizamos para representar valores numéricos no dia a dia.
- O **sistema binário**, com os dígitos 0 e 1, é o método mais amplamente usado para interpretar definições de bits como inteiros não-negativos no computador.
- O **sistema octal**, com 8 digitos, guarda correspondência de cada digito com uma palabra binária de 3 bits.
- O **sistema hexadecimal**, com 16 digitos, guarda correspondência de cada digito com uma palabra binária de 4 bits. É muito utilizado para representar de forma concisa palavras binárias múltiplas de 4 bits.

Além de armazenar informações codificadas em binário, o computador também realiza operações sobre números binários utilizando <a href="Aritmetica_Binaria" class="wikilink" title=" Aritmética Binária"> <strong>Aritmética Binária</strong></a>. Nestas operações, **números binários inteiros positivos ou negativos** são representados no computador na forma de **complemento de 2**.

A informação binária pode ser representada por outros <a href="Codigos_Digitais" class="wikilink" title=" Códigos Digitais"> Códigos Digitais</a>, como por exemplo o **Código BCD** (*binary coded decimal*).

## Números Reais

**Números reais** são normalmente representados nos computadores utilizando a [**notação de ponto flutuante**](http://pt.wikipedia.org/wiki/Ponto_flutuante).

O conceito chave da notação de ponto flutuante é que um número real é representado por um número, chamado **mantissa**, vezes uma **base** elevada a uma potência de inteiro, chamada **expoente**.

Exemplo[^1]  
Inteiro base 10

`38,753 = 38753 x 10`<sup>`-3`</sup>  
`         |         |`  
`         Mantissa  Expoente`

  
Uma representação comum é representar a mantissa por um inteiro, sem os 0s (zeros) finais.

### Binários de ponto flutuante

As representações normatizadas para binários de ponto flutuante definem números de **precisão simples** (32 bits) ou **precisão dupla** (64 bits).

Precisão simples de 32 bits  

- 24 bits -\> Mantissa
- 8 bits -\> Expoente
- Base fixa 10

Exemplo[^2]  
Decimal:

`38,753 = 38753 x 10`<sup>`-3`</sup>  
`         |         |`  
`         Mantissa  Expoente`

  
Binário:

`000000001001011101100001 (Mantissa 24 bits)`  
`11111101 (Expoente 8 bits - Representado em Complemento de 2)`

Exercícios  
Representar em binário de ponto flutuante de precisão simples:

1.  0
2.  100
3.  0,5
4.  0,00005
5.  12
6.  -12
7.  12000
8.  -12000

### Padrão para representação de ponto flutuante: IEEE 754

A indústria de computadores definiu um padrão para representação de ponto flutuante, conhecido como [IEEE 754](http://en.wikipedia.org/wiki/IEEE_754-1985).

Neste padrão, números de ponto flutuante podem ser representados com precisão simples (***float**'') ou dupla (***double**''):

| nível | n\. bits | faixa | precisão\* |
|----|----|----|----|
| precisão simples | 32 bits | ±1.18E-38 to ±3.4E38 | aprox. 7 dígitos decimais |
| precisão dupla | 64 bits | ±2.23E-308 to ±1.80E308 | aprox. 15 dígitos decimais |

Neste padrão a **mantissa** é representada com 23 bits mais 1 bit de sinal. Para o **expoente** são utilizados 8 bits, entretanto, para expoentes negativos não é utilizado a representação em complemento de 2, mas sim, o conceito de [***bias***](http://en.wikipedia.org/wiki/Exponent_bias). Para maiores detalhes da implementação dos tipos float e double, verificar página da Wikipédia [IEEE 754](http://en.wikipedia.org/wiki/IEEE_754-1985).

## Strings de Caracteres

Para representar objetos não numéricos no computador, como as letras do alfabeto ou os símbolos numéricos, os mesmos devem ser codificados em algum <a href="Códigos_Digitais" class="wikilink" title=" código digital"> código digital</a>, como, por exemplo, o [código ASCII](http://pt.wikipedia.org/wiki/ASCII).

No código ASCII, por exemplo, a letra 'A' é representada por 01000001 e a letra 'B' por 01000010, logo, a string de caracteres 'AB' deve ser representada pela palavra binária 0100000101000010. Em geral, uma string de caracteres é representada pela concatenação das palavras binárias que representam os caracteres individuais da string.

## Memória do Computador

As informações binárias são normalmente armazenadas na **memória** do computador na forma de **palavras** binárias de 8 bits, ou **Bytes**. Cada Byte armazenado na memória recebe um **endereço**, o qual guarda a posição do dado da memória e é utilizado para acessar este dado.

Declaração de dados  
Nas linguagem de programação de alto nível, como a **linguagem C**, quando declaramos varáveis estamos informando ao computador a quantidade de Bytes que deve ser reservada na memória para cada tipo de dado.

Tipos de dados da linguagem C:

|        |         |
|--------|---------|
| Tipo   | Tamanho |
| char   | 1 Byte  |
| int    | 2 Bytes |
| float  | 4 Bytes |
| double | 8 Bytes |

## Hardware, software e o conceito de implementação

Todo computador tem um conjunto de **instruções** e **tipos de dados** "nativos", que depende da organização de seu hardware. O conjunto de instruções nativas de um computador é chamado de **linguagem de máquina**.

As instruções da linguagem de máquina são normalmente codificadas em binário. Entretanto, para facilitar a programação com esta linguagem, normalmente as instruções são representadas de forma mnemônica, formando o que se chama **linguagem Assembly**.

Cada instrução de uma linguagem de máquina corresponde a uma sequência de operações simples, como por exemplo, transferir um dado da memória para a um registrador interno da CPU, somar o dado transferido com o valor de outro registrador e armazenar o resultado em um terceiro registrador.

Os **tipos de dados** que podem ser manipulados pelo computador podem ser **implementados pelo hardware**, quando o circuito utilizado para efetuar as operações sobre os dados é construído como parte do computador.

Quando o conceito de tipo de dado é dissociado dos recursos do hardware do computador, um número ilimitado de tipos de dados pode ser construído. Neste caso, estes novos tipos de dados podem ser **implementados por software**, na qual um programa, que utiliza instruções de máquina já existentes, é criado para realizar as operações necessárias sobre os novos tipos de dados.

Uma linguagem de alto nível, como a **linguagem C**, implementa **tipos de dados** diversos, os quais são traduzidos por compiladores para a linguagem de máquina correspondente para poderem ser executados.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h30min de 12 de junho de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Estruturas_de_Dados" class="wikilink" title="Categoria:Estruturas de Dados">Categoria:Estruturas de Dados</a>

[^1]: TENENBAUM, Aaron M.; LANGSAM, Yedidyah; AUGENSTEIN, Moshe. Estruturas de dados usando C. Makron Books, 1995.

[^2]:
