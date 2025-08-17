# Experimento: MQTT e Arduino

O suporte para **MQTT** para **Arduíno** é provido por uma **biblioteca** que pode ser obtida em: <https://github.com/knolleary/pubsubclient> .

Uma boa descrição do uso da biblioteca **PubSubClient.h** pode ser encontrada em: [^1]

Para interagir com a **rede** é necessário um ***shild* Ethernet** colocado sobre a placa Arduíno.

## Descrição do experimento

Neste experimento foi utilizado um **Arduino UNO** com um ***Shield* Ethernet**, rodando a **biblioteca PubSubClient.h** para interagir um com **brocker Mosquitto** e **clientes publicadores** e **subscritores** através do **protocolo MQTT**.

A comunicação foi realizada através de uma **rede local** residencial e foram utilizados os seguintes **endereços IP**:

- brocker **Mosquito**: 192.168.1.19/24
- **Arduino**: 192.168.1.50/24
- Clientes (**mosquitto_pub** e **mosquitto_sub**): 192.168.1.19/24

### Código fonte Arduino

O **código** Arduino abaixo descreve o cenário da aplicação e ilustra o uso das funções da **biblioteca PubSubClient.h** para implementar a comunicação MQTT.

``` c
/*            
 Baseado no exemplo da bilbioteca PubSubClient.h: Basic MQTT example

 Exemplo: MQTT com Arduíno/Shield Ethernet e Mosquitto: 
 Anunciar status do Arduino, receber comando para led e publicar status do led.

 Este sketch demonstra a comunicação de um Arduino com um brocker Mosquitto usando MQTT:
  - conecta ao brocker e informa lastWill para o tópico "arduino/status" com mensagem "off-line"
    (será publicada caso o Arduino seja desconectado involuntariamente);
  - publica para o tópico "arduino/status" a mensagem  "on-line" anunciando que está ativo;
  - subscreve o tópico "arduino/led" para receber comandos para um led;
  - caso receba mensagem para o tópico "arduino/led", aciona o led conforme comando recebido.
*/

#include <SPI.h>
#include <Ethernet.h>
#include <PubSubClient.h>

// Endereçamento IP utilizado para o cliente e servidor
byte mac[]    = { 0xDE, 0xED, 0xBA, 0xFE, 0xFE, 0xED };
IPAddress ip(192, 168, 1, 50);
IPAddress server(192, 168, 1, 19);

EthernetClient ethClient;
PubSubClient client(ethClient);

//Função callback chamada quando uma mensagem for recebida para subscrições:
void callback(char* topic, byte* payload, unsigned int length) {
  Serial.print("message arrived [");
  Serial.print(topic);
  Serial.print("] ");
  for (int i=0;i<length;i++) {
    Serial.print((char)payload[i]);
  }
  Serial.println();
  //comanda o LED
  if ((char)payload[0] == '1') {
    digitalWrite(4, HIGH);
  } else if  ((char)payload[0] == '0') {
    digitalWrite(4, LOW);
  } 
}

void setup()
{
  Serial.begin(57600);

  pinMode(4, OUTPUT);

  client.setServer(server, 1883);
  client.setCallback(callback);

  Ethernet.begin(mac, ip);
  delay(5000); // Allow the hardware to sort itself out
  
  delay(10000);
}

void loop(){
  // Aguarda conexão    
  while (!client.connected()) {

    Serial.print("Attempting MQTT connection...");

    //Mensagem lastWill
    byte willQoS = 0;
    const char* willTopic = "arduino/status";
    const char* willMessage = "OFF_LINE";
    boolean willRetain = true;
    //Conexão
    if (client.connect("arduinoClient", willTopic, willQoS, willRetain, willMessage)) {
      Serial.println("connected");
      //Uma vez conectado publica status
      char* message = "ON_LINE";
      int length = strlen(message);
      boolean retained = true; //Retain message
      client.publish("arduino/status", (byte*)message, length, retained);
      // ... and resubscribe
      client.subscribe("arduino/led");
    } else {
      Serial.print("failed, rc=");
      Serial.print(client.state());
      Serial.println(" try again in 5 seconds");
      delay(5000);
    }
  }
  //Uma vez conectado client.loop() deve ser chamada periodicamente para manter conexão
  //e aguardar recebimento de mensagens
  client.loop();
}        
```

## Comandos nos terminais clientes MQTT

Cliente Subscritor  

`mosquitto_sub -h 192.168.1.19 -t arduino/status`

Cliente Publicador  

`mosquitto_pub -h 192.168.1.19 -t arduino/led -m 1`  
`mosquitto_pub -h 192.168.1.19 -t arduino/led -m 0`

## Análise da troca de mensagens com Wireshark

A comunicação foi realizada através de uma **rede local** residencial e foram utilizados os seguintes **endereços IP**:

- Brocker **Mosquito**: 192.168.0.13/24
- **Arduino**: 192.168.0.30/24
- Clientes (**mosquitto_pub** e **mosquitto_sub**): 192.168.0.18/24

<a href="Arquivo:brockerMQTT&amp;Arduino.png" class="wikilink" title="Arquivo:brockerMQTT&amp;Arduino.png">Arquivo:brockerMQTT&amp;Arduino.png</a>

Análise das mensagens trocadas  

- Na **marca de tempo 5.6...** um **cliente** se conectou ao **brocker** e subscreveu o **tópico "status"**.
- Na **marca de tempo 36.3...** o **Arduíno** se conectou ao **brocker** e informou **tópico/mensagem lastWill** (**"status = OFF_LINE"**), publicou o **tópico "status = ON_LINE"** e subscreveu o **tópico "led"**. O **brocker** também publicou o **tópico "status"** para o **cliente**.
- Na **marca de tempo 42.6...** outro **cliente** se conectou ao **brocker** e publicou o **tópico "led = ON"**. O **brocker** também publicou o **tópico "led = ON"** ao **Arduino** (que **acionou um led**) e publicou ao cliente o **tópico "status = ON_LINE: led ON"**
- Em seguida o Arduíno foi desligado.
- Na **marca de tempo 65.6..., como o**brocker**não recebeu do Arduíno um PINGREC, ele supos que o**Arduino**foi**desconectado involuntariamente**e publicou ao cliente o**tópico "status = OFF_LINE"'''.

Observação  
As **mensagens em preto**, com indicação de *TCP ACKED unseen segment*, como indicado em [^2], "se referem a pacotes que foram transferidos e reconhecidos, mas que não foram capturados pelo Wireshark. Usualmente isto acontece quando o dispositivo não é rápido o suficiente". O que pede ser o caso do Arduino.

## Projeto: Arduíno e MQTT

Construir um projeto utilizando dois **Arduínos** e comunicação utilizando o **protocolo MQTT**. Um dos Arduínos deve **monitorar sensores** (temperatura, luminosidade ou outros) e **publicar** periodicamente os dados lidos em um **broker MQTT**. O outro Arduío deve **subscrever tópicos** no **broker** e, a partir dos tópicos subscritos, **comandar dispositivos**, como relés, leds ou motores.

## Referências

<references />

<a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a> <a href="Categoria:Arduíno" class="wikilink" title="Categoria:Arduíno">Categoria:Arduíno</a>

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 17h21min de 27 de junho de 2023 (-03)

[^1]: Nick O’Leary. Arduino PubSubClient - MQTT Client Library Encyclopedia, September 13, 2015 <https://www.hivemq.com/blog/mqtt-client-library-encyclopedia-arduino-pubsubclient/>

[^2]: <https://osqa-ask.wireshark.org/questions/46134/tcp-acked-unseen-segment>
