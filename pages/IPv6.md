# IPv6

Referências: Textos e vídeos [^1].

O protocolo **IPv6** é a **nova versão do IP**, especificado pela RFC2460, e deve substituir o IPv4. Além disto, o IPv6 é incrementado por várias outras RFCs, por exemplo: RFC2463 (*ICMP for the Internet Protocol Version 6*) e RFC3775 (*Mobility Support in IPv6*).

Apesar de ter sido definido a 20 anos o IPv6 ainda não tem data para ser implementado em definitivo na Internet. Este atraso se justifica pelo sucesso do IPv4, em particular por sua simplicidade de administração. Sua resiliência, que é a capacidade de voltar ao seu estado normal depois de ter sofrido uma pressão, como por exemplo, congestão ou falta de memória. Sua escalabilidade, na qual partes do sistema podem ser administrados como sistemas autônomos independentes. Sua flexibilidade e extensibilidade, a qual tem possibilitado soluções de alguns de seus problemas, como o CIDR que acabou com as classes de endereçamento, o NAT que possibilitou o uso de IP privados em uma rede interna e a autoconfiguração dos endereços em uma rede local com DHCP.

Um dos motivos que levaram ao desenvolvimento do IPv6 foi a escassez de endereços IP que se avizinhava no início dos anos 1990. Em partes isto foi devido ao uso de classes no IPv4, a qual atribuiu faixas gigantescas de endereços para algumas poucas empresas e instituições. Posteriormente, este problema acabou sendo minimizado com a proposição do endereçamento IP sem classes (CIDR) e também com o uso do NAT. Além da limitação do espaço de endereçamento o IPv4 não incluía em seu projeto original suporte para mobilidade, segurança e qualidade de serviço. Na questão da qualidade de serviço (QoS), o campo TOS (*type of service*) acabou sendo utilizado posteriormente, como especificado na RFC1349 (*Type of Service in the Internet Protocol Suite*).

As principais melhorias introduzidas pelo IPv6 são:

- Ampliação do espaço de endereçamento de 32 bits para 128 bits;
- Melhoria no formato do datagrama IP;
- Melhoria no processo de autoconfiguração;
- Inserção de mecanismos para tratamento de mobilidade (MIPv6);
- Inserção de mecanismos de segurança (IPsec);
- Inserção de mecanismos para facilitar o gerenciamento de QoS.

## Estrutura do datagrama IPv6

O **datagrama IPv6** possui seu **cabeçalho** com tamanho fixo de **40 bytes**, como mostra a figura [^2]:

`  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+`  
`  |Version| Traffic Class |           Flow Label                  |`  
`  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+`  
`  |         Payload Length        |  Next Header  |   Hop Limit   |`  
`  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+`  
`  |                                                               |`  
`  +                                                               +`  
`  |                                                               |`  
`  +                         Source Address                        +`  
`  |                                                               |`  
`  +                                                               +`  
`  |                                                               |`  
`  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+`  
`  |                                                               |`  
`  +                                                               +`  
`  |                                                               |`  
`  +                      Destination Address                      +`  
`  |                                                               |`  
`  +                                                               +`  
`  |                                                               |`  
`  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+`

- **Versão** (*Version*), de 4 bits, indica a versão do protocolo, no caso = 6 (0110).
- **Classe de tráfego** (*Traffic Class*), com 8 bits, é utilizado por nós de origem e roteadores intermediários para diferenciar diferentes classes e prioridade de tráfego entre os pacotes IPv6; tem funcionalidade similar a utilização do campo TOS do IPv4 permitindo de implementar serviços diferenciados de QoS (*DiffServ*) para os pacotes IP.
- **Rótulo de fluxo** (*Flow Label*), com 20 bits, pode ser utilizado por nós de origem para rotular sequências de pacotes que requerem tratamento especial em roteadores, como serviços tempo real.
- **Comprimento dos dados** (*Payload Length*), com 16 bits, especifica o tamanho dos dados após o cabeçalho, em bytes.
- **Próximo cabeçalho** (*Next Header*), com 8 bits, especifica o tipo do cabeçalho imediatamente após o cabeçalho IPv6; pode utilizar números similares aos do campo *Protocol* do IPv4, ou números específicos para o IPv6, os quais são atualmente estabelecidos *Next Header*por uma base *on-line* [^3].
- **Limite de saltos** (*Hop Limit*), com 8 bits, é decrementado de 1 em cada nó de encaminhamento do pacote; o pacote é descartado quando o *Hop Limit* chega a zero.
- **Endereço fonte** (*Source Address*), com 128 bits.
- **Endereço destino** (*Destination Address*), com 128 bits.

Diferenças do cabeçalho do IPv6 em relação a <a href="Datagrama_IP" class="wikilink" title="IPv4">IPv4</a>  
Foram removidos do cabeçalho IPv6 os seguintes campos que haviam no IPv4:

- Tamanho do cabeçalho (*Header Length*), uma vez que o cabeçalho IPv6 possui tamanho fixo de 40 bytes;
- *Identification*, *Flags* e *Fragment Offset*, no IPv6 a fragmentação é realizada na origem e utiliza um cabeçalho de extensão (ver abaixo);
- *Header Checksum*, o que tornou o processamento mais leve, evitando recalcular o valor do *checksum* em cada nó.
- Opções e complementos (*Options* e *Padding*), que tiveram suas funções viabilizadas com os *Next Header*.

### Extensões do cabeçalho IPv6

As **extensões do cabeçalho** do IPv6 localizam-se entre o cabeçalho base e o cabeçalho da camada de superior e não possuem quantidade ou tamanho fixo.

<a href="Arquivo:Cabecalhos-Extencao-IPv6.png" class="wikilink" title="400px">400px</a> [^4]

As principais **extensões** do cabeçalho **IPv6**são  

- ***Hop-by-Hop*** carrega informações que devem ser processadas por todos nós ao longo do caminho. Algumas opções incluem o *Router Alert*, utilizado para reserva de recursos (exemplo RSVP) ou encontrar destinos de *multicast* e a opção *Jumbogram* permite que pacotes maiores que 64K sejam transmitidos.
- ***Destination Options*** deve ser processado apenas pelo nó de destino do pacote. Ele é utilizado no suporte ao mecanismo de mobilidade do IPv6.
- ***Routing Header*** permite informar um conjunto de roteadores que devem ser visitados até o seu destino final e pode ser utilizada por aplicações que exigem qualidade de serviço. Também é utilizado como parte do mecanismo de suporte a mobilidade do IPv6.
- ***Fragmentation*** é usada para possibilitar a fragmentação e remontagem de datagramas. O IPv6 usa a técnica *PATH MTU Discovery* para determinar a máxima MTU na trajetória do pacote. Se o pacote for maior que esta MTU então ele é fragmentado na origem. Os roteadores ao longo da rota não fragmentam o pacote. O destino remonta o pacote fragmentado. Os parâmetros utilizados são equivalentes aos do IPv4: *Identification*, identificação pacote; *Flag*, se igual a 1 indica que há mais fragmentos, se igual a 0 indica fragmento final; *Fragment Offset*, deslocamento do fragmento, em unidades de oito bytes, em relação ao início do pacote original.
- ***Authentication Header**'' e***Encapsulating Security Payload**'' fazem parte do cabeçalho IPSec.

Códigos para *Next Header* e ordem recomendada no pacote  
[^5]

**`Ordem Tipo Código`**  
`           `*`No next header`*`      59`  
`1          `*`Hop-by-Hop`*`          00`  
`2          `*`Destination`*`         60`  
`3          `*`Routing`*`             43`  
`4          `*`Fragmentation`*`       44`  
`5          `*`Authentication`*`      51`  
`6          `*`Security`*`            50`  
`Protocolo  TCP                 06`  
`Protocolo  UDP                 17`  
`Protocolo  ICMPv6              58`

## Endereçamento IPv6 (RFC 3513)

O IPv6 tem **endereçamento de 128 bits**: espaço de 2<sup>128</sup> endereços.

É utilizada uma **notação hexadecimal** com agrupamento de **16 bits** separados por **dois pontos**, como por exemplo:

`2001:0DB8:5002:2019:1111:76ff:FEAC:E8A6`

São utilizadas regras para **simplificar** a representação de zeros, por exemplo o endereço:

`0237:0000:ABCD:0000:0000:0000:0000:0010`

pode ser transformado em:

`237::ABCD:0:0:0:0:10`

ou, melhor ainda, 237:0:ABCD::10

### Prefixos de rede

No **IPv6** os **prefixos de rede** são escritos do mesmo modo que no IPv4, utilizando a **notação CIDR**. Esta notação é representada da forma **endereço-IPv6/tamanho do prefixo**, onde tamanho do prefixo é um valor decimal que especifica a quantidade de bits contíguos à esquerda do endereço que compreendem o prefixo. O exemplo de prefixo de sub-rede apresentado a seguir indica que dos 128 bits do endereço, 64 bits são utilizados para identificar a rede. Uma rede também pode ser subdividida em sub-redes [^6]:

`   Prefixo 2001:db8:3003:2::/64`  
`   Prefixo global 2001:db8::/32`  
`   ID da sub-rede 3003:2`

No IPv6 o **identificador da interface** dentro de uma rede tem tamanho padrão de **64 bits**.

### Tipos de endereçamento IPv6

- ***Unicast***: identifica uma única interface, de modo que um pacote enviado a um endereço *unicast* é entregue a uma única interface.
- ***Anycast***: identifica um conjunto de interfaces. O roteamento da Internet permite encaminhar pacotes ao endereço *anycast* mais próximo. Um endereço anycast é utilizado em comunicações de um-para-um-de-muitos.
- ***Multicast***: identifica um conjunto de interfaces, entretanto, um pacote enviado a um endereço *multicast* é entregue a todas as interfaces associadas a esse endereço. Um endereço multicast é utilizado em comunicações de um-para-muitos. O Ipv6 eliminou o *broadcast* e enriqueceu o processo de multicast;.

#### Endereços *Unicast*

Existem alguns tipos de endereços *unicast* IPv6 [^7]:

- ***Global Unicast***: equivalente aos **endereços públicos** IPv4, o endereço global *unicast* é globalmente acessível na Internet IPv6. Utiliza os 64 bits mais a esquerda para **identificação da rede** e os 64 bits mais a direita para **identificação da interface**. A identificação da rede engloba duas partes: o prefixo de roteamento global e a identificação da sub-rede.
- ***Link-Local***: pode ser usado apenas no enlace específico onde a interface está conectada e traz a noção de **endereços privados** dentro de uma rede. O endereço *link-local* é atribuído automaticamente utilizando o prefixo FE80::/64.
- ***Unique-Local***: é endereço globalmente único para ser utilizado apenas para comunicações locais.

Outros endereços notáveis  

- Endereço ***Loopback***:

`::1`

- Endereço não especificado:

`::`

- Endereços ***Multicast***:

`FF02::1 -- todos os nós do enlace;`  
`FF02::2 -- todos os roteadores do enlace.`

### Formação do Endereço a partir do MAC

Os 64 bits do identificador de hospedeiro são formados pela inserção de FFFE entre o terceiro e quarto byte do MAC e complementando-se o segundo bit menos significativo do primeiro byte do MAC.

Se endereço MAC da interface for:

`AA:11:BB:2A:EF:35 `

adiciona-se os dígitos FFFE na metade do endereço:

`AA11:BBFF:FE2A:EF35`

complementa-se o segundo bit menos significativo do primeiro byte:

`AA = 10101010 -> 10101000 = A8`  
`A811:BBFF:FE2A:EF35`

prefixo recebido do Roteador (via Advertência):

`2001:10:/64 `

endereço final:

`2001:10::A811:BBFF:FE2A:EF35`

## ICMPv6

O ICMPv6 (RFC2463) reporta erros se pacotes não podem ser processados apropriadamente e envia informações sobre o status da rede. Apresenta várias melhorias em relação ao ICMPv4. O IGMP, que trata *multicast* no IPv4, foi incorporado no ICMPv6. O ARP/RARP foi incorporado através da utilização da técnica *Neighbour Discovery* (descoberta de informações da vizinhança). Incorporou mensagens de registro de localização para IP Móvel.

As mensagens ICMPv6 são transportadas por datagramas IPv6 com número *Next Header* igual a 58H e tem formato geral mostrado na figura:

`      0                   1                   2                   3`  
`      0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1`  
`     +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+`  
`     |     Type      |     Code      |          Checksum             |`  
`     +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+`  
`     |                                                               |`  
`     +                         Message Body                          +`  
`     |                                                               |`

As mensagem com bit mais significativo (MSB) do campo *type* = 0 indicam **erro** (valores de 0--127) e com o MSB = 1 são de **informação** (valores de 128--255).

São exemplos de mensagens de erro:

`      Type`  
`         1    Destination Unreachable      `  
`         2    Packet Too Big               `  
`         3    Time Exceeded                `  
`         4    Parameter Problem           `

São exemplos de mensagens de informação:

`      Type`  
`       128      Echo Request                 `  
`       129      Echo Reply                  `  
`       133-136  Neighbor Discovery`

O campo *Code* indica o código da mensagem, por exemplo, para mensagens de erro *Destination Unreachable* poderemos ter:

`  Type           1`  
`  Code           0 - No route to destination`  
`                 1 - Communication with destination`  
`                       administratively prohibited`  
`                 2 - Beyond scope of source address`  
`                 3 - Address unreachable`  
`                 4 - Port unreachable`  
`                 5 - Source address failed ingress/egress policy`  
`                 6 - Reject route to destination`

A mensagems de erro *Packet Too Big* (*Type* = 2, *Code* = 0) é utilizada pela técnica de descoberta da MTU do enlace (*Path MTU Discovery*), uma vez que o IPv6 não fragmenta do datagrama nos roteadores intermediários. Nesta técnica o nó emissor assume a MTU do seu enlace de saída e envia o pacote para destino. Caso algum roteador da rota detecte que o pacote é muito grande para o MTU então ele avisa o nó fonte com ICMPv6 *Packet Too Big* (que inclui o tamanho da MTU do enlace problema). O nó usa esta nova MTU para encaminhar o pacote novamente ao seu destino, podendo o processo todo pode se repetir em outros roteadores.

A mensagems de erro *Time Exceeded* (*Type* = 3, *Code* = 0) é enviada quando o limite de saltos (*hop limit*) é excedido em um dado roteador.

## Autoconfiguração

A **autoconfiguração** (RFC2462) é um dos pontos fortes do **IPv6** permitindo gerar endereços IP automaticamente para as interfaces, sem nenhum tipo de configuração manual. Para isto o IPv6 combina **prefixos** divulgados pelos **roteadores** com o **endereço de MAC** (ou número randômico). Na ausência de roteadores usa-se o prefixo FE80 para gerar um endereço privado *link-local*.

A autoconfiguração é usada quando um sítio não necessita estabelecer endereços particulares as estações. Caso haja necessidade de se atribuir endereços específicos, pode-se utilizar o DHCPv6, como no IPv4.

Na **autoconfiguração** são utilizadas mensagens ICMPv6 de **descoberta de vizinhos** (*Neighbor Discovery*) (RFC2461), as quais são equivalentes as mensagens ARP. As mensagens ICMPv6 *Neighbor Discovery* podem ser do tipo (entre outras):

`Type Code`  
`133  0    Router Solicitation`  
`134  0    Router Advertisement`  
`135  0    Neighbor Solicitation`  
`136  0    Neighbor Advertisement`

As mensagens *Neighbor Solicitation* e *Neighbor Advertisement* são utilizadas para a descoberta de vizinhos e detecção de endereços duplicados.

<a href="Arquivo:NeighborSolicitation.png" class="wikilink" title="Arquivo:NeighborSolicitation.png">Arquivo:NeighborSolicitation.png</a>

A mensagem *Router Solicitation* é utilizada para a descoberta de roteadores na rede local e *Router Advertisement* são utilizadas pelos roteadores, periodicamente, para anunciar sua presença e divulgar seu prefixo.

<a href="Arquivo:RouterSolicitation.png" class="wikilink" title="Arquivo:RouterSolicitation.png">Arquivo:RouterSolicitation.png</a>

### Passos para autoconfiguração

1.  Um endereço tentativa é formado com o prefixo FE80 (*link-local address*) e associado ao endereço MAC da interface;
2.  O nó se junta aos grupos *multicasting*;
3.  Uma mensagem *Neighbor Solicitation* é enviado com o endereço tentativa como *target address*. Se detectado IP duplicado o nó deverá ser configurado manualmente;
4.  O nó realiza um *Router Solicitation* para o endereço FF02::2. (*multicast* dos roteadores);
5.  Todos roteadores do grupo *multicast* respondem e o nó se autoconfigura para cada um deles;

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 15h06min de 12 de maio de 2020 (-03)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>

[^1]: <http://ipv6.br/>

[^2]: <https://www.rfc-editor.org/rfc/rfc2460.txt>

[^3]: <https://www.iana.org/assignments/ipv6-parameters/ipv6-parameters.xhtml>

[^4]:

[^5]: <https://www.cisco.com/en/US/technologies/tk648/tk872/technologies_white_paper0900aecd8054d37d.html>

[^6]:

[^7]:
