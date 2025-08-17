# Arduíno: Ethernet

## Comunicação usando módulo Ethernet

O módulo **Ethernet** (*'Ethernet*Shield**''), juntamente com a**[biblioteca Ethernet.h](https://www.arduino.cc/reference/en/libraries/ethernet/)**, permite que um Arduíno se conecte a Internet. Esta biblioteca provê funcionalidades tanto para**cliente**quanto par**servidor**, além de permitir a conexão com a**rede local**tanto usando**IP fixo**,**DHCP**e também usando**DNS'''.

<a href="Arquivo:Arduino_Ethernet_Shield.jpg" class="wikilink" title="300px">300px</a>

O **Ethernet Shield 2** permite conectar o Arduíno a rede local e a Internet com conector RJ45 e velocidade de 10/100 Mbps. A conexão do *shield* com o Arduíno é realizada pelo barramento **SPI** (*Serial Peripheral Interface*), que faz uso dos pinos 10, 11, 12 e 13 do Arduíno para comunicação e necessita da biblioteca **SPI.h**. O SPI é uma interface de comunicação serial síncrona usada para comunicação em distâncias curtas. O Ethernet Shield possui ainda um *slot* para **cartão SD** e usa o pino 4 para controlar o pino de seleção do cartão SD.

Para uso do módulo Ethernet há uma serie de exemplos prontos ([Examples from Libraries](https://www.arduino.cc/en/Tutorial/LibraryExamples)).

### Laboratório 1: Web Server

Este laboratório mostra como utilizar um *'Ethernet*Shield**'' juntamente com o**Arduíno**para criar um**Web Server''' que forneça informações sobre sensores conectados a entradas analógicas [^1].

Procedimentos  

1.  Conectar o **Shield Ethernet** a placa Arduíno e a **rede local** (usando cabos de rede CAT 5/6 e conector RJ45);
2.  Conectar alguns **sensores** as **entradas analógicas** do Arduíno para monitorar via Web (Pode Modificar o programa exemplo em função dos sensores que utilizar);
3.  Carregar o **programa exemplo**: [**Arquivo/Exemplos/Ethernet/WebServer**](https://www.arduino.cc/en/Tutorial/LibraryExamples/WebServer);
    - **Atenção**:
      - Configurar **IP** de acordo com a **<a href="Rede_Academica_do_Campus" class="wikilink" title="Rede Acadêmica do Campus">Rede Acadêmica do Campus</a>**;
      - Configurar **MAC** único para a rede local.
    - **Sugestão**: Configurar último byte **MAC** com o número do Kit utilizado e o **IP** com 2xx, onde xx é o número do Kit utilizado.
4.  Testar a conectividade com o **servidor Web** com o aplicativo de rede **ping**;
5.  Testar o acesso ao **servidor Web** a partir de um **navegador**.

#### Análise do funcionamento do programa Web Server

Código exemplo  
[^2] Comentários traduzidos.

``` c
/*
 Web Server
 Servidor Web simples que mostra os valores das entradas analógicas.
*/
#include <SPI.h>
#include <Ethernet.h>
// Definição do endereço MAC:
// São 6 bytes em hexadecimal e deve ser único para a rede local.
byte mac[] = {
  0xDE, 0xAD, 0xBE, 0xEF, 0xFE, 0xED
};
// Definição do endereço IP fixo:
IPAddress ip(192, 168, 71, 2xx);
// Inicialização do servidor e definição da porta para escuta 
// (porta 80 é default para HTTP):
EthernetServer server(80);
void setup() {
  // Inicialização da serial
  Serial.begin(9600);
  while (!Serial) {
    ; // Espera serial conectar. 
  }
  Serial.println("Ethernet WebServer Example");
  // Inicialização da conexão Ethernet e do servidor:
  Ethernet.begin(mac, ip);
  // Checa se o hardware Ethernet está presente:
  if (Ethernet.hardwareStatus() == EthernetNoHardware) {
    Serial.println("Ethernet shield was not found:(");
    while (true) {
      delay(1); // Nada a fazer sem hardware Ethernet
    }
  }
  if (Ethernet.linkStatus() == LinkOFF) {
    Serial.println("Ethernet cable is not connected.");
  }
  // Inicialização do servidor
  server.begin();
  Serial.print("server is at ");
  Serial.println(Ethernet.localIP());
}
void loop() {
  // Escuta por clientes
  EthernetClient client = server.available();
  if (client) {
    Serial.println("new client");
    // Requisições HTTP terminam com uma linha em branco
    boolean currentLineIsBlank = true;
    while (client.connected()) {
      if (client.available()) {
        char c = client.read();
        Serial.write(c);
        // Se chegou no final da linha (recebeu caractere: newline)
        // e a linha é vazia, a requisição HTTP terminou,
        // portando, envia resposta:
        if (c == '\n' && currentLineIsBlank) {
          // Envia cabeçalho da resposta HTTP 
          client.println("HTTP/1.1 200 OK");
          client.println("Content-Type: text/html");
          client.println("Connection: close");  // fecha a conexão após resposta
          client.println("Refresh: 5");  // atualiza página a cada 5 s
          client.println();
          client.println("<!DOCTYPE HTML>");
          client.println("<html>");
          // Imprime a saída de cada porta analógica
          for (int analogChannel = 0; analogChannel < 6; analogChannel++) {
            int sensorReading = analogRead(analogChannel);
            client.print("analog input ");
            client.print(analogChannel);
            client.print(" is ");
            client.print(sensorReading);
            client.println("<br />");
          }
          client.println("</html>");
          break;
        }
        if (c == '\n') {
          // Se está iniciando nova linha
          currentLineIsBlank = true;
        } else if (c != '\r') {
          // Se recebeu novo caractere na nova linha
          currentLineIsBlank = false;
        }
      }
    }
    // Tempo para processar o dado
    delay(1);
    // Fecha a conexão:
    client.stop();
    Serial.println("client disconnected");
  }
}
```

Comentários e complementos sobre a requisição HTTP  

- **<a href="Protocolo_HTTP" class="wikilink" title="Protocolo HTTP">Protocolo HTTP</a>**: Veja formato da mensagem de requisição HTTP;
- O programa não faz checagem do **método** (GET, PUT, POST, ... ) recebido na mensagem de requisição (aceita qualquer coisa, mesmo mensagem vazia).

### Laboratório 2: Análise do Web Server com Wireshark

Ativar análise de pacotes com **Wireshark** utilizando filtro para IP e TCP porta 80:

`ip.addr == 192.168.71.2xx and tcp.port == 80`

Obs: Fechar outras janelas de navegador que estejam ativas no computador;

Análise de interação com navegador  

Utilizar **navegador** para acessar **servidor Web** rodando no **Arduíno** e analisar pacotes com **Wireshark**.

Procedimentos:

1.  Abrir navegador a acessar IP do Servidor Web;
2.  Acompanhar mensagens no monitor serial do Arduíno;
3.  Acompanhar dados recebidos pelo no navegador;
4.  Identificar no Wireshark as mensagens de abertura e fechamento de conexão TCP;
5.  Identificar no Wireshark as mensagens HTTP com troca de informações e os reconhecimentos enviados pelo TCP.

Análise de interação com telnet  

Iniciar uma nova captura de pacotes com o Wiewshark.

Acessar **servidor Web** rodando no **Arduíno** com **telnet** na **porta 80** e analisar pacotes com **Wireshark**:

`telnet 192.168.71.2xx 80`

Procedimentos:

1.  Acompanhar mensagens no monitor serial do Arduíno;
2.  Acompanhar dados recebidos pelo terminal telnet;
3.  Identificar no Wireshark as mensagens de abertura de conexão TCP;
4.  Digitar uma sequência de caracteres: GET (ou outra qualquer);
    - Acompanhar mensagens no monitor serial do Arduíno;
    - Acompanhar dados recebidos pelo telnet;
    - Identificar no Wireshark as mensagens trocadas;
5.  Enviar linha vazia CRLF (Enter):
    - Acompanhar mensagens no monitor serial do Arduíno;
    - Acompanhar dados recebidos pelo telnet;
    - Identificar no Wireshark as mensagens trocadas e o encerramento da conexão TCP.

Análise de interação com curl  

Repetir procedimentos acessando **servidor Web** rodando no **Arduíno** com **curl** e analisar pacotes com **Wireshark**:

`curl 192.168.71.2xx`

### Laboratório 3: DHCP Address Print

Este laboratório mostra como configurar o arduíno para obter endereço IP dinamicamente com DHCP. O endereço obtido é impresso no monitor serial. [^3].

Procedimentos  

1.  Conectar o **Shield Ethernet** a placa Arduíno e a **rede local** (usando cabos de rede CAT 5/6 e conector RJ45);
2.  Carregar o **programa exemplo**: [**Arquivo/Exemplos/Ethernet/DhcpAddressPrinter**](https://www.arduino.cc/en/Tutorial/LibraryExamples/DhcpAddressPrinter);
3.  Rodar o programa e observar no **monitor serial** o endereço IP obtido por **DCHP**;
4.  Testar a conectividade com o aplicativo de rede **ping**.

### Laboratório 4: Consulta a Servidor de Data/Hora

Este laboratório mostra como utilizar um *'Ethernet*Shield***para o **Arduíno** obter. por meio de uma requisição **UDP**, a **dada e hora** de um servidor da Internet por meio do **protocolo NTP** (*Network Time Protocol'') [^4]. Neste exemplo o Arduíno recebe endereço IP dinamicamente de um servidor**DHCP'''.

Procedimentos  

1.  Conectar o **Shield Ethernet** a placa Arduíno e a **rede local** (usando cabos de rede CAT 5/6 e conector RJ45);
2.  Carregar o **programa exemplo**: [**Arquivo/Exemplos/Ethernet/UdpNtpClient**](https://www.arduino.cc/en/Tutorial/LibraryExamples/UdpNtpClient);
3.  Testar o programa e acompanhar pelo **monitor serial** a data e hora obtida.
4.  Pesquisar e testar consulta a servidores NTP no Brasil.

## Cartão SD do módulo Ethernet

O **Ethernet *Shield* 2** possui um *slot* para **cartão SD** que pode ser utilizado para gravação e leitura de dados com ajuda da **biblioteca SD**. A biblioteca usa nomes curtos 8.3 para arquivos (8 caracteres para o nome do arquivo e 3 para extensão) e o diretório de trabalho é sempre a raiz do cartão SD.

A comunicação entre o microcontrolador e o cartão SD usa o barramento SPI, que faz uso dos pinos 10, 11, 12 e 13 do Arduíno. O pino 4 é usado também para controlar a seleção do cartão SD.

### Laboratório 5: Escrita e leitura no cartão SD

Este laboratório mostra como utilizar o **cartão SD** para escrita e leitura de dados em um arquivo.

Procedimentos  

1.  Conectar o **Shield Ethernet** a placa Arduíno e inserir um **cartão SD** no módulo;
2.  Carregar o **programa exemplo**: [**Arquivo/Exemplos/SD/ReadWrite**](https://www.arduino.cc/en/Tutorial/LibraryExamples/ReadWrite);
3.  Testar o programa e acompanhar pelo **monitor serial** o processo de escrita e leitura.

### Laboratório 6: Armazenamento de dados de sensores em cartão SD

Este laboratório mostra como utilizar o **cartão SD** para armazenamento de dados de sensores em um arquivo.

Procedimentos  

1.  Conectar o **Shield Ethernet** a placa Arduíno e inserir um **cartão SD** no módulo;
2.  Conectar ao Arduíno três **sensores** para leitura pelas entradas **analógicas**;
3.  Carregar o **programa exemplo**: [**Arquivo/Exemplos/SD/Datalogger**](https://www.arduino.cc/en/Tutorial/LibraryExamples/Datalogger);
4.  Adaptar o programa exemplo para os sensores conectados.

## Projeto: Servidor Web com armazenamento de dados em cartão SD

Construa um **servidor Web** rodando em um **Arduíno**, capaz de ler periodicamente um **sensor de temperatura** e, a cada leitura, armazenar os dados como uma linha de um arquivo em **cartão SD**. Os dados de cada leitura do sensor devem ser acompanhados da **data e hora** consultadas em um **servidor NTP**.

A cada acesso ao **servidor Web** através de um **navegador**, o servidor deve fornecer as **leituras** dos dados do **sensor de temperatura**.

Obs:

- O programa para o servidor Web pode combinar vários dos exemplos vistos nos laboratórios.
- Consulte outros programas exemplos das bibliotecas **Ethernet** e **SD**.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 16h26min de 20 de junho de 2023 (-03)

------------------------------------------------------------------------

<a href="Categoria:Arduíno" class="wikilink" title="Categoria:Arduíno">Categoria:Arduíno</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>

[^1]: <https://www.arduino.cc/en/Tutorial/LibraryExamples/WebServer>

[^2]: <https://www.arduino.cc/en/Tutorial/LibraryExamples>

[^3]: <https://www.arduino.cc/en/Tutorial/LibraryExamples/DhcpAddressPrinter>

[^4]: <https://www.arduino.cc/en/Tutorial/LibraryExamples/WebServer>
