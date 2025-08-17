# Protocolo ARP

<a href="Protocolo_ARP" class="wikilink" title="Protocolo ARP">Protocolo ARP</a>  

## Laboratório para verificar tabela arp

### Comando ifconfig

Executar o comando **ifconfig** e verificar o endereçamento IP e endereço físico de cada interface de rede:

### Comando arp

Executar o comando **arp**, com parâmetro **-a**, e verificar a tabela ARP que relacona endereços IP e endereços físicos. Esta tabela é dinâmica e fica armazenada em uma **memória *cache*** associada a interface de rede.

`evandrocantu@NBP-EVANDRO:~$ arp -a`  
`? (192.168.1.1) em 00:1c:f0:52:05:4a [ether] em wlan0`

  
O exemplo mostra o comando executado na máquina do professor, mostrando o endereço IP do roteador padrão da rede e seu endereço físico.

#### Exercícios

1.  Verifique a configuração de rede da máquina com o comando **ifconfig**.
2.  Verifique a **tabela ARP** com o comando **arp**.
3.  Execute o comando **ping** em uma máquina da rede local, não constante da **tabela ARP**. Em seguida execute novamente o comando **arp** para verificar se a nova máquina entrou na tabela.
4.  Verifique se o IP do **roteador padrão** está na **tabela ARP**. Se não estiver, acesse algum site da Internet e verifique novamente a tabela ARP.
5.  Verifique novamente a **tabela ARP** após um certo tempo e veja se a mesma é modificada.

### Captura de pacotes ARP com Wireshark

Execute o **<a href="wireshark" class="wikilink" title="wireshark">wireshark</a>** para capturar pacotes na rede local, incluindo pacotes ARP.

#### Exercícios

1.  Execute o **wireshark** para capturar pacotes ARP.
2.  Verifique a **tabela ARP** com o comando **arp**.
3.  Execute o comando **ping** em uma máquina da rede local, não constante da **tabela ARP**. Em seguida execute novamente o comando **arp** para verificar se a nova máquina entrou na tabela.
4.  Verifique os **pacotes ARP** capturados pelo **wireshark**.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 11h45min de 6 de outubro de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>
