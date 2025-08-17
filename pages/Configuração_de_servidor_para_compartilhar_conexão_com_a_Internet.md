# Configuração de servidor para compartilhar conexão com a Internet

Um **servidor** com **duas placas de rede** pode ser configurado como **roteador**, separando o tráfego proveniente da Internet do tráfego da rede local.

Exemplo de uma configuração típica de um servidor com duas placas  
Referência [^1].

<a href="Arquivo:ServidorAcesso.png" class="wikilink" title="600px">600px</a>

No exemplo a interface **eth0** usa **endereços IP privados** na faixa 192.168.1.x/24. A interface **eth1** é configurada como **cliente DHCP**, recebendo endereço IP do provedor.

Se o acesso a Internet é provido via **ADSL** é recomendável manter o modem configurado como ***bridge***, desta forma o servidor recebe a configuração completa do **endereçamento IP** do provedor e acesso a todas as **portas** de entrada, permitindo que o servidor seja acessado remotamente via **SSH** [^2].

Da mesma forma, o ***access point*** da rede privada também pode ser configurado como ***bridge*** para que os computadores da **rede cabeada** e da **rede sem fio** permaneçam na mesma **rede local**.

Configuração de rede do Servidor  
Exemplo de configuração do arquivo **/etc/network/interfaces**:

`auto lo`  
`iface lo inet loopback`  
  
`iface eth0 inet static`  
`  address 192.168.1.1`  
`  netmask 255.255.255.0`  
`  network 192.168.1.0`  
`  broadcast 192.168.1.255`  
  
`iface eth1 inet dhcp`

A interface de rede do **servidor** voltada para a rede interna (eth0) deve receber um endereço **IP estático**, dentro da faixa de **IP privados** escolhida para a rede interna. O endereço IP de rede local do servidor será o **roteador padrão** (***gateway***) da rede.

Para configurar as demais **estações da rede interna** pode-se utilizar configuração via **DHCP**, com o servidor de configuração dinâmica de IP sendo provido pelo servidor.

Ativando o servidor como roteador  

Para ativar o **roteamento** no servidor deve-se executar o comando:

`echo 1 > /proc/sys/net/ipv4/ip_forward`

Com isto o servidor assume papel de roteador, encaminhando para a Internet pacotes originados na rede local.

## NAT

O <a href="NAT" class="wikilink" title="NAT (Network Address Translation)"><strong>NAT</strong> (<em>Network Address Translation</em>)</a> é um mecanismo que possibilita a uma rede local usar apenas um endereço **IP público**, no que concerne ao mundo exterior, e utilizar endereços **IP privados** no que concerne a rede interna.

Configuração do NAT no servidor  
Referência: [^3].

O **NAT** no Ubuntu se configura com [**iptables**](http://manpages.ubuntu.com/manpages/trusty/en/man8/iptables.8.html). Exemplo de comandos:

`modprobe iptable_nat`  
`iptables -t nat -A POSTROUTING -s 192.168.1.0/24 -o eth1 -j MASQUERADE`

O primeiro comando ativa o **NAT** no módulo **iptables**.

O segundo comando define a regra para fazer com que todo o tráfego originado em 192.168.1.0/24, e que sai pela interface eth1 deve ser mascarado com o endereço IP dessa interface. Esta regra diz o seguinte: todos os pacotes que passarem (POSTROUTING) por esta máquina com origem de 192.168.1.0/24 e sairem pela interface eth1 serão mascarados, ou seja sairão desta máquina com o endereço de origem como sendo da eth1. O alvo MASQUERADE foi criado para ser usado com links dinâmicos (tipicamente discados ou ADSL), pois os mapeamentos se perdem se o link sair do ar.

Configuração permanente ativada no *boot* do sistema  
Depois de realizada a configuração do servidor como roteador para a rede interna deve-se fazer com que os comandos sejam ativados no *boot* do sistema.

Uma forma de fazer isto é inserir os comandos no arquivo **/etc/rc.local**:

`#!/bin/sh `  
`# rc.local`  
  
`modprobe iptable_nat`  
`echo 1 > /proc/sys/net/ipv4/ip_forward`  
`iptables -t nat -A POSTROUTING -s 192.168.1.0/24 -o eth1 -j MASQUERADE`

## Servidor DHCP

Um **servidor DHCP** permite configurar **automaticamente** as interfaces de rede de máquinas em uma rede local.

Dentre os parâmetros que podem ser configurados automaticamente pelo **servidor DHCP** estão: **endereço IP**, **máscara de rede**, **roteador padrão**, **servidores DNS**, *'nome de*host**'' e**nome de domínio''', entre outros.

O serviço de configuração automática utiliza o **<a href="Protocolo_DHCP" class="wikilink" title="Protocolo DHCP">Protocolo DHCP</a>**, o qual define as regras de negociação entre cada interface de rede e o servidor DHCP.

Cliente DHCP  
O **cliente DHCP** (**[dhclient](http://manpages.ubuntu.com/manpages/dapper/en/man8/dhclient.8.html)**)vem instalado por padrão nas estações Ubuntu. Este serviço é acionado automaticamente quando a estação é configurada para **obter endereço IP automaticamente**.

<!-- -->

  
Também é possível chamar o serviço para obter a configuração IP automática para uma dada interface de rede, por exemplo, o comando:

`dhclient eth0`

### Instalação e configuração do servidor DHCP

Instalação do servidor DHCP  
Para instalação do servidor DHCP usa-se o comando:

`sudo apt install isc-dhcp-server`

Quando instalado o servidor DHCP o mesmo fica disponível através do serviço **[dhcpd](http://manpages.ubuntu.com/manpages/wily/en/man8/dhcpd.8.html)**.

Configuração do servidor DHCP  
A configuração do **servidor DCHP** é realizada através do arquivo **[/etc/dhcpd.conf](http://manpages.ubuntu.com/manpages/dapper/en/man5/dhcpd.conf.5.html)**:

Exemplo de configuração:

`ddns-update-style none;`  
  
`default-lease-time 600;`  
`max-lease-time 7200;`  
  
`authoritative;`  
  
`subnet 192.168.1.0 netmask 255.255.255.0 {`  
`   range 192.168.1.100 192.168.1.150;`  
`   option broadcast-address 192.168.1.255;`  
`   option routers 192.168.1.1;`  
`   option domain-name-servers 200.17.101.9;`  
`}`

Opções usadas na configuração:

- *lease-time* controla o tempo de renovação cada 10 minutos (600 segundos);
- *max-lease-time* controla o tempo máximo que uma estação pode usar o endereço IP. Usado quando existe mais clientes que endereços IP disponíveis para aluguel;
- *range* indica a faixa de IP que será usada para aluguel;
- *routers* indica o endereço do roteador padrão;
- *domain-name-servers* indica os servidores DNS que serão usados pelas estações.

Interface que será servida pelo serviço DHCP  
Deve ser indicada editando o arquivo:

`/etc/default/isc-dhcp-server`

  
Conteúdo:

`INTERFACES="eth0"`

  
Esta configuração provê aluguel de endereços IP na faixa 192.168.1.100 a 192.168.1.150.

<!-- -->

Iniciar o servidor DHCP  

`service isc-dhcp-server restart`

Arquivo de log  
No arquivo **/var/log/syslog** ficam gravadas as trocas de mensagens entre o cliente e o servidor DHCP:

`tail /var/log/syslog`

Aluguéis no servidor DHCP  
São visíveis no arquivo:

`cat /var/lib/dhcp/dhcpd.leases`

## Configuração do cliente DNS

A configuração cliente do <a href="DNS" class="wikilink" title="servidor de nomes (DNS)"><strong>servidor de nomes</strong> (<strong>DNS</strong>)</a> indica qual o servidor de nomes será consultado para traduzir **nomes de domínio** para **endereços IP**.

No Ubuntu o arquivo de configuração do DNS é o **[/etc/resolve.conf](http://manpages.ubuntu.com/manpages/trusty/en/man5/resolv.conf.5.html)** e é atualizado automaticamente pelo sistema.

Para se editar manualmente este arquivo deve-se desabilitar o serviço automático de atualização, através do comando **dpkg-reconfigure resolvconf**, escolhendo a primeira opção como yes e as demais opções deixando o padrão. Em seguida edita-se o arquivo **/etc/resolv.conf**, por exemplo:

`#DNS público da Google`  
`nameserver 8.8.8.8`

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 18h43min de 22 de novembro de 2015 (BRST)

------------------------------------------------------------------------

<a href="Categoria:Administração_de_Servidores" class="wikilink" title="Categoria:Administração de Servidores">Categoria:Administração de Servidores</a>

[^1]: MORIMOTO, C. E. Seridores Linux: Guia prático, Sul Editores, Porto Alegre, 2013.

[^2]:

[^3]: VALLE, O. T. Gerência de Redes, Diário Aula, 2014. <http://wiki.sj.ifsc.edu.br/wiki/index.php/GER20706-2014-1>
