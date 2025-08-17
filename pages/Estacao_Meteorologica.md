# Estação Meteorológica Automatizada com Arduíno

## Objetivo

O objetivo deste projeto é construir uma estação hidrometeorológica automatizada no Campus Foz do Iguaçu, com o objetivo de dispor um banco de dados dinâmico de informações para uso em pesquisas e estudos sobre manejo da água, integrando as áreas de conhecimento de Informática, Eletrônica, Física, Hidrologia e Aquicultura.

<a href="Mídia:ProjetoEstacaoHidroMeteorologica2.pdf" class="wikilink" title="Projeto da Estação Hidrometeorológica">Projeto da Estação Hidrometeorológica</a>  
Aprovado no programa PIBIC/CNPq, IFPR, 2016.

### Equipe

Professores  

- <a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro Cantú">Evandro Cantú</a> (Coordenador)
- Alcione Benacchio (Colaborador)

2015  
**Estudos e testes preliminares**

Alunos voluntários

- Jade Mathias da Silva (CST Análise e Desenvolvimento de Sistemas)
- José Antonio Kazienko Sallet (CST Análise e Desenvolvimento de Sistemas)

2016  
**Versão operacional incluindo sensores de campo, transmissão de dados via rede sem fio, banco de dados e Servidor Web**.

Bolsistas PIBIC/IFPR:

- Thiago Henrique Ribeiro (CST Análise e Desenvolvimento de Sistemas) (abr a jul)
- Bruno Henrique Oliveira (CST Análise e Desenvolvimento de Sistemas) (ago a dez)

Alunos voluntários:

- Matheus Santos (Licenciatura em Física)
- Frederik Nazario Moschkowich (CST Análise e Desenvolvimento de Sistemas)
- Matheus Marques Martinês (CST Análise e Desenvolvimento de Sistemas)

2017  
**Manutenção e aprimoramentos**:

Alunos voluntários:

- Pablo Souza dos Santos (Licenciatura em Física)

### Produções

RIBEIRO, T. H. ; OLIVEIRA, B. H. ; SILVA, M. S. ; MOSCHKOWICH, F. N. ; MARTINES, M. M. ; SALLET, J. A. K. ; SILVA, J. M. ; BENACCHIO, A. ; BENEDUZZI, H. M. ; CANTÚ, E. . Estação hidrometeorológica automatizada com microcontrolador Arduíno. **I Mostra de Inovação, Pesquisa, Ensino, Extensão e Cultura do IFPR**, Foz do Iguaçu, 2016.

RIBEIRO, T. H. ; OLIVEIRA, B. H. ; SILVA, M. S. ; MARTINES, M. M. ; CANTÚ, E. . Estação hidrometeorológica automatizada com microcontrolador Arduíno. **V Seminário de Extensão, Ensino, Pesquisa e Inovação do IFPR**, Cascavel, 2016 (<a href="Mídia:EstacaoMeteorologica.pdf" class="wikilink" title="Poster SEPIN2016">Poster SEPIN2016</a>).

RIBEIRO, T. H. ; OLIVEIRA, B. H.; MARTINES, M. M. Estação hidrometeorológica. **Projeto Integrador II, Curso Superior de Tecnologia em Análise e Desenvolvimento de Sistemas, IFPR**, Foz do Iguaçu, 2016 (<a href="Mídia:PI_II_TADS-EstacaoMeteorologica.pdf" class="wikilink" title="Documentação PI-II Estação Meteorológica">Documentação PI-II Estação Meteorológica</a>).

Esposição **Espaço Maker**. PTI, Foz do Iguaçu, 2016.

<a href="Arquivo:EspacoMaker.jpg" class="wikilink" title="300px">300px</a> <a href="Arquivo:EspacoMaker2.jpg" class="wikilink" title="300px">300px</a>

## Estudos sobre Meteorologia

<a href="Estudos_sobre_Hidrometeorologia" class="wikilink" title="Estudos sobre Hidrometeorologia">Estudos sobre Hidrometeorologia</a>  
Responsável: Matheus Santos (Licenciatura em Física)

## Sensores Meteorológicos Sparkfun

Conjunto de **Sensores Meteorológicos Sparkfun** [^1] [^2], contendo os seguintes elementos:

- Sensor de Direção do Vento (**Biruta**)
- Sensor de Volume de Chuva (**Pluviômetro**)
- Sensor de Velocidade do Vento (**Anemômetro**)

### Biruta

A **Biruta** ou **sensor de direção do vento** é fisicamente composto por oito chaves, ligadas a resistores variados. Quando o vento muda de direção um imã fecha um ou dois contatos, permitindo a medição de 16 resistências diferentes.

Na ligação em hardware, um resistor de 10 kΩ é utilizado como **divisor de tensão**, produzindo uma tensão de saída que pode ser medido por um conversor analógico-digital.

<a href="Arquivo:biruta_sparkfun_resistores.png" class="wikilink" title="Arquivo:biruta_sparkfun_resistores.png">Arquivo:biruta_sparkfun_resistores.png</a>

No Arduíno a tensão medida nas **entradas analógicas** (variando de 0V a 5V) é convertida internamente em um **número digital de 10 bits** (variando de 0 a 1023).

Para o sensor de direção do vento os 16 valores de resistência no divisor de tensão produzem as seguintes entradas no Arduino:

<table>
<thead>
<tr>
<th><p>Direção (Graus)</p></th>
<th><p>Resistencia (Ohms)</p></th>
<th><p>Tensão (Entrada=5V Resistencia=10 KΩ)</p></th>
<th><p>Binário (Saída porta Analógica)</p></th>
<th colspan="2"><p>Saída Leitura em Binário de 10 bits (0 - 1023)</p></th>
</tr>
</thead>
<tbody>
<tr>
<td><p><strong>Mínimo</strong></p></td>
<td><p><strong>Máximo</strong></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td><p>0</p></td>
<td><p>33k</p></td>
<td><p>3,84</p></td>
<td><p>786</p></td>
<td><p>744</p></td>
<td><p>805</p></td>
</tr>
<tr>
<td><p>22,5</p></td>
<td><p>6,57k</p></td>
<td><p>1,98</p></td>
<td><p>405</p></td>
<td><p>346</p></td>
<td><p>432</p></td>
</tr>
<tr>
<td><p>45</p></td>
<td><p>8,2k</p></td>
<td><p>2,25</p></td>
<td><p>460</p></td>
<td><p>433</p></td>
<td><p>529</p></td>
</tr>
<tr>
<td><p>67,5</p></td>
<td><p>891</p></td>
<td><p>0,41</p></td>
<td><p>84</p></td>
<td><p>75</p></td>
<td><p>87</p></td>
</tr>
<tr>
<td><p>90</p></td>
<td><p>1k</p></td>
<td><p>0,45</p></td>
<td><p>92</p></td>
<td><p>88</p></td>
<td><p>109</p></td>
</tr>
<tr>
<td><p>112,5</p></td>
<td><p>688</p></td>
<td><p>0,32</p></td>
<td><p>65</p></td>
<td><p>0</p></td>
<td><p>74</p></td>
</tr>
<tr>
<td><p>135</p></td>
<td><p>2,2k</p></td>
<td><p>0,9</p></td>
<td><p>184</p></td>
<td><p>156</p></td>
<td><p>213</p></td>
</tr>
<tr>
<td><p>157,5</p></td>
<td><p>1,41k</p></td>
<td><p>0,62</p></td>
<td><p>127</p></td>
<td><p>110</p></td>
<td><p>115</p></td>
</tr>
<tr>
<td><p>180</p></td>
<td><p>3,9k</p></td>
<td><p>1,4</p></td>
<td><p>286</p></td>
<td><p>265</p></td>
<td><p>345</p></td>
</tr>
<tr>
<td><p>202,5</p></td>
<td><p>3,14k</p></td>
<td><p>1,19</p></td>
<td><p>243</p></td>
<td><p>214</p></td>
<td><p>264</p></td>
</tr>
<tr>
<td><p>225</p></td>
<td><p>16k</p></td>
<td><p>3,08</p></td>
<td><p>630</p></td>
<td><p>615</p></td>
<td><p>665</p></td>
</tr>
<tr>
<td><p>247,5</p></td>
<td><p>14,12k</p></td>
<td><p>2,93</p></td>
<td><p>599</p></td>
<td><p>530</p></td>
<td><p>614</p></td>
</tr>
<tr>
<td><p>270</p></td>
<td><p>120k</p></td>
<td><p>4,62</p></td>
<td><p>945</p></td>
<td><p>886</p></td>
<td><p>961</p></td>
</tr>
<tr>
<td><p>292,5</p></td>
<td><p>42,12k</p></td>
<td><p>4,04</p></td>
<td><p>827</p></td>
<td><p>806</p></td>
<td><p>885</p></td>
</tr>
<tr>
<td><p>315</p></td>
<td><p>64,9k</p></td>
<td><p>4,78</p></td>
<td><p>978</p></td>
<td><p>962</p></td>
<td><p>1023</p></td>
</tr>
<tr>
<td><p>337,5</p></td>
<td><p>21,88k</p></td>
<td><p>3,43</p></td>
<td><p>702</p></td>
<td><p>666</p></td>
<td><p>743</p></td>
</tr>
</tbody>
</table>

--José Sallet 18h52min de 18 de novembro de 2015 (BRST)--

Rosa dos ventos  
Códigos utilizados para apontar a direção do vento no Brasil.

<a href="Arquivo:rosa_dos_ventos.png" class="wikilink" title="400px">400px</a>

### Pluviômetro

O **pluviômetro** é um tipo de balde de auto esvaziamento. A cada 0.2794 mm de chuva causa um fechamento de contato momentâneo que pode ser gravado com um contador digital ou acionar uma interrupção de microcontrolador (Arduíno).

O interruptor do pluviômetro é conectado com dois condutores centrais anexados em um cabo RJ11.

--Jade Mathias 16h17min de 17 de novembro de 2015 (BRST)

Pluviômetro no Arduíno  
A cada **0.2794 mm de chuva** uma **interrupção** é gerada. A rotina de interrupção, portanto, apenas deverá soma 0.2794 a uma variável que guarda a **chuva acumulada** em **mm**.

O contador de **chuva acumulada** em **mm** foi construído com uma **variável circular**, de 0 a 999. Isto é, uma vez chegado a 999 mm a contagem da chuva acumulada volta a zero.

<!-- -->

Interrupções no Arduíno  
No **Arduíno UNO** as **interrupções externas** são acionadas pelo comando **[AttachInterrupt](https://www.arduino.cc/en/Reference/AttachInterrupt)** e são acionadas pelo **pino 2** (interrupção 0) e/ou **pino 3** (interrupção 1).

<!-- -->

  
No Arduíno as **interrupções externas** podem ser acionadas de diferentes modos:

- LOW: Quando o pino está baixo;
- CHANGE: Quando o valor do pino muda;
- RISING: Quando o valor do pino sobe de baixo para alto;
- FALLING: Quando o valor do pino desce de alto para baixo;
- HIGH: Quando o pino está alto.

A cada fechamento de contados ocasionado pelos sensores uma **rotina de tratamento de interrupção** será acionada.

<!-- -->

  
Conforme ilustrado no tópico abaixo sobre o **hardware para a chave do pluviômetro**, será utilizado a **borda de subida** do pino (RISING) para acionar a **interrupção** e contar a **chuva acumulada**.

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 22h16min de 17 de abril de 2016 (BRT)

### Anemômetro

O **anemômetro** mede a **velocidade do vento**, fechando um contato com a ajuda de um ímã. Para uma velocidade do vento de 2.4 km/h o interruptor fecha uma vez por segundo.

O interruptor anemômetro está ligado a dois condutores internos do cabo RJ11 compartilhada pelo anemômetro e cata-vento (pinos 2 e 3).

--Jade Mathias 18h28min de 18 de novembro de 2015 (BRST)

#### Anemômetro no Arduíno

Medição por largura de pulsos  
A **largura dos pulsos** gerados pelo **anemômetro** serão medidos pelo Arduíno através da função **[pulseln()](http://www.arduino.cc/en/Reference/PulseIn)**. O tempo da largura de pulso retornado pela função pulseln() é medido em microsegundos, portando a velocidade do vento será determinada pela expressão:

`velocidadeVento = 2,4 * 10`<sup>`6`</sup>` / larguraPulso `

  
Conforme o hardware do anemômetro mostrado abaixo, a **largura dos pulsos** do anemômetro será medida durante o tempo que estiver em nível lógico baixo (LOW), entre dois fechamentos de contato.

<!-- -->

Medição por interrupção  
Para um **vento com velocidade de 2,4 km/h** o fechamento da chave ocorre uma vez por segundo (1 Hz).

Uma rotina de interrupção no Arduíno necessita apenas implementar um **contador de pulsos**. No programa principal, para uma dada **base de tempo** a **velocidade** é determinada pela expressão:

`Vel = ( contadorPulsos / baseTempo ) * 2,4`

  
  
Exemplo:

- Base de tempo = 10s
- Contador de pulsos = 10

`Vel = (10 / 10 ) * 2,4 = 2,4 km/h`

Obs: A **medição por interrupção** se mostrou mais estável e é a forma implementada na última versão do programa.

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 22h16min de 17 de abril de 2016 (BRT)

### Hardware para chaves do pluviômetro e anemômetro

Circuito para conectar as chaves do **pluviômetro** e **anemômetro** nas entradas de **Interrupção** do Arduíno:

<a href="Arquivo:ChaveInterrupcao.png" class="wikilink" title="600px">600px</a>

### Conexão dos Sensores Meteorológicos Sparkfun ao Arduíno

Os Sensores Meteorológicos Sparkfun são conectados ao Arduíno segundo os seguintes diagramas e **códigos de cores** para os **fios** provenientes dos sensores:

<a href="Arquivo:SensorChuva.png" class="wikilink" title="400px">400px</a>

<a href="Arquivo:SensorVelVento.png" class="wikilink" title="400px">400px</a>

<a href="Arquivo:SensorDirVento.png" class="wikilink" title="400px">400px</a>

## Sensores de Temperatura e Humidade

### Sensor de temperatura (LM35)

Funcionamento do sensor LM35  
O **LM35** é um **circuito integrado** exclusivo para medir temperatura com uma tensão de saída variando linearmente com a temperatura em graus Célsius.

Na configuração básica este sensor mede temperaturas entre 2<sup>o</sup>C e 150<sup>o</sup>C, variando a saída em função da temperatura de 0 mV + 10mV por 1<sup>o</sup>C.

<!-- -->

Esquema de ligação com Arduíno  

`            _______`  
`           |       |`  
`           | LM 35 | `  
`           |_______|`  
`             | | |`  
`   (+5v) ----+ | +---- (Ground)`  
`               |`  
`          Analog Pin `  
`       0mV + 10mV / `<sup>`o`</sup>`C`

Leitura pela entrada analógica do Arduíno  
O valor de tensão (entre **0V e 5V**) lido pelo Arduíno na **entrada analógica** é convertido um número digital com **10 bits de magnitude**, ou seja, 2<sup>10</sup> (1024) valores (entre 0 e 1023).

<!-- -->

  
Para obter o valor de tensão, para uso no cálculo da temperatura, multiplica-se o valor digital obtido na leitura por 5/1023.

<!-- -->

  
Como a tensão medida pelo sensor varia de 0 mV + 10mV/1<sup>o</sup>C, se multiplicarmos por 100, teremos o valor em graus Celsius:

<!-- -->

Programa Exemplo  

``` c
 //Sensor de temperatura LM35
 float valorSensor;
 float temperatura;
 void setup() {
 Serial.begin(9600);
 }
 void loop() {
   valorSensor = analogRead(A0) * 5.0 / 1023.0;
   temperatura = valorSensor * 100.0;
   Serial.print("Temperatura: ");
   Serial.println(temperatura);
   delay(2000); //Tempo entre as leituras em ms
 }
```

O **sensor de temperatura** **LM35** será utilizado para medir a **tempetarura interna** do módulo de campo da **Estação Meteorolótica**.

### Sensor de Temperatura e Humidade DHT11

O DHT11 é um sensor de temperatura e humidade. Este sensor inclui um medidor de humidade resistivo e um sensor de temperatura tipo NTC conectado a um microcontrolador de 8 bits [^3].

O DHT11 possui uma biblioteca com funções prontas para seu funcionamento [^4]. Para uso, baixe a biblioteca <a href="Mídia:DHT11.zip" class="wikilink" title="DHT11.zip">DHT11.zip</a> e insira no ambiente da IDE do Arduíno:

`Sketch -> Import Library -> Add Library`

Esquema de ligação com Arduíno  

`            _______`  
`           |       |`  
`           | DHT11 | `  
`           |_______|`  
`             | | |`  
`(Ground) ----+ | +---- (+5v)`  
`               |`  
`          Analog Pin 1`

Programa exemplo  

``` c
 //Sensor de temperatura LDHT11
 #include <dht11.h>
 dht11 sensor; //Inicializa sensor
 void setup() {
   Serial.begin(9600);
   delay(1000);
 }
 void loop() {
   sensor.read(A1);
   Serial.print("Temperatura (oC): ");
   Serial.println(sensor.temperature);
   Serial.print("Unidade (%): ");
   Serial.println(sensor.humidity);
   delay(2000); //Tempo entre as leituras em ms
 }
```

O **sensor de temperatura e humidade** **DHT11** será utilizado para medir a **tempetarura externa** e a **humidade relativa do ar** no módulo de campo da **Estação Meteorolótica**.

## Sensor de Pressão Barométrica BMP180

O **Sensor de Pressão Barométrica BMP180** [^5] mede a **pressão absoluta** do ar ao seu redor. A pressão do ar varia com as **condições do tempo** e também com a **altitude**. Portanto, dependendo de como os dados medidos forem interpretados, pode-se tanto aferir mudanças nas condições do tempo como na altitude.

Interface I<sup>2</sup>C  
O **BMP180** utiliza uma interface **I<sup>2</sup>C** para se comunicar com o microcontrolador do Arduíno. A interface I<sup>2</sup>C é padronizada para conectar dispositivos periféricos de baixa velocidade a uma placa mãe ou sistema embarcado e usa duas linhas para comunicação: Dados Seriais (*Serial Data* - SDA) e Clock Serial (*Serial Clock* - SCL). O clock é gerado pelo mestre e a linha de dados seriais é bidirecional.

<!-- -->

Conexões com o hardware do sensor  
O sensor BMP180 possui 4 pinos para conexão com o Arduíno:

- **+** (Vcc): **5 V**;
- **-** (GND): **Terra**;
- **SDA** (SDA) (I<sup>2</sup>C data): Conectar ao pino **A4** UNO
- **SCL** (SCL) (I<sup>2</sup>C clock): Conectar ao pino **A5** UNO

Instalação da biblioteca para o BMP180  
Este sensor possui uma biblioteca e exemplo que facilitam a comunicação com o sensor e o desenvolvimento de programas. Para uso com o Arduíno, baixar a biblioteca [Adafruit_BMP085.h](https://github.com/adafruit/Adafruit-BMP085-Library) e instalar na IDE do Arduíno com os comandos:

`Scketch -> Import Library -> Add library`

Exemplos  
Há um exemplo incluído junto com a biblioteca, que pode ser utilizado para testar o sensor BMP180 e também serem utilizados como referência para a construções de novos programas.

<!-- -->

Modificado em função da troca de sensor  
--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 19h49min de 27 de novembro de 2017 (BRST)

### Medição de tempo e altitude

O **BMP180** é um **sensor de pressão barométrica** e pode ser usado tanto aferir mudanças nas **condições do tempo** como na **altitude** [1](https://learn.sparkfun.com/tutorials/bmp180-barometric-pressure-sensor-hookup-).

#### Pressão atmosférica

A **pressão** é medida pela **força** por unidade de **área**. No Sistema Internacional é medida por **newton** por **metro quadrado**, ou **pascal** (**Pa**).

A **pressão atmosférica** é dada pela força exercida pelo ar que forma a atmosfera sobre a superfície da terra. Uma coluna de ar de um centímetro quadrado, ao nível do mar, pesa aproximadamente um quilograma, ou 101325 pascals. Em uma altitude de 3810 m, a pressão atmosférica é a metade da pressão ao nível do mar.

O **BMP180** mede a **pressão absoluta** em **pascal** (**Pa**). Entretanto, um pascal é uma unidade muito pequena, sendo normalmente a pressão dada em hectopascals (1 hPa = 100 Pa). Outras unidades utilizadas para medir a pressão atmosférica são o **bar** e o **atm**:

- 1 mbar = 1 hPa

Pressão atmosférica ao nível do mar  
1 atm

- 1 atm = 101 325 Pa = 1013,25 hPa = 1013,25 mbar = 1,01325 bar

#### Efeito da temperatura

A **temperatura** afeta a **densidade** de um gaz, a densidade de um gaz afeta a **massa** do gaz, e a massa do gaz afeta a **pressão**, portanto, a **pressão atmosférica** é bastante influenciada pela variação da **temperatura**.

#### Observações do tempo

A **pressão atmosférica** em um dado ponto da terra não é constante. Há uma interação complexa entre o movimento de rotação da terra, a inclinação do eixo da terra, e muitos outros fatores relacionados ao movimento das áreas de alta e baixa pressão. Todavia, observando a **variação de pressão** em um dado ponto é possível fazer **previsões de curto prazo sobre o tempo**. Por exemplo, **quedas de pressão** normalmente indicam **mau tempo** (chuva) ou tormenta se aproximando. **Subida de pressão** normalmente indica que o **tempo bom** (seco) está chegando.

#### Efeito da altitude

A **pressão atmosférica** também varia com a **altitude**. A pressão medida em um dado local é a **pressão absoluta**. Para comparar a pressão em dois lugares com altitude diferente, deve-se descontar os efeitos da altitude, gerando o que se chama **pressão relativa**.

Na biblioteca do BP180 a função **seaLevel(P,A)** utiliza como parâmetros a **pressão absoluta (P)** em hPa, e a **altitude corrente (A)** em metros, para devolver a **pressão relativa**. A partir da pressão relativa é possível comparar as pressões atmosféricas em diferentes pontos da terra.

#### Determinando a altitude

Uma vez que a **pressão atmosférica varia com a altitude**, é possível utilizar o medidor de pressão atmosférica para aferir a altitude de um local.

A pressão atmosférica média ao nível do mar é 1013.25 hPa e cai a zero no vácuo do espaço.

A variação da altitude entre duas medidas de pressão (p e p<sub>0</sub>) é dada pela fórmula:

$`altitude = 44330 * ( 1 - ({p \over p_0})^{1 \over 5.255})`$

Formas de utilizar esta equação:

1.  Se utilizarmos p<sub>0</sub> como a pressão atmosférica ao nível do mar (1013.25 hPa), teremos a altitude acima do nível do mar do local;
2.  Se utilizarmos p<sub>0</sub> como a pressão atmosférica do um local com altitude conhecida, teremos a altitude relativa, podendo ser positiva ou negativa, dependendo se subirmos ou descermos em relação a altitude conhecida.

Na biblioteca do BP180 a função **altitude(P,P0)** está pronta para realizar medições de altitude.

Tradução e adaptação  
--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h33min de 23 de agosto de 2015 (BRT)

------------------------------------------------------------------------

### Conexão dos Sensores DHT11 e BMP180 ao Arduíno

Sensores DHT11 e BMP180  
Os sensores de **Temperatura e Unidade do Ar** (**DHT11**) e **Pressão Atmosférica** (**BMP180**) são conectados ao Arduíno através de um *flat cable* de 10 vias:

<a href="Arquivo:FlatCable10vias.png" class="wikilink" title="250px">250px</a>

Os sensores são conectados da seguinte forma:

<a href="Arquivo:ConexaoSensores-FlatCable2.png" class="wikilink" title="Arquivo:ConexaoSensores-FlatCable2.png">Arquivo:ConexaoSensores-FlatCable2.png</a>

Código de cores utilizados nos fios de conexão com o Arduíno:

- GND - **Preto** (pinos 2 e 9)
- 5V - (<font color="red">**Vermelho**</font>) (pino 4 e 10)
- Data - (<font color="yellow">**Amarelo**</font>) (pino 3) -\> A2
- DA - (<font color="blue">**Azul**</font>) (pino 7) -\> A4
- CL - (<font color="green">**Verde**</font>) (pino 8) -\> A5

Modificado em função da troca de sensor  
--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 19h53min de 27 de novembro de 2017 (BRST)

## Código para Arduíno que controla a Estação Meteorológica

Código para leitura dos **sensores de campo**, com resultados podendo ser apresentados no **monitor serial** da IDE do Arduíno, ou enviados via **comunicação sem fio Xbee** para armazenamento em **banco de dados** e **servidor Web**..

``` c

/*
      Estação Meteorológica com Microcontrolador Arduino
      2015-2016 - Instituto Federal do Paraná
      Versão: V2
      Programadores: José Sallet (V1 2015)
                     Thiago Henrique Ribeiro (V2 2016)
                     Evandro Cantú (V3 2017)
      Orientador:    Evandro Cantú

      Mudanças em 2016:
      Abr4/2016 - Inclusão da função de leitura de vento por pulseIn()
                - Carregar strings literais da memória flash -> Serial.println(F("String literal));
                - Inclusão dos sensores LM35 (temperatura) e DHT11 (temperatura, umidade)
                - Testes com anemômetro e biruta com soprador de ar
                 
      Mudanças em 2017:
      Nov/2017: - Troca do sensor de Pressão Atmosférica
                - Inclusão de ventilador para resfrigeração
*/

#include<string.h>

//incluindo biblioteca do sensor de temperatura e pressao DHT11
#include <dht11.h>

//incluindo biblioteca do sensor de pressão
#include <Adafruit_BMP085.h>

//biblioteca do protocolo I2C
#include <Wire.h>       // biblioteca de comunicação I2C - necessária para o sensor barométrico BMP180
 
#define ALTITUDE  180.0 // Altitude de Foz do Iguaçu, Parana, Brasil
#define BASETEMPO 10    // define o tempo de repeticao

Adafruit_BMP085 bmp;          //inicializando sensor de temperatura e pressão
dht11 sensorUmidade;          //inicializando sensor DHT11

const int PINO_VENTILADOR = 13;   //pino digital   13 - Acionamento do ventilador interno
const int PINO_BIRUTA     = A0;   //pino analógico A0 - Leitura da tensão da biruta
const int PINO_LM35       = A1;   //pino analógico A1 - Leitura do sensor LM35 (temperatura)
const int PINO_DHT11      = A2;   //pino analógico A2 - Leitura do sensor DHT11 (temperatura + umidade)
                                  //pino analógico A3 livre
                                  //pino analógico A4 usado no BMP180 (temperatura + pressão)
                                  //pino analógico A5 usado no BMP180 (temperatura + pressão)

const int BUFFER_SIZE = 100;     //quantidade de leituras do sensor LM35 para fazer a média
                                 //para reduzir a margem de erro
const float CONVERSAO_GRAUS_CELSIUS = 0.488758553;  //constante para calcular a temperatura do sensor LM35

//Váriáveis para dados da Estação Meteorológica
float  mmChuva = 0;         //chuva acumulada
int    contVento = 0;       //contador de pulsos de vento
double altitude_local;      //altitude do local
float  temperatura1;        //temperatura do sensor DHT11
float  umidade;             //umidade do sensor DHT11
int    tensaoBiruta;        //valor da tensão na biruta
String direcao;             //direção da biruta
float  velocidadeVento;     //velocidade do vento
float  temperatura2;        //temperatura do sensor LM35 interno da estação
double temperatura3;        //temperatura do sensor BMP180
double pressaoAbsoluta;     //pressão absolutado sensor BMP180
double pressaoRelativa;     //calculo pressão relativa
double altitudeCalculada;   //calculo da altitude
double pontoOrvalho;        //calculo do ponto de orvalho

//Váriáveis para base de tempo para contagem de interrupções do anemômetro
float tempoAnterior = 0;
float tempoAtual;
float baseTempo = 0;

//Váriáveis para medida do tempo total de execução do programa
unsigned long inicio; 
unsigned long fim;
unsigned long tempo;

//-----------------------------------------------------------
//  ROTINA DE INTERRUPÇÃO 1 - PLUVIÔMETRO
//-----------------------------------------------------------

void choveu() {
  mmChuva = mmChuva + 0.2794;
  if (mmChuva > 1000) 
    mmChuva = mmChuva - 1000;
}

//-----------------------------------------------------------
//  ROTINA DE INTERRUPÇÃO 0 - ANEMÔMETRO
//-----------------------------------------------------------

void vento(){
   contVento++;
}

//-----------------------------------------------------------
//  ANEMÔMETRO
//-----------------------------------------------------------

float velVento(){
          tempoAtual = millis();
          baseTempo = tempoAtual - tempoAnterior;
          float _velVento = (contVento / (baseTempo/1000)) * 2.4;
          tempoAnterior = tempoAtual;
          contVento = 0;    
     return _velVento;
  }

//-----------------------------------------------------------
//  BIRUTA (Sparkfun)
//-----------------------------------------------------------

String biruta(int Tensao)
{
  String direcao;
  if (Tensao >= 744 && Tensao <= 805) {
    direcao = "Norte";
  }
  else if (Tensao >= 346 && Tensao <= 432) {
    direcao = "Norte-Nordeste";
  }
  else if (Tensao >= 433 && Tensao <= 529) {
    direcao = "Nordeste";
  }
  else if (Tensao >= 75 && Tensao <= 87) {
    direcao = "Leste-Nordeste";
  }
  else if (Tensao >= 88 && Tensao <= 109) {
    direcao = "Leste";
  }
  else if (Tensao >= 0 && Tensao <= 74) {
    direcao = "Leste-Sudeste";
  }
  else if (Tensao >= 156 && Tensao <= 213) {
    direcao = "Sudeste";
  }
  else if (Tensao >= 110 && Tensao <= 155) {
    direcao = "Sul-Sudeste";
  }
  else if (Tensao >= 265 && Tensao <= 345) {
    direcao = "Sul";
  }
  else if (Tensao >= 214 && Tensao <= 264) {
    direcao = "Sul-Sudoeste";
  }
  else if (Tensao >= 615 && Tensao <= 665) {
    direcao = "Sudoeste";
  }
  else if (Tensao >= 530 && Tensao <= 614) {
    direcao = "Oeste-Sudoeste";
  }
  else if (Tensao >= 886 && Tensao <= 961) {
    direcao = "Oeste";
  }
  else if (Tensao >= 806 && Tensao <= 885) {
    direcao = "Oeste-Noroeste";
  }
  else if (Tensao >= 962 && Tensao <= 1023) {
    direcao = "Noroete";
  }
  else if (Tensao >= 666 && Tensao <= 743) {
    direcao = "Norte-Noroeste";
  }
  else{
    Serial.println(F("[ERRO] Leitura na biruta fora da faixa!"));
    direcao = "Erro de leitura da Biruta";
  }  
  return direcao;
}

//-----------------------------------------------------------
//  SENSOR DE TEMPERATURA LM35
//-----------------------------------------------------------

//ler temperatura do sensor LM35 uma única vez
float temperaturaLM35() {
  return analogRead(PINO_LM35) * CONVERSAO_GRAUS_CELSIUS;
}

//ler temperatura do sensor LM35 (BUFFER_SIZE) vezes e calcular a média para obter uma medição mais precisa
//aumentar o valor de BUFFER_SIZE aumenta a precisão mas aumenta a carga do sistema
float temperaturaLM35Buffer() {
  float buffer = 0;
  for (int i = 0; i < BUFFER_SIZE ; i++) 
    buffer += analogRead(PINO_LM35);
  return (buffer / BUFFER_SIZE) * CONVERSAO_GRAUS_CELSIUS;
}

//-----------------------------------------------------------
//  CÁLCULO DE PONTO DE ORVALHO
//  Funções de ponto de orvalho obtidas em http://playground.arduino.cc/Main/DHT11Lib
//  A fazer: Verificar e referenciar o código apropriadamente
//  O código abaixo foi copiado e usado sem alterações
//-----------------------------------------------------------

// dewPoint function NOAA
// reference (1) : http://wahiduddin.net/calc/density_algorithms.htm
// reference (2) : http://www.colorado.edu/geography/weather_station/Geog_site/about.htm

double dewPoint(double celsius, double humidity)
{
  // (1) Saturation Vapor Pressure = ESGG(T)
  double RATIO = 373.15 / (273.15 + celsius);
  double RHS = -7.90298 * (RATIO - 1);
  RHS += 5.02808 * log10(RATIO);
  RHS += -1.3816e-7 * (pow(10, (11.344 * (1 - 1 / RATIO ))) - 1) ;
  RHS += 8.1328e-3 * (pow(10, (-3.49149 * (RATIO - 1))) - 1) ;
  RHS += log10(1013.246);

  // factor -3 is to adjust units - Vapor Pressure SVP * humidity
  double VP = pow(10, RHS - 3) * humidity;

  // (2) DEWPOINT = F(Vapor Pressure)
  double T = log(VP / 0.61078); // temp var
  return (241.88 * T) / (17.558 - T);
}

// delta max = 0.6544 wrt dewPoint()
// 6.9 x faster than dewPoint()
// reference: http://en.wikipedia.org/wiki/Dew_point
double dewPointFast(double celsius, double humidity)
{
  double a = 17.271;
  double b = 237.7;
  double temp = (a * celsius) / (b + celsius) + log(humidity * 0.01);
  double Td = (b * temp) / (a - temp);
  return Td;
}

//    **Fim das funções de orvalho copiadas**

//-----------------------------------------------------------
//  TELEMETRIA - MEMÓRIA LIVRE NO SISTEMA
//-----------------------------------------------------------

int freeRam () {
  extern int __heap_start, *__brkval;
  int v;
  return (int) &v - (__brkval == 0 ? (int) &__heap_start : (int) __brkval);
}

//-----------------------------------------------------------
//  Função para imprimir na serial: Estação em modo StandAlone
//-----------------------------------------------------------

void imprimeSerial () {
  //  exibir dados na tela ou terminal serial

  Serial.println(F("================================================"));
  
  Serial.print(F("Temperatura [DHT11]:\t\t\t"));
  Serial.print(temperatura1);
  Serial.println(F(" graus Celsius"));

  Serial.print(F("Temperatura Interna [LM35]:\t\t"));
  Serial.print(temperatura2);
  Serial.println(F(" graus Celsius"));

  Serial.print(F("Temperatura [BMP180]:\t\t\t"));
  Serial.print(temperatura3);
  Serial.println(F(" graus Celsius"));

  Serial.print(F("Velocidade do vento:\t\t\t"));
  Serial.print(velocidadeVento);
  Serial.println(F(" km/h"));

  Serial.print(F("Direcao do vento:\t\t\t"));
  Serial.print(direcao);
  Serial.println(F(""));
  
  Serial.print(F("Pressao absoluta (local):\t\t"));
  Serial.print(pressaoAbsoluta);
  Serial.println(F(" milibar"));
  
  Serial.print(F("Pressao relativa (nivel do mar):\t"));
  Serial.print(pressaoRelativa);
  Serial.println(F(" milibar"));
  
  Serial.print(F("Altitude:\t\t\t\t"));
  Serial.print(altitudeCalculada);
  Serial.println(F(" metros"));
  
  Serial.print(F("Chuva acumulada:\t\t\t"));
  Serial.print(mmChuva);
  Serial.println(F(" mm"));

  Serial.print(F("Umidade relativa do ar:\t\t\t"));
  Serial.print(umidade);
  Serial.println(F("%"));
  
  Serial.print(F("Ponto de orvalho:\t\t\t"));
  Serial.print(pontoOrvalho);
  Serial.println(F(" graus Celsius"));
  
  //exibir tempo de execução
  Serial.print(F("\nTempo de execucao total:\t\t"));
  Serial.print(tempo);
  Serial.println(F("ms\n"));

  // exibir memória livre pra determinar estabilidade
  Serial.print(F("Memoria Livre:\t\t\t\t"));
  Serial.print(freeRam());
  Serial.println(F(" bytes\n"));
  
}

//-----------------------------------------------------------
//  Função para enviar PAYLOAD com dados via Xbee
//-----------------------------------------------------------

void enviaXbee () {
  //  Montar dados em formato Jason
      
  String payload = "{";
  payload += "\"a\":";
  payload += temperatura1;

  payload +=", \"b\":";
  payload += temperatura2;
  
  payload +=", \"c\":";
  payload += temperatura3;

  payload +=", \"d\":";
  payload += velocidadeVento;

  payload +=", \"e\":\"";
  payload += direcao;
  
  payload +="\", \"f\":";
  payload += pressaoAbsoluta;
  
  payload +=", \"g\":";
  payload += pressaoRelativa;
  
  payload +=", \"h\":";
  payload += umidade;
  
  payload +=", \"i\":";
  payload += mmChuva;
  
  payload +=", \"j\":";
  payload += pontoOrvalho;

  payload +=", \"k\":";
  payload += "\"IFPR0001\"";
  
//  payload += (fim/1000);
  payload +="}";

  Serial.print(payload);     
}

//-----------------------------------------------------------
//  SETUP (Preparação)
//-----------------------------------------------------------

void setup()
{
  pinMode(PINO_VENTILADOR, OUTPUT); //Saída digital para acionamento do ventilador
  Serial.begin(9600);  //define a taxa de transmissão da serial

  attachInterrupt(0, vento,  RISING); // interrupcao do anemometro
  attachInterrupt(1, choveu, RISING); // interrupcao do pluviometro

  //Inicialização do sensor de pressão BMP180
  if (!bmp.begin()) {
    Serial.println(F("[FAIL]\n\nA estação não pode ser inicializada. Verifique o sensor barométrico e reinicie o aparelho."));
    while (1) {}
  }
}

//-----------------------------------------------------------
//  PROGRAMA PRINCIPAL
//-----------------------------------------------------------

//repeticao que imprime as informacoes do programa ao usuario
//TODO: organizar a ordem de execução levando em consideração o tempo tolerado por cada sensor
void loop()
{
  /* 
   *  Ações do programa:
   *  1.  Obter leitura do sensor de umidade (só pode ser lido a cada 2 segundos, são dois valores inteiros)
   *  2.  Obter leituras de tensão da biruta
   *  3.  Obter leituras do anemômetro
   *  4.  Obter leituras de temperatura do sensor LM35
   *  5.  Obter leituras de temperatura e pressão do sensor BMP180
  */
  
  int espera = 5000;
  inicio = millis(); // millis() e micros() - medem o tempo corrido em milisegundos e microsegundos
  
  sensorUmidade.read(PINO_DHT11);
  altitude_local = (double)ALTITUDE;                    //adquire a altitude do local
  temperatura1 = (float) sensorUmidade.temperature;     //adquire temperatura do sensor DHT11
  umidade = (float) sensorUmidade.humidity;             //adquire umidade do sensor DHT11
  tensaoBiruta = analogRead(PINO_BIRUTA);               //adquire o valor da tensão na biruta
  direcao = biruta(tensaoBiruta);                       //calcula a direção da biruta
  velocidadeVento = velVento();                         //adquire a velocidade do vento
  temperatura2 = temperaturaLM35Buffer();               //adquire temperatura do sensor LM35
  temperatura3 = bmp.readTemperature();                 //adquire temperatura do sensor BMP180
  pressaoAbsoluta = (bmp.readPressure() / 100);         //adquire pressão absolutado sensor BMP180
  pressaoRelativa = (bmp.readSealevelPressure() / 100); //calcula pressão relativa
  altitudeCalculada = bmp.readAltitude();               //calcula altitude
  pontoOrvalho = dewPoint(temperatura1, umidade);       //calcula ponto de orvalho

  //Controle de temperatura interna para acionar ventilador
  if(temperatura2 > 35.0)
    digitalWrite(PINO_VENTILADOR, HIGH);
  else
    digitalWrite(PINO_VENTILADOR, LOW);
  
  //calcular e exibir tempo de execução
  fim = millis();          //fim da cronometração da função
  tempo = fim - inicio;    //cálculo do tempo de execução

  if(tempo < espera){
    delay(espera - tempo);               //cálculo do tempo de espera
  }                                      //(não pode ser menor que 2s)

//-----------------------------------------------------------
//Funções para mostrar dados:
//- imprimeSerial: Imprime dados na serial -> Estação em modo StandAlone
//- enviaXbee: Envia dados via Xbee para receptor remoto -> Estação em modo transmissão
//-----------------------------------------------------------

//  imprimeSerial ();
  enviaXbee ();

//-----------------------------------------------------------

}
```

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 08h58min de 12 de dezembro de 2017 (BRST)

### Formato json para envio dos dados via serial

Os **dados** lidos pelos sensores da **estação meteorológica** serão concatenados em uma ***string*** em formato **json** e transmitidos de forma **serial** para o servidor que armazenará os dados, utilizando os módulos **Xbee**.

O **json** (*JavaScript Object Notation*) [^6] é um formato de padrão aberto que utiliza texto legível a humanos para transmitir objetos de dados consistindo de **pares atributo-valor**, bastante utilizados em ***web services***.

Código jason utilizado na estação:

``` JavaScript
{ "a": temperatura1, "b": temperatura2,    "c": temperatura3,    "d": velocidadeVento,
  "e": direcao,      "f": pressaoAbsoluta, "g": pressaoRelativa, "h": umidade,
  "i": mmChuva,      "j": pontoOrvalho,    "k": "IFPR0001"
}
```

## Código para Arduíno que recebe dados via Xbee

Código para recepção dos dados enviados pela **Estação Meteorológica** via comunicação **Xbee** e implementação de **cliente Web** para envio dos dados para armazenamento em **banco de dados** e **servidor Web**.

``` c
/*
      Estação Meteorológica com Microcontrolador Arduino
      2015-2016 - Instituto Federal do Paraná
      Versão: V2
      Programadores: Thiago Henrique Ribeiro (V2 2016)
                     Frederik Nazario Moschkowich 
                     Matheus Marques Martines
      Orientador:    Evandro Cantú
*/

#include <SPI.h>
#include <Ethernet.h>
#include <stdlib.h>

String json;

byte mac[] = { 0xDE, 0xAD, 0xBE, 0xEF, 0xFE, 0xED };
IPAddress ip(192,168,40,99);        //Define o endereco IP
IPAddress subnet(255, 255, 252, 0); //Define a mÃ¡scara de rede
IPAddress server(192,168,40,98);    //ip do webservice
//Inicializa biblioteca de cliente Ethernet
EthernetClient client;

String vetor;
char incomingByte;

void setup() {
  Serial.begin(9600);
  Serial1.begin(9600);
  Ethernet.begin(mac, ip);
  delay(1000);
  Serial.println("connecting...");
}

void loop() {
  if (Serial1.available() > 0) {
    Serial.println("Recebendo dados..>");
    incomingByte = Serial1.read();
    Serial.print(incomingByte);

    vetor += incomingByte;
  }

  if (incomingByte == '}') {
    incomingByte = ' ';
    client.stop();
    Ethernet.begin(mac, ip);

    json = vetor;

    vetor = "";
    Serial.println(json);
    //conecta ao WebService e envia os dados 
    if (client.connect(server, 8080)) {
      Serial.println("connected");
      String request;
      request += "POST /WSEstacao/server/sensores HTTP/1.1\n";
      request += "Host: 192.168.40.98:8080\n";
      request += "Connection: close\n";
      request += "User-Agent: Arduino/1.0\n";
      request += "Content-Type: application/json\n";
      request += "Content-Length: ";
      request += String(request.length());
      request += "\n\n";
      request += json;

      client.println(request);
      client.stop();
    } else {
      Serial.println("connection failed");
    }

    if (client.available()) {
      char c = client.read();
      Serial.print(c);
    }

    // if the server's disconnected, stop the client:
    if (!client.connected()) {
      Serial.println();
      Serial.println("disconnecting.");
    }
  } else {
    //Serial.println("Problema de comunicacao");
  }
//  delay(5000);
}
```

### Detalhes do código

Este código foi construído para **Arduíno Leonardo** com dois ***shiels*** adicionais:

- **Shield Xbee** [^7] para recepção dos dados remotos da **Estação Meteorológica**;
- **Shield Ethernet** [^8] para conexão com a rede **Internet** e comunicação com o **Web Service** para armazenar dados no **banco de dados**.

Recepção de dados seriais via Xbee  
A comunicação serial via Xbee utiliza a interface **Serial1** do **Arduíno Leonardo** e recebe os dados codificados em formato **json**. A interface **Serial**, por sua vez, é utilizada para impressão de informações no monitor serial da IDE do Arduíno visando acompanhamento da execução do programa.

<!-- -->

Implementação de cliente Web para envio das informações a um Web Service  
Através do shield **Ethernet** é implementado um **cliente Web** [^9] (endereço IP 192.168.40.99), o qual se conecta a um **servidor Web** (endereço IP 192.168.40.98) e envia informações dos dados meteorológicos utilizando o método **POST** do protocolo **HTTP**.

## Referências

<references />

------------------------------------------------------------------------

<a href="Categoria:Arduíno" class="wikilink" title="Categoria:Arduíno">Categoria:Arduíno</a> <a href="Categoria:LabMaker" class="wikilink" title="Categoria:LabMaker">Categoria:LabMaker</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>

[^1]: Weather Meters <https://www.sparkfun.com/products/8942>

[^2]: Manual Weather Sensor Assembly <https://www.sparkfun.com/datasheets/Sensors/Weather/Weather%20Sensor%20Assembly>..pdf

[^3]: Sensor DHT11 <http://www.micro4you.com/files/sensor/DHT11.pdf>

[^4]: Uso da biblioteca DHT11 para Arduino <https://playground.arduino.cc/Main/DHT11Lib>

[^5]: Sensor BMP180 <https://www.adafruit.com/product/391>

[^6]: Formato Json <https://pt.wikipedia.org/wiki/JSON>

[^7]: Wireless shield Xbee <https://store.arduino.cc/usa/arduino-wirelss-sd-shield>

[^8]: Shield Ethernet <https://www.arduino.cc/en/Tutorial/WebClient>

[^9]:
