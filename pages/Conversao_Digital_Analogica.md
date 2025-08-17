# Conversão Digital Analógica

Um dispositivo **conversor digital analógico** (**DAC**) permite gerar uma **tensão elétrica analógica** a partir de um **dado digital**.

## Conversores DA

Um exemplo de **Conversor Digital Analógico** (**DAC**) de **4 bits** é ilustrado na figura, utilizando um **circuito somador** com **amplificador operacional** e uma malha resistiva com pesos binários.

<a href="Arquivo:ConversaoDA.png" class="wikilink" title="Arquivo:ConversaoDA.png">Arquivo:ConversaoDA.png</a>

`-v`<sub>`out`</sub>` = 1/2 D`<sub>`3`</sub>` + 1/4 D`<sub>`2`</sub>` + 1/8 D`<sub>`1`</sub>` + 1/16 D`<sub>`0`</sub>` `

Funcionamento do circuito  
Entradas digitais (0V ou 5V) e saída analógica variando entre 0V e 5V.

O circuito DAC de 4 bits vai fornecer uma saída analógica escalonada em 16 níveis de tensão.

Exemplos de algumas entradas e os respectivos níveis de tensão de saída:

{\| class="wikitable"

\|- \| Entrada digital \|\| Ganho Ampop \|\| Saída analógica \|- \| 1000 \|\| 1/2 \|\| 2,5 V \|- \| 0100 \|\| 1/4 \|\| 1,25 V \|- \| 0010 \|\| 1/8 \|\| 0,625 V \|- \| 0001 \|\| 1/16 \|\| 0,3125 V \|}

  
Todos os 16 valores:

{\| class="wikitable"

\|- \| Entrada digital \|\| Saída analógica \|- \| 0001 \|\| 0,3125 V \|- \| 0010 \|\| 0,625 V \|- \| 0011 \|\| 0,9375 V \|- \| 0100 \|\| 1,25 V \|- \| 0101 \|\| 1,5625 V \|- \| 0110 \|\| 1,875 V \|- \| 0111 \|\| 2,1875 V \|- \| 1000 \|\| 2,5 V \|- \| 1001 \|\| 2,8125 V \|- \| 1010 \|\| 3,125 V \|- \| 1011 \|\| 3,4375 V \|- \| 1100 \|\| 3,75 V \|- \| 1101 \|\| 4,0625 V \|- \| 1110 \|\| 4,375 V \|- \| 1111 \|\| 4,6875 V \|}

  
Para uma conversão com um número elevado de bits, a relação entre as resistências se torna elevada o que dificulta a precisão.

Existem outras estruturas eletrônicas que permitem implementar conversores DA, além de placas conversoras DAC para uso com microcontroladores.

## Módulo Conversor Digital Analógico DAC

Um exemplo de módulo **Conversor Digital Analógico DAC** é a placa **MCP4725**, a qual pode ser utilizada com Arduíno ou outros tipos de microcontroladores.

<a href="Arquivo:conversor-dac.jpg" class="wikilink" title="200px">200px</a>

O módulo MCP4725 converte sinais digitais em sinais analógicos. Os sinais são enviados via **interface I2C** e no pino OUT sai o valor analógico correspondente.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 13h53min de 18 de outubro de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:Sistemas_Digitais" class="wikilink" title="Categoria:Sistemas Digitais">Categoria:Sistemas Digitais</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>
