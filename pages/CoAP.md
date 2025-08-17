# CoAP

Referências: [^1], [^2], [^3], [^4]

## Introdução ao CoAP

O **CoAP** (*Constrained Application Protocol*) (RFC7252) é uma **alternativa mais leve** ao **HTTP**, com alvo nos dispositivos limitados em termos de energia e interface de comunicação. O **CoAP** usa **UDP**, ao invés do **TCP** usado pelo **HTTP**, reduzindo o *overhead* de mensagens ocasionado pela abertura e encerramento de uma conexão TCP, assim como reconhecimentos e retransmissões.

O **CoAP** provê interação usando um **modelo pedido/resposta** (*request/response*) entre aplicações, com comunicação assíncrona por meio de mensagens UDP. Este modelo é semelhante ao modelo **cliente/servidor** usado no HTTP, porém, ambas as máquinas podem atuar nas duas funções, diferente do HTTP. O CoAP apresenta baixo *overhead* de cabeçalho e processamento e suporta URI (*Uniform Resource Identifier*) e *Content-type*.

Pode-se visualizar o **CoAP** em duas camadas, uma **camada de mensagens** interagindo de forma assíncrona com o UDP e uma camada de interações **pedido/resposta** usando métodos e códigos de resposta.

`+----------------------+`  
`|      Application     |`  
`+----------------------+  \`  
`|  Requests/Responses  |  |`  
`|----------------------|  | CoAP`  
`|       Messages       |  |`  
`+----------------------+  /`  
`|          UDP         |`  
`+----------------------+`

**CoAP** roda por padrão na **porta UDP 5683**.

As mensagens **CoAP**, assim como o **HTTP**, seguem a arquitetura **REST** (*Representational State Transfer*) para **criar**, **ler**, **atualizar** ou **apagar** de dados de aplicação em servidores remotos.

## REST (*Representational State Transfer*)

Na **arquitetura REST** um **servidor REST** simplesmente provê acesso a **recursos** e um **cliente REST** acessa e apresenta os recursos. Cada recurso é identificado por uma **URI** (*Uniform Resource Identifier*), que é sua identidade global.

Um sistema com capacidade de aplicar os princípios de **REST** é chamado de **RESTful**.

Métodos **RESTful**  

1.  GET - ler informação
2.  PUT - atualizar informação
3.  POST - criar uma nova informação
4.  DELETE - apagar informação

A arquitetura **REST** é fortemente influenciada pelas tecnologias Web, sendo o **HTTP** uma de suas instâncias mais relevantes.

Muitas **aplicações de IoT** que utilizam **protocolos IP** fazem uso **publicadores MQTT** (sensores) e **subscritores MQTT** (atuadores), mas podem também utilizar **REST Web Services**.

O **CoAP** é um protocolo de transferência **RESTful** para nós e redes com recursos restritos em termos de processamento, memória e consumo de energia.

## Interação entre CoAP e HTTP

Por sua arquitetura **REST**, o **CoAP** pode ser integrado ao **HTTP** por meio de um ***proxy/cache***, permitindo, por exemplo, que um usuário utilizando a Web e HTTP interaja com um dispositivo restrito que suporta o CoAP.

`HTTP Client           `**`Proxy`**`           CoAP Server`  
`     | HTTP GET /temp   |                  |`  
`     +----------------->|  CON GET /temp   |`  
`     |                  +----------------->|`  
`     |                  |   ACK "22.5"     |`  
`     |  200 OK "22.5"   |<-----------------+`  
`     |<-----------------+                  |`  
`     |             `**`cache`**` "22.5"            |`  
`     |                  |                  |`  
`     | HTTP GET /temp   |                  |`  
`     +----------------->|                  |`  
`     |  200 OK "22.5"   |                  |`  
`     |<-----------------+                  |`

## Modelo de mensagens

O **CoAP** usa **mensagens curtas** com **cabeçalho** de tamanho fixo (4 bytes) que podem ser seguidas por **opções** e **dados** (*payload*). Cada mensagem contém um **identificador** (*Message ID*) usado para implementar o serviço de entrega garantida de mensagens.

Para a **entrega garantida** uma mensagem é marcada como **confirmável** (CON). Uma mensagem confirmável é **retransmitida**, usando um **temporizador**, até receber uma **reconhecimento** (ACK). Se o receptor não estiver habilitado a fornecer uma resposta adequada ele responde com a mensagem de ***reset*** (RST).

`Client              Server`  
`   |                  |`  
`   |   CON [0x7d34]   |`  
`   +----------------->|`  
`   |                  |`  
`   |   ACK [0x7d34]   |`  
`   |<-----------------+`  
`   |                  |`

Uma mensagem que não requer confirmação é marcada como **não confirmável** (NON).

`Client              Server`  
`   |                  |`  
`   |   NON [0x01a0]   |`  
`   +----------------->|`  
`   |                  |`

## Modelo pedido/resposta

Os **pedidos** e **respostas** são carregados por **mensagens CoAP**, as quais incluem o **código do método** e da **resposta**.

Os **métodos** utilizados pelo **CoAP** são GET, PUT, POST, e DELETE de modo similar ao **HTTP**.

Os **métodos** podem usar **mensagens confirmáveis** (CON) ou **não confirmáveis** (NON). A **resposta**, se tiver disponível, pode ser enviada imediatamente, confirmável ou não confirmável.

`Client              Server       Client              Server`  
`   |                  |             |                  |`  
`   |   CON [0xbc90]   |             |   CON [0xbc91]   |`  
`   | GET /temperature |             | GET /temperature |`  
`   |   (Token 0x71)   |             |   (Token 0x72)   |`  
`   +----------------->|             +----------------->|`  
`   |                  |             |                  |`  
`   |   ACK [0xbc90]   |             |   ACK [0xbc91]   |`  
`   |   2.05 Content   |             |  4.04 Not Found  |`  
`   |   (Token 0x71)   |             |   (Token 0x72)   |`  
`   |     "22.5 C"     |             |   "Not found"    |`  
`   |<-----------------+             |<-----------------+`  
`   |                  |             |                  |`

`Client              Server`  
`   |                  |`  
`   |   NON [0x7a11]   |`  
`   | GET /temperature |`  
`   |   (Token 0x73)   |`  
`   +----------------->|`  
`   |                  |`  
`   |   NON [0x23bc]   |`  
`   |   2.05 Content   |`  
`   |   (Token 0x73)   |`  
`   |     "22.5 C"     |`  
`   |<-----------------+`  
`   |                  |`

Se a **resposta** não estiver disponível imediatamente, pode ser enviada **posteriormente** em mensagem separada.

`Client              Server`  
`   |                  |`  
`   |   CON [0x7a10]   |`  
`   | GET /temperature |`  
`   |   (Token 0x74)   |`  
`   +----------------->|`  
`   |                  |`  
`   |   ACK [0x7a10]   |`  
`   |<-----------------+`  
`   |                  |`  
`   ... Time Passes  ...`  
`   |                  |`  
`   |   CON [0x23bb]   |`  
`   |   2.05 Content   |`  
`   |   (Token 0x74)   |`  
`   |     "22.5 C"     |`  
`   |<-----------------+`  
`   |                  |`  
`   |   ACK [0x23bb]   |`  
`   +----------------->|`  
`   |                  |`

## Formato das mensagens

As **mensagens CoAP** são codificadas em binário, iniciando com um **cabeçalho fixo** de **4 bytes**.

`   0                   1                   2                   3`  
`   0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1`  
`  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+`  
`  |Ver| T |  TKL  |      Code     |          Message ID           |`  
`  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+`  
`  |   Token (if any, TKL bytes) ...`  
`  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+`  
`  |   Options (if any) ...`  
`  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+`  
`  |1 1 1 1 1 1 1 1|    Payload (if any) ...`  
`  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+`

Campos:

- ***Ver***: 1
- ***T*** (*Type*): CON (0), NON (1), ACK (2) ou RST (3)
- ***TKL***: Comprimento variável do *Token* (0 a 8 bytes).
- ***Code***: Código da mensagem:
  - *Class* (3 bits): *request* (0), *success response* (2), *client error response* (4), *server error response* (5) ou *signaling codes* (7)
  - *Detail* (5 bits): Em caso de pedido, indica o método. Em caso de resposta indica o código da resposta.

`Method:0.XX Success:2.XX Client Error:4.XX Server Error: 5.XX       Signaling Codes: 7.XX`  
`0 EMPTY     1 Created    0 Bad Request     0 Internal Server Error  0 Unassigned`  
`1 GET       2 Deleted    1 Unauthorized    1 Not Implemented        1 CSM`  
`2 POST      3 Valid      2 Bad Option      2 Bad Gateway            2 Ping`  
`3 PUT       4 Changed    3 Forbidden       3 Service Unavailable    3 Pong`  
`4 DELETE    5 Content    4 Not Found       4 Gateway Timeout        4 Release`  
`5 FETCH                  ...               5 Proxying Not Supported 5 Abort`  
`6 PATCH`  
`7 iPATCH`

- ***Message ID***: Identificador da mensagem, usado para detectar duplicatas ou correspondências entre uma mensagem CON com a mensagem ACK/RST ou entre uma mensagem NON com uma mensagem RST (caso o nó não possa processar a mensagem).

Campos opcionais:

- ***Token***: Usado para correlacionar pedidos e respostas
- ***Options***: A especificação CoAP define um conjunto de opções, identificadas por números, para serem utilizadas nas mensagens.
- ***Payload***: Dados

## Observação de Recursos CoAP

Uma característica importante do **CoAP** para aplicações de **IoT** é a possibilidade de **observar recursos**, recebendo atualizações, por exemplo, quando os dados de um sensor são atualizados.

Para observar recursos usa-se um **GET** com a **opção observar**:

`Client                                      Server`  
`   |                                          |`  
`   |   CON GET /temp Observe: 0 Token: 0x3f   |`  
`   +----------------------------------------->|`  
`   |   ACK Observe: 20 Token: 0x3f "22,5"     |`  
`   |<-----------------------------------------+`  
`   |                                          |`  
`   |                                          | temp change`  
`   |   ACK Observe: 21 Token: 0x3f "22,8"     |`  
`   |<-----------------------------------------+`  
`   |            ACK Token: 0x3f               |`  
`   +----------------------------------------->|`  
`   |                                          |`

## Descoberta de Recursos CoAP

Outra característica do **CoAP** para aplicações de **IoT** é a possibilidade de **descoberta de serviços ou recursos**. Esta característica é importante para aplicações de comunicação máquina máquina.

Um servidor é descoberto por um cliente aprendendo a **URI** que referencia um recurso no servidor. Ou, pode utilizar mensagens CoAP ***multicast*** para descobrir servidores.

## URI (*Uniform Resource Identifier*)

Estrutura de uma **URI**:

[`coap://`](coap://)`   host     [:port] path [? query] [#fragment]`

  
parâmetros *query* :

`?key1=value1&key2=value2 `

  
lista de chave/valor separados por &.

`#fragment `

  
é um marcador para um fragmento do próprio recurso.

Exemplo[^5]:

              userinfo       host      port
              ┌──┴───┐ ┌──────┴──────┐ ┌┴┐
      https://john.doe@www.example.com:123/forum/questions/?tag=networking&order=newest#top
      └─┬─┘   └───────────┬──────────────┘└───────┬───────┘ └───────────┬─────────────┘ └┬┘
      scheme          authority                  path                 query           fragment

## Clientes e Servidores CoAP

Algumas referências:

- Artigo: (Porciúncula etal, 2018) [^6]
- Video: [^7]

### Agente Usuário CoAP para Chrome

**Agente usuário** **CoAP** desenvolvido por **Kovatsch Matthias** como **extensão** para o o navegador **Chrome** [^8].

### Cliente e Servidor CoAP para Ubuntu

**coap-client** e **coap-server** baseado na biblioteca **[libcoap](https://libcoap.net/)**.

  
Instalação Ubuntu 20.04:

`sudo apt-get update`  
`sudo apt-get install libcoap2`

### Biblioteca CoAP para Arduíno

Biblioteca **CoAP-simple-library**: [^9], [^10]

### CoAP para Raspberry Pi

**coap-client** e **coap-server** baseado na biblioteca **[libcoap](https://libcoap.net/)**.

Instalação: Ver [^11]

## CoAP: Análise do protocolo com Arduíno e Wireshark

Para a análise do protocolo CoAP foram utilizadas as seguintes ferramentas  

- **Arduíno** e **programas exemplo** da biblioteca **CoAP-simple-library** (IP 192.168.0.30) ;
- **coap-server** e **coap-client**: rodando em **Ubuntu 18.04** (IP 192.168.0.13);
- **wireshark** para captura e análise dos pacotes.

### Cenário 1: Arduíno *request* e coap-server *response*

Cenário com **Arduíno Leonardo** (IP 192.168.0.30) rodando programa exemplo **coaptest** da biblioteca **CoAP-simple-library**, interagindo através de *request* (GET) com servidor **coap-server** (IP 192.168.0.13) rodando em **Ubuntu 18.04**.

O programa **coaptest** no **Arduíno** envia a cada 5s uma **mensagem GET** para o **coap-server** solicitando a **hora relógio** (*time*) e imprime no monitor serial.

Saída do monitor serial do Arduino  

`My IP address: 192.168.0.30`  
`Setup Response Callback`  
`Send Request`  
`Coap Response got:`  
`May 21 10:04:14`  
`Send Request`  
`Coap Response got:`  
`May 21 10:04:19`

  
Mostra a sequência de **mensagens enviadas** (Send Request) e as **respostas recebidas** do servidor (Coap Response got:) seguida da **hora relógio**.

<!-- -->

Captura de pacotes com Wireshark  

<a href="Arquivo:Wireshark-coaptest.png" class="wikilink" title="800px">800px</a>

Mostra duas trocas de mensagens, cada uma incluindo um **pedido CON** (**GET** com confirmação exigida) e a **resposta ACK** (incluindo o **time** solicitado).

<a href="Arquivo:WiresharkFlowGraph-coaptest.png" class="wikilink" title="6--px">6--px</a>

Detalhes da captura de pacotes  

- Destaque para o protocolo de transporte **UDP** e as **portas** CoAP padrão **5683** utilizados pelas mensagens.
- Na primeira mensagem **CoAP** pode-se observar o **Code** (GET) e a **URI** \[Uri-Path: <coap://192.168.0.13/time>\] da solicitação.
- O detalhe da mensagem mostra o **tamanho reduzido** da **mensagem CoAP**, 4 bytes de cabeçalho, mais as opções com o Uri-Path: <coap://192.168.0.13/time>.

### Cenário 2: Arduíno *request* e **coap-server *response* e**coap-client *request* e Arduíno *response*

Cenário com **Arduíno Leonardo** (IP 192.168.0.30) rodando programa exemplo **coapserver** da biblioteca **CoAP-simple-library**, interagindo com um servidor **coap-server** rodando em Ubuntu 18.04 (IP 192.168.0.13) e também respondendo a requisições de um **coap-client** rodando no mesmo Ubuntu 18.04 (IP 192.168.0.13).

O programa **coapserver** no **Arduíno** também envia a cada 5s uma requisição (GET) para o **coap-server** solicitando a **hora relógio** (*time*) e imprime no monitor serial. Além disto, aceita requisições de um **coap-client** (PUT) que permite comandar um led conectado a uma porta do Arduíno.

Comando executado no coap-client  

`coap-client -e "0" -m put `[`coap://192.168.0.30/light`](coap://192.168.0.30/light)

  
para desligar o led

`coap-client -e "1" -m put `[`coap://192.168.0.30/light`](coap://192.168.0.30/light)

  
para ligar o led

<!-- -->

Captura de pacotes com Wireshark  

<a href="Arquivo:WiresharkFlowGraph-coapserver.png" class="wikilink" title="800px">800px</a>

Análise dos pacotes capturados  

- Na **marca de tempo 9,41...** o **Arduíno** requisita (CON GET) a **hora relógio** ao **coap-server** e recebe a resposta (ACK);
- Na **marca de tempo 11,79...** o **coap-client** requisita (CON PUT) ao **Arduíno** para apagar led.
- Na **marca de tempo 14,26...** uma nova requisição (CON PUT) com mesmo identificador (MID) pois não houve resposta imediata.
- Nas **marcas de tempo 14,4172... e 14,4187...** as respostas (ACK) foram enviadas.
- Na **marca de tempo 14,4188...** uma mensagem ICMP (Destination unreachable) foi enviada pelo **coap-client** ao **Arduíno** pois mesmo encerrou após o recebimento da primeira resposta.
- Na sequência tivemos mais duas requisições (CON GET) de hora relógio pelo **Arduíno** ao **coap-server** e mais uma última requisição (CON PUT) pelo **coap-client** ao **Arduíno**.

#### Agente usuário Copper (Cu)

Outra maneira de interagir com o **Arduíno** rodando o **coapserver** para acionamento de leds é através da extensão **Copper (Cu)** no **Google Chrome**:

<a href="Arquivo:Copper.png" class="wikilink" title="800px">800px</a>

## Referências

<references />

<a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a> <a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 15h22min de 14 de maio de 2020 (-03)

[^1]: <https://www.rfc-editor.org/info/rfc7252>

[^2]: <https://en.wikipedia.org/wiki/Constrained_Application_Protocol>

[^3]: <http://www.tigli.fr/lib/exe/fetch.php?media=cours:tutorial_rest_coap_mit_2016_2017.pdf>

[^4]: Zach Shelby. Constrained Application Protocol (CoAP) Tutorial: <https://www.youtube.com/watch?v=4bSr5x5gKvA>

[^5]: <https://en.wikipedia.org/wiki/Uniform_Resource_Identifier>

[^6]: Cleber B. da Porciúncula, Sílvio Beskow, Daniel Stefani Marcon e Jéferson Campos Nobre. [Constrained Application Protocol (CoAP) no Arduino UNO R3: Uma Análise Prática](https://sol.sbc.org.br/index.php/wpietf/article/view/3212/3174), Anais do V Workshop Pré-IETF, 2018.

[^7]: <https://www.youtube.com/watch?v=pfG8uEDZj5g>

[^8]: <https://github.com/mkovatsc/Copper4Cr>

[^9]: <https://www.arduinolibraries.info/libraries/co-ap-simple-library>

[^10]: <https://github.com/hirotakaster/CoAP-simple-library>

[^11]: <https://raspberry-valley.azurewebsites.net/CoAP-Getting-Started/>
