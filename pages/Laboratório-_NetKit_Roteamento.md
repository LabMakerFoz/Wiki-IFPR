# Laboratório: NetKit Roteamento

O **[Netkit2](http://wiki.sj.ifsc.edu.br/wiki/index.php/Netkit2)** [^1] é um ambiente para experimentos com redes de computadores desenvolvido no Câmpus São José, do IFSC, inspirado no **[Netkit](http://wiki.netkit.org/index.php/Main_Page)** [^2], desenvolvido pela Universidade de Roma, na Itália.

O Netkit2 se compõe de **máquinas virtuais Linux** (implementadas com kernel Linux UML – *User Mode Linux*), que funcionam como roteadores ou computadores e *switches* virtuais (UML *switch*) para interligar as máquinas virtuais. Para todos os efeitos, cada máquina virtual funciona como se fosse um computador real, possuindo uma ou mais interfaces de rede. Com esses recursos é possível criar redes de configurações arbitrárias para estudar protocolos de comunicação e serviços de rede [^3].

## Teste do Netkit2

O **Netkit2** já está instalado no laboratório e pode ser iniciado com o comando:

`netkit2`

Caso deseja instalar o Netkit2 em outro computador Linux, consultar a referência [^4].

### Rede de computadores básica

O *script* abaixo apresenta uma rede de computadores básica para ser testado (Consulte [^5] para mais detalhes sobre a sintaxe dos *scripts*):

`pc1[type]=generic`  
`pc2[type]=generic`  
  
`pc1[eth0]=lan1:ip=192.168.0.1/24`  
`pc2[eth0]=lan1:ip=192.168.0.2/24`

1.  Edite um arquivo de texto e salve em uma pasta de trabalho (extensão .conf);
2.  Carregue o arquivo no NetKit2 com a opção *File -\> Load and Run*;
3.  Clique na opção *File -\> Graph* e veja a topologia da rede em execução;
4.  Verifique as configurações de cada **pc** com o comando **ifconfig**;
5.  Verifique a conectividade em rede entre os **pc** com o comando **ping**;

### Redes de computadores interligadas por roteador

O *script* abaixo apresenta duas redes de computadores interligadas por um roteador:

`pc1[type]=generic`  
`r1[type]=gateway`  
`pc2[type]=generic`  
  
`pc1[eth0]=lan0:ip=192.168.0.1/24`  
`r1[eth0]=lan0:ip=192.168.0.2/24`  
`r1[eth1]=lan1:ip=192.168.1.2/24`  
`pc2[eth0]=lan1:ip=192.168.1.1/24`  
` `  
`pc1[default_gateway]=192.168.0.2`  
`pc2[default_gateway]=192.168.1.2`

1.  Edite um arquivo de texto e salve em uma pasta de trabalho (extensão .conf);
2.  Carregue no NetKit2 com a opção *File -\> Load and Run*;
3.  Clique na opção *File -\> Graph* e veja a topologia da rede em execução;
4.  Verifique as configurações de cada máquina com o comando **ifconfig**;
5.  Verifique a conectividade em rede entre as máquinas com o comando **ping**;
6.  Verifique a rota dos pacotes entre os computadores **pc1** e **pc3** com o comando **traceroute**.

## Exercício sobre Rede e Roteamento

### Exercício 1

Montar no **NetKit2** a rede experimental mostrada na figura: <a href="Arquivo:Sub-redes.png" class="wikilink" title="Arquivo:Sub-redes.png">Arquivo:Sub-redes.png</a>

Exemplo de comandos para incluir no *script* a criação de **rotas estáticas**:

`r1[route]=192.168.0.0/24:gateway=192.168.10.10`

  
Cria na máquina r1 uma rota para a rede 192.168.0.0 através do roteador 192.168.10.10.

As **rotas estáticas** também podem ser criadas através do comando **route** diretamente no roteador em operação.

Procedimentos:

1.  Faça uma alocação de endereços IP para cada sub-rede (rede 1, 2 e 3);
2.  Faça também uma alocação de endereços IP para cada enlace ponto a ponto (**enlaces AB, AC e AB**).
3.  Defina as **tabelas de roteamento** entre para que os *hosts* possam trocar pacotes entre si.
4.  Faça teste **conectividade** entre os *hosts*.

Para entregar  
**PARTE 1**

1.  Relatório descrevendo a **distribuição dos endereços** IP.
2.  ***Script* comentado** da rede experimental.
3.  Descrição dos **procedimentos de teste** realizados com o Netkit, anexando:
    - Telas ilustrando a **configuração IP** das máquinas em cada rede;
    - Telas mostrando a **conectividade em rede** entre as máquinas (ping);
    - Telas ilustrando as **tabelas de roteamento** de cada roteador (route);
    - Telas ilustrando a **rota** seguida pelos pacotes entre hosts de duas redes remotas (traceroute).

## Comandos para configurar interfaces de rede e roteamento estático

### Configuração da interface de rede de um host

Exemplo: host **PC1**:

- Configuração de uma interface, incluindo IP, máscara de rede e *broadcast*:

`ifconfig eth0 192.168.0.1/24 broadcast 192.168.0.255 up`

- Configuração do **roteador padrão** da rede:

`route add default gw 192.168.0.254 dev eth0`

- Visualizar a configuração de uma interface:

`ifconfig`

- Derrubar uma interface:

`ifconfig eth0 down`

- Subir uma interface com a configuração anterior:

`ifconfig eth0 up`

### Configuração das interfaces e rotas estáticas em roteadores

Exemplo: roteador **R1**:

- Configuração das **interfaces** do roteador:

`ifconfig eth0 192.168.0.254/24 broadcast 192.168.0.255 up`  
`ifconfig eth1 10.0.0.1 netmask 255.255.255.252 broadcast 10.0.0.3 up`

  
A máscara de rede pode ser adicionada com a notação "/" ou decimal.

- Adição de uma **rota estática** em um roteador:

`route add -net 192.168.1.0/24 gw 10.0.0.2 dev eth1`

- Visualizar as **tabelas de roteamento**:

`route -n `

- Remover uma rota:

`route del -net 192.168.1.0/24 gw 10.0.0.2 dev eth1`

### Exercício 2

Use a rede do **exercício 1** para realizar os exercícios.

1.  Modifique a **interface de rede** de um host e em seguida verifique a mudança com **ifconfig** e teste conectividade com **ping** a partir de outros hosts.
2.  **Derrube uma interface ponto a ponto** de um dos **enlaces** entre dois roteadores e teste conectividade com ping.
3.  **Modifique o roteamento** de forma a contornar o enlace derrubado e teste conectividade com ping entre todos os hosts.
      
    **Atenção**: Lembre de configurar rotas em ambos os sentidos, pois no teste com ping temos pacotes ICMP *Echo Request* e *Echo Replay*, ou seja, pacotes circulando nos dois sentidos.
4.  Execute um **traceroute** para verificar a nova rota percorrida pelos pacotes.

Para entregar  
**PARTE 2**

1.  Anexar telas ilustrando as **tabelas de roteamento** depois que a interface do roteador for derrubada;
2.  Anexar telas ilustrando a **ausência de conectividade** com ping;
3.  Mostre os comandos utilizados para adicionar novas **rotas estáticas** e anexar telas com as novas **tabelas de roteamento**;
4.  Anexar telas do **traceroute** para mostrar a nova rota percorrida pelos pacotes.

## Protocolos de Roteamento Dinâmico

Os **protocolos de roteamento dinâmicos** permitem encontrar, de forma automática, o caminho que os **datagramas** tomarão entre a fonte e o destino.

Dois protocolos de roteamento **intra domínio** bastante utilizados na Internet são o **RIP** e o **OSPF**

No **NetKit** para ativar protocolos de roteamento é necessário usar máquinas virtuais do tipo ***router***. Um ***router**'' tem sua função de***gateway**'' ativada automaticamente e executa o programa [Quagga](http://www.quagga.net/), que implementa protocolos de roteamento (tais como OSPF, RIP e BGP).

Veja abaixo como incluir no arquivo de configuração do NetKit máquinas tipo ***router*** e configurar suas interfaces:

`r1[type]=router`  
`r1[ppp0]=link0:ip=10.0.0.1/30`  
`r1[eth0]=lan0:ip=192.168.0.254/24`

  
Nos exemplos acima, além de interfaces **ethernet** (eth0), note que é também possível criar nos roteadores interfaces **ponto a ponto** (ppp0).

### Ativação dos protocolos de roteamento nos roteadores

Para a ativação dos protocolos de roteamento no **NetKit**, conforme [^6], é necessário incluir algumas diretivas no arquivo de configuração. Veja exemplos:

`# Ativa os protocolos RIP e OSPF no roteador r1`  
`r1[router]=rip, ospf`  
`# Preserva as configurações do roteador r1`  
`r1[preserve]=/etc/quagga`

#### RIP

O *RIP* (*Routing Information Protocol*) é um protocolo padronizado, definido na RFC 1058, e utiliza o algoritmo de roteamento **vetor de distâncias**.

Há duas versões do protocolo:

- RIP versão 1: ***classfull***, ou seja, suporta apenas classes cheias (A, B ou C);
- RIP versão 2: suporta **CIDR** (*classless*).

Em ambas as versões os roteadores trocam informações utilizando **UDP** na **porta 520** [^7].

#### Terminal vtysh dos roteadores

Um roteador implementado com **quagga** apresenta um **shell** parecido com o de um **roteador Cisco** real, conhecido como **vtysh**, e aceita comandos específicos para a configuração dos roteadores. O comando **?** mostra os demais comandos disponíveis.

Comandos para verificar a configuração do roteador  

- Verificar a configuração de cada interface:

`show interface eth0`  
`show interface ppp0`

- Verificar as tabelas de roteamento:

`show ip route`

Comandos para configuração do RIP versão 1  
Exemplo **roteador R1** conectado a outros roteadores pelas **interfaces ppp0** e **ppp1**. Terminar configuração com **CTRL-Z**:

`r1#conf t`  
`r1(config)#router rip`  
`r1(config-router)#redistribute connected`  
`r1(config-router)#network ppp0`  
`r1(config-router)#network ppp1`  
`r1(config-router)#^Z`  
`r1(config)#`

Comandos para configuração do RIP versão 2  
Exemplo **roteador R1** conectado a outros roteadores pelas **interfaces ppp0 (rede 10.0.0.0/30)** e **ppp1 (rede 10.0.0.4/30)**. Terminar configuração com **CTRL-Z**:

`r1#conf t`  
`r1(config)#router rip`  
`r1(config-router)#version 2`  
`r1(config-router)#redistribute connected`  
`r1(config-router)#network 10.0.0.0/30`  
`r1(config-router)#network 10.0.0.4/30`  
`r1(config-router)#^Z`  
`r1(config)#`

### Exercício 3

Use a rede do **exercício 1** para realizar os exercícios.

1.  Substitua no arquivo de configuração todos roteadores tipo **gateway** por tipo **router**;
2.  **Remova** todas as **rotas estáticas** do arquivo de configuração;
3.  Carregue a rede no **netkit** e verifique se o leiaute (**gráfico da rede**) está correto.
4.  Verifique a configuração dos PC com **ifconfig** e **route**;
5.  Teste conectividade com **ping** entre computadores pertencentes a mesma redes local e entre redes diferentes.
6.  Acesse o terminal **vtysh** de cada roteador e verifique a configuração das **interfaces** e das **tabelas de roteamento**:

`show interface eth0`  
`show interface ppp0`  
`show interface ppp1`  
`show ip route`

Ativação e teste do RIP versão 2  

1.  Ativar o **RIP versão 2** em cada roteador, conforme explicado acima. Preste atenção nas **redes** (**network**) onde as mensagens RIP devem ser propagadas, no caso devem ser as redes correspondentes as **interfaces ponto a ponto** de cada roteador (ppp0 e ppp1), com as respectivas **máscaras de rede** na notação com **/**;
2.  Verificar as **tabelas de roteamento** em cada um dos roteadores (show ip route);
3.  Realizar testes de conectividade com **ping** entre máquinas de redes diferentes;
4.  Derrubar uma **interface ponto a ponto** de um roteador. Para tal, você deve sair do terminal **vtysh** com **exit**. Derrubar a interface com **ifconfig ppp0 down**. Voltar ao terminal **vtysh** digitando **vtysh**;
5.  Esperar 30 segundos e verificar novamente as **tabelas de roteamento** dos roteadores (show ip route);
6.  Realizar novamente testes de conectividade com **ping** entre máquinas de redes diferentes;
7.  Realizar **tracetoure** entre máquinas de redes diferentes a fim de verificar os pacotes percorrendo a **nova rota** gerada pelo RIP.

Para entregar  
**PARTE 3**

1.  Anexar telas ilustrando as **tabelas de roteamento** de cada roteador antes da ativação do RIP (show ip route). Explicar as rotas presentes.
2.  Anexar telas ilustrando as **tabelas de roteamento** de cada roteador depois da ativação do RIP (show ip route). Explicar as rotas presentes.
3.  Anexar telas ilustrando a **conectividade** com ping entre as máquinas.
4.  Anexar telas ilustrando a **interface que foi derrubada**;
5.  Anexar telas ilustrando as **tabelas de roteamento** de cada roteador depois da reconfiguração do RIP (show ip route). Explicar as rotas presentes.
6.  Anexar telas do **traceroute** para mostrar a nova rota percorrida pelos pacotes depois que o RIP reconfigurou as rotas.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 17h51min de 9 de junho de 2015 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: <http://wiki.sj.ifsc.edu.br/wiki/index.php/Netkit2>

[^2]: <http://wiki.netkit.org/index.php/Main_Page>

[^3]:

[^4]:

[^5]:

[^6]:

[^7]: <http://www.dltec.com.br/blog/cisco/configuracao-basica-do-rip-versao-1-e-2-para-o-ccna/>
