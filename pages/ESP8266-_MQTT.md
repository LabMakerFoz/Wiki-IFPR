# Experimento: MQTT e ESP8266

O suporte para **MQTT** para o **<a href="ESP8266_e_ESP32" class="wikilink" title="ESP8266">ESP8266</a>** é provido por uma **biblioteca** que pode ser obtida em: <https://github.com/knolleary/pubsubclient> .

Neste experimento foi utilizado um **NodeMCU 8266** utilizando a **biblioteca PubSubClient.h** para interagir um com **brocker Mosquitto** e **clientes publicadores** e **subscritores** através do **protocolo MQTT**.

A comunicação foi realizada através de uma **rede local** residencial e foram utilizados os seguintes **endereços IP**:

- brocker **Mosquito**: 192.168.1.19/24
- **ESP**: 192.168.1.24/24 (Obtido por DHCP da rede Wifi)
- Clientes (**mosquitto_pub** e **mosquitto_sub**): 192.168.1.19/24

## Código fonte ESP8266

O **código** abaixo é baseado no exemplo **mqtt_esp8266** da **biblioteca PubSubClient.h**:

``` c
/*
 Basic ESP8266 MQTT example
 Baseado no exemplo da bilbioteca PubSubClient.h: mqtt_esp8266

 Este sketch demonstra a comunicação de um ESP8266 com um brocker Mosquitto usando MQTT:
  - conecta ao brocker e informa lastWill para o tópico "esp/status" com mensagem "off-line"
    (será publicada caso o ESP seja desconectado involuntariamente);
  - publica para o tópico "esp/status" a mensagem  "on-line" anunciando que está ativo;
  - subscreve o tópico "esp/led" para receber comandos para um led;
  - caso receba mensagem para o tópico "esp/led", aciona o led conforme comando recebido.
  - publica periodicamente para o tópico "esp/temp" a temperatura medida por um sensor LM35.
 O ESP se reconecta so servidor caso perca a conexão.
*/

#include <ESP8266WiFi.h>
#include <PubSubClient.h>

//Varíaveis sensor temperatura
char msgTemperatura[10];
float temperatura;

// Identificação da rede Wifi
const char* ssid = "Zhone_EB1C";
const char* password = "aaaaabbbbb";

// Identificação do Brocker
const char* mqtt_server = "192.168.1.19"; 

unsigned long lastMsg = 0;

WiFiClient espClient;
PubSubClient client(espClient);

void setup_wifi() {
  delay(10);
  // Conecta a rede WiFi
  Serial.println();
  Serial.print("Connecting to ");
  Serial.println(ssid);
  WiFi.mode(WIFI_STA);
  WiFi.begin(ssid, password);
  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
  }
  randomSeed(micros());
  Serial.println("");
  Serial.println("WiFi connected");
  Serial.println("IP address: ");
  Serial.println(WiFi.localIP());
}

void callback(char* topic, byte* payload, unsigned int length) {
  Serial.print("Message arrived [");
  Serial.print(topic);
  Serial.print("] ");
  for (int i = 0; i < length; i++) {
    Serial.print((char)payload[i]);
  }
  Serial.println();
  // Aciona LED se 1 for recebido como primeiro caractere
  if ((char)payload[0] == '1') {
    digitalWrite(BUILTIN_LED, HIGH);   
  } else {
    digitalWrite(BUILTIN_LED, LOW);  
  }
}

void reconnect() {
  //Mensagem lastWill
  byte willQoS = 0;
  const char* willTopic = "esp/status";
  const char* willMessage = "OFF_LINE";
  boolean willRetain = true;
  // Loop até reconectar
  while (!client.connected()) {
    Serial.print("Attempting MQTT connection...");
    // Cria identificação randômica do cliente
    String clientId = "ESP8266Client-";
    clientId += String(random(0xffff), HEX);
    if (client.connect(clientId.c_str(), willTopic, willQoS, willRetain, willMessage)) {
      Serial.println("connected");
      // Uma vez conectado publica anúncio:
      char* message = "ON_LINE";
      int length = strlen(message);
      boolean retained = true; 
      client.publish("esp/status", (byte*)message, length, retained);
      // Subscreve tópico
      client.subscribe("esp/led");
    } else {
      Serial.print("failed, rc=");
      Serial.print(client.state());
      Serial.println(" try again in 5 seconds");
      delay(5000);
    }
  }
}

void setup() {
  pinMode(BUILTIN_LED, OUTPUT);     
  Serial.begin(115200);
  setup_wifi();
  client.setServer(mqtt_server, 1883);
  client.setCallback(callback);
}

void loop() {
  if (!client.connected()) {
    reconnect();
  }
  client.loop();
  unsigned long now = millis();
  if (now - lastMsg > 5000) {
    lastMsg = now;
    //Sensor temperatura LM35
    int   analogValue = analogRead(A0);
    float millivolts = (analogValue/1023.0) * 3.3;
    float temperatura = millivolts*100;
    //Publicação da temperatura
    Serial.print("Publish message: ");
    Serial.print("temperature oC = ");
    Serial.println(temperatura);
    //converte temperatura em string
    sprintf(msgTemperatura,"%.1f",temperatura);
    boolean retained = true; 
    client.publish("esp/temp", (byte*)msgTemperatura, strlen(msgTemperatura), retained);
    }
}
```

## Comandos nos terminais clientes MQTT

Cliente Subscritor  
Status

`mosquitto_sub -h 192.168.1.19 -t esp/status`

Cliente Subscritor  
Temperatura

`mosquitto_sub -h 192.168.1.19 -t esp/temp`

Cliente Publicador  

`mosquitto_pub -h 192.168.1.19 -t esp/led -m 1`  
`mosquitto_pub -h 192.168.1.19 -t esp/led -m 0`

## Sensor de temperatura LM35

O **LM35** é um **circuito integrado** exclusivo para medir temperatura com uma tensão de saída variando linearmente com a temperatura em graus Célsius.

  
Esquema de ligação:

`            _______`  
`           |       |`  
`           | LM 35 | `  
`           |_______|`  
`             | | |`  
` (+3,3v) ----+ | +---- (Ground)`  
`               |`  
`          Analog Pin A0`  
`       0mV + 10mV / `<sup>`o`</sup>`C`

:\*O valor de tensão (entre **0V e 3,3V**) lido pela **entrada analógica** é convertido um número digital com **10 bits de magnitude**, ou seja, 2<sup>10</sup> (1024) valores (entre 0 e 1023).

:\*Para obter o valor de tensão, para uso no cálculo da temperatura, multiplica-se o valor digital obtido na leitura por 3.3/1023.

:\*Como a tensão medida pelo sensor varia de 0 mV + 10mV/1<sup>o</sup>C, se multiplicarmos por 100, teremos o valor em graus Celsius:

## Referências

<references />

<a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a> <a href="Categoria:Arduíno" class="wikilink" title="Categoria:Arduíno">Categoria:Arduíno</a>

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 11h19min de 8 de outubro de 2020 (-03)
