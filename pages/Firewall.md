# *Firewall*

Um ***Firewall*** tem por objetivo aplicar **políticas de segurança** no acesso a uma rede ou servidor. O ***firewall*** pode ser do tipo **filtros de pacotes**, atuando no nível da camada IP, ou **<a href="Servidor_Proxy" class="wikilink" title="Servidor Proxy">Servidor Proxy</a>**, atuando no nível das aplicações.

<a href="Arquivo:Firewall.png" class="wikilink" title="Arquivo:Firewall.png">Arquivo:Firewall.png</a>

## *Firewall* com Iptables

O **[Iptables](http://manpages.ubuntu.com/manpages/trusty/en/man8/iptables.8.html)** é uma ferramenta que permite implementar regras para ***firewall***, disponível em todas as distribuições Linux.

O **Iptables** normalmente já vem instalado no Ubuntu.

As páginas **man** fornecem referência para utilizar o comando **iptables** para construir regras para filtros de pacotes':

`man iptables`

### Tabelas (Tables)

Com o **Iptables** é possível cinco tipos diferentes **tabelas** (**Tables**) para filtragem ou tratamento de pacotes, cada uma delas com diferentes tipos de **regras** (**Chain**).

  
Parâmetro: -t

<!-- -->

  
tabelas:

- **filter** -\> tabela *default* para filtragem de pacotes
- **nat** -\> implementa o NAT (*network address translation*)
- **mangle** -\> alteração de pacotes
- **raw** -\> implementação de rastreamento de conexões
- **security** -\> usada para controle de segurança de acesso

### Regras (Chain)

Para verificar as regras existentes, pode utilizar o comando:

`sudo iptables -L`

  
Parâmetro: -L (lista regras).

`Chain INPUT (policy ACCEPT)`  
`target     prot opt source               destination         `  
  
`Chain FORWARD (policy ACCEPT)`  
`target     prot opt source               destination          `  
  
`Chain OUTPUT (policy ACCEPT)`  
`target     prot opt source               destination`

Cada **Chain** é um conjunto de **regras** utilizadas para **filtrar pacotes**.

Tipos de Chain  
Por default há três tipos de regras:

1.  **INPUT**, pacotes destinados ao *Socket* local;
2.  **FORWARD**, pacotes a serem roteados;
3.  **OUTPUT**,pacotes originados localmente.

Policy  
Para cada **Chain** é estabelecida uma **policy** (política), quais sejam:

1.  **ACCEPT** (aceitar), deixa o pacote passar (política ***default***);
2.  **DROP**, descarta o pacote;
3.  **RETURN**, avança para a próxima regra.

Observa-se também o **cabeçalho** de cada coluna que formam as **regras**:

:\***target** (alvo),

:\***prot** (protocolo),

:\***opt** (opções),

:\***source** (fonte) e

:\***destination** (destino).

### Exemplos de filtros de pacotes TCP e UDP

Referência: [^1].

Exemplo 1  
Regra que pode ser utilizada em um computador desktop conectado a Internet para **ignorar conexões** vindas em qualquer porta **TCP**:

- Execute a regra no seu Servidor:

`sudo iptables -A INPUT -p tcp --syn -j DROP`

  
Comando:

- **-A INPUT**, (-A append) adiciona regra INPUT,

Parâmetros:

- **-p tcp --syn**, (-p protocol) protocolo TCP e pacote SYN solicitando abertura de conexão,
- **-j DROP**, (-j jump) define que o pacote será descartado.

- Verifique o resultado com:

`sudo iptables -L`

`Chain INPUT (policy ACCEPT)`  
`target   prot opt source      destination         `  
`DROP     tcp  --  anywhere    anywhere       tcp flags:FIN,SYN,RST,ACK/SYN`

- Teste o acesso ao **servidor Web** de seu servidor;
- Elimine a regra com o comando:

`sudo iptables -D INPUT -p tcp --syn -j DROP`

  
Comando:

- **-D**, (-d delete) deleta a regra.

- Teste novamente o acesso ao **servidor Web**.

Exemplo 2  
Regra que permite aos computadores da **rede interna** de se conectar normalmente, mas **bloqueia** tudo que vem da Internet em qualquer porta **TCP** ou **UDP**:

`sudo iptables -A INPUT -p tcp --syn -s 192.168.70.0/255.255.254.0 -j ACCEPT`  
`sudo iptables -A INPUT -p tcp --syn -j DROP`  
`sudo iptables -A INPUT -p udp -j DROP`

  
Comando:

- **-s 192.168.70.0/255.255.254.0**, (-s source) especifica a fonte .

<!-- -->

Exemplo 3  
Regra equivalente a anterior, mas **aceita** conexões **SSH**:

`sudo iptables -A INPUT -p tcp --destination-port 22 -j ACCEPT`  
`sudo iptables -A INPUT -p tcp --syn -s 192.168.70.0/255.255.254.0 -j ACCEPT`  
`sudo iptables -A INPUT -p tcp --syn -j DROP`  
`sudo iptables -A INPUT -p udp -j DROP`

### Sequência de análise das regras

O **Iptables** processa os comandos em sequência, regra por regra. Se um pacote vem para a porta 22 ele é aceito antes de ir para as demais regras. Se não passou pela primeira regra mas vem de um dos endereços da rede local é imediatamente aceito. Os demais vão para as duas últimas regras e acabam recusados [^2].

Todas as regras podem ser eliminadas com o comando:

`sudo iptables -F`

  
Comando:

- **-F** (-F flush) apaga todas as regras.

### Exemplo de filtro de pacotes ICMP

Pacotes do **<a href="Protocolo_ICMP" class="wikilink" title="Protocolo ICMP">Protocolo ICMP</a>** são utilizados por aplicativos importantes para a administração de redes, como o **ping** e o **traceroute**. Também servem para enviar **mensagens de erro e controle** entre hosts e roteadores, alertando sobre anormalidades no funcionamento do roteamento e da rede, informando situações como destino inalcançável, redirecionamentos, esgotamento de tempo, etc. Portanto, o **bloqueio de pacotes ICMP deve ser evitado, ou realizado com critério**.

Filtro de ICMP ping  

`iptables -A INPUT -p icmp --icmp-type echo-request -j DROP`

### Regras úteis de segurança com Iptables

Na Internet é possível encontrar várias dicas e regras úteis de segurança com Iptables, segue alguns links:

- [TAIOQUE, J.L. Regras úteis de segurança com iptables,2004](https://www.vivaolinux.com.br/dica/Regras-uteis-de-seguranca-com-iptables)

## Configuração do NAT no Linux

O **<a href="NAT" class="wikilink" title="NAT">NAT</a>** é um mecanismo que possibilita a uma rede local usar apenas um endereço **IP público** no que concerne ao mundo exterior e utilizar endereços **IP privados** no que concerne a rede interna.

<a href="Arquivo:Nat.png" class="wikilink" title="Arquivo:Nat.png">Arquivo:Nat.png</a>

O **NAT** no Ubuntu se configura com **iptables** com os seguintes comandos:

`modprobe iptable_nat`  
`iptables -t nat -A POSTROUTING -s 192.168.0.0/16 -o eth1 -j MASQUERADE`

1.  O primeiro comando ativa o **NAT** no módulo **iptables**.
2.  O segundo comando define a regra para fazer com que todo o tráfego originado em 192.168.0.0/16, e que sai pela interface eth1 deve ser mascarado com o endereço IP dessa interface [^3].

## Proxy transparente com Iptables

Um **<a href="Servidor_Proxy" class="wikilink" title="Servidor Proxy">Servidor Proxy</a>** isolado, montado com **Squid**, além da **configuração do servidor** é necessário configurar cada um dos **navegadores** e outros programas que vão acessar a Internet via servidor Proxy.

Com o **Iptables** é possível construir um **Proxy transparente**, evitando que seja necessário informar no navegador o endereço do servidor e a porta.

### Exemplo de configuração de roteador com firewall e proxy

Roteador com **Firewall** (**Iptables**) e **Proxy** (**Squid**) servindo a **rede local** com **IP privado** 192.168.0.0/16 pela interface Eth0 e acesso a **Internet** com **IP público** 200.17.101.10 pela interface Eth1:

<a href="Arquivo:ProxyTransparente.png" class="wikilink" title="Arquivo:ProxyTransparente.png">Arquivo:ProxyTransparente.png</a>

Passos para a configuração:

1.  Configurar **Squid** para funcionar em **modo transparente**;
2.  Configurar o servidor como **roteador NAT**;
3.  Configurar o **Iptables** para encaminhar toda **requisição HTTP** para **porta 3128**.

Referência: [^4]

Configuração do Squid  
Arquivo **/etc/squidw/squid.conf**:

`#  TAG: http_port`  
`http_port 3128 transparent`  
  
`#  TAG: acl`  
`#  ...`  
`#  Demais regras de acesso acl do Firewall`

Configuração do servidor como roteador NAT  
Setar para que o servidor **encaminhe** pacotes:

`echo 1 > /proc/sys/net/ipv4/ip_forward`

  
Configurar **NAT** com **Iptables** de forma a mascarar pacotes vindos da interface Eth0 (rede local) e saindo pela interface Eth1 (Internet) como o endereço desta interface:

`modprobe iptable_nat`  
`iptables -t nat -A POSTROUTING -s 192.168.0.0/16 -o eth1 -j MASQUERADE`

Configuração do Iptables  
Adicionar regras para que toda **requisição HTTP** (**porta 80**) seja redirecionada o **Squid**, na **porta 3128**:

`iptables -t nat -A PREROUTING -i eth1 -p tcp --dport 80 -j DNAT --to 192.168.0.1:3128`  
`iptables -t nat -A PREROUTING -i eth0 -p tcp --dport 80 -j REDIRECT --to-port 3128`

## Tarefa: Proxy transparente

Implementar com **Iptables** um **proxy transparente** para acesso ao **servidor Web**. No caso, configurar somente o acesso ao servidor e não a computadores da rede local, para o que seria necessário um roteador.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h01min de 23 de fevereiro de 2016 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Administração_de_Servidores" class="wikilink" title="Categoria:Administração de Servidores">Categoria:Administração de Servidores</a>

[^1]: MORIMOTO, C. E. Seridores Linux: Guia prático, Sul Editores, Porto Alegre, 2013.

[^2]:

[^3]: VALLE, O. T. Gerência de Redes, Diário Aula, 2014. <http://wiki.sj.ifsc.edu.br/wiki/index.php/GER20706-2014-1>

[^4]: GITE, V. Linux: Setup a transparent proxy with Squid in three easy steps, nixCraft, 2006. <http://www.cyberciti.biz/tips/linux-setup-transparent-proxy-squid-howto.html>
