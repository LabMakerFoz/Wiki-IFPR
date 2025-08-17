# Arduíno: Acionamento de Cargas e Motores

O Arduíno pode acionar **cargas** maior potência por meio de **relés** e controlar **motores** através de dispositivos chamados **ponte H**.

## Informações sobre Arduíno

<a href="Arduino" class="wikilink" title="Arduino">Arduino</a>  
<a href="Arduino:_Entradas_e_Saidas" class="wikilink" title="Arduíno: Entradas e Saídas">Arduíno: Entradas e Saídas</a>  
[Site oficial do Arduíno](https://www.arduino.cc/)  

## Acionamento de Cargas com Relés

Um **relé** é um **interruptor eletromecânico** que pode ser utilizado para ligar ou desligar **cargas** de maior potência conectadas em **127/220V CA**.

Muitos relés operam através de uma **bobina eletromagnética** (eletroímã) utilizada para abrir e fechar o interruptor e para executar a operação mecânica sobre a chave.

### Módulos Relés

Para utilização com o **Arduíno** é comum a utilização de **módulos** montados em uma placa com terminais que facilitam a prototipagem. Estes módulos trazem montados na placa o **circuito de acionamento da bobina**, necessário para o funcionamento do relé. Neste caso, o **acionamento do relé** pelo **Arduíno** é realizado a partir de uma **saída digital**, além do fornecimento das tensões 5V e GNG para alimentar a parte lógica do relé.

<a href="Arquivo:Rele.png" class="wikilink" title="Arquivo:Rele.png">Arquivo:Rele.png</a>

A **carga CA** é conectada nos terminais de potência do relé, o qual geralmente apresenta três terminais:

- **NA** - Normalmente Aberto
- **COM** - Comum
- **NF** - Normalmente Fechado

Para acionamento de uma **carga simples**, como uma **lâmpada**, utilizar **NA-COM** como **chave liga-desliga**.

### Circuito de Acionamento de Relés

Para utilização do **relé eletromagnético**, não montado em um módulo pronto, é necessário um **circuito para acionamento e proteção da bobina**. Para isso, uma estrutura comum é utilizar um **diodo** em paralelo com a bobina e uma **chave com transistor** para acionar a bobina.

<a href="Arquivo:releCircuito.png" class="wikilink" title="Arquivo:releCircuito.png">Arquivo:releCircuito.png</a>

O **diodo de proteção** é importante, pois a bobina é uma **carga indutiva** e pode gerar altas tensões quando a corrente for interrompida sobre a mesma. Assim, quando o transistor corta a corrente, o diodo fica polarizado diretamente e mantem a corrente circulando por instantes na bobina, suprimindo o surto de tensão. Caso não se utilize esta proteção, o surto de tensão pode danificar o transistor ou o microcontrolador que aciona o circuito de comando.

### Laboratório 1: Acionamento de uma lâmpada com relé

LDR e relé  

- Montar hardware com **sensor LDR** e um **relé** para acionamento pelo Arduíno de uma **lâmpada 127/220V**.
- O circuito da **lâmpada** na **rede 127/220 V CA** é mostrado na figura abaixo.

<a href="Arquivo:LampadaRele.png" class="wikilink" title="Arquivo:LampadaRele.png">Arquivo:LampadaRele.png</a>

## Controle de Motores com Ponte H

A **ponte** H é um arranjo de **chaves** em forma de **H**, que serve para inverter o sentido da corrente elétrica em **motores de corrente contínua**, **motores de passo** ou outras cargas indutivas, permitindo com isto inverter o sentido de rotação do motor.

<a href="Arquivo:PonteH.png" class="wikilink" title="Arquivo:PonteH.png">Arquivo:PonteH.png</a>

O funcionamento da **ponte H** é baseado na operação combinada de **quatro as chaves**. Se S1 e S4 estiverem fechadas e S2 e S3 abertas tem-se o motor rodando em um sentido. Já com as chaves S3 e S2 fechadas e S1 e S4 abertas, o sentido do fluxo da corrente sobre o motor é invertido, fazendo com que a rotação do motor também se inverta.

A **velocidade de rotação do motor**, por outro lado, pode ser controlada variando o nível da tensão contínua aplicada sobre o motor.

## Circuitos Integrados e Módulos Ponte H

Existem **circuitos integrados** monolíticos, de diferentes fabricantes, que implementam **pontes H** através de **chaves transistorizadas**, como o **L293**, **L298** e o **L9110S**.

Também existem diversos **módulos** (*shields*) que utilizam **circuitos integrados ponte H** e oferecem uma plataforma pronta para prototipagem, incluindo terminais de conexão para as cargas e pinos para conexão dos sinais de controle.

### Circuito Integrado L298N

O **L298N** (*[datasheet](https://www.sparkfun.com/datasheets/Robotics/L298_H_Bridge.pdf)*) é um circuito integrado **ponte H** de **maior potência**, permite controlar velocidade e direção de até 2 **motores DC** que precisem de até 3 A de corrente contínua, acionados por voltagem de até 50 volts. Ele também pode ser usado para ativar relés, motores de passo e outros.

O funcionamento do L298N (similar ao L293D) segue a seguinte **tabela verdade** (exemplo para motor A):

|         |         |                 |                                  |
|---------|---------|-----------------|----------------------------------|
| **1IN** | **2IN** | **EnA**         | Motor A                          |
| H       | L       | PWM<sup>1</sup> | Sentido Horário<sup>2</sup>      |
| L       | H       | PWM<sup>1</sup> | Sentido Anti-horário<sup>2</sup> |
| L       | L       | X               | Pára motor                       |
| H       | H       | X               | Pára motor                       |
| X       | X       | L               | Ponto morto                      |
|         |         |                 |                                  |

Obs:

  
<sup>1</sup> Velocidade controlada pelo sinal PWM,

<sup>2</sup> O sentido de rotação depende também da forma de conexão dos fios nos bornes do motor.

<!-- -->

Controle da corrente sobre a carga  
Alem dos pinos de controle e saída, o circuito integrado **L298** apresenta dois pinos de saída chamados **Sense A** e **Sense B**, nos quais devem ser conectados resistores para **controlar a corrente sobre a carga** (respectivamente para o Motor A e Motor B). O valor dos resistores R<sub>S1</sub> e R<sub>S2</sub> dependem da corrente da carga (Sugestão: R<sub>S1</sub> = R<sub>S2</sub> = 0.5 Ω). Além disto, deve ser conectada a alimentação dos motores em Vs.

#### Módulo Ponte H L298N

Este módulo utiliza o circuito integrado L298N, oferecendo plataforma pronta para **prototipagem** para controlar até dois motores de corrente contínua ou um motor de passo e pode ser comandado por microcontroladores como o Arduíno.

<a href="Arquivo:PonteH_L298N.jpg" class="wikilink" title="250px">250px</a> [^1]

A referência [FelipeFlop. Motor DC com Driver Ponte H L298N](https://www.filipeflop.com/blog/motor-dc-arduino-ponte-h-l298n/) apresenta uma descrição detalhada deste módulo e a forma de utilização com o **Arduíno**.

### Laboratório 2: Controle de Motor CC com L298N

Procedimentos práticos  
Realizar o laboratório utilizando **componentes físicos** ou o **SimulIDE** com os componentes **Motor DC** e o circuito integrado **L298N** controlados por um **Arduíno**.

<!-- -->

Montagem do hardware  

- Utilizar duas saídas digitais do Arduíno (p.ex. 7 e 8) para controlar as entradas 1IN e 2IN da L298N;
- Utilizar uma saída PWM do Arduíno (p.ex. 6) para controlar a entrada EnA da L298N;
- Conectar o Motor DC nas saídas OUT1 e OUT2 da L298N.
- Construir programa exemplo para teste do motor em diferentes velocidades.

### Circuito Integrado L293D

O circuito integrado **L293D** ([datasheet](https://www.ti.com/lit/ds/symlink/l293d.pdf?ts=1635172984343&ref_url=https%253A%252F%252Fwww.ti.com%252Fproduct%252FL293D%253Futm_source%253Dgoogle%2526utm_medium%253Dcpc%2526utm_campaign%253Dasc-mdbu-null-prodfolderdynamic-cpc-pf-google-wwe%2526utm_content%253Dprodfolddynamic%2526ds_k%253DDYNAMIC%2BSEARCH%2BADS%2526DCM%253Dyes%2526gclid%253DCjwKCAjw_L6LBhBbEiwA4c46uv7OgNKJekP1tGSxrHC_js_UONZwywH9JbpqSpk-K8FjEWZhJPxzcRoCiz4QAvD_BwE%2526gclsrc%253Daw.ds)) permite controlar velocidade e direção de até 2 **motores DC** que precisem de até 600 mA de corrente contínua, acionados por voltagem de 4.5 à 36 volts. Ele também pode ser usado para ativar relés, motores de passo e outros.

<a href="Arquivo:PonteH_L293d.png" class="wikilink" title="Arquivo:PonteH_L293d.png">Arquivo:PonteH_L293d.png</a>

O funcionamento do L293D segue a seguinte **tabela verdade** (para cada motor):

<table>
<tbody>
<tr>
<td colspan="2"><p>Entradas</p></td>
<td><p>Saídas</p></td>
</tr>
<tr>
<td><p><strong>A</strong></p></td>
<td><p><strong>EN</strong></p></td>
<td><p><strong>Y</strong></p></td>
</tr>
<tr>
<td><p>H</p></td>
<td><p>H</p></td>
<td><p>H</p></td>
</tr>
<tr>
<td><p>L</p></td>
<td><p>H</p></td>
<td><p>L</p></td>
</tr>
<tr>
<td><p>X</p></td>
<td><p>L</p></td>
<td><p>Z</p></td>
</tr>
<tr>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

Onde:

  
H = Nível Lógico Alto (HIGH),

L = Nível Lógico Baixo (LOW),

X = Irrelevante,

Z = Alta Impedância.

O circuito integrado L293D apresenta alimentação separada para a **parte lógica** (V<sub>cc1</sub>) e para a **alimentação do motor** (V<sub>cc2</sub>). Desta forma, quando as **entradas de controle A** forem acionadas com as **tensões lógicas** (H e L) as **saídas Y** recebem as **tensões do motor** (H e L), respectivamente.

Exemplo para controle do Motor M1  

|        |        |                 |                                  |
|--------|--------|-----------------|----------------------------------|
| **1A** | **2A** | **1,2EN**       | Motor                            |
| H      | L      | PWM<sup>1</sup> | Sentido Horário<sup>2</sup>      |
| L      | H      | PWM<sup>1</sup> | Sentido Anti-horário<sup>2</sup> |
| L      | L      | X               | Motor parado                     |
|        |        |                 |                                  |

Obs:

  
<sup>1</sup> Velocidade controlada pelo sinal PWM,

<sup>2</sup> O sentido de rotação depende também da forma de conexão dos fios nos bornes do motor.

### Laboratório 3: Controle de Motor CC com L293D

Procedimentos práticos  
Realizar o laboratório utilizando o **SimulIDE** com os componentes **Motor DC** e o circuito integrado **L293** controlados por um **Arduíno**.

<!-- -->

Montagem do hardware  

- Utilizar duas saídas digitais do Arduíno (p.ex. 7 e 8) para controlar as entradas 1A e 2A da L293;
- Utilizar uma saída PWM do Arduíno (p.ex. 6) para controlar a entrada 1,2EN da L293;
- Conectar o Motor DC nas saídas 1Y e 2Y da L293.

Programa de teste  

``` c
//Programa para teste do motor CC com o L293D
int velocidade = 55; //Velocidade do motor (0 a  255)   
void setup()  
{  
  //Define os pinos como saida  
  pinMode(6, OUTPUT);  
  pinMode(7, OUTPUT);  
  pinMode(8, OUTPUT);  
}   
void loop()  
{  
  analogWrite(6, velocidade);   
  //Aciona o motor  
  digitalWrite(7, LOW);  
  digitalWrite(8, HIGH);  
  delay(3000);  
  //Pára motor  
  digitalWrite(7, LOW);  
  digitalWrite(8, LOW);  
  delay(1000); 
  //Aciona o motor no sentido inverso  
  digitalWrite(7, HIGH);  
  digitalWrite(8, LOW);  
  delay(3000);  
  //Pára motor  
  digitalWrite(7, LOW);  
  digitalWrite(8, LOW);  
  delay(1000); }    
```

### Módulo Ponte H L9110S

Permite controlar dois motores de corrente continua ou um motor de passo e pode ser comandado por microcontroladores como o Arduíno.

<a href="Arquivo:PonteH_L9110S.png" class="wikilink" title="400px">400px</a>

Este módulo é compacto e permite controlar motores de 2,5 V até 12 V com consumo de 800mA por motor.

Pinos de alimentação e controle:

- Vcc: (2,5 V até 12V)
- GND: (0 V)
- A1-A: Controle do motor A (Digital)
- A1-B: Controle do motor A (PWM)
- B1-A: Controle do motor B (Digital)
- B1-B: Controle do motor B (PWM)

Funcionamento do controle dos motores (Exemplo **Motor A**):

|          |               |           |                             |
|----------|---------------|-----------|-----------------------------|
| **A1-A** | **Sentido\*** | **A1-B**  | **Velocidade**              |
| LOW      | Horário       | 0 -\> 255 | 0 (Parado) -\> 255 (Máxima) |
| HIGH     | Anti-horário  | 255 -\> 0 | 255 (Parado) -\> 0 (Máxima) |

<i>\*</i> O sentido também depende da forma de ligação dos motores nos bornes de conexão.

Há outro módulo no mercado com o L9110S, que denomina os pinos de controle como IA1 e IB1 para o Motor 1 e IA2 e IB2 para o Motor 2, com o mesmo princípio de funcionamento.

## Ponte H com Relés

Para acionamento de **motores CC** que exigem maior tensão e maior corrente pode-se utilizar uma estrutura de **ponte H** construída com **relés** e chaveada com **transistores de potência**.

<a href="Arquivo:PonteH_Reles.png" class="wikilink" title="Arquivo:PonteH_Reles.png">Arquivo:PonteH_Reles.png</a>

Funcionamento do circuito  

- Os **relés** conectam a tensão de alimentação aos motores, sendo que no primeiro relé a tensão está conectada no terminal **NA** (normalmente aberto) e o segundo no terminal **NF** (normalmente fechado);
- A alteração do **sentido de rotação do motor** é realizada chaveando os dois relés ao mesmo tempo, o que altera a polaridade da tensão sobre o motor.
- A chave com **transistor de potência** permite **ligar e desligar** a corrente no motor.
- O chaveamento da corrente sobre o motor com um **sinal PWM** pode ser utilizado para **controlar a velocidade** do motor.
- Um **transistor** como o TIP122 permite controlar motores de até 100V/5A.

### Laboratório 4: Controle de motor CC através de ponte H com relés

O laboratório pode ser realizado com **componentes físicos** ou utilizando o **SimulIDE**.

- Montar hardware para controle de motor CC utilizando **saídas digitais** do **Arduíno** para controle de uma **ponte H** montada com dois **relés** de três pontos (NA, COM, NF) (No SimulIDE, configurar parâmetro DT do relé para *true*);
- Utilizar **saída PWM** do **Arduíno** para acionar **transistor como chave** para controle da velocidade do motor.

## Projeto 1: Controle de motores CC com Ponte H

Construir um projeto de controle de **motores CC**, utilizando **ponte H com relés**, **circuitos integrados** ou **módulos ponte H**. O sistema deve prever mecanismos para inverter a rotação do motor (p.ex. botões ou chaves) e também alteração da velocidade de rotação (p.ex. potenciômetros).

Pense em uma aplicação que o projeto poderia ser utilizado, como um elevador, um guincho, uma máquina para levantar material, um veículo, etc.

O projeto pode ser construído com **componentes físicos** ou usando o **SimulIDE**.

## Servo Motor

Os **servo motores** são atuadores utilizados em aplicações onde é necessário fazer o **controle de movimento** com posicionamento preciso, por exemplo, para controlar um braço de um robô ou o ângulo de abertura de uma chave.

Micro Servo motor SG90  
<a href="Arquivo:ServoMotor.jpeg" class="wikilink" title="Arquivo:ServoMotor.jpeg">Arquivo:ServoMotor.jpeg</a>

- O SG90 tem três fios: **alimentação** (5 V) na cor vermelho, **terra** (GND) na cor marrom e o **sinal** na cor laranja para controle do servo motor.
- O **controle** do servo motor é realizado por uma saída digital **PWM**, que permite **movimentar o braço** do servo de **0<sup>o</sup> a 180<sup>o</sup>**. O controle do ângulo é realizado pela largura do pulso PWM (*duty cicle*), variando entre 1 - 2 ms, para um período de 20 ms (50 Hz).
- Para uso com o **Arduíno** usa-se a **biblioteca** **servo.h**, que permite controlar diversos tipos de servo motores.

### Laboratório 5: Controle de servo motor

Teste do Servo motor SG90  

- Carregar programa exemplo **[Arquivo/Exemplos/Servo/Sweep](https://www.arduino.cc/en/Tutorial/Sweep)** para controle do servo motor de 0 a 180 graus.

Controle do Servo motor SG90 com potenciômetro  
O laboratório pode ser realizado com **componentes físicos** e o **servo motor SG90** ou utilizando o **SimulIDE** e o **Servo**.

- Montar hardware conectado a um **Arduíno**, com **servo motor** com o sinal conectado a **saída digital 9** (PWM) e um **potenciômetro** com o pino central conectado a **entrada analógica A0** para controlar o servo motor.
- Carregar programa exemplo **[Arquivo/Exemplos/Servo/Knob](https://www.arduino.cc/en/Tutorial/Knob)** para controle do servo motor a partir do potenciômetro.
- Verifique a utilização pelo programa da biblioteca \<Servo.h\>.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 09h35min de 17 de setembro de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:_Arduíno" class="wikilink" title="Categoria: Arduíno">Categoria: Arduíno</a> <a href="Categoria:_IoT" class="wikilink" title="Categoria: IoT">Categoria: IoT</a>

[^1]: FelipeFlop. Motor DC com Driver Ponte H L298N, 2013. <https://www.filipeflop.com/blog/motor-dc-arduino-ponte-h-l298n/>
