# Wemos D1 ESP8266

O módulo **Wemos D1 Mini Pro** é uma placa indicada para utilização em projetos de **Internet das Coisas** que conta com o microcontrolador **ESP8266**, com 16MB de memória *flash* e interface **WiFi**.

**Pinagem**  

<a href="Arquivo:D1_ESP8266_pinagem.png" class="wikilink" title="500px">500px</a> [^1]

## Configuração da IDE do Arduíno para uso com o ESP8266

Instalação da placa do **ESP8266** na **IDE do Arduino**  

1.  IDE -\> Arquivo -\> Preferências
2.  URLs Adicionais para Gerenciadores de Placa: *<http://arduino.esp8266.com/stable/package_esp8266com_index.json>*
3.  Ferramentas -\> Placa -\> Gerenciadores de Placa -\> Instalar ESP8266

Seleção da placa ESP8266 e outros ajustes  

1.  Ferramentas -\> Placa -\> LOLIN(WEMUS) D1 Mini Pro
    - Selecione o módulo ESP8266 que esteja utilizando.
2.  Ferramentas -\> Upload Speed -\> 115200
    - O ESP8266 funciona melhor com a velocidade de 115200;
    - Ao iniciar o monitor serial, ajustar a velocidade de comunicação como 115200 para o correto funcionamento.

Ubuntu 22.04  
Caso um computador com Ubuntu 22.04 ou superior não reconheça a porta USB, realizar o comando para desabilitar a interface de Braile:

`sudo apt-get remove brltty`

## Entradas e Saídas

O módulo **Wemos D1 Mini Pro** possui 9 pinos de **entrada/saída digitais** (com PWM) (níveis lógicos 0V e 3,3V), 2 pinos TX/RX para **comunicação serial** e 1 pino de **entrada analógico** (máximo 3.2V). Todos os pinos de entrada/saída digitais também aceitam **interrupções**.

### Laboratório 1: Saída digital

- Carregar no **Wemos D1** o programa exemplo **Arquivo/Exemplos/Basic/Blink** para piscar o **LED_BUILTIN**.
- O LED_BUILTIN do módulo Wemus é conectado a saída D4 (GPIO 2), entretanto a saída D4 é ativo alto e o LED_BUILTIN e ativo baixo. Coloque um led na saída D4 e verifique o funcionamento.
- Teste o Blink com o led em outros pinos de saída digital.

### Laboratório 2: Entrada digital

- Escolha uma entrada e uma saída do módulo **Wemos D1** e adapte programa exemplo **Arquivo/Exemplos/Digital/Button** para ligar ou desligar um led em função de pressão em chave digital.

### Laboratório 3: Saída PWM

- Escolha uma saída do módulo **Wemos D1** e adapte programa exemplo exemplo **Arquivo/Exemplos/Basic/Fade** para variar a luminosidade do **led**.

### Laboratório 4: Entrada analógica

O pino ADC do ESP8266 tem a tensão de entrada na faixa de 0V a 1V. Entretanto, muitas placas de desenvolvimento vem com um divisor de tensão interno que permite conectar tensões de 0V a 3,3V.

- Montar hardware com utilizando o ponto central de um **potenciômetro** conectado a **entrada analógica** (com os demais terminais conectados ao GND e 3,3V, respectivamente).
- Carregar programa exemplo **Arquivo/Exemplos/Basic/AnalogReadSerial** e verificar o valor da entrada analógica no **monitor serial**.
- Modificar programa exemplo **Arquivo/Exemplos/Basic/ReadAnalogVoltage** para mostrar o valor da entrada analógica em **Volts** no **monitor serial**.

### Laboratório 5: Comunicação Serial

Montar experimento envolvendo **comunicação serial** entre um **Arduíno** e o **ESP8266**.

- Lembrar que o Arduíno trabalha com níveis lógicos 0V e 5V e o ESP8266 0V e 3,3V. Portanto, o TX do Arduíno deve ser conectado ao RX do ESP8266 por meio de um **divisor de tensão**.

## Web Server

Exemplo apresentado em [**Random Nerd Tutorials: Build an ESP8266 Web Server**](https://randomnerdtutorials.com/esp8266-web-server/), mostrando a construção de um **servidor Web** que controla dois leds conectados a um **ESP8266** [^2].

Hardware  
O **Web Server** vai permitir controlar **dois leds**, conectados aos pinos GPIO 4 (D1) e GPIO 5 (D2).

### Código

``` c
/*********
  Rui Santos
  Complete project details at http://randomnerdtutorials.com  
*********/

// Load Wi-Fi library
#include <ESP8266WiFi.h>

// Replace with your network credentials
const char* ssid     = "REPLACE_WITH_YOUR_SSID";
const char* password = "REPLACE_WITH_YOUR_PASSWORD";

// Set web server port number to 80
WiFiServer server(80);

// Variable to store the HTTP request
String header;

// Auxiliar variables to store the current output state
String output5State = "off";
String output4State = "off";

// Assign output variables to GPIO pins
const int output5 = 5;
const int output4 = 4;

// Current time
unsigned long currentTime = millis();
// Previous time
unsigned long previousTime = 0; 
// Define timeout time in milliseconds (example: 2000ms = 2s)
const long timeoutTime = 2000;

void setup() {
  Serial.begin(115200);
  // Initialize the output variables as outputs
  pinMode(output5, OUTPUT);
  pinMode(output4, OUTPUT);
  // Set outputs to LOW
  digitalWrite(output5, LOW);
  digitalWrite(output4, LOW);

  // Connect to Wi-Fi network with SSID and password
  Serial.print("Connecting to ");
  Serial.println(ssid);
  WiFi.begin(ssid, password);
  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
  }
  // Print local IP address and start web server
  Serial.println("");
  Serial.println("WiFi connected.");
  Serial.println("IP address: ");
  Serial.println(WiFi.localIP());
  server.begin();
}

void loop(){
  WiFiClient client = server.available();   // Listen for incoming clients

  if (client) {                             // If a new client connects,
    Serial.println("New Client.");          // print a message out in the serial port
    String currentLine = "";                // make a String to hold incoming data from the client
    currentTime = millis();
    previousTime = currentTime;
    while (client.connected() && currentTime - previousTime <= timeoutTime) { // loop while the client's connected
      currentTime = millis();         
      if (client.available()) {             // if there's bytes to read from the client,
        char c = client.read();             // read a byte, then
        Serial.write(c);                    // print it out the serial monitor
        header += c;
        if (c == '\n') {                    // if the byte is a newline character
          // if the current line is blank, you got two newline characters in a row.
          // that's the end of the client HTTP request, so send a response:
          if (currentLine.length() == 0) {
            // HTTP headers always start with a response code (e.g. HTTP/1.1 200 OK)
            // and a content-type so the client knows what's coming, then a blank line:
            client.println("HTTP/1.1 200 OK");
            client.println("Content-type:text/html");
            client.println("Connection: close");
            client.println();
            
            // turns the GPIOs on and off
            if (header.indexOf("GET /5/on") >= 0) {
              Serial.println("GPIO 5 on");
              output5State = "on";
              digitalWrite(output5, HIGH);
            } else if (header.indexOf("GET /5/off") >= 0) {
              Serial.println("GPIO 5 off");
              output5State = "off";
              digitalWrite(output5, LOW);
            } else if (header.indexOf("GET /4/on") >= 0) {
              Serial.println("GPIO 4 on");
              output4State = "on";
              digitalWrite(output4, HIGH);
            } else if (header.indexOf("GET /4/off") >= 0) {
              Serial.println("GPIO 4 off");
              output4State = "off";
              digitalWrite(output4, LOW);
            }
            
            // Display the HTML web page
            client.println("<!DOCTYPE html><html>");
            client.println("<head><meta name=\"viewport\" content=\"width=device-width, initial-scale=1\">");
            client.println("<link rel=\"icon\" href=\"data:,\">");
            // CSS to style the on/off buttons 
            // Feel free to change the background-color and font-size attributes to fit your preferences
            client.println("<style>html { font-family: Helvetica; display: inline-block; margin: 0px auto; text-align: center;}");
            client.println(".button { background-color: #195B6A; border: none; color: white; padding: 16px 40px;");
            client.println("text-decoration: none; font-size: 30px; margin: 2px; cursor: pointer;}");
            client.println(".button2 {background-color: #77878A;}</style></head>");
            
            // Web Page Heading
            client.println("<body><h1>ESP8266 Web Server</h1>");
            
            // Display current state, and ON/OFF buttons for GPIO 5  
            client.println("<p>GPIO 5 - State " + output5State + "</p>");
            // If the output5State is off, it displays the ON button       
            if (output5State=="off") {
              client.println("<p><a href=\"/5/on\"><button class=\"button\">ON</button></a></p>");
            } else {
              client.println("<p><a href=\"/5/off\"><button class=\"button button2\">OFF</button></a></p>");
            } 
               
            // Display current state, and ON/OFF buttons for GPIO 4  
            client.println("<p>GPIO 4 - State " + output4State + "</p>");
            // If the output4State is off, it displays the ON button       
            if (output4State=="off") {
              client.println("<p><a href=\"/4/on\"><button class=\"button\">ON</button></a></p>");
            } else {
              client.println("<p><a href=\"/4/off\"><button class=\"button button2\">OFF</button></a></p>");
            }
            client.println("</body></html>");
            
            // The HTTP response ends with another blank line
            client.println();
            // Break out of the while loop
            break;
          } else { // if you got a newline, then clear currentLine
            currentLine = "";
          }
        } else if (c != '\r') {  // if you got anything else but a carriage return character,
          currentLine += c;      // add it to the end of the currentLine
        }
      }
    }
    // Clear the header variable
    header = "";
    // Close the connection
    client.stop();
    Serial.println("Client disconnected.");
    Serial.println("");
  }
}
```

### Laboratório 6: Web Server

Procedimentos  

1.  Configurar o **identificador e senha** da rede **Wifi** e carregar o programa no módulo ESP8266;
2.  Verificar com o **monitor serial** se o ESP8266 se conectou corretamente na rede Wifi e verifique o **endereço IP** que obteve;
3.  Testar conectividade com o servidor Web rodando no ESP8266 com **ping**;
4.  Acessar o servidor Web a partir de um **navegador**;
5.  Acompanhar pelo **monitor serial** as informações acerca da **requisição HTTP**;
6.  Testar o **controle dos leds** clicando dos botões correspondentes e acompanhar pelo **monitor serial** as informações acerca de cada **requisição HTTP**.

Funcionamento do código  

1.  Verifique detalhes do funcionamento do código em [^3];
2.  Analise as mensagens de **requisição HTTP** e **resposta HTTP** recebidas e enviadas pelo servidor Web e compare com a especificação do <a href="Protocolo_HTTP" class="wikilink" title="protocolo HTTP"><strong>protocolo HTTP</strong></a>;
3.  Observe o **documento HTML** e **formatação CCS** montado pelo servidor para a representação dos botões no navegador.
    - Programação **HTML** e **CCS** são temas a serem abordados na disciplina de **Desenvolvimento Web** da **Pós-Graduação em Internet das Coisas**.

## Outros exemplos e projetos

Veja outros exemplos de projetos com ESP8266 em [Random Nerd Tutorials](https://randomnerdtutorials.com/projects-esp8266/).

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 17h40min de 8 de novembro de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Arduíno" class="wikilink" title="Categoria:Arduíno">Categoria:Arduíno</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>

[^1]: <https://randomnerdtutorials.com/getting-started-with-esp8266-wifi-transceiver-review/>

[^2]: <https://randomnerdtutorials.com/esp8266-web-server/>

[^3]:
