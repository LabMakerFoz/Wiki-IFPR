# Aritmética Binária[^1]

**"Só existem**10''' tipos de pessoas no mundo, as que entendem binário e as que não entendem".

## Adição em binário

- 0 + 0 = 0
- 0 + 1 = 1
- 1 + 0 = 1
- 1 + 1 = 10 = 0 e vai 1 para próxima posição (*Carry* = 1)
- 1 + 1 + 1 = 11 = 1 e vai 1 para próxima posição (*Carry* = 1)

Exemplo  

`  1   1    <- vai 1`  
`   101010`  
` + 110011`  
` --------`  
`  1011101`

### Exercícios

Efetue a soma dos seguintes pares de números binários:

1.  10110 + 00111
2.  011101 + 010010
3.  10001111 + 00000001

## Subtração em binário

- 0 - 0 = 0
- 1 - 0 = 1
- 1 - 1 = 0
- 0 - 1 = 1 precisa emprestar 1 (**1**0 - 1 = 1)

Exemplo  

`    1      <- empresta 1`  
`   110011`  
` - 101010`  
` --------`  
`   001001`

### Exercícios

Efetue a subtração dos seguintes pares de números binários:

1.  101101 - 010010
2.  10001011 - 00110101
3.  101011101 - 011100110

### Exercícios para entrega

Converta os pares números decimais em binário e efetue as operações:

1.  85 + 73
2.  233 + 120
3.  233 - 120
4.  255 - 127
5.  128 - 15

## Multiplicação em binário

- 0 \* 0 = 0
- 0 \* 1 = 0
- 1 \* 0 = 0
- 1 \* 1 = 1

Exemplo  
A multiplicação segue a lógica da multiplicação em decimal:

`     1010 (multiplicando)`  
`   x  101 (multiplicador)`  
`   ------`  
`     1010`  
`    0000  (produtos parciais)`  
` + 1010`  
` --------`  
`   110010 (produto)`

Número de dígitos do **produto** = Número de dígitos do **multiplicando** + Número de dígitos do **multiplicador**.

- Exemplo: 8 bits x 8 bits = 16 bits

### Exercícios

Efetue a multiplicação dos seguintes pares de números binários:

1.  1001 \* 1011
2.  10110 \* 00111
3.  011101 \* 010010
4.  11011101 \* 10110110

### Método para somar várias parcelas simultaneamente

Método apresentado pelo aluno **Fernando Koguti** (TADS 2016):

`         11011101 (multiplicando)`  
`       x 10110110 (multiplicador)`  
`         --------`  
`      111`  
`    1111111       (vai 1, 2 ou 3)*`  
` 11111111111      `  
` `<font color="yellow">`||||||||`</font>`00000000 (produtos parciais)`  
` `<font color="yellow">`|||||||`</font>`11011101`<font color="yellow">`|`</font>` `  
` `<font color="yellow">`||||||`</font>`11011101`<font color="yellow">`||`</font>`  `  
` `<font color="yellow">`|||||`</font>`00000000`<font color="yellow">`|||`</font>  
` `<font color="yellow">`||||`</font>`11011101`<font color="yellow">`||||`</font>`    `  
` `<font color="yellow">`|||`</font>`11011101`<font color="yellow">`|||||`</font>`     `  
` `<font color="yellow">`||`</font>`00000000`<font color="yellow">`||||||`</font>`      `  
`+`<font color="yellow">`|`</font>`11011101`<font color="yellow">`|||||||`</font>`       `  
` ----------------`  
` 1001110100011110 (produto)`  

Lógica  

- Se o número de **1s** é **par**, dá **0** e vai a **metade** do número de 1s;
- Se o número de **1s** é **impar**, dá **1** e vai a **metade** do número de 1s que restou;

`1 + 1 = 0 e vai 1`  
`1 + 1 + 1 = 1 e vai 1`  
`1 + 1 + 1 + 1 = 0 e vai 2 `  
`1 + 1 + 1 + 1 + 1 = 1 e vai 2 `  
`1 + 1 + 1 + 1 + 1 + 1 = 0 e vai 3`  
`1 + 1 + 1 + 1 + 1 + 1 + 1 = 1 e vai 3 `  
`1 + 1 + 1 + 1 + 1 + 1 + 1 + 1 = 0 e vai 4 `  
`1 + 1 + 1 + 1 + 1 + 1 + 1 + 1 + 1 = 1 e vai 4 `

#### Alternativa para diminuir o número de 1s na próxima coluna

Quando **vai 2 (ou 3 ou 4)** 1s, posso transferir o binário correspondente, por exemplo, **10 (ou 11 ou 100)** para as próximas colunas à esquerda, cada bit na sua posição correspondente.

Exemplo:

`         11011101 (multiplicando)`  
`       x 10110110 (multiplicador)`  
`         --------`  
`     `<font color="blue">`1`</font><font color="brown">`10`</font>` `<font color="pink">`1`</font>  
` `<font color="grey">`1`</font><font color="purple">`1`</font><font color="cyan">`10`</font><font color="green">`10`</font><font color="orange">`11`</font><font color="magenta">`10`</font><font color="red">`1`</font>  
` `<font color="yellow">`||||||||`</font>`00000000 (produtos parciais)`  
` `<font color="yellow">`|||||||`</font>`11011101`<font color="yellow">`|`</font>  
` `<font color="yellow">`||||||`</font>`11011101`<font color="yellow">`||`</font>  
` `<font color="yellow">`|||||`</font>`00000000`<font color="yellow">`|||`</font>  
` `<font color="yellow">`||||`</font>`11011101`<font color="yellow">`||||`</font>`    `  
` `<font color="yellow">`|||`</font>`11011101`<font color="yellow">`|||||`</font>`     `  
` `<font color="yellow">`||`</font>`00000000`<font color="yellow">`||||||`</font>`      `  
`+`<font color="yellow">`|`</font>`11011101`<font color="yellow">`|||||||`</font>`       `  
` ----------------`  
` 1`<font color="grey">`0`</font><font color="purple">`0`</font>`1`<font color="cyan">`1`</font><font color="blue">`1`</font><font color="green">`0`</font><font color="brown">`1`</font><font color="orange">`0`</font><font color="pink">`0`</font><font color="magenta">`0`</font><font color="red">`1`</font>`1110 (produto)`  
`  `<font color="yellow">`|| ||||||||`</font>  
`  `<font color="yellow">`|| |||||||`</font><font color="red">`1 e vai 1`</font>  
`  `<font color="yellow">`|| ||||||`</font><font color="magenta">`0 e vai 10`</font>  
`  `<font color="yellow">`|| |||||`</font><font color="pink">`0 e vai 1`</font>  
`  `<font color="yellow">`|| ||||`</font><font color="orange">`0 e vai 11`</font>  
`  `<font color="yellow">`|| |||`</font><font color="brown">`1 e vai 10`</font>  
`  `<font color="yellow">`|| ||`</font><font color="green">`0 e vai 10`</font>  
`  `<font color="yellow">`|| |`</font><font color="blue">`1 e vai 1`</font>  
`  `<font color="yellow">`|| `</font><font color="cyan">`1 e vai 10`</font>  
`  `<font color="yellow">`||`</font>  
`  `<font color="yellow">`|`</font><font color="purple">`0 e vai 1`</font>  
`  `<font color="grey">`0 e vai 1`</font>

### Exercícios para entrega

Converta os pares números decimais em binário e efetue as operações:

1.  12 \* 10
2.  170 \* 31
3.  170 \* 128

## Divisão em binário

A **divisão em binário** segue a lógica da divisão em decimal. O processo é inclusive mais simples, pois quando verificamos quantas vezes o **divisor** cabe dentro do **dividendo**, existem apenas duas possibilidades, 0 ou 1.

Exemplo de divisão:

`1001 : 11   (9 : 3 = 3)`  
` 11    11`  
`---`  
`  11`  
`  11`  
`  --`  
`   0`

`1010 : 10   (10 : 2 = 5)`  
`10     101`  
`--`  
` 010`  
`  10`  
`  --`  
`   0`

### Exercício

Converta os números decimais em binário a faça as divisões:

1.  16 : 4
2.  30 : 6
3.  80 : 10
4.  100 : 5

## Números binários fracionários

Os **números binários fracionários**, ou **números com vírgula**, também seguem a lógica dos números decimais com fracionários.

Exemplo de **número decimal fracionário**:

`53,74`<sub>`10`</sub>  
`= 5 x 10`<sup>`1`</sup>` + 3 x 10`<sup>`0`</sup>` + 7 x 10`<sup>`-1`</sup>` + 4 x 10`<sup>`-2`</sup>

Exemplo de **número binário fracionário**:

`101,1`<sub>`2`</sub>` `  
`= 1 x 2`<sup>`2`</sup>` + 0 x 2`<sup>`1`</sup>` + 1 x 2`<sup>`0`</sup>` + 1 x 2`<sup>`-1`</sup>  
`= 5,5`

Algumas potências negativas de 2  

`2`<sup>`-1`</sup>` = 1/2  = 0,5`  
`2`<sup>`-2`</sup>` = 1/4  = 0,25`  
`2`<sup>`-3`</sup>` = 1/8  = 0,125`  
`2`<sup>`-4`</sup>` = 1/16 = 0,0625`

### Exercício

Converta os números decimais em binário a faça as divisões usando o ponto fraconário:

1.  10 : 4
2.  20 : 16

Resolução dos exercícios:

`10 : 4  `  
`Conversão para binário:`  
`8  4  2  1   -> Peso dos bits   `  
`1  0  1  0   -> 10`  
`   1  0  0   ->  4`  
`Divisão:                `  
`   1 0 1 0  :  1 0 0`  
` - 1 0 0       1 0, 1  -> 2,5`  
`   -----            |`  
`       1 0 0        + Peso 1/2 = 0,5`  
`      -1 0 0`  
`       -----`  
`           0  `

`20 : 16`  
`Conversão para binário:`  
`16  8  4  2  1   -> Peso dos bits   `  
` 1  0  1  0  0   -> 20`  
` 1  0  0  0  0   -> 16`  
`Divisão:`  
`   1 0 1 0 0  :  1 0 0 0 0`  
`  -1 0 0 0 0     1, 0 1     -> 1,25`  
`   ---------          |`  
`       1 0 0 0 0      + Peso 1/4 = 0,25`  
`       1 0 0 0 0`  
`       ---------`  
`               0`

### Exercícios para entrega

Converta os números decimais em binário a faça as divisões:

1.  70 : 5
2.  54 : 9
3.  40 : 16
4.  60 : 16

## Números positivos e negativos

Números sem sinal  
A representação de números sem sinal em um computador aproveita todos os bits do número para representar quantidades: de 0 até 2<sup>n</sup> - 1 (2<sup>n</sup> valores diferentes).

<!-- -->

  
Por exemplo, um número de 8 bits pode armazenar números binários de 00000000 até 11111111 (de 0 a 255 em decimal). Isto representa a magnitude do número.

<!-- -->

  
Exemplo:

`N = 8 bits`  
`Números sem sinal: 0 ≤ X ≤ 255`

Números positivos e negativos  
A representação dos números positivos e negativos em um computador também permite representar quantidades em função do número de bits do número, entretanto, precisam reservar um bit para a representação do sinal (+ ou -). Isto é feito em geral acrescentando ao número um outro bit, chamado **bit de sinal**.

Quando trabalhamos com binários com sinal, somente podemos representar números com a metade da magnitude de um binário sem sinal, pois o bit mais significativo é reservado para o sinal, por exemplo:

`N = 8 bits`  
`Binário sem sinal: 0 ≤ X ≤ 255`  
`Binário com sinal: -127 ≤ X ≤ 127`

A forma mais utilizada de representar **números binários positivos e negativos** é o método chamado **complemento de 2**.

### Complemento de 2

Sinal e magnitude  
No método do **complemento de 2** o bit mais a esquerda (MSB) representa o **sinal**:

- **0** indica número **positivo**;
- **1** indica número **negativo**.

Os (N - 1) bits restantes representam a **magnitude** do número.

#### Binários positivos

Para os números **binários positivos**, o **bit de sinal** é **0** e os n-1 bits restantes representam a magnitude do número, que pode ser determinada de forma direta.

  
Exemplo:

**`0`**`0101010`<sub>`2`</sub>` = + 42`<sub>`10`</sub>

#### Binários negativos

Para representar os números **binários negativos** é necessário calcular o **complemento de 2** do número, em dois passos:

1.  Calcula-se o **complemento de 1** do número (veja abaixo);
2.  Soma-se **1** ao complemento de 1.
      
    Despreza-se o transporte no bit mais significativo (chamado de ***carry* externo**), caso exista.

Complemento de 1  
O **complemento de 1** de um binário é o simétrico dele, com todos os bits complementados, incluindo o bit de sinal.

**`Complemento de 1`**`: Troque 0 por 1 e vice-versa.`

Exemplos  
Veja a forma de representar números decimais com sinal como números binário com sinal no método do **complemento de 2**, usando um total de 5 bits (incluindo o bit de sinal).

- **Número decimal +13**

  
É positivo, portanto é representado de forma direta:

`13`<sub>`10`</sub>` = 1101`<sub>`2`</sub>

  
Anexando o **sinal** o temos:

`+13 = `**`0`**`1101`  
`      |`  
`      Bit de sinal`

- **Número decimal -13**

  
É negativo, portanto sua magnitude deve ser representada na forma de **complemento de 2**:

` 13`<sub>`10`</sub>` = 1101`<sub>`2`</sub>` (magnitude)`

  
Calculando o **complemento de 2**:

` 0010 (complemento de 1)`  
`+   1`  
`------`  
` 0011 (complemento de 2)`

  
Anexando o **sinal** o temos:

`-13 = `**`1`**`0011`  
`      |`  
`      Bit de sinal`

#### Extensão do sinal

Nos exemplos anteriores foi necessário usar um total de cinco bits para representar os números com sinal, um bit a mais que o necessário para representar a magnitude do número.

Normalmente os computadores usam registros para armazenar os números binários que são múltiplos de quatro bits, como 4, 8, 16, 32 ou 64. Por exemplo, em um sistema que representa números de 8 bits, o bit mais significativo (MSB) é o sinal e os outros sete são a magnitude.

Veja o caso dos números dos exemplos anteriores:

`+13 = `**`0`**`0001101`  
`      |`  
`      Bit de sinal`

  
Como é **positivo**, basta acrescentar **zeros** a esquerda.

`-13 = `**`1`**`1110011`  
`      |  |`  
`      |  Bit de sinal no formato de cinco bits`  
`      Extensão do bit de sinal no formato de oito bits.`

  
Como é **negativo**, acrescentamos **uns** a esquerda.

#### Negação

A **negação** é a operação de conversão de um número positivo em seu equivalente negativo, ou de um número negativo em seu equivalente positivo.

Para realizar a **negação** de um número basta calcular seu **complemento de 2**.

Exemplo de binário com sinal de oito bits  

Positivo:

`+ 42`<sub>`10`</sub>` = `**`0`**`0101010`<sub>`2`</sub>` ( 1 bit de sinal + 7 bits magnitude)`

Negativo:

`Passo 1: calcula-se o complemento 1 do número`  
` 00101010 (positivo)`  
` 11010101 (complemento 1)`  
`Passo 2: soma-se 1 ao complemento 1`  
` 11010101`  
`+       1`  
`---------`  
` `**`1`**`1010110`<sub>`2`</sub>` = - 42`<sub>`10`</sub>` (bit de sinal + complemento de 2)`

Negação: a negação de um número negativo será o seu simétrico positivo:

` `**`1`**`1010110`<sub>`2`</sub>` = - 42`<sub>`10`</sub>` (negativo)`  
`Passo 1: calcula-se o complemento 1 do número`  
` 00101001 (complemento 1)`  
`Passo 2: soma-se 1 ao complemento 1`  
` 00101001`  
`+       1`  
`---------`  
` `**`0`**`0101010`<sub>`2`</sub>` = 42`<sub>`10`</sub>` (simétrico positivo)`

### Aritmética com complemento de 2

A **subtração** pode ser implementada como **soma** do **complemento de** 2. Isto permite que a adição e a subtração sejam efetuadas pelo mesmo circuito digital.

Exemplo:

` Operação: + 4`<sub>`10`</sub>` - 3`<sub>`10`</sub>` (representados em binários de 4 bits)`  
`   4`<sub>`10`</sub>` = 0100`<sub>`2`</sub>  
`   3`<sub>`10`</sub>` = 0011`<sub>`2`</sub>  
`  -3`<sub>`10`</sub>` = 1100 + 1 = 1101`<sub>`2`</sub>` (complemento de 1 + 1 = complemento de 2)`  
` Realizando a soma do positivo com o negativo:`  
`    0100`  
`   +1101`  
`   -----`  
`   `**`1`**`0001 `  
`   |`  
`   Bit de `*`carry`*` externo desprezado`

#### Exercícios:

1.  Represente os números decimais com sinal como números binários com sinal no sistema de complemento de 2, usando um total de 8 bits (bit de sinal + 7 bits de magnitude):
    - +3
    - -2
    - +8
    - -8
    - +56
    - -100
2.  Efetue a subtração dos seguintes pares de números binários positivos, usando **complemento de 2**. Converter o resultado para decimal, indicando se é positivo ou negativo:
    - \(00101101\) - (00010010) -\> números de 8 bits: sinal + magnitude
    - \(00010010\) - (00101101) -\> números de 8 bits: sinal + magnitude
    - (000010001011) - (000000110101) -\> números de 12 bits: sinal + magnitude
    - (000101011101) - (000011100110) -\> números de 12 bits: sinal + magnitude

### Exercícios para entrega:

Converta os números decimais em binário de 8 bits, com sinal, e realize as operações indicadas usando soma, usando **complemento de 2** para representar os negativos. Converter o resultado para decimal, indicando se é positivo ou negativo:

1.  55 - 77
2.  \- 43 - 61
3.  \- 15 - 28

### Sobre a multiplicação no sistema de complemento de 2

1.  Número de bits do produto:
    - O número de bits do produto será o dobro do numero de bits do multiplicando e do multiplicador. Por exemplo, de multiplicando e multiplicador forem de 8 bits, o produto será de 16 bits. O MSB é sempre o bit de sinal.
2.  Sinal do produto:
    - Se os dois números forem positivos, poderão ser multiplicados diretamente e o resultado será positivo (bit de sinal 0);
    - Se os dois números forem negativos, representados em complemento de 2, deve-se obter o complemento de 2 dos números para convertê-los em positivos e em seguida multiplicá-los. O produto será positivo (bit de sinal 0);
    - Se um número for positivo e o outro negativo, o negativo deverá ser convertido em positivo, através do complemento de 2, para então multiplicar os números. Como o resultado deve ser negativo, o produto deverá ser convertido em negativo, através do complemento de 2 (bit de sinal 1).

#### Exercícios

1.  Converta os números decimais em binário de 8 bits, com sinal, e realize as operações de multiplicação indicadas, explicitando se os produtos são positivos ou negativos.:
    - (-43) \* (+61)
    - (-15) \* (-28)

`        00111101 (61)`  
`        00101011 (43)`  
`      * --------`  
`      1111`  
`    11111111 `  
`        00111101`  
`       00111101 `  
`      00000000  `  
`     00111101   `  
`    00000000    `  
`   00111101     `  
` + -------------`  
`0000101000111111 (2623)`

  
Deve-se passar o resultado para negativo, pois o produto de (-43) \* (+61) -e negativo.

### *Carry* e *Overflow*

#### *Carry* interno

Em uma soma (ou subtração em complemento de 2) de números binários sem sinal, toda vez que "**vai 1**" em uma coluna para a coluna da esquerda, temos um ***carry* interno**.

Exemplo  

`      1    <- vai 1 (`*`carry`*` interno)`  
`   101010`  
` + 010011`  
` --------`  
`   111101`

#### *Carry* externo

Caso o "**vai 1**" ocorra no bit mais significativo (MSB) temos um ***carry* externo**. Neste caso, este bit de *carry* poderá ser utilizado para indicar que o resultado da soma não cabe nesta quantidade de bits.

Exemplo  

`  `**`1`**`   1    <- vai 1 (O "vai 1" do bit MSB é um `*`carry`*` externo, o outro um `*`carry`*` interno)`  
`   101010  (6 bits)`  
` + 110011  (6 bits)`  
` --------`  
`  `**`1`**`011101  (7 bits!)`

#### *Overflow* aritmético

O *overflow* ocorre quando o resultado de uma operação supera a capacidade do registro usado para guardar este resultado.

Para somas ou subtração de números com sinal (+ ou -), o *overflow* ocorre caso o sinal do resultado não seja aquele que seria o esperado (por exemplo, um resultado negativo da soma de dois números positivos):

Exemplo  
Soma dos números binários +9 com +8, ambos com 4 bits de magnitude e 1 bit de sinal:

` +9  ->  0 1001`  
` +8  ->  0 1000`  
`        --------`  
`         1 0001  <- Magnitude incorreta`  
`         |`  
`         Sinal incorreto`

  
Explicação do *overflow* no exemplo dado:

  
Com números em complemento de 2 é possível representar a faixa de valores entre -2<sup>N-1</sup> ≤ X ≤ 2<sup>N-1</sup> - 1, onde n é o número de bits. No exemplo n = 5, logo pode representar valores entre -2<sup>5-1</sup> ≤ X ≤ 2<sup>5-1</sup> - 1, ou seja, -15 ≤ X ≤ 15. Como resultado da operação (+9) + (+8) teria que dar 17, ocorreu o *overflow*.

#### *Flags* de *carry* e *overflow*

As CPU (Unidades Centrais de Processamento) normalmente dispõe de um **registrador de estado** (*status register*) com alguns bits para indicar se em uma operação ocorreu um ***carry* externo** ou ***overflow***.

|     |     |     |     |     |     |     |     |
|-----|-----|-----|-----|-----|-----|-----|-----|
| \_  | \_  | C   | \_  | O   | \_  | \_  | \_  |

Portanto, é importante checar:

- ***Flag carry*** (C) após soma ou subtração de números sem sinal;
- ***Flag overflow*** (O) após soma ou subtração de números com sinal.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 11h40min de 23 de fevereiro de 2017 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Sistemas_Digitais" class="wikilink" title="Categoria:Sistemas Digitais">Categoria:Sistemas Digitais</a>

[^1]: TOCCI, R.J.; WIDMER, N.S.; MOSS, G.L. Sistemas Digitais: princípios e aplicações, São Paulo: Pearson, 2011.
