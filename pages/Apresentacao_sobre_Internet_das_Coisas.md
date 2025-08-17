# Conceitos, Protocolos, Tecnologias e Ferramentas para Aplicações de Internet das Coisas

  
**Evandro Cantú**

Professor da Área de Informática

IFPR - Campus Foz do Iguaçu

## Aplicações

Internet das Coisas  
A **Internet das Coisas** pode ser vista como um extensão da Internet, na qual objetos do mundo físico são conectados a rede para fins de monitoramento e controle.

<!-- -->

Aplicações de Internet das Coisas  

- **Bens e consumo**, como smartphones, televisores, geladeiras e outros aparelhos inteligentes.

<!-- -->

- **Casas inteligentes**, como automatização e monitoramento da iluminação, climatização, segurança ou o consumo de energia em uma residência.

<!-- -->

- **Cidades inteligentes**, como semáforos automatizados, controle da iluminação pública, controle e monitoramento do transporte coletivo.

<!-- -->

- **Comercio e logística**, como controle de estoque e rastreamento de produtos.

<!-- -->

- **Indústria**, criando produtos, linhas de produção e serviços inteligentes, envolvendo processamento na nuvem da Internet e a troca de informações entre os diferentes tipos de sensores, controladores e atuadores.

<!-- -->

- **Agricultura**, também envolvendo processamento na nuvem da Internet e troca de informações entre sensores e atuadores localizados em campo.

## O que é Internet das Coisas

Segundo: <a href="Arquivo:IoT-FromHipeToReality.jpeg" class="wikilink" title="150px">150px</a> [^1]

A **Internet das Coisas** (**IoT**) pode ser considerada uma rede de dispositivos físicos, destacando [^2]:

- **Sensores**: para coletar informação.
- **Identificadores**: para identificar a fonte dos dados (ex. sensor, dispositivo).
- **Software**: para analisar dados.
- **Conectividade com Internet**: para comunicação e notificação.

A ideia principal da **IoT** é **conectar coisas** (sensores, dispositivos, máquinas, pessoas, animais, árvores, etc) e realizar **processamento** de dados através da **Internet** para fins de **monitoramento** e **controle**.

Em sua definição mais simples pode ser considerada a intersecção de **coisas**, **dados** e a **Internet**.

<a href="Arquivo:IoT-simple-definition.png" class="wikilink" title="200px">200px</a> [^3] (p. 3)

### Como monitorar coisas em qualquer lugar do mundo?

Os requisitos básicos para IoT são [^4]:

- **identificação única** para as coisas;
- habilidade de **sensoriamento** (ou **atuação**) de alguma informação sobre as coisas;
- habilidade de **comunicação** entre as coisas;
- habilidade de **controle** e **gerenciamento** das as coisas

<a href="Arquivo:Basic-requirements-for-IoT.png" class="wikilink" title="400px">400px</a> [^5] (p. 5)

O **monitoramento** e/ou **controle** de um sistema de IoT pode ser realizado por pessoas ou máquinas.

Quatro níveis de referência para as soluções de IoT  
- **Dispositivos de IoT** (coisas: sensores e atuadores);
- **Rede de IoT** (infraestrutura de transporte de dados);
- **Plataformas de serviços de IoT** (softwares conectando coisas e aplicações e provendo monitoramento do sistema);
- **Aplicações de IoT**.

<a href="Arquivo:IoT-reference-levels.png" class="wikilink" title="400px">400px</a> [^6] (p. 8)

## Limitações dos protocolos da Internet para Internet das Coisas

<a href="Arquivo:Protocolos_Redes_Internet.png" class="wikilink" title="Arquivo:Protocolos_Redes_Internet.png">Arquivo:Protocolos_Redes_Internet.png</a>

## Requisitos tecnológicos

Visão baseada nos seguintes autores  

<a href="Arquivo:IoT-FromHipeToReality.jpeg" class="wikilink" title="190px">190px</a> [^7] <a href="Arquivo:Rethinking-IoT.jpeg" class="wikilink" title="300px">300px</a> [^8]

- **<a href="Internet_das_Coisas_do_exagero_a_realidade" class="wikilink" title="Internet das Coisas do exagero a realidade">Internet das Coisas do exagero a realidade</a>**

<!-- -->

- **<a href="Repensando_a_Internet_das_Coisas" class="wikilink" title="Repensando a Internet das Coisas">Repensando a Internet das Coisas</a>**

## Novos protocolos de rede para Internet das Coisas

<a href="Arquivo:Protocolos_Redes_IoT.png" class="wikilink" title="Arquivo:Protocolos_Redes_IoT.png">Arquivo:Protocolos_Redes_IoT.png</a>

## Organização em camadas para aplicações de Internet das Coisas

<a href="Arquivo:Arquitetura-IoT2.png" class="wikilink" title="Arquivo:Arquitetura-IoT2.png">Arquivo:Arquitetura-IoT2.png</a>

## Protocolos de aplicação MQTT e CoAP

- **<a href="MQTT" class="wikilink" title="MQTT">MQTT</a>**
- **<a href="CoAP" class="wikilink" title="CoAP">CoAP</a>**

## Tecnologias para prototipagem em Internet das Coisas

### Ferramentas de Software

- **<a href="Docker" class="wikilink" title="Docker">Docker</a>**

O **Docker** é um **contêiner**, que é uma unidade padronizada de software que permite aos desenvolvedores isolar suas aplicações do meio no qual vai rodar.

A imagem de um contêiner Docker é leve, roda de forma independente, e possui todas os requisitos necessários para rodar as aplicações, como códigos, ferramentas de sistema, bibliotecas e configurações.

- **<a href="Mosquitto" class="wikilink" title="Mosquitto">Mosquitto</a>**

O **Mosquitto** é um Brocker MQTT que implementa o modelo **publilsher/subscriber** e pode ser utilizado em aplicações de **Internet das Coisas**.

O Mosquitto oferece comandos de linha como **mosquitto_pub** e **mosquitto_sub** para publicar e subscrever no **brocker**, respectivamente, além de bibliotecas em C para implementação de cliente MQTT.

- **<a href="Node-RED" class="wikilink" title="Node-RED">Node-RED</a>**

O **Node-RED** é uma ferramenta de programação ***Low Code***, voltada para **Internet das Coisas**, que permite interligar dispositivos físicos, ambientes de desenvolvimento de software e serviços em nuvem.

### Dispositivos de Hardware

- **Arduíno**

<a href="Arquivo:PinosArduinoUno.png" class="wikilink" title="200px">200px</a>

- **ESP8266** e **ESP32**

<a href="Arquivo:NodeMCU_ESP8266.jpg" class="wikilink" title="300 px">300 px</a> <a href="Arquivo:ESP8266.jpg" class="wikilink" title="150px">150px</a>

- **Raspberry Pi** / **Pico**

<a href="Arquivo:RaspberryPi.jpg" class="wikilink" title="300 px">300 px</a> <a href="Arquivo:RaspberryPico.jpg" class="wikilink" title="300 px">300 px</a>

## Oficinas e Laboratórios

<a href="MQTT_e_Arduino" class="wikilink" title=" Laboratório: MQTT e Arduino"> Laboratório: MQTT e Arduino</a>  

<!-- -->

<a href="MQTT_e_ESP8266" class="wikilink" title=" Laboratório: MQTT e ESP8266"> Laboratório: MQTT e ESP8266</a>  

<!-- -->

<a href="Laboratorios:_Node-RED" class="wikilink" title="Laboratórios: Node-RED">Laboratórios: Node-RED</a>  

## Referências

<references />

<a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 09h26min de 24 de abril de 2021 (-03)

------------------------------------------------------------------------

[^1]: Ammar Rayes & Samer Salam. <a href="Media:InternetOfThingsFromHypeToReality.pdf" class="wikilink" title="Internet of Things From Hype to Reality">Internet of Things From Hype to Reality</a>: The Road to Digitization, Springer, 2019.

[^2]:

[^3]:

[^4]:

[^5]:

[^6]:

[^7]: Ammar Rayes & Samer Salam. <a href="Media:InternetOfThingsFromHypeToReality.pdf" class="wikilink" title="Internet of Things From Hype to Reality">Internet of Things From Hype to Reality</a>: The Road to Digitization, Springer, 2019.

[^8]: Francis da Costa. <a href="Media:Rethinking-Internet-Of-Things-Book.pdf" class="wikilink" title="Rethinking Internet of Things">Rethinking Internet of Things</a>: A scalable approach to connecting everything. Apress Open, 2013.
