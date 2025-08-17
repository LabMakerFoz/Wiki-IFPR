# Conversão de Pulsos PWM em Tensão Elétrica

## Microcontroladores e Saídas PWM

A maioria dos microcontroladores, como o **<a href="Arduino" class="wikilink" title="Arduíno">Arduíno</a>**, emulam **saídas analógicas** através de **modulação PWM** (*Pulse Width Modulation*).

O **sinal PWM** é uma **onda quadrada**, com frequência constante, mas a fração de tempo em que o sinal é HIGH (5V) (*duty cycle*) pode variar entre 0 e 100%, fornecendo uma média de tensão variável na saída [^1]. <a href="Arquivo:PWM.gif" class="wikilink" title="Arquivo:PWM.gif">Arquivo:PWM.gif</a>

O Arduíno possui **6 saídas PWM** são identificadas pelo sinal **~** e fornecem **pulsos PWM** de **8 bits**, possibilitando, portanto, **256 valores** diferentes de **tensão analógica** entre **0V e 5V**, com passos de **0 a 255**.

Entretanto, em situações onde uma **sinal PWM** não possa para ser utilizado como **controle analógico** pode ser necessário utilizarmos um **filtro de saída PWM** ou até dispormos de um **conversor DAC**, o qual pode necessitar circuitos eletrônicos analógicos, como Amplificadores Operacional, capacitores, resistores e outros.

## Filtro para Converter PWM em Tensão Elétrica

Em situações onde uma onda quadrada **PWM** não for apropriado para realizar um controle analógico pode utilizar um **filtro passa baixas** visando converter a saída em uma **tensão elétrica** correspondente ao percentual do sinal PWM. Desta forma, poderemos ter um **conversor DA** para uso com o Arduíno ou outros microcontroladores.

### Filtro Passa Baixas

O circuito **<a href="Filtros_Eletricos" class="wikilink" title="filtro passa baixas RC">filtro passa baixas RC</a>** abaixo pode ser utilizado neste caso.

<a href="Arquivo:FiltroRC_PassaBaixa.png" class="wikilink" title="Arquivo:FiltroRC_PassaBaixa.png">Arquivo:FiltroRC_PassaBaixa.png</a>

Neste circuito, quando um tensão é aplicada na entrada do resistor R, o capacitor C começa a carregar. Lembre que o capacitor bloqueia corrente contínua e permite um maior fluxo de corrente a medida que a frequência do sinal elétrico aumenta. Para altas frequências o capacitor se comporta como um curto circuito. Para valores de frequência intermediária o **circuito RC** vai **filtrar** o sinal de entrada de acordo com a **constante de tempo** do circuito.

O circuito é bastante simples, entretanto a escolha do **resistor R** e do **capacitor C** tem influencia na **frequência de corte** do circuito, na **ondulação da tensão sobre o capacitor** (***ripple***) e no **tempo de resposta** do circuito.

A referência [^2] faz uma análise detalhada destes fatores e também fornece um link para uma ferramenta para calculo *online* [**RC Low-pass Filter Design for PWM**](http://sim.okawa-denshi.jp/en/PWMtool.php) do **ripple** a partir da **frequência de corte** ou dos valores do **resistor** e **capacitor** escolhidos para filtragem de uma onda quadrada **PWM**.

Como descrito em [^3], o ***ripple*** e o **tempo de resposta** do circuito são parâmetros excludentes. Se diminuirmos muito o *ripple* o tempo de resposta aumenta, e vice-versa.

### Ganho de potência

Esta estrutura com **filtro RC passa baixas** funciona bem caso a carga não exija corrente significativa na saída. Caso a **carga** demande **corrente** pode-se utilizar um ***buffer*** com **amplificador operacional** para fornecer mais corrente a carga, oferecendo assim um **ganho de potência**.

A estrutura que pode ser utilizada para o ***buffer*** pode ser o **seguidor de tensão** com **Ampop**.

<a href="Arquivo:Buffer.png" class="wikilink" title="Arquivo:Buffer.png">Arquivo:Buffer.png</a>

### Exemplo de filtragem da saída PWM do Arduíno

O Arduíno fornece saída PWM (portas 3, 5, 6, 9, 10 e 11) com frequência de 490 Hz (pinos 5 e 6: 980 Hz) [^4].

Utilizando a ferramenta para calculo *online* [**RC Low-pass Filter Design for PWM**](http://sim.okawa-denshi.jp/en/PWMtool.php), para uma onda PWM de 0V a 5V, com *duty cicle* de 50% e frequência de corte de 10 Hz, obtêm-se um *ripple* aceitável (Vpp = 0,15 V) e um tempo de resposta de 0,04 s, como mostra a figura abaixo.

<a href="Arquivo:rc_ripple.png" class="wikilink" title="Arquivo:rc_ripple.png">Arquivo:rc_ripple.png</a>

Cálculo dos valores de **R** e **C** a partir da **frequência de corte**:

`f`<sub>`c`</sub>` = 1 / 2πRC`

Escolhendo

`C = 2,2 uF`  
`f`<sub>`c`</sub>` = 10 Hz`

temos

`R = 1/2πf`<sub>`c`</sub>`C`  
`R = 1/2π 10 2,2u`  
`R = 7,2 kΩ`

### Laboratório: Análise e filtragem de pulso PWM

- Utilizar o **SimulIDE** e montar circuito com um **Arduíno**, um **led** conectado a **saída digital 9** e um **potenciômetro** com o ponto central conectado a **entrada analógica A0** (com os demais terminais do potenciômetro conectados ao GND e 5V, respectivamente);
- Carregar programa exemplo **[Arquivo/Exemplos/Analog/AnalogInOutSerial](https://www.arduino.cc/en/Tutorial/AnalogInOutSerial)** e verificar a variação da luminosidade do **led** do **pino 9** em função do **potenciômetro**;
- Utilizar o **osciloscópio** do **SimulIDE** para examinar a forma de onda de uma saída PWM (pino 9). Variar o ***dutty cicle* do PWM**, através do potenciômetro e verificar as alterações na forma de onda PWM;
- Construir um **filtro RC** para **converter o sinal PWM em tensão elétrica**, incluindo também no circuito um ***buffer* seguidor de tensão** com **Ampop**. Verificar no osciloscópio o resultado da filtragem.

  
Considere que o **sinal PWM** opera com frequência de 980 Hz. Utilize os valores de R = 7,2 kΩ e C = 2,2 uF.

- Utilize o simulador de filtro RC [**RC Low-pass Filter Design for PWM**](http://sim.okawa-denshi.jp/en/PWMtool.php) para verificar o ***ripple*** e o **tempo de resposta** do circuito. Varie os valores de R, C e também da frequência de corte e analise as mudanças no filtro RC.

## Módulo Conversor de Sinal PWM para Tensão Analógica

Existem no mercado módulos para conversão do **sinal PWM** para **tensão analógica**, como o módulo **LC-LM358**.

<a href="Arquivo:conversor-pwm-para-tensao-0-a-10v.jpg" class="wikilink" title="200px">200px</a>

O módulo **LC-LM358** converte sinal PWM para sinal analógico, PWM *duty cicle* 0% a 100% para tensão de 0 a 10V.

São aplicados para interface com **PLC** (**Controladores Lógico Programáveis**) ou outras placas de controle industrial.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 16h00min de 19 de maio de 2023 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:Sistemas_Digitais" class="wikilink" title="Categoria:Sistemas Digitais">Categoria:Sistemas Digitais</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a> <a href="Categoria:Arduíno" class="wikilink" title="Categoria:Arduíno">Categoria:Arduíno</a>

[^1]: <https://www.arduino.cc/reference/en/language/functions/analog-io/analogwrite/>

[^2]: SCOTT. Arduino’s AnalogWrite – Converting PWM to a Voltage, 2011. <https://provideyourown.com/2011/analogwrite-convert-pwm-to-voltage/>

[^3]:

[^4]:
