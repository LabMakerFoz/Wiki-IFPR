## Comunicação com Wireless Shield Xbee

O **[Wireless Shield](https://www.arduino.cc/en/Main/ArduinoWirelessShield)** permite a **comunicação serial sem fio** baseado no módulo **[Xbee](http://www.digi.com/products/wireless-wired-embedded-solutions/zigbee-rf-modules/zigbee-mesh-module/xbee-zigbee)** da Digi.

<a href="Arquivo:Arduino_WirelessSDShield.jpg" class="wikilink" title="300px">300px</a>

### Configuração do Wireless Shield

A placa **Wireless Shield** possui uma **chave de configuração** da comunicação serial entre o módulo **Xbee** e o **microcontrolador do Arduino** e o **conversor serial USB** (ver: <https://www.arduino.cc/en/Main/ArduinoWirelessShield>):

<a href="Arquivo:WirelessShield_SD_switchUSB.png" class="wikilink" title="100px">100px</a>

- **Posição micro**: O pino Dout do módulo Wireless é conectado ao pino RX do microcontrolador do Arduino e o pino Din ao pino TX do microcontrolador. **O módulo sem fio se comunica de forma serial com o microcontrolador do Arduino.** Destaca-se que os pinos TX e RX do microcontrolador também continuam conectados aos pinos RX e TX do conversor serial USB. Desta forma, dados transmitidos pelo microcontrolador serão enviados simultaneamente ao módulo sem fio e a serial USB. Neste modo o microcontrolador do Arduino não pode ser programado via USB.
- **Posição USB**: O pino Dout do módulo Wireless é conectado ao pino RX do conversor serial USB e o pino Din ao pino TX do conversor serial USB. **O módulo sem fio se comunica diretamente com o computador.** Para usar este modo o microcontrolador do Arduíno deve ser programado com um **sketch vazio**:

`void setup() { }`  
`void loop() { }`

Xbee Explorer USB  
A placa **Wireless Shield** com a chave na **posição USB** e o **microcontrolador do Arduíno** programado com **sketch vazio** se comporta como um módulo **Xbee Explorer USB**, com o Xbee se comunicando diretamente com o computador.

<a href="Arquivo:XbeeExplorerUSB.png" class="wikilink" title="200px">200px</a>

### Exemplo de utilização

Exemplo de comunicação usando a **configuração padrão** dos módulos **Xbee**, apresentado em <https://www.arduino.cc/en/Guide/ArduinoWirelessShield>:

- Para fazer a carga de programas no microcontrolador do Arduíno, colocar a **chave** do módulo wireless na **posição USB**.
- Em um dos Arduínos com módulo Wireless carregar o programa

`Exemples->Communication->Physical Pixel`

  
Este programa faz o Arduíno acender ou apagar o led da porta 13 a partir do envio do caracter H ou L a partir do **monitor serial**. Testar o funcionamento do programa com a chave do módulo wireless na **posição USB**. Em seguida desconectar o Arduíno da interface USB e mudar a chave do módulo wireless para a **posição micro**.

``` c
 //  Physical Pixel
 const int ledPin = 13; // the pin that the LED is attached to
 int incomingByte;      // a variable to read incoming serial data into
 void setup() {
   Serial.begin(9600);
   pinMode(ledPin, OUTPUT);
 } 
 void loop() {
   if (Serial.available() > 0) {
     incomingByte = Serial.read();
     if (incomingByte == 'H') {
       digitalWrite(ledPin, HIGH);
     } 
     if (incomingByte == 'L') {
       digitalWrite(ledPin, LOW);
     }
   }
 }
```

- Em outro Arduíno com módulo wireless, carregar o programa abaixo com chave do módulo wireless na **posição USB**. Verificar o funcionamento do programa no **monitor serial**. Depois de carregado o programa mudar a chave do módulo wireless para a **posição micro**.

``` c
 void setup()
 {
   Serial.begin(9600);
 }
 void loop()
 {
   Serial.print('H');
   delay(1000);
   Serial.print('L');
   delay(1000);
 }
```

- Para **testar a comunicação serial sem fio**, conectar o primeiro Arduíno na fonte de alimentação e verificar se a comunicação entre os Arduínos acontece, fazendo o led piscar.
  - Caso não haja comunicação, tente restabelecer a **configuração padrão** (***default***) nos módulos **Xbee** (veja abaixo).

Arduíno Leonardo  
O **Arduíno Leonardo** usa a **Serial** exclusivamente para comunicação com a **porta USB**. Para comunicação serial TTL (5V) nos pinos 0 (RX) and 1 (TX) deve-se utilizar a **Serial1**.

### Endereçamento dos módulos Xbee

Vários parâmetros precisam ser configurados para que os módulos Xbee possam se comunicar:

1.  Os dispositivos precisam estar na mesma **rede**, definida pelo parâmetro **ID**;
2.  Os dispositivos precisam usar o mesmo **canal**, definido pelo parâmetro **CH**;
3.  O **endereço destino** (DH e DL) determina qual módulo da rede receberá os dados:
    - Se o **DH = 0** e o **DL \< 0xFFFF** (i.e. 16 bits), o dado transmitido pelo módulo será recebido por qualquer módulo cujo **endereço** de 16-bit **MY** é igual a **DL**;
    - Se o **DH = 0** e o **DL = 0xFFFF**, o dado transmitido será recebido por **todos** os módulos (*broadcast*);
    - Se o **DH ≠ 0** e o **DL \> 0xFFFF**, o dado transmitido será recebido somente pelo módulo cujo **número serial** seja igual ao **endereço destino** (i.e. **SH = DH** e **SL = DL**).

Síntese de alguns parâmetros:

|               |                                   |                            |
|---------------|-----------------------------------|----------------------------|
| **Parâmetro** | **Descrição**                     | **Valor default**          |
| ID            | Identificador de rede             | 3332                       |
| CH            | Canal                             | C                          |
| SH SL         | Numero de série                   | Diferente para cada módulo |
| MY            | Endereço do módulo                | 0                          |
| DH DL         | Endereço destino                  | 0                          |
| BD            | Vazão da comunicação serial (bps) | 3 (9600 bps)               |

### Configuração do módulo Xbee

Para a configuração do módulo Xbee é interessante utilizar o software [XCTU](http://www.digi.com/support/productdetail?pid=3352) da Digi ou o [moltosenso Network Manager](http://www.moltosenso.com/), os quais apresentam facilidades para configuração e atualização dos módulos wireless.

Exemplo de configuração com o software moltosenso Network Manager  
Baixar e instalar o software **moltosenso Network Manager IRON 1.0** (*Free*):

- Na guia ***Port Setup**'' é possível verificar a configuração da porta, clique em***Open Port**'' e verifique se o dispositivo foi detectado;
- Clique no dispositivo e verifique as informações do mesmo em ***Current Device***;

<a href="Arquivo:moltosenso.png" class="wikilink" title="400px">400px</a>

- Na guia ***Node Settings*** é possível selecionar o módulo e verificar seus parâmetos de configuração;

<a href="Arquivo:moltosenso2.png" class="wikilink" title="400px">400px</a>

- Para **restaurar os parâmetros *default*** do dispositivo clique em ***Restore All**'' e depois em***Write Permanently**'';

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h17min de 30 de outubro de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Arduíno" class="wikilink" title="Categoria:Arduíno">Categoria:Arduíno</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>
