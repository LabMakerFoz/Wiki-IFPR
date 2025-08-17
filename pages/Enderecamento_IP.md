# Endereçamento IP

O **endereço IP** é um endereço lógico de **32 bits**, escrito em **quatro bytes representados em decimal** e separados por pontos [^1].

Cada byte do endereço IP pode variar em decimal de **O** (00000000) a **255** (11111111).

Exemplo  

`200.17.101.9`

  
é um endereço válido e sua notação em binário é:

`11001000 00010001 01100101 00001001`

### Endereços de uso especial

`0.0.0.0`

  
Endereço com todos os **32 bits iguais a 0**. É usado em **tabelas de roteamento** para identificar destino para *'rotas*default**'' e também para indicar a**própria rede''' como próximo encaminhamento.

`255.255.255.255`

  
Endereço com todos os **32 bits iguais a 1**. É considerado um **endereço de difusão** (ou *broadcast*) limitado a rede do *host* origem do datagrama (não encaminhado).

`127.0.0.1`

  
Identifica a própria máquina, ou ***localhost***, e é usado para testes comunicação entre processos na mesma máquina.

Todos os endereços com o primeiro byte 127 (127.0.0.0/8) são reservados para **testes de *loopback***.

## Endereçamento de redes e *hosts*

Todo computador na Internet necessita de um endereço IP exclusivo e pertence a uma rede.  

Cada **endereço IP** engloba duas partes:

- **Identificador da rede**: identifica a rede onde se encontram todos os computadores da mesma rede local.
- **Identificador do *host***: identifica um dispositivo em uma rede local, como um computador ou roteador.

O identificador de rede é obtido a partir da **máscara de rede**, a qual indica quais bits do IP identificam a rede e quais identificam o host.

Por exemplo, na figura abaixo temos três redes locais interconectadas por um roteador. Em cada rede, a **máscara de rede**, na notação **/24**, indica que os 24 bits mais à esquerda (dos 32 bits do IP) identificam a rede e os 8 bits restantes identificam cada *host* ou roteador dentro da rede. Desta forma, na rede local da direita, todos os hosts compartilham os 24 bits mais à esquerda do endereço IP, ou seja, os três primeiros bytes em representados em decimal, **200.1.1**.X, o que **identifica a rede**. Idem para as redes **200.1.2**.Y e **200.1.3**.Z. O último byte do endereçamento identifica um *host* da respectiva rede.

<a href="Arquivo:EnderecamentoIP.png" class="wikilink" title=" 600px"> 600px</a>

### Máscara de rede

O valor da **máscara de rede** também pode ser representada na notação decimal com pontos. Por exemplo, a máscara **/24** pode ser representada como

`255.255.255.0`

  
é equivalente a

`11111111 11111111 11111111 00000000`

  
o que significa que os 24 primeiros bits são um e os 8 restantes zero.

Através da máscara de rede podemos extrair o **identificador da rede** de um endereço IP utilizando uma operação lógica **AND** entre o **endereço IP** e a **máscara de rede**.

Por exemplo, para descobrir o identificador de rede do computador cujo **endereço IP** é **200.17.101.9** e cuja **máscara de rede** é **255.255.255.0**, devemos fazer uma **operação lógica AND** destes dois valores.

`    11001000 00010001 01100101 00001001     |   AND: 0 & 0 = 0`  
`    11111111 11111111 11111111 00000000     |        0 & 1 = 0`  
`AND ___________________________________     |        1 & 0 = 0`  
`    11001000 00010001 01100101 00000000     |        1 & 1 = 1`

  

## Classes de Endereçamento e CIDR

A **classe de endereçamento** de uma rede é dada pela sua **máscara de rede**, a qual define seu tamanho em número de endereços possíveis.

Quando o **protocolo IP** foi criado existiam cinco **<a href="Classes_de_Endereçamento" class="wikilink" title="Classes de Endereçamento">Classes de Endereçamento</a>**. Dentre estas, as classes A, B e C eram utilizadas para definir os tamanhos das redes.

Entretanto, com o crescimento da Internet e o desperdício de endereços que o uso das classes de endereço acarretava, foi criado um novo formato para definir o tamanho das redes. Este formato é conhecido como <a href="CIDR" class="wikilink" title=" CIDR ou endereço IP sem classes"> <strong>CIDR</strong> ou <strong>endereço IP sem classes</strong></a>.

## Alocação dinâmica de endereços IP

A alocação dinâmica de endereços IP dentro de uma rede local pode ser realizada pelo **<a href="Protocolo_DHCP" class="wikilink" title="Protocolo DHCP">Protocolo DHCP</a>** (*Dynamic Host Configuration Protocol*).

Com o DHCP instalado em uma rede local, o servidor DHCP recebe uma solicitação de uma máquina cliente, solicitando endereçamento IP, e aloca dinamicamente um endereço IP em resposta ao pedido do cliente.

## Endereços IP privados e NAT

Alguns blocos de endereços IP são reservados para uso privado na Internet.

`10.0.0.0    - 10.255.255.255  (10/8)`  
`172.16.0.0  - 172.31.255.255  (172.16/12)`  
`192.168.0.0 - 192.168.255.255 (192.168/16)`

Os **endereços IP privados** e tem validade somente no escopo da rede interno de uma organização.

Para que computadores da **Internet pública** acessem um *host* de uma organização é necessário que este *host* possua um **endereço IP público**.

Os **endereços privados** são úteis para computadores clientes de uma organização, que somente necessitam acessar recursos comuns da Internet como acesso a Web ou Email. Neste caso, estes computadores não precisão ocupar endereços públicos, podendo serem mediados por dispositivos que façam uma tradução destes endereços, como **<a href="NAT" class="wikilink" title=" roteadores NAT"> roteadores NAT</a>**.

## Endereços IP reservados para *Link-local*

Os endereços ***Link-local*** são reservados para uso interno na **rede local**.

`169.254.0.0/16`

Pode ser atribuído as interfaces pelo sistema operacional do *host* por **auto configuração** quando outros modos de endereçamento não estão disponíveis, como por exemplo por DHCP. Isto permite que, automaticamente, os hosts conectados a uma rede local se comuniquem entre si.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h36min de 12 de junho de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: KUROSE, J.F; ROSS K. W. Redes de Computadores e a Internet: Uma abordagem *top-down*, São Paulo: Pearson, 2010.
