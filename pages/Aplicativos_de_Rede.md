# Conceitos sobre redes locais e endereçamento IP

## Topologia típica de uma LAN conectada a Internet

<a href="Arquivo:RedeLocalTipica.png" class="wikilink" title="Arquivo:RedeLocalTipica.png">Arquivo:RedeLocalTipica.png</a>

Cada **dispositivo** em **uma rede local** é identificado pelas seguintes informações:

- **Endereço MAC**: É o **endereço físico** da interface de rede, gravado pelo fabricante;
- **Endereço IP**: É o endereço do dispositivo na Internet, o qual pode ser **configurado manualmente** ou ser **alocado dinamicamente** por **DHCP**;
- **Máscara de Rede**: Permite identificar a **rede local** na qual o dispositivo está conectado;
- *'Endereço de*broadcast**'': É o**endereço de difusão''' na rede local.

Outro elemento crucial de uma **rede local** é o **roteador padrão**, o qual é o dispositivo que conecta a rede local à Internet.

## Endereçamento IP

### Endereço IP

Um **endereço IP** (v. 4) é um endereço lógico de **32 bits**, escrito em **quatro bytes** representados em decimal e separados por pontos.

Cada byte do endereço IP pode variar em decimal de **O** (00000000) a **255** (11111111).

Exemplo  

`192.168.1.10`

  
é um endereço válido e sua notação em binário é:

`11000000.10101000.00000001.00001010`

### Máscara de rede

A **máscara de rede** é um parâmetro de configuração das **redes locais** e define o **tamanho da rede** em número de *hosts*.

O valor da **máscara de rede** pode ser representada na **notação decimal** com pontos ou na **notação com barra "/"**.

Por exemplo, a máscara

`/24`

  
pode ser representada na notação decimal como

`255.255.255.0`

  
e é equivalente ao binário

`11111111 11111111 11111111 00000000`

Esta **máscara de rede** indica que os 24 primeiros bits do endereço IP servem para **identificar a rede** e os 8 restantes identificam um **host** dentro desta rede.

O número de bits que identificam os ***hosts*** dentro da rede definem o **tamanho da rede**, no exemplo acima, a rede local pode endereçar 2<sup>8</sup> endereços.

### Endereços IP especiais em uma rede

Endereço da rede  
Possui bits "**tudo zero**" nos bits correspondentes ao **identificador de host**.

Este endereço é utilizado em **tabelas de roteamento** visando identificar a rede destino de um datagrama encaminhado a um *host*.

<!-- -->

Endereço de *broadcast*  
Possui bits "**tudo um**" nos bits correspondentes ao **identificador de host**.

O endereço de broadcast é considerado um endereço de difusão limitado a rede.

### Exemplo endereçamento de rede

Para um dado **endereços IP** e **máscara de rede** é possível determinar:

:\*A **máscara de rede** na notação decimal ou por barra;

:\*O endereço IP da rede, ou **identificador de rede**;

:\*A **quantidade de hosts** possíveis para esta rede;

:\*O **endereço de *broadcast*** da rede.

Exemplo  
Dado o IP **192.168.1.10/24**:

Resolução:

  
Máscara de rede em binário:

`11111111.1111111.1111111.00000000`

  
  
Máscara de rede em decimal:

`255.255.255.0`

  
  
Endereços IP e número de *hosts* possíveis:

`192.168.1.`**`0`**`   -> Idenfificador da rede`  
`192.168.1.`**`1`**`   -+`  
`192.168.1.`**`2`**`    | `  
`192.168.1.`**`3`**`    | Endereços para `*`hosts`*` e roteadores `  
`...            | dentro da rede (2`<sup>`8`</sup>` - 2 = 254)`  
`192.168.1.`**`253`**`  |`  
`192.168.1.`**`254`**` -+`  
`192.168.1.`**`255`**` -> `*`Broadcast`*` dentro da rede`

## Calculadoras de IP

Use aplicativos gratuitos para **cálculo do endereçamento IP** em smartphones ou na Web.

Exemplo:

[IP Calculator](http://jodies.de/ipcalc)  

# Aplicativos de Rede

Existem **aplicativos de rede** que permitem ao usuário descobrir a configuração do **endereçamento IP** de um dispositivo, identificar a **rede local** e o **roteador padrão**, e também verificar a rota de saída dos pacotes da rede local para a Internet.

`ifconfig`  
`route`  
`ping`  
`traceroute`

Há também aplicativos para **capturar pacotes** em uma dada interface de rede, permitindo com isto analisar o tráfego de rede e o funcionamento dos protocolos de comunicação.

`tcpdump `  
`wireshark`

## ifconfig

`ifconfig`

O aplicativo **ifconfig** pode ser utilizado para visualizar a configuração ou configurar uma interface de um dispositivo conectado a Internet. Se nenhum argumento for passado na chamada do ifconfig, o comando mostra a configuração atual de cada interface de rede.

A saída do aplicativo retorna as seguintes informações:

- Endereço MAC;
- Endereço IP;
- Máscara de Rede;
- Endereço de broadcast.

Teste  
Execute o **ifconfig** para verificar a configuração do endereçamento IP de seu computador.

<!-- -->

Windows  
No sistema operacional Windows o comando de terminal equivalente para verificar a configuração de IP é o **[ipconfig](https://docs.microsoft.com/pt-br/windows-server/administration/windows-commands/ipconfig)**.

## route

O comando **route** mostra a **tabela de roteamento** de um dispositivo e permite identificar o **roteador padrão** de uma rede local.

`route -n`

Exemplo  

`evandro@NBP-EVANDRO:/etc$ route -n`  
`Tabela de Roteamento IP do Kernel`  
`Destino         Roteador        MáscaraGen.    Opções Métrica Ref   Uso Iface`  
`0.0.0.0         192.168.70.1     0.0.0.0         UG    0      0        0 wlan0`  
`192.168.70.0     0.0.0.0         255.255.252.0   U     2      0        0 wlan0`

  
Na primeira linha o **destino 0.0.0.0** indica uma **rota default**, ou qualquer IP diferente da rede local -\> Para tal a saída é o **roteador padrão** 192.168.40.1.

Na segunda linha o destino 192.168.70.0 indica a **rede local** -\> Para tal, o **roteador 0.0.0.0** indica que **não há necessidade de roteamento** pois o destino está na própria rede.

<!-- -->

Teste  
Execute o **route** para verificar o **roteador padrão** de sua rede local.

## ping

`ping `<ip_destino>

Aplicativo **ping** permite a um usuário verificar se um *host* remoto está ativo. É bastante utilizado para detectar se há problemas de comunicação na rede.

Teste  
Execute o **ping** para testar conectividade com os seguintes hosts:

- Host local (endereço de loopback ou próprio IP)
- Host da LAN
- Roteador padrão
- Servidor Externo

## traceroute

`traceroute `<ip_destino>

O **traceroute**, que é capaz de **traçar uma rota** aproximada entre dois hosts.

Teste  
Execute o **traceroute** para traçar rotas entre sua máquina local e os seguintes hosts:

- Host da LAN
- Roteador padrão
- Servidor Externo

  
Verifique que qualquer **rota de saída** passa obrigatoriamente pelo **roteador padrão**.

Identifique outros **roteadores** chave de saída da rede da instituição.

## Captura de Pacotes

### Wireshark

O **Wireshark** é um aplicativo gráfico que permite capturar e analisar o tráfego de rede em uma dada interface de rede.

Tela do Wiresark  

<a href="Arquivo:Wireshark.png" class="wikilink" title=" 600px"> 600px</a>

Filtros de pacotes  
Para facilitar a análise do tráfego capturado, pode-se utilizar **filtros**, especificando quais os protocolos que se quer analisar, como por exemplo, **tcp**, **udp**, **icmp**, **mqtt** etc.

### tcpdump

`tcpdump`

O **tcpdump** é um aplicativo equivalente ao **Wireshark** para uso em um **terminal de comandos**.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h04min de 13 de junho de 2023 (-03)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>
