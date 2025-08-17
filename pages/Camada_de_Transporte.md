# Camada de Transporte

A **Camada de Transporte** está situada entre a camada aplicação e a camada rede da <a href="Arquitetura_Internet" class="wikilink" title="Arquitetura Internet">Arquitetura Internet</a> e tem a função de prover um **canal de comunicação lógico fim-a-fim entre os processos de aplicação** rodando em diferentes computadores [^1].

Os dois **Protocolos de Transporte** da Internet são o **TCP** e o **UDP**:

<a href="Protocolo_TCP" class="wikilink" title="Protocolo TCP">Protocolo TCP</a>  
Oferece um serviço orientado a conexão, com **transmissão de dados garantida** ou livre de erros.

<a href="Protocolo_UDP" class="wikilink" title="Protocolo UDP">Protocolo UDP</a>  
Oferece um serviço não orientado a conexão, com transmissão de dados tipo **melhor esforço**, portanto sujeita a erros.

Apesar da diferença nos serviços oferecidos pelo TCP e UDP, ambos implementam um serviço de **multiplexação/demultiplexação de aplicações** e um serviço de **checagem de erros** através do método de ***<a href="Checksum" class="wikilink" title="Checksum">Checksum</a>***.

## Suporte a serviços comuns para as aplicações

O objetivo das redes de pacotes é oferecer um suporte de comunicação para que as aplicações rodando em dois computadores remotos possam trocar informações.

Intuitivamente, podemos ver a rede como provendo um **canal lógico de comunicação** para que os processos de aplicação cliente e servidor possam se comunicar. Para usar este canal de comunicação, os programas de aplicação cliente enviam seus pedidos através de uma **porta**, que conecta o cliente ao servidor, e através da qual ele espera a resposta do serviço é requisitado.

<a href="Arquivo:CanalLogicoTransporte.png" class="wikilink" title="Arquivo:CanalLogicoTransporte.png">Arquivo:CanalLogicoTransporte.png</a>

Dois tipos comuns de serviço solicitado pelas aplicações à rede são:

- Serviço tipo **pedido/resposta** (*request/reply*);
- Serviço tipo **fluxo de áudio/vídeo** (*audio/video streaming*).

A **paginação na Web** é um exemplo de serviço tipo **pedido/resposta**, onde um processo cliente solicita uma informação e um processo servidor fornece a informação solicitada. Não há restrições de tempo entre o pedido e a resposta, entretanto, é necessário que a informação transmitida seja livre de erros.

Uma **conversa telefônica** via Internet é um exemplo de **fluxo de áudio**, neste caso há restrições temporais na transmissão, por outro lado, um pequeno silêncio ocasionado por um erro ou ruído pode não ser um problema grave para o entendimento geral da conversa.

<a href="Arquivo:ArquiteturaInternet.jpeg" class="wikilink" title="Arquivo:ArquiteturaInternet.jpeg">Arquivo:ArquiteturaInternet.jpeg</a> -\> <a href="Arquivo:CamadasInternet2.jpeg" class="wikilink" title="Arquivo:CamadasInternet2.jpeg">Arquivo:CamadasInternet2.jpeg</a>

Para estes dois tipos de requisições de serviços a **Internet** dispõem de dois **protocolos de transporte**:

- **TCP** (*Transmission Control Protocol*), que oferece serviço orientado a conexão e com transmissão de dados garantida;
- **UDP** (*User Datagram Protocol*), que oferece serviço sem conexão tipo **melhor esforço** (*best effort*).

As aplicações conhecidas como o telnet, correio eletrônico, transferência de arquivos e WWW usam o TCP. Outras aplicações usam o UDP, como o DNS (Domain Name System) e aplicações multimídia como voz sobre Internet e aplicações de áudio e vídeo[^2].

Quando uma aplicação usa **TCP** o cliente e o servidor trocam pacotes de controle entre si antes de enviarem os pacotes de dados. Isto é chamado de procedimento de **estabelecimento de conexão** (*handshaking*), onde se estabelecem os parâmetros para a comunicação. Uma vez concluído o *handshaking* a conexão é dita estabelecida e os dois sistemas terminais podem trocar dados. O serviço de **transferência garantida**, que assegura que os dados trocados são livres de erro, o que é conseguido a partir de **temporizações**, **mensagens de reconhecimento** e **retransmissão de pacotes**. Por exemplo, quando um sistema terminal B recebe um pacote de A, ele envia um reconhecimento; quando o sistema terminal A recebe o reconhecimento ele sabe que o pacote que ele enviou foi corretamente recebido; caso A não recebe confirmação, ele assume que o pacote não foi recebido por B e retransmite o pacote.

Com o **UDP** não há *handshaking*, portanto, é **não orientado a conexexão**. Quando um lado de uma aplicação quer enviar pacotes ao outro lado ele simplesmente envia os pacotes. Como o **serviço é não garantido**, também não há reconhecimento, de forma que a fonte nunca tem certeza que o pacote foi recebido pelo destinatário. Como o serviço é mais simples, os dados podem ser enviados mais rapidamente.

## Multiplexação/demultiplexação de aplicações através de portas

A **camada rede** e o **protocolo IP** são responsáveis por entregar **datagramas**, ou pacotes IP, de um host a outro host, identificados pelos **endereços IP** origem e destino.

Como em cada host podem haver vários **processos de aplicação** rodando, a **camada transporte**, com os **protocolos TCP e UDP**, são responsáveis por entregar pacotes, chamados **segmentos**, de um processo rodando em um host origem a outro processo rodando no host destino, identificados pelos **números de porta** origem e destino. Este serviço é chamado multiplexação / demultiplexação de aplicações.

### Exemplo 1: Cliente e servidor HTTP

  
Um servidor de aplicações espera conexões em portas bem conhecidas. Por exemplo, um **servidor Web** utiliza a **porta 80** para aceitar conexões. Quando um **navegador Web** inicia uma seção, ele envia ao servidor um **segmento TCP** com porta **destino 80** e coloca como número de porta origem uma porta que não esteja sendo utilizada no host cliente, por exemplo, a **porta 18123**. A porta 18123 será onde o cliente vai esperar a resposta do servidor. Quando o servidor recebe o segmento, ele verifica que o mesmo é endereçado a porta 80 e então sabe que se trata da aplicação Web. No envio da resposta o servidor inverte as portas origem e destino. Enviando ao cliente um segmento com porta destino 18123 e origem 80.

<a href="Arquivo:PortasTCP.png" class="wikilink" title="Arquivo:PortasTCP.png">Arquivo:PortasTCP.png</a>

### Portas reservadas e portas de uso geral

- Portas de 0 a 1023: **Portas reservadas**, utilizadas pela aplicações bem conhecidas.
- Portas de 1024 a 65535: **Portas de uso geral**.

Algumas portas reservadas  

|       |            |                      |
|-------|------------|----------------------|
| Porta | Transporte | Aplicação            |
| 13    | TCP        | Daytime              |
| 13    | UDP        | Daytime              |
| 20    | TCP        | FTP \[Default Data\] |
| 21    | TCP        | FTP \[Control\]      |
| 22    | TCP        | SSH                  |
| 23    | TCP        | Telnet               |
| 25    | TCP        | SMTP (email)         |
| 53    | UDP        | DNS                  |
| 80    | TCP        | Web HTTP             |
| 110   | TCP        | POP3                 |
| 443   | TCP        | HTTPS                |

- [Wikipédia: Lista de portas de protocolos](http://pt.wikipedia.org/wiki/Lista_de_portas_de_protocolos)

### Exemplo 2: Três clientes e um servidor Web

  
No *host* A temos dois processos cliente Web acessando o servidor C (porta 80), cada um identificado por uma porta origem (1028 e 1029, respectivamente). No host B temos outro processo cliente (porta 1155) está acessando o servidor C (porta 80). O servidor encaminha as respostas ao cliente identificando o IP e a porta correspondente.

<a href="Arquivo:PortasTCP2.png" class="wikilink" title="Arquivo:PortasTCP2.png">Arquivo:PortasTCP2.png</a>

<!-- -->

Perguntas  

1.  É possível que o host A e o host B acessem o servidor C utilizando a mesma porta origem? Explique.
2.  Liste quantos e quais campos são necessários na estrutura de dados que o servidor deve manter para identificar corretamente cada um dos processos clientes que acessam cada um dos serviços que ele oferece.

## Checksum

O ***<a href="Checksum" class="wikilink" title="Checksum">Checksum</a>*** é serviço de **checagem de erros** em mensagens transmitidas na forma de pacotes.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h33min de 12 de junho de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: KUROSE, J.F; ROSS K. W. Redes de Computadores e a Internet: Uma abordagem *top-down*, São Paulo: Pearson, 2010.

[^2]: KUROSE, J.F; ROSS K. W. Redes de Computadores e a Internet: Uma abordagem *top-down*, São Paulo: Pearson, 2010.
