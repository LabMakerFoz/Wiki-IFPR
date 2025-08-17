# Comunicação serial e paralela

## Comunicação serial

Em telecomunicações e informática a **comunicação serial** é o processo de enviar dados **um bit de cada vez**, de forma sequencial, num canal de comunicação. É diferente da comunicação paralela, em que todos os bits de cada símbolo são enviados juntos. Na parte física, utilizando um meio de comunicação metálico, a comunicação serial somente necessita de um **par de fios** para que a comunicação aconteça, uma vez que o dado é transmitido bit a bit

## Comunicação palalela

A **comunicação paralela** é o processo de enviar dados em que **todos os bits de um símbolo são enviados juntos**. Na parte física a comunicação paralela necessita de **um fio para cada bit do dado a ser transmitido**, uma vez que são transmitidos ao mesmo tempo.

------------------------------------------------------------------------

Vantagens e desvantagens da comunicação serial e paralela  
Nos primeiros sistemas de comunicação digital, a **comunicação serial** era vantajosa para transmitir dados a **longas distâncias**, pois, com apenas um par de fio a comunicação poderia ser realizada.

A **comunicação paralela** era utilizada em **pequenas distâncias**, como para conectar uma impressora a um computador. A parte física para a comunicação paralela é mais complexa, exigindo um fio para cada bit de dados a ser transmitido e ainda necessidade de sincronização de todos os bits sendo transmitidos.

Hoje, com a melhoria da qualidade e da velocidade dos meios de transmissão, a **comunicação serial** é mais vantajosa e amplamente utilizada para a troca de informações entre dispositivos, como um computador e uma impressora. Nos computadores modernos a interface paralela está em desuso.

A **comunicação paralela** somente é utilizada internamente no computador, para realizar a troca de dados entre o processador, memórias e demais dispositivos de entrada e saída, através dos **barramentos**.

## Detecção de erros em pelo método de paridade

A **transmissão de dados** ou **códigos binários** de um dispositivo transmissor para um receptor está sujeita a ocorrência de **erros** quando o receptor não recebe a informação idêntica àquela que foi enviada pelo emissor. A principal **causa de erros** são **ruídos elétricos** e **interferências** sobre o sinal sendo transmitido [^1].

Uma das técnicas mais simples utilizadas na detecção de erros de dados transmitidos é o **método de paridade**.

Bit de paridade  
No método de paridade é acrescentado aos bits da informação a ser transmitida um **bit de paridade**. O bit de paridade pode ser 0 ou 1, dependendo do número de 1s contido no conjunto de bits do código.

## Interfaces seriais

As interfaces seriais mais conhecidas são a **RS-232**,**RS-485** e a **USB**.

### RS-232

A **RS-232** é uma interface serial assíncrona de baixa velocidade e atualmente vem sendo substituída pela interface USB nos computadores pessoais, está última, mais rápida e com conector mais simples.

**Taxas de transmissão** comuns da RS-232: 300, 1200, 2400, 9600, 19200 **bps**.

A interface **RS-232** normalmente utiliza o **conector DB-9** para interconexão de dispositivos. <a href="Arquivo:DB9.jpeg" class="wikilink" title="Arquivo:DB9.jpeg">Arquivo:DB9.jpeg</a>

A comunicação RS-232 é utiliza **níveis de tensão positiva e negativa**, normalmente +/-12V. O **nível lógico 1** é definido como **negativo** e o **nível lógico 0** como **positivo**.

### RS-485

A interface **RS-485** foi criada com o objetivo de expandir as capacidades físicas da interface RS-232 e é bastante utilizada em aplicações industriais, como equipamentos médicos, automação industrial, rotótica etc.

A **RS-485** utiliza o conceito de **sinal diferencial** no par de fios de transmissão, o que permite uma filtragem dos ruídos captados pelo cabo ao longo de seu comprimento.

Quanto aos **níveis de tensão**, no **RS-485** o transmissor deve oferecer uma tensão de no mínimo 1.5V/-1.5V e o receptor deve possuir uma sensibilidade de no mínimo 200mV/-200mV.

### USB (*Universal Serial Bus*)

<a href="Arquivo:USB.jpeg" class="wikilink" title=" 80px"> 80px</a>

A USB é uma interface serial de média velocidade, largamente utilizada para conectar periféricos a um computador.

A interface **USB** foi concebida para funcionar no padrão *plug-and-play*, no qual os computadores reconhecem automaticamente os dispositivos conectados.

As **velocidades de transmissão** serial da interface **USB** são[^2]:

- USB 1.1: 1,5 a 12 Mbps
- UBB 2.0: 480 Mbps
- USB 3.0: 4,8 Gbps
- USB 3.2: 20 Gbps

Os dispositivos que dispõe de interfaces USB, como computadores pessoais, tem um **controlador de USB** que pode gerenciar até 128 portas, conectadas por meio de um *hub*. Entretando, todos os dispositivos conectados as interfaces USB disponíveis vão compartilhar a banda disponível.

No nível físico os **cabos USB** tem **quatro fios**: dois para **dados**, um para o **terra** e um para a linha de **alimentação** de +5 V.

Para alimentar dispositivos, a interface USB tem **capacidade de carga** de até **0,5 A**[^3].

<a href="Arquivo:padroesUSB.png" class="wikilink" title="Arquivo:padroesUSB.png">Arquivo:padroesUSB.png</a>

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h46min de 12 de junho de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Sistemas_Digitais" class="wikilink" title="Categoria:Sistemas Digitais">Categoria:Sistemas Digitais</a> <a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: TOCCI, R.J.; WIDMER, N.S.; MOSS, G.L. Sistemas Digitais: princípios e aplicações, São Paulo: Pearson, 2011.

[^2]: <http://pt.wikipedia.org/wiki/Universal_Serial_Bus>

[^3]: <http://www.hardware.com.br/analises/usb3-teoria-pratica/>
