# Conversão Analógico Digital

Um dispositivo **conversor analógico digital** (**ADC**) permite gerar uma representação digital a partir de uma grandeza analógica, normalmente um sinal representado por um nível de tensão elétrica.

No processo de **conversão analógico digital**, a faixa possível de valores que a grandeza analógica pode assumir é dividida em frações, cada um correspondendo a um valor digital. Por exemplo, um **conversor ADC** de **4 bits** o sinal de **entrada analógica** de **0V a 5V** deve ser dividido em 16 frações, como mostra a figura:

<a href="Arquivo:ConversaoAD.png" class="wikilink" title="Arquivo:ConversaoAD.png">Arquivo:ConversaoAD.png</a>

## Microcontroladores com Entradas Analógicas

Alguns **microcontroladores digitais** possuem **entradas analógicas** que utilizam **conversores analógico digitais** para converter o sinal lido em um valor numérico para uso pelo microcontrolador.

Arduíno  
O **Arduíno** é um exemplo de microcontrolador que possui **seis entradas analógicas**, nomeadas de **A0** até **A5**, as quais recebem **valores analógicos** entre **0V e 5V** e convertem para digital com **10 bits** de resolução (**valores de 0 a 1023**).

<!-- -->

ESP8266  
O **ESP8266** possui **uma entrada analógica**, nomeada como **A0**, a qual recebe **valores analógicos** entre **0V e 1V** e convertem para digital com **10 bits** de resolução (**valores de 0 a 1023**).

Alguns módulos de prototipagem com ESP8266, como o NodeMCU, permitem receber valores analógicos' entre 0V e 3,3V.

## Módulos Conversores ADC

Existem dispositivos programáveis que não possuam entradas analógicas. Neste caso, pode-se utilizar **módulos conversores ADC**. Um exemplo de dispositivo que não possui entradas analógicas é o **Raspberry Pi**.

Existem no mercado diversos **módulos conversores ADC** que podem ser utilizados de forma integrada com microcontroladores.

Módulo Conversor Analógico Digital ADS1015  
Fornece quatro canais, ou dois canais diferenciais, com resolução de **12-bits** e utiliza **comunicação serial I2C** com o microcontrolador. Opera com tensões de 2V a 5V.

<a href="Arquivo:ADC1.jpeg" class="wikilink" title="200px">200px</a>

Conversor Analógico Digital AD7705  
Pode ser utilizado em projetos com microcontroladores sem conversor integrado ou quando se busca maior precisão na conversão ADC. Possui dois canais diferenciais com resolução de **16-bits** e utiliza **comunicação serial SPI** com o microcontrolador. Opera com tensões de 3,3V a 5V.

<a href="Arquivo:conversor-analogico-digital-16-bits-adc-ad7705.jpg" class="wikilink" title="300px">300px</a>

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 17h11min de 18 de maio de 2023 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:Sistemas_Digitais" class="wikilink" title="Categoria:Sistemas Digitais">Categoria:Sistemas Digitais</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>
