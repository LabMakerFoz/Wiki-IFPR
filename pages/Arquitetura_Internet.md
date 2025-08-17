# Arquitetura Internet

## Camadas de Protocolos

A **arquitetura Internet** organiza os protocolos de rede da Internet em **quatro camadas**:

<a href="Arquivo:ArquiteturaInternet.jpeg" class="wikilink" title="Arquivo:ArquiteturaInternet.jpeg">Arquivo:ArquiteturaInternet.jpeg</a> -\> <a href="Arquivo:CamadasInternet.jpeg" class="wikilink" title="Arquivo:CamadasInternet.jpeg">Arquivo:CamadasInternet.jpeg</a>

Ilustração das **camadas** da **arquitetura Internet** e seus principais **protocolos**:

<a href="Arquivo:ArquiteturaInternet.png" class="wikilink" title="Arquivo:ArquiteturaInternet.png">Arquivo:ArquiteturaInternet.png</a>

Camada Enlace/Física  
Trata da **comunicação entre nós vizinhos** diretamente conectados por **enlaces de comunicação**.

<!-- -->

  
A camada enlace/física é responsável por transferir pacotes de dados entre computadores ou roteadores conectados em uma **rede local**, como uma rede local **Ethernet** (IEEE802.3) ou uma **rede local sem fio** (IEEE802.11), bem como entre computadores ou roteadores conectados por um **enlace ponto a ponto**.

<!-- -->

Camada de Rede  
A camada rede é responsável pela *'comunicação*host*a*host**'' na Internet. Isto é realizado pelo protocolo**IP**através de**comutação de pacotes**, usando um esquema de**endereçamento**global e implementando o**roteamento''' dos pacotes pela malha de roteadores da Internet.

<!-- -->

Camada de Transporte  
Trata da **comunicação processo a processo**, cada qual rodando em um host da Internet. Como em cada host podem haver mais de um processo rodando, a camada transporte implementa a **multiplexação de aplicações** entre os diversos processos, utilizando as chamadas **portas**. Há dois tipos de protocolos de transporte na Internet, o **TCP** e o **UDP**.

<!-- -->

Camada de Aplicação  
Define as **regras para a troca de mensagens entre os processos de aplicação** rodando em cada *host*.

<!-- -->

  
Cada aplicação da Internet utiliza um protocolo de aplicação próprio, por exemplo, a Aplicação Web usa o **HTTP**, o Correio Eletrônico o **SMTP**, a Transferência de Arquivos o **FTP**, etc.

## Encapsulamento de protocolos

Toda comunicação fim a fim na Internet é iniciada na **camada aplicação**, a qual conta com os serviços das camadas inferiores para realizar sua comunicação.

Por exemplo, suponha que uma **aplicação cliente** deseja enviar uma **mensagem** para o lado **servidor da aplicação**:

1.  A **aplicação** cliente prepara a **mensagem** para enviar e indica o **endereço IP** e a **porta** do servidor que irá receber a mensagem e passa os dados a camada inferior;
2.  A **camada transporte**, logo abaixo da aplicação, agrega à mensagem as informações da **porta**, e outras informações dependendo do tipo de serviço requerido, montando um novo pacote chamado **segmento**, e passa a camada inferior para que envie ao IP destino;
3.  A **camada rede**, recebe o segmento e acrescenta novas informações, entre elas o **IP fonte e destino**, e monta um novo pacote, chamado **datagrama**. O datagrama é então passado para a camada enlace/física para ser entregue ao roteador de saída da rede;
4.  A **camada enlace/física** encapsula então o datagrama em um **quadro** do enlace local, acrescentando novas informações, como o **endereço físico** (**MAC**) do roteador e envia ao barramento da rede local para que o roteador de prosseguimento ao envio do pacote.

<a href="Arquivo:EncapsulamentoProtocolos.png" class="wikilink" title="Arquivo:EncapsulamentoProtocolos.png">Arquivo:EncapsulamentoProtocolos.png</a>

Uma vez recebido o **quadro** pela placa de rede do **roteador**, o mesmo retira o **datagrama**, verifica o IP destino, consulta a **tabela de roteameto**, e encaminha o datagrama para o **enlace destino**, encapsulando novamente o datagrama em um **quadro** do próximo enlace.

Uma vez no ***host* destino** o processo é invertido para recuperar a **mensagem** para ser entregue ao lado **servidor da aplicação**.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 17h07min de 6 de março de 2015 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>
