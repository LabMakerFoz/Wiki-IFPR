# Laboratório: Comunicação Serial com Arduíno

## Arduíno

O **Arduíno** é um microcontrolador montado em uma plataforma de prototipagem eletrônica de hardware livre que pode ser utilizado em múltiplas aplicações. O Arduíno é facilmente programável e pode ser utilizado para automação de dispositivos eletrônicos, acionamento de motores e leds, monitoramento de sensores, construção de protótipos de soluções tecnológicas e um mundo de possibilidades.

- **<a href="Arduíno" class="wikilink" title="Arduíno">Arduíno</a>**

## Ambiente de desenvolvimento do Arduíno

O ambiente de desenvolvimento de software do Arduíno usa uma linguagem de programação própria, baseada na **linguagem C**.

Os programas fonte são identificados pela extensão **`.ino`**.

A própria IDE do Arduíno apresenta vários exemplos de aplicações e programas que ajudam quem está iniciando a programá-lo.

<figure>
<img src="ArduinoIDE.png" title=" 400 px" />
<figcaption> 400 px</figcaption>
</figure>

Exercício 1  
Programa teste para **piscar um led**.

**Software**: Compile e faça o download do programa exemplo **Examples-\>Basics-\>Blink**, disponível na biblioteca de exemplos do ambiente de desenvolvimento do Arduíno.

**Hardware**: Conecte um led na porta 13 do Arduíno. **Atenção!** Os **leds** necessitam de um resistor para limitar a corrente, sob o risco de colocar a saída do Arduíno em curto-circuito:

- <http://200.17.101.9/wiki/index.php/Eletr%C3%B4nica#Leds>.

A porta 13 do Arduíno é a única que tem um resistor interno de proteção.

## Comunicação serial no Arduíno

Ver fundamentos da comunicação serial e paralela:

- <a href="Comunicação_serial_e_paralela" class="wikilink" title="Comunicação serial e paralela">Comunicação serial e paralela</a>
- [Comunicação serial com Arduíno](http://www.embarcados.com.br/arduino-comunicacao-serial)/

Exercício 2  
Programa teste para **acender e apagar led** a partir do teclado do computador usando **comunicação serial via USB**.

**Software**: Compile e faça o download do programa exemplo **Examples-\>Communication-\>PhysicalPixel**, disponível na biblioteca de exemplos do ambiente de desenvolvimento do Arduíno.

**Hardware**: Conecte um led na porta 13 do Arduíno.

**Serial Monitor**: Ative e monitor serial disponível na guia **Tools-\>SerialMonitor**, o qual captura o que for teclado e envia o caracter ASCII correspondente pela serial USB.

<!-- -->

Exercício 3  
Programa para **comandar 3 leds** (vermelho, amarelo e verde) a partir do teclado do computador usando **comunicação serial via USB**.

**Software**: Modifique o programa **PhysicalPixel** para acionar os três leds.

**Hardware**: Conecte os leds em três portas digitais do Arduíno. **Atenção!** Os **leds** necessitam de um resistor para limitar a corrente, sob o risco de colocar a saída do Arduíno em curto-circuito:

- [Resistor de proteção para leds](http://200.17.101.9/wiki/index.php/Eletr%C3%B4nica#Leds).

A porta 13 do Arduíno é a única que tem um resistor interno de proteção.

<!-- -->

Exercício 4  
Programa para a **comunicação serial entre um computador e dois arduínos**.

**Software**: Tome como referências o programa **PhysicalPixel** e o programa exemplo de comunicação disponível em:

- [Comunicação serial entre dois Arduínos](http://200.17.101.9/wiki/index.php/Ardu%C3%ADno#Comunica.C3.A7.C3.A3o_Serial).

O **computador** deverá enviar comandos via **serial USB** ao **Arduíno mestre**, e este envia comandos via **interface serial (pinos 0 e 1)** para o **Arduíno Escravo** visando comandar leds.

**Hardware**: Conectar os Arduínos mestre e escravo via serial: **Tx(mestre) -\> Rx(escravo)** (note que não há necessidade da conexão Tx(escravo) -\> Rx(mestre), pois a transmissão é somente em um sentido). Conectar os leds a serem comandados no Arduíno escravo.

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h48min de 12 de junho de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Sistemas_Digitais" class="wikilink" title="Categoria:Sistemas Digitais">Categoria:Sistemas Digitais</a>
