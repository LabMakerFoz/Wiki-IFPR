# Internet das Coisas do exagero a realidade

Página Wiki com síntese de algumas ideias do livro **<a href="Media:InternetOfThingsFromHypeToReality.pdf" class="wikilink" title="Internet of Things From Hype to Reality">Internet of Things From Hype to Reality</a>** (Rayes and Salam, 2019) [^1]. Os autores são engenheiros da Cisco e atuando em tecnologias emergentes no Vale do Silício, Califórnia.

## Pilha de protocolos de rede para IoT

Descrição das principais tecnologias de rede para atender as aplicações de IoT.

### Camada Enlace

Os desafios das tecnologias de enlace para atender aos **dispositivos de IoT** são devido as **características diversas dos dispositivos**, as **características do tráfego**, as **características do acesso ao meio** e a questão da **escalabilidade**, como mostra a figura.

  
<a href="Arquivo:LinkLayerChallenges.png" class="wikilink" title="600px">600px</a> [^2] (p. 104)

A **comunicação de rede** tipicamente é responsável por grande parte do **consumo de energia** no processamento local de um dispositivo, portanto, as tecnologias de comunicação devem ser otimizadas para os dispositivos de baixa potência.

A questão das **características do tráfego** dependem do tipo de **aplicações** e da natureza dos dispositivos. Algumas aplicações podem relaxar restrições como **perda de pacotes**, **atraso** e ***jitter*** (como o monitoramento meteorológico), outras tem restrições severas (como aplicações de engenharia de controle). Ambas podem utilizar os mesmos tipos de dispositivos (como sensores de ambiente), mas as características das aplicações que que vão ditar os requisitos de comunicação.

Nas aplicações tradicionais de TI as tecnologias dominantes são as redes **LAN** no acesso local e **WAN** no acesso a Internet. Entretanto, nas aplicações de IoT os requisitos são diversos e dependem da localização dos dispositivos, por exemplo, aplicações industriais, automação veicular, monitoramento do corpo humano, etc. Nestes ambientes topologias como as redes **FAN** (*field area network*), **NAN** (*neighborhood area network*) e **PAN** (*personal area network*).

LLN (*low-power and lossy networks*)  
Muitos desenvolvimentos em IoT utilizam tecnologias de enlace desenvolvidas para dispositivos com limitações de processamento, memória e energia, referidas como redes **LLN** (*low-power and lossy networks*). Fazem partes das redes LLN as tecnologias de enlace **IEEE 802.15.4**, **Bluetooth**, **PLC** (*power-line communication*) etc.

<!-- -->

Algumas tecnologias de enlace usadas em IoT  

- **IEEE 802.15.4**: Focada em soluções de comunicação sem fio com baixa taxa de transmissão e baixo consumo de energia, com destaca para a tecnologia **Zigbee**.
- **IEEE 802.11ah**: Redes **WiFi** bastante difundida como rede de acesso a Internet tem limitações para aplicações de IoT, em particular devido ao alto consumo de energia e a faixa de transmissão inadequada devido a interferência que obstáculos oferecem as transmissões.
- **LoRa WAN**: Projetadas para redes com baixo consumo de energia e transmissões a longas distâncias.
- **TSN**: As redes **TSN** (*Time-Sensitive Networking*) foram desenvolvidas para aplicações industriais e de automação com requisistos estritos de tempo.

### Camada Rede

Aplicações de IoT que utilizam **dispositivos restritos** e enlaces de comunicação baseados em redes **LLN**, em particular **IEEE802.15.4**, necessitam de adaptações serem integrados as redes **<a href="IPv6" class="wikilink" title="IPv6">IPv6</a>**. Isto é necessário devido as limitações de **tamanho do quadro** impostas pelas redes **LLN** e uma solução tecnológica é a **<a href="6LowPAN" class="wikilink" title="6LowPAN">6LowPAN</a>**.

  
<a href="Arquivo:6lowPAN.png" class="wikilink" title="200px">200px</a> [^3] (p. 126)

### Camada Aplicação

Os **protocolos de aplicação** são responsáveis por realizarem a comunicação entre as entidades envolvidas em uma aplicação, como **objetos**, ***gateways*** e **aplicações**. Envolve fluxo dos dados monitorados pelos sensores ou das ações de controle para atuadores.

Paradigma de comunicação  
Na **Internet** o paradigma de comunicação dominante é o **pedido/resposta**, como na aplicação Web, na qual o cliente envia um pedido e o servidor envia uma resposta, numa comunicação fim a fim. Nas **aplicações de IoT**, em muitos cenários a comunicação é somente em um sentido, dos objetos às aplicações ou vice-versa. Neste caso, o paradigma mais apropriado é o **publicador/subscritor**, pois permite a comunicação unidirecional de um publicador para um ou vários subscritores.

#### Alguns protocolos de aplicação para IoT

<a href="CoAP" class="wikilink" title="CoAP">CoAP</a> (*Constrained Application Protocol*)  
É uma **alternativa mais leve** ao **HTTP**, com alvo nos dispositivos limitados em termos de energia e comunicação (redes **LLN**). O **CoAP** usa **UDP**, ao invés do **TCP** usado pelo **HTTP**, reduzindo o *overhead* de mensagens ocasionado pela abertura e encerramento de uma conexão TCP.

<!-- -->

<a href="MQTT" class="wikilink" title="MQTT">MQTT</a>  
O **MQTT** (***Message Queue Telemetry Transport***) é um **protocolo de mensagens** para **sensores** e pequenos **dispositivos móveis**, baseado no modelo **Publicador/Subscritor**, ideal para aplicações de **Internet das Coisas**, em particular para a comunicação **máquina a máquina** (**M2M** - *Machine to Machine*). O **MQTT** trabalha no topo da pilha de protocolos **TCP/IP**.

## Fog Computing

***Fog Computing*** refere-se a uma plataforma integrada de computação, armazenamento e serviços de rede que são altamente distribuídos e virtualizados. Esta plataforma pode ser estendida até a localidade dos dispositivos de IoT e *gateways*, trazendo serviços de computação próximo ao local onde são produzidos (p.ex. sensores) ou consumidos (p. ex. atuadores).

  
<a href="Arquivo:Fog-and-Cloud.png" class="wikilink" title="600px">600px</a> [^4] (p. 156)

### *Fog Computing* e as demandas das aplicações de IoT

Aumento da geração e fluxo de dados de IoT  
O crescimento das aplicações de IoT trará crescimento do **volume de dados** gerado e por consequência da necessidade de **comunicação de dados** em direção aos serviços em nuvem. Portanto, serviços de ***fog computing*** próximo aos dispositivos podem diminuir a necessidade de transferir grandes volumes de informação em direção a nuvem.

<!-- -->

Aplicações com rápida mobilidade  
Aplicações de IoT com **rápida mobilidade**, como veículos autônomos, podem ocorrer pertubações na comunicação de dados dos dispositivos com a nuvem, portanto, serviços de ***fog computing*** podem trazer soluções mais eficientes.

<!-- -->

Aplicações de controle confiável  
Aplicações de IoT voltadas a **controle confiável em tempo real** requerem armazenamento de grandes volumes de dados e respostas rápidas, portanto, serviços de ***fog computing*** podem melhorar os tempos de resposta dos sistemas mantendo os dados e o processamento próximo aos laços de controle.

<!-- -->

Análise e gerenciamento de dados  
Distribuir a análise e gerenciamento de dados em locais próximos a onde são gerados pode melhorar o desempenho geral dos sistemas, combinando análise descentralizada de dados em serviços de ***fog computing**'' e análise global do sistema em servidos de***cloud computing**''.

### Tecnologias para *fog computing*

As tecnologias de ***fog computing*** tem como objetivos localizar os serviços de informática próximos aos locais onde são produzidos ou consumidos. Esta característica pode ser obtida com **serviços de virtualização** que possam ser instanciados nos locais onde são necessários.

Contêineres e máquinas virtuais  
São dois ambientes de virtualização bastante utilizados por serviços em nuvem.

- **Máquinas virtuais**: São tecnologias de **virtualização operando no nível do hardware**, provendo abstração do hardware e dos recursos software de uma plataforma computacional, incluindo drivers e bibliotecas.
- **Contêineres**: São tecnologias de **virtualização operando no nível do sistema operacional**, incluindo somente a parte do sistema operacional e bibliotecas necessárias para rodar a aplicação desejada. Contêineres são mais leves que as máquinas virtuais, tanto em termos de processamento quanto em uso de memória.

  
<a href="Arquivo:VirtualMachine-Container-Paradigm.png" class="wikilink" title="400px">400px</a> [^5] (p. 161)

<!-- -->

Suporte de rede para mobilidade  
Para assegurar a não interrupção das aplicações de IoT, com suporte de *fog computing*, é necessário que a **rede suporte a mobilidade dos dispositivos** e envolve a identificação do dispositivo e sua localização. Para esta tarefa, algumas tecnologias proeminentes são as **EVPN** (Ethernet Virtual Private Network) e a **LISP** (Locator/Identifier Separation Protocol).

<!-- -->

Orquestração de serviços de IoT em *fog computing*  
Outra questão complexa nas aplicações de IoT, apoiadas por ***fog computing*** é a orquestração necessária para o gerenciamento global do sistema, que pode envolver múltiplos componentes rodando em sistemas heterogêneos e distribuídos em múltiplas localizações.

<!-- -->

  
<a href="Arquivo:FogOrchestration.png" class="wikilink" title="600px">600px</a> [^6] (p. 171)

## Progressos na padronização industrial

**Arquitetura de rede** proposta pelo **ETSI** (European Telecommunications Standards Institute)

  
<a href="Arquivo:NetworkArchitecture.png" class="wikilink" title="600px">600px</a> [^7] (p. 143)

Este modelo está baseado nas tecnologias de rede existentes e compreende três níveis: o domínio dos dispositivos com a conectividade entre objetos e *gateways*, o domínio de rede e o domínio das aplicações.

## Requisitos para protocolos de redes para IoT

Os dispositivos de IoT são limitados em termos de processamento, memória e provimento de energia, colocando restrições para a implementação de protocolos para comunicação em rede, em particular para implementar a pilha TCP/IP.

A crescimento massivo do número de dispositivos de IoT impõem vários requisitos para a implementação de protocolos de comunicação, incluindo formas de **identificação dos dispositivos**, **resolução de nomes**, **segurança**, **protocolos de roteamento**, além da questão do controle e gerenciamento da rede.

Identificação dos dispositivos  
Um dos objetivos da IoT é integrar de maneira uniforme todos os dispositivos inteligentes conectados ao redor do globo. Isto requer uma identificação única de cada dispositivo. Para uso da rede IP, o endereçamento IPv4 não pode ser utilizado devido a limitação do número de endereços possíveis, restando, portanto, a necessidade acelerar a transição para o **IPv6**.

<!-- -->

Determinismo e tempo real  
Muitas aplicações de automação em IoT requerem **comunicação determinística** e com requisitos em **tempo real**, como controle veicular, controle de ferrovias, entre outros. Nestes sistemas, um requisito fundamental numa comunicação de pacotes é garantir a entrega correta de pacotes em um tempo estabelecido, o que requer **diminuição do *delay**'' (atraso),**perda de pacotes**e***jitter**'' (diferença de atraso entre pacotes).

<!-- -->

Segurança e privacidade  
Também devido as limitações de hardware, novos algoritmos serão necessários para **criptografia** de dados e autenticação para os dispositivos de IoT. Os principais algoritmos utilizados atualmente, como o AES (*Advanced Encryption Standard*) para transporte de dados confidenciais e o RSA (*Rivest-­Shamir-­Adleman*) para autenticação, não são possíveis de serem implementados na maioria dos dispositivos de IoT.

## Dispositivos para IoT

### Sensores

Sensores permitem **detectar certas condições do ambiente** (temperatura, umidade, pressão atmosférica, etc) e produzir uma saída. Muitas **grandezas físicas** são **analógicas** (p.ex. temperatura) e um **sensor eletrônico** geralmente produz uma valor analógico correspondente ao medido na forma de uma **tensão elétrica**.

Sensor Inteligente  
Para um **sensor** poder interagir com um sistema de **IoT** é preciso que um **valor analógico** medido seja convertido para um **valor digital**, através de um **Conversor Analógico Digital**. Além disto, para poder ser transmitido pela **Internet** o sensor precisa ter uma **interface de rede**. Neste caso, a estrutura do sensor deve conter pelo menos três elementos: o **sensor**, um **microcontrolador** e a **interface de rede**. Com um microcontrolador o sensor pode ser incrementado, incluindo processamento local para filtrar e analisar os dados medidos antes enviar a Internet.

<!-- -->

Características de um sensor para IoT  
Aplicações de IoT requerem sensores pequenos e com funções avançadas para coleta de dados, além de processadores com baixo consumo de energia, baterias com longa duração e respostas rápidas.

<!-- -->

  
Características desejadas para os sensores para IoT:

- **Filtragem de dados**: Habilidade de coletar dados e realizar filtragem mínima antes de enviar os dados a *gateways* ou outros sistemas.
- **Baixo consumo de energia**: Necessário para instalação em locais de difícil acesso para troca de baterias.
- **Compacto**: Para poder ser instalado em locais com limitações de espaço.
- **Medição não invasiva**: De forma a não interferir no ambiente físico a ser monitorado.
- **Alta sensibilidade**: Medição da menor variação possível da grandeza medida.
- **Linearidade**: Variação linear entre a grandeza medida e a saída do sensor.
- **Faixa dinâmica de atuação** (*Dynamic Range*): Faixa de atuação do sensor para a grandeza medida.
- **Precisão** (*Accuracy*): Máximo erro esperado na medição.
- **Histerese**: Quando o sensor não retorna o mesmo valor na saída para uma variação da entrada de alto par baixo (ou vice-versa).
- **Limite de Ruído**: Todo sensor produz algum ruído na saída para um dado sinal medido.
- **Largura de Banda**: Frequência máxima entre duas medidas.
- **Alta Resolução**: Detecção mínima da variação de uma medida.
- **Mínima interrupção**: Tempo mínimo para voltar a funcionar normalmente após uma interrupção.
- **Alta confiabilidade**: Confiabilidade dos dados medidos.
- **Fácil de usar**: Fácil instalação e funcionamento adequado assim que for ligado.

### Identificação de um dispositivo de IoT

Uma maneira de identificar um dispositivo de IoT é utilizar um **endereço IP** para cada dispositivo. Entretanto, o IPv4 possui limitações do número de endereços possíveis para atender a questão de escala colocada pelos sistemas de IoT e o IPv6 ainda não está totalmente difundido.

Outra questão é que muitos dispositivos não possuem hardware e software suficientes para a implementação da pilha TCP/IP. Neste caso, os dispositivos podem ser identificados por seus respectivos ***gateways*** na Internet.

RFID  
**RFID** (*radio-frequency identification*) é uma tecnologia que pode ser utilizada para identificar objetos a partir de informações gravadas em uma ***tag***.

<!-- -->

  
Um sistema de RFID possui duas partes, a *tag* e o leitor. A *tag* é formada por um microchip com informações gravadas e uma antena para receber e transmitir sinal. O leitor lê as informações gravadas na *tag* por meio de um rádio transmissor e receptor e passa para um programa para análise do códido RFID.

<!-- -->

  
<a href="Arquivo:RFID.png" class="wikilink" title="100px">100px</a> [^8] (p. 77)

<!-- -->

  
A vantagem do **RFID** em relação a outras técnicas como **código de barras** é que a informação na *tag* pode ser facilmente regravada e a leitura pode ser feita a distâncias maiores. **Tags** passivas podem ser lidas por distâncias de até 10 metros e *tags* equipadas com sistemas de bateria podem ser lidas a distâncias de até 100 metros. Além disto, o leitor pode realizar a leitura de várias *tags* ao mesmo tempo.

### Controle de um dispositivo

Um dispositivo de IoT pode ser **monitorado** e **controlado** de duas maneiras: **localmente** ou **remotamente**. Para o **controle local** o dispositivo deve possuir **capacidade de processamento**. Para o **controle remoto** o dispositivo realiza medidas e envia para a **nuvem** da Internet, onde um **programa de monitoramento e controle** envia ao dispositivo a ser controlado os comandos necessários.

Atuadores  
**Atuadores** são dispositivos que podem **realizar uma ação** sobre o meio, como ligar ou desligar uma chave ou controlar a abertura de uma válvula.

<!-- -->

  
Tipos de atuadores:

- **Atuadores elétricos**: Recebem comando através de um sinal elétrico, podem ser chaves eletrônicas ou micromotores elétricos.
- **Atuadores mecânicos**: Como chaves mecânicas para acionamento de válvulas, as quais podem ser acionadas também por micromotores.
- **Atuadores hidráulicos e pneumáticos**: Atuadores mecânicos que utilizam a compressão de líquidos ou gases para aumentar a força de atuação sobre o ambiente (Lei de Pascal).
- **Atuadores manuais**: Comandados manualmente, como chaves e válvulas.

## Referências

<references />

<a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 17h00min de 29 de abril de 2020 (-03)

[^1]: Ammar Rayes & Samer Salam. <a href="Media:InternetOfThingsFromHypeToReality.pdf" class="wikilink" title="Internet of Things From Hype to Reality">Internet of Things From Hype to Reality</a>: The Road to Digitization, Springer, 2019.

[^2]:

[^3]:

[^4]:

[^5]:

[^6]:

[^7]:

[^8]:
