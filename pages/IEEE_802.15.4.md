# IEEE 802.15.4

As redes padronizadas **IEEE 802.15.4** estão focadas em soluções de comunicação sem fio com baixa taxa de transmissão para dispositivos de baixa complexidade e baterias de longa duração, com autonomia para vários meses ou múltiplos anos.

A tecnologia **IEEE 802.15.4** é um **protocolo simples de pacotes para transmissão via rádio** que pode se intercomunicar e enviar dados com baixa taxa de transmissão para um dispositivo centralizado. Suporta taxas de transmissão de 10kbps até 1Mbps, em faixas de frequência de 169 MHz a 2450MHz. As distâncias de transmissão variam de 10m até 1km.

O **padrão IEEE 802.15.4** define apenas a **camada física** e a **camada de acesso ao meio** (MAC). Uma das tecnologias desenvolvidas dentro deste padrão é a **Zigbee**.

Há dois tipos de dispositivos numa **rede 802.15.4**, os **FFD** (*full-function device*) e os **RFD** (*reduced-function device*). Os **FFD** implementam toda a pilha de comunicação, podendo se comunicar com qualquer outro dispositivo da rede e podem atuar também como **coordenador** de uma **PAN** (*personal area network*), alocando endereços da rede local e atuando com *gateway* com outras redes. Os **RFD** são bastante simples, podendo se comunicar com outros RFD mas não podendo atuar como coordenadores de uma PAN.

As **topologias** para uma rede **rede 802.15.4** podem ser: **estrela**, na qual todos os dispositivos se comunicam com um nó coordenador central da PAN; **mesh**, na qual os dispositivos podem se comunicar com qualquer outro, podendo também se auto organizar e reconfigurar em caso de falha de um enlace; ou **cluster** em formato de árvore.

<a href="Arquivo:IEEE802_15_4-topologies.png" class="wikilink" title="500px">500px</a> [^1] (p. 107)

Os casos de uso englobam controle industrial e monitoramento de processos, redes de sensores sem fio (WSN), agricultura de precisão, entre outros.

IEEE 802.15.4e TSCH  
O **IEEE 802.15.4e** é a nova geração para **redes *mesh* sem fio**, com foco no baixo consumo de energia e aumento da confiabilidade.

## Tecnologias

Shield XBee para Arduino  
<a href="Arduino:_Wireless_Shield_Xbee" class="wikilink" title="Arduíno: Wireless Shield Xbee">Arduíno: Wireless Shield Xbee</a>

<!-- -->

6LowPAN e ZigBee  
[^2]

## Referências

<references />

<a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a> <a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 08h54min de 8 de maio de 2020 (-03)

[^1]: Ammar Rayes & Samer Salam. Internet of Things From Hype to Reality: The Road to Digitization, Springer, 2019.

[^2]: <http://ipv6.br/post/zigbee-usa-agora-6lowpan-sua-proxima-lampada-tera-ipv6/>
