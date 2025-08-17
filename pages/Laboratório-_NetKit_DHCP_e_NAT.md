# Laboratório: NetKit DHCP e NAT

O **[Netkit2](http://wiki.sj.ifsc.edu.br/wiki/index.php/Netkit2)** [^1] é um ambiente para experimentos com redes de computadores desenvolvido no Câmpus São José, do IFSC, inspirado no **[Netkit](http://wiki.netkit.org/index.php/Main_Page)** [^2], desenvolvido pela Universidade de Roma, na Itália.

O Netkit2 se compõe de **máquinas virtuais Linux** (implementadas com kernel Linux UML – *User Mode Linux*), que funcionam como roteadores ou computadores e *switches* virtuais (UML *switch*) para interligar as máquinas virtuais. Para todos os efeitos, cada máquina virtual funciona como se fosse um computador real, possuindo uma ou mais interfaces de rede. Com esses recursos é possível criar redes de configurações arbitrárias para estudar protocolos de comunicação e serviços de rede [^3].

O **Netkit2** já está instalado no laboratório e pode ser iniciado com o comando:

`netkit2`

Caso deseja instalar o Netkit2 em outro computador Linux, consultar a referência [^4].

## Exercício 1: Teste do Netkit2

O *script* abaixo apresenta uma rede de computadores básica para ser testada no Netkit2 [^5]:

`pc1[type]=generic`  
`pc2[type]=generic`  
`pc1[eth0]=lan1:ip=192.168.0.1/24`  
`pc2[eth0]=lan1:ip=192.168.0.2/24`

A rede resultante é:

<a href="Arquivo:Netkit-lab1.png" class="wikilink" title="Arquivo:Netkit-lab1.png">Arquivo:Netkit-lab1.png</a>

1.  Edite um arquivo de texto e salve em uma pasta de trabalho (extensão .conf);
2.  Carregue o arquivo no NetKit2 com a opção *File -\> Load and Run*;
3.  Clique na opção *File -\> Graph* e veja a topologia da rede em execução;
4.  Verifique as configurações de cada **pc** com o comando **ifconfig**;
5.  Verifique a conectividade em rede entre os **pc** com o comando **ping**;
6.  Lance o **tcpdump** (ou **wireshark**) para capturar pacotes em um dos **pc**, e a partir do outro execute novamente o comando **ping** e verifique os pacotes **<a href="Protocolo_ICMP" class="wikilink" title="ICMP">ICMP</a>** capturados.

## Exercício 2: Redes interligadas por *gateway*

O *script* abaixo apresenta duas redes locais interligadas por um *gateway* [^6]:

`pc1[type]=generic`  
`pc2[type]=gateway`  
`pc3[type]=generic`  
`pc1[default_gateway]=192.168.0.2`  
`pc3[default_gateway]=192.168.1.1`  
` `  
`pc1[eth0]=lan0:ip=192.168.0.1/24`  
`pc2[eth0]=lan0:ip=192.168.0.2/24`  
`pc2[eth1]=lan1:ip=192.168.1.1/24`  
`pc3[eth0]=lan1:ip=192.168.1.2/24`

A rede resultante é:

<a href="Arquivo:Netkit-lab2.png" class="wikilink" title="Arquivo:Netkit-lab2.png">Arquivo:Netkit-lab2.png</a>

Parte 1  

1.  Edite e carregue o arquivo no NetKit2;
2.  Verifique as configurações de cada **pc** com o comando **ifconfig**;
3.  Verifique as **tabelas de roteamento** de cada **pc** com o comando **route -n**;
4.  Verifique a conectividade em rede entre os **pc** com o comando **ping**;
5.  Execute o comando **traceroute** entre os **pc** dos extremos da rede e verifique a rota seguida pelos pacotes;
6.  Lance o **tcpdump** (ou **wireshark**) para capturar pacotes em um dos pc de um extremo da rede, e a partir do outro execute novamente o comando **traceroute** e analise os pacotes capturados. Veja o funcionamento do **<a href="Protocolo_ICMP" class="wikilink" title="traceroute">traceroute</a>** para entender as mensagens trocadas e as mensagens de erro **ICMP** utilizadas.

Parte 2  
Inclua mais um ***gateway*** na rede, como mostra a figura:

<a href="Arquivo:Netkit-lab3.png" class="wikilink" title="Arquivo:Netkit-lab3.png">Arquivo:Netkit-lab3.png</a>

1.  Verifique as configurações de cada **pc** com o comando **ifconfig**;
2.  Verifique as **tabelas de roteamento** de cada **pc** com o comando **route -n**;
3.  Verifique a conectividade em rede entre os **pc** com o comando **ping**;
4.  Acrescente **rotas estáticas** com o comando **route -n**, de forma que todas as redes possam trocar pacotes (ver: [Rotas estáticas](http://wiki.foz.ifpr.edu.br/wiki/index.php/Rede_e_Roteamento#route));
5.  Verifique novamente as **tabelas de roteamento** com o comando **route -n**;
6.  Verifique a conectividade em rede entre os **pc** com o comando **ping**;
7.  Execute o comando **traceroute** entre os **pc** dos extremos da rede e verifique a rota seguida pelos pacotes.

## Exercício 3: Redes com *gateway* e servidor DHCP

Pesquise sobre a configuração de servidor DHCP no Netkit2 (ver [Usando DHCP no Netkit2](http://wiki.sj.ifsc.edu.br/wiki/index.php/Netkit2#Usando_DHCP))

1.  Modifique o *script* do exercício anterior, de forma que o **PC2** atue como **servidor DHCP** para a interface **eth0**.
2.  Inclua novos PCs configurados para **obter endereço IP dinamicamente** na rede 192.168.0.0/24.
3.  Verifique no arquivo **/etc/dhcp/dhcpd.conf** as configurações do servidor DHCP.
4.  Verifique no arquivo **/etc/default/isc-dhcp-server** as interfaces de rede que estão sendo providas por DHCP.
5.  Verifique no arquivo **/var/lib/dhcp/dhcpd.leases** a listagem dos IP alugados pelo servidor.
6.  Modifique o *script* acrescentando pelo menos dois novos PCs **sem configuração da interface de rede**, incluindo no script linhas do tipo: **pc4\[eth0\]=link**.
7.  Executar manualmente em um dos PC sem configuração da interface o comando **dhclient eth0** e verifique se obtem configuração de IP do DHCP.
8.  Ative **captura de pacotes** com **tcpdump** (ou **Wireshark**) na interface **eth0** do **PC2** (**Servidor DHCP**) e em seguida, em outro **computador sem interface configurada** execute o comando **dhclient eth0**. Em seguida verifique os pacotes capturados relativos a negociação do cliente com o servidor DHCP.

## Exercício 4: Redes com *gateway* e NAT

Pesquise sobre a configuração do roteador NAT no Netkit2 (ver [Usando NAT no Netkit2](http://wiki.sj.ifsc.edu.br/wiki/index.php/Netkit2#NAT))

1.  Modifique o *script* do exercício anterior, de forma que o **PC2** atue como **roteador NAT** para os pacotes saindo pela interface **eth1**, agora chamada de interface externa.
2.  Execute o comando **ping** entre computadores das diversas redes para testar conectividade.
3.  Ative em um PC externo ao NAT o **servidor apache** com o comando **service apache2 start** e inclua uma **página HTML** básica no arquivo **/var/www/index.html**.
4.  Acesse a **página Web** no servidor apache com o **navegador lynx**.
5.  Capturar pacotes com **tcpdump** (ou **Wireshark**) na interface de um PC externo ao roteador NAT e identifique o **tráfego HTTP** entre o **servidor apache** e o **navegador lynx**.
6.  Verifique nos pacotes capturados se o **roteador NAT** está mascarando os pacotes saindo pela sua interface externa.

## Exercício 5: Redes com *gateway* para acesso a Internet

Pesquise sobre a interligação das **redes virtuais** do Netkit2 com a **rede real** (ver [Uplink para rede real](http://wiki.sj.ifsc.edu.br/wiki/index.php/Netkit2#Uplink_para_a_rede_real))

1.  Modifique o *script* do exercício anterior, de forma que o **PC2** tenha um ***uplink*** para a **rede real**.
    1.  Execute o comando **ping** entre computadores da rede virtual e servidores da Internet.

## Avaliação

Elaborar relatório descrevendo os experimentos realizados, incluindo a criação de **rotas estáticas**, funcionamento do **servidor DHCP**, **roteador NAT** e acesso da **rede virtual** do NetKit à **rede real**:

- Incluir figuras das topologias de rede, telas mostrando as configurações e saídas dos comandos (p.ex. ifconfig, ping, traceroute, route, etc).

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 16h49min de 25 de novembro de 2015 (BRST)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: <http://wiki.sj.ifsc.edu.br/wiki/index.php/Netkit2>

[^2]: <http://wiki.netkit.org/index.php/Main_Page>

[^3]:

[^4]:

[^5]:

[^6]:
