# Kathará: Roteamento

Veja como instalar o emulador de redes de computadores **Kathará** e exemplos introdutórios de redes na página **<a href="Kathara" class="wikilink" title="Kathará">Kathará</a>**.

## Laboratório: Redes interligadas por roteador

Exemplo de **redes interligadas por roteador** construída com comandos **Kathará l-commands**:

<a href="Arquivo:Kathara-lab2.png" class="wikilink" title="Arquivo:Kathara-lab2.png">Arquivo:Kathara-lab2.png</a>

Hierarquia de arquivos e diretórios para os scripts do laboratório  

`lab.conf`  
`pc1.startup`  
`pc2.startup`  
`r1.startup`  
`pc1/`  
`pc2/`  
`r1/`

Conteúdo dos arquivos:

`lab.conf`  
`  pc1[0]=A`  
`  r1[0]=A`  
`  r1[1]=B`  
`  pc2[0]=B`

`pc1.startup`  
`  ifconfig eth0 192.168.0.1/24 up`

`pc2.startup`  
`  ifconfig eth0 192.168.1.2/24 up`

`r1.startup`  
`  ifconfig eth0 192.168.0.2/24 up`  
`  ifconfig eth1 192.168.1.1/24 up`

Iniciar rede do laboratório:

`kathara lstart`

Verificar **tabelas de roteamento** com **route**:

- pc1, pc2 e r1:

`route`

Definir **roteador default** com **route add** manualmente em cada dispositivo:

- pc1:

`route add default gw 192.168.0.2 dev eth0`

- pc2:

`route add default gw 192.168.1.1 dev eth0`

  
Verificar novamente as **tabelas de roteamento** .

Obs: Rotas estáticas e o roteador padrão podem ser incluídas nos arquivos .startup.

Testar conectividade com **ping**:

- pc1 -\> pc2:

`ping 192.168.1.2`

- pc2 -\> pc1:

`ping 192.168.0.1`

Verificar rota com **traceroute**:

- pc1 -\> pc2:

`traceroute 192.168.1.2`

Remover rede do laboratório:

`kathara lclean`

## Laboratório: Roteamento Estático

Exemplo de **rede de computadores** com **roteamento estático** construída com comandos **Kathará l-commands**:

<a href="Arquivo:Kathara-lab3.png" class="wikilink" title="Arquivo:Kathara-lab3.png">Arquivo:Kathara-lab3.png</a>

Hierarquia de arquivos e diretórios para os scripts do laboratório  

`lab.conf`  
`pc1.startup`  
`pc2.startup`  
`pc3.startup`  
`r1.startup`  
`r2.startup`  
`r3.startup`  
`pc1/`  
`pc2/`  
`pc3/`  
`r1/`  
`r2/`  
`r3/`

Conteúdo dos arquivos:

`lab.conf`  
`  pc1[0]=A`  
`  r1[0]=A`  
`  r1[1]=AB`  
`  r1[2]=AC`  
`  pc2[0]=B`  
`  r2[0]=B`  
`  r2[1]=AB`  
`  r2[2]=BC`  
`  pc3[0]=C`  
`  r3[0]=C`  
`  r3[1]=BC`  
`  r3[2]=AC`

  
Rotas *default* incluídas no arquivo de configuração:

`pc1.startup`  
`  ifconfig eth0 192.168.1.1/24 up`  
`  route add default gw 192.168.1.2 dev eth0`

`pc2.startup`  
`  ifconfig eth0 192.168.2.1/24 up`  
`  route add default gw 192.168.2.2 dev eth0`

`pc3.startup`  
`  ifconfig eth0 192.168.3.1/24 up`  
`  route add default gw 192.168.3.2 dev eth0`

`r1.startup`  
`  ifconfig eth0 192.168.1.2/24 up`  
`  ifconfig eth1 10.0.1.1/24 up`  
`  ifconfig eth2 10.0.2.1/24 up`

`r2.startup`  
`  ifconfig eth0 192.168.2.2/24 up`  
`  ifconfig eth1 10.0.1.2/24 up`  
`  ifconfig eth2 10.0.3.1/24 up`

`r3.startup`  
`  ifconfig eth0 192.168.3.2/24 up`  
`  ifconfig eth1 10.0.3.2/24 up`  
`  ifconfig eth2 10.0.2.2/24 up`

### Procedimentos práticos

Iniciar rede do laboratório:

`kathara lstart`

Verificar **tabelas de roteamento** com **route**:

- pc1, pc2, pc2
- r1, r2, r3

`route`

**Testar conectividade** entre as máquinas com **ping**:

- pc1 -\> r1:

`ping 192.168.1.2`

- pc1 -\> pc2:

`ping 192.168.2.1`

- pc1 -\> pc3:

`ping 192.168.3.1`

  
Note que **não há conectividade** entre os pc1, pc2 e pc3.

<!-- -->

Rotas estáticas  

Definir **rotas estáticas** nos roteadores r1, r2 e r3 para conectividade completa entre os dispositivos.

  
Exemplo de rotas em r1 para atingir redes B e C:

`route add -net 192.168.2.0/24 gw 10.0.1.2 dev eth1`  
`route add -net 192.168.3.0/24 gw 10.0.2.2 dev eth2`

  
Configurar também para r2 e r3.

Testar novamente **conectividade** entre as máquinas com **ping**.

Verificar **rotas** entre as máquinas com **traceroute**.

Remover rede do laboratório:

`kathara lclean`  
`kathara wipe`

## Roteamento Dinâmico

O **roteamento dinâmico** permite gerar automaticamente as rotas que os pacotes seguirão entre uma origem e um destino.

Há duas classes de **protocolos de roteamento dinâmico** na Internet: os **protocolos intra-SA** e **inter-SA** (SA - Sistema Autônomo).

Os protocolos de roteamento **intra-SA** atuam internamente ao **sistema autônomo**, definindo as melhores rotas em função de um custo atribuído a cada enlace a percorrer. Dois protocolos de roteamento intra--SA bastante utilizados na Internet são o **RIP** e o **OSPF**:

- **RIP** (*Routing Information Protocol*): Constrói as tabelas dinamicamente utilizando um **algoritmo de roteamento** chamado **vetor de distâncias**, calculando as melhores rotas tendo como base o número de enlaces a percorrer.
- **OSPF** (*Open Shortest Path First*): É um protocolo de roteamento mais elaborado, baseado no algoritmo **estado do enlace**, desenhado para convergir rapidamente ao ser informado de qualquer alteração de estado do enlace dentro da rede.

O roteamento **inter-SA** permite interconectar diferentes sistemas autônomos. Na Internet o protocolo mais utilizado neste domínio é o **BGP** (*Border Gateway Protocol*), o qual permite implementar políticas específicas dependendo dos sistemas autônomos que serão integrados.

## Laboratório: Roteamento Dinâmico

Ha alguns pacotes de software que implementam os protocolos de roteamento dinâmico, como o **Quagga** e o **FFR**, sendo este último uma versão mais nova, originada de um *fork* do Quagga.

Para este laboratório vamos utilizar o **Quagga** e o protocolo **RIP**, baseado no exemplo descrito em [^1].

### Preparação da estrutura para o laboratório

Utilizar a mesma estrutura do **laboratório Roteamento Estático**, com os mesmos arquivos de configuração.

Iniciar rede do laboratório:

`kathara lstart`

Verificar **tabelas de roteamento** com **route**:

- pc1, pc2, pc2
- r1, r2, r3

`route`

**Testar conectividade** entre as máquinas com **ping**:

- pc1 -\> r1:

`ping 192.168.1.2`

- pc1 -\> pc2:

`ping 192.168.2.1`

- pc1 -\> pc3:

`ping 192.168.3.1`

  
Note que **não há conectividade** entre os pc1, pc2 e pc3.

### Ativação e testes do protocolo RIP

Para ativar o **RIP** é necessário incluir **arquivos de configuração** em cada um dos roteadores.

Os arquivos de configuração do RIP em um roteador são:

`/etc/quagga/daemons`  
`/etc/quagga/ripd.conf`  
`/etc/quagga/zebra.conf`

Conteúdo dos arquivos para ativar RIP no roteador r1:

`daemons`  
` #Indica quais `*`daemons`*` devem ser iniciados:`  
` zebra=yes`  
` bgpd=no`  
` ospfd=no`  
` ospf6d=no`  
` ripd=yes`  
` ripngd=no`

`ripd.conf`  
` hostname ripd`  
` password zebra`  
` enable password zebra`  
` !`  
` router rip`  
` redistribute connected`  
` network 10.0.0.0/16`  
` !`  
` log file /var/log/quagga/ripd.log`

`zebra.conf`  
` hostname r1`  
` password zebra`  
` enable password zebra`

Estes arquivos devem ser incluídos no diretório

`/r1/etc/quagga/`

Para os demais roteadores deve-se fazer o mesmo, mudando o nome do roteador no arquivo zebra.conf.

Ativação do RIP  

Uma vez configurado, o RIP deve ser ativado manualmente em cada roteador:

`/etc/init.d/quagga start`

Testes de conectividade  

Testar novamente **conectividade** entre as máquinas com **ping**.

Verificar **rotas** entre as máquinas com **traceroute**.

**Derrubar um enlace** e verificar novamente as rotas e testar conectividade.

  
Por exemplo, para derrubar o enlace AB, derrubar as interfaces correspondentes em r1 e r2:

`ifconfig eth1 down`

Remover rede do laboratório:

`kathara lclean`  
`kathara wipe`

## Terminal vtysh dos roteadores

Um roteador implementado com **quagga** apresenta um **shell** similar a um **roteador Cisco** real, conhecido como **vtysh**, e aceita comandos específicos para a configuração dos roteadores. O comando **?** mostra os demais comandos disponíveis.

Comandos para verificar a configuração do roteador  

- Verificar a configuração das interfaces de rede:

`show interface`

- Verificar as tabelas de roteamento:

`show ip route`

- Sair do vtysh:

`exit`

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 11h18min de 23 de fevereiro de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: <https://github.com/KatharaFramework/Kathara-Labs/tree/main/main-labs/intradomain-routing/quagga/rip/kathara-lab_rip>
