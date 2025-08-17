# Arduíno: Comunicação Serial e Bluetooth

## Comunicação Serial

### Conceitos sobre comunicação serial e paralela

<a href="Comunicação_serial_e_paralela" class="wikilink" title="Comunicação serial e paralela">Comunicação serial e paralela</a>  

### Comunicação Serial no Arduíno

O **Arduíno UNO** possui uma **porta serial** ([**Serial**](https://www.arduino.cc/reference/en/language/functions/communication/serial/)) (também referida como UART) e se comunica através dos pinos 0 (**RX**) e 1 (**TX**), assim como com o computador via USB. Se você utiliza a comunicação serial não pode utilizar os pinos 0 e 1 como entradas e saídas.

Também é possível utilizar o **monitor serial**, disponível na IDE do Arduíno, para comunicação bidirecional com uma placa Arduíno conectada em uma porta USB.

Não é possível utilizar as **portas seriais** do **Arduíno** diretamente em uma comunicação com uma **interface RS232**, pois esta usa tensões de -12 V e 12 V.

Outras placas Arduíno  

- O **Arduíno Leonardo** usa a **Serial** exclusivamente para comunicação com a **porta USB**. Para **comunicação serial** nos pinos 0 (RX) and 1 (TX) deve-se utilizar a **Serial1**.
- O **Arduíno Mega** tem três portas de **comunicação serial** adicionais: **Serial1**, **Serial3** e **Serial3**.

### Laboratório 1: Comunicação serial entre dois Arduínos

Monitor Serial  
O **monitor serial** permite enviar dados do **computador** ao **Arduíno** pela **interface serial USB**.

Procedimentos:

1.  Carregar programa exemplo **[Arquivo/Exemplos/Communication/PhysicalPixel](http://www.arduino.cc/en/Tutorial/PhysicalPixel)** e **acionar** o **led** do **pino 13** a partir de comandos **H** e **L** enviados pelo **monitor serial**.

Comunicação entre dois Arduínos  

Procedimentos:

1.  Conectar com um par de fios os dois Arduínos através das **portas seriais** de ambos os microcontroladores: TX-\>RX e RX\<-TX;
2.  Carregar no **receptor** o programa exemplo **[Arquivo/Exemplos/Communication/PhysicalPixel](http://www.arduino.cc/en/Tutorial/PhysicalPixel)**;
3.  Carregar no **emissor** o código abaixo;
4.  Observar a comunicação serial a partir do led piscando no receptor e também monitorar a troca de mensagens a partir do monitor serial.

``` c
 //emissor  
 int num = 0;
 void setup(){
  Serial.begin(9600);
 }
 void loop(){
  Serial.write('H');
  delay(2000);
  Serial.write('L');
  delay(2000);
 }
 }
```

### Configuração do SimulIDE para comunicação serial com Arduíno

É possível realizar **comunicação serial** entre um **Arduíno** rodando no **SinulIDE** e um **Arduíno** conectado a porta **USB** do computador.

1.  No Arduíno conectado a **USB**, verificar a partir da IDE a porta de comunicação que está sendo utilizada: **ttyACM0** (p.ex.);
2.  No Arduíno no **SimulIDE**, clicar com o botão direito do mouse sobre a placa e selecionar **Open Serial Port**;
3.  No bloco **Uart** que vai abrir, clicar com o botão direito do mouse e selecionar **properties**;
4.  Escrever em **port name** o nome da porta serial;
5.  Clicar em **Open** para ativar a porta (deve indicar sucesso com o botão vermelho).

## Comunicação I2C

A comunicação **I2C** é um protocolo de **comunicação serial** que permite que dispositivos diferentes se comuniquem e troquem dados através de um **barramento compartilhado**, permitindo que múltiplos dispositivos possam ser conectados no mesmo barramento.

No **I2C** um dispositivo é designado como **mestre** e os demais dispositivos são considerados **escravos**. O mestre envia uma solicitação de dados para o escravo desejado, e o escravo responde enviando os dados solicitados. Isso é possível graças ao uso de **endereços únicos** para cada dispositivo **escravo**, que permitem que o mestre saiba exatamente qual dispositivo deve ser acessado.

A **comunicação I2C** é realizada por meio de duas linhas de comunicação, o **SDA** (linha de dados) e o **SCL** (linha de sincronismo).

<a href="Arquivo:Barramento_I2C.png" class="wikilink" title="Arquivo:Barramento_I2C.png">Arquivo:Barramento_I2C.png</a>

Arduíno UNO  
No **Arduíno UNO** a comunicação I2C utiliza a biblioteca chamada **Wire** [^1] e os pinos **SDA** e **SCL** próximos ao pino Aref, ou pinos A4 (**SDA**) e A5 (**SCL**).

<!-- -->

ESP  
No **ESP8266** a comunicação I2C utiliza por padrão pinos GPIO4 (**SDA**) e GPIO5 (**SCL**).

Uma vantagem importante da comunicação I2C é que podemos ter um dispositivo mestre se comunicando com vários dispositivos escravos (até 127), como diferentes tipos de sensores ou mesmo outros microcontoladores.

### Laboratório 2: Comunicação entre Arduínos utilizando I2C

Realizar a comunicação entre dois (ou mais) Arduínos utilizando a comunicação **I2C** e a biblioteca **Wire.h**.

Utilize os exemplos prontos da apresentados na **IDE do Arduíno**, no caminho **Arquivo/Exemplos/Wire**, como os exemplos `master_reader` e `master_writer` para uso como mestre, e `slave_sender` e `slave_receiver` para uso como escravo.

Se utilizar mais de um Arduíno como escravo, ajustar o endereço de forma que cada dispositivo tenha um endereço único no barramento.

Veja exemplo de comunicação I2C entre dois Arduínos em [^2].

## Comunicação com Módulo Bluetooth

O **módulo Bluetooth** permite interagir com o Arduíno, por exemplo, utilizando um aplicativo em um smartphone.

Dois módulos Bluetooth bastante utilizados são o **HC05** e o **HC06**. O HC05 pode funcionar como mestre ou escravo. O HC06 somente como escravo. Isto significa que o HC05 pode iniciar conexões com outros dispositivos e o HC06 pode somente aceitar conexões de outros dispositivos [^3].

<a href="Arquivo:Bluetooth_HC-05_HC-06_ZS-040.jpg" class="wikilink" title="400px">400px</a> [^4]

### Pinagem e conexão com o Arduíno

Estes módulos apresentam 6 pinos, mas com apenas 4 pinos é possível colocar o mesmo para funcionar e fazer o Arduíno interagir dispositivos Bluetooth (o HC06 tem conexões apenas com estes 4 pinos).

`            _________`  
`           |         |`  
`           |         |`  
`           |         |`  
`           |Bleutooth|`  
`           |         |`  
`           |   HC06  |`  
`           |         |`  
`           |         |`  
`           |_________|`  
`             | | | |`  
`     Vcc ----+ | | +---- Rxd`  
`     Gnd ------+ +------ Txd`

:\*O pino EN, quando colocado em 0V desabilita o módulo;

:\*O pino Status pode ser lido e indica de esta desconectado (LOW) ou conectado (HIGH).

Cuidados com a conexão do módulo Bluetooth HC06 com o Arduíno  

- Os módulos HC05 e HC06 funcionam com **alimentação** (Vcc) de **3,3V**, mas possuem regulador interno e podem ser alimentados com tensão de 5 V;
- A **comunicação serial**, entretanto, opera somente com **3,3V**, Como o Arduíno opera com 5V, é necessário utilizar um **[divisor de tensão](http://200.17.101.9/wiki/index.php/Resistores#Divisor_de_Tens.C3.A3o)** na entrada Rxd do módulo, conforme exemplo abaixo:

<a href="Arquivo:DivisorTensao-Bleutooth.png" class="wikilink" title="Arquivo:DivisorTensao-Bleutooth.png">Arquivo:DivisorTensao-Bleutooth.png</a>

`V`<sub>`Rxd`</sub>` = R2/(R1 + R2).5`

  
Exemplo:

`R1=470 Ω, R2=1 KΩ -> V`<sub>`Rxd`</sub>` = 3,4 V`

### Laboratório 3: Comunicação serial entre Arduíno com módulo Bluetooth e Android

Permite acender e apagar led a partir de aplicativo **Android** pareado com módulo **Bluetooth** rodando em um Arduíno:

Procedimentos  

1.  Conectar hardware **Bluetooth** no Arduíno, utilizando **divisor de tensão** para adaptar as tensões de comunicação serial;
2.  Carregar programa exemplo **[Arquivo/Exemplos/Communication/PhysicalPixel](http://www.arduino.cc/en/Tutorial/PhysicalPixel)**;
3.  Instalar em um dispositivo Android o aplicativo **Bluetooth Terminal**;
4.  Abrir aplicativo **Bluetooth Terminal** e **parear** com módulo Bluetooth;
5.  Enviar a partir do **Bluetooth Terminal** os caracteres **H** e **L** para acender a apagar o led 13 do Arduíno.

### *Smartphone* Android

Para enviar caracteres de um ***Smartphone* Android** para o módulo **Bluetooth** pode-se utilizar aplicativos como o [Bluetooth Serial Port Terminal](https://play.google.com/store/apps/details?id=com.ucconnect.ucbtadapter_hex&hl=pt-BR) ou [Bluetooth V2.1 SPP Terminal](https://play.google.com/store/apps/details?id=project.bluetoothterminal&hl=pt-BR)

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 16h25min de 20 de junho de 2023 (-03)

------------------------------------------------------------------------

<a href="Categoria:Arduíno" class="wikilink" title="Categoria:Arduíno">Categoria:Arduíno</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>

[^1]: <https://www.arduino.cc/reference/en/language/functions/communication/wire/>

[^2]: <https://portal.vidadesilicio.com.br/i2c-comunicacao-entre-arduinos/>

[^3]: <http://www.martyncurrey.com/hc-05-and-hc-06-zs-040-bluetooth-modules-first-look/>

[^4]:
