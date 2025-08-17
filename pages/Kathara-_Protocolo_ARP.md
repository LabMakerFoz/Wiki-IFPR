# Kathará

## Laboratório: Protocolo ARP

<a href="Protocolo_ARP" class="wikilink" title="Protocolo ARP">Protocolo ARP</a>  
Alguns fundamentos sobre o protocolo ARP.

Laboratório para verificação do funcionamento do protocolo ARP utilizando de **redes interligadas por roteador** (Referência: [^1]):

<a href="Arquivo:Kathara-ARP.png" class="wikilink" title="Arquivo:Kathara-ARP.png">Arquivo:Kathara-ARP.png</a>

Hierarquia de arquivos e diretórios para os scripts do laboratório  

`lab.conf`  
`pc1.startup`  
`pc2.startup`  
`pc3.startup`  
`r1.startup`  
`pc1/`  
`pc2/`  
`pc3/`  
`r1/`

Conteúdo dos arquivos:

`lab.conf`  
`  pc1[0]=A`  
`  pc2[0]=A`  
`  r1[0]=A`  
`  r1[1]=B`  
`  pc3[0]=B`

`pc1.startup`  
`  ifconfig eth0 192.168.0.1/24 up`  
`  route add default gw 192.168.0.3 dev eth0`

`pc2.startup`  
`  ifconfig eth0 192.168.0.2/24 up`  
`  route add default gw 192.168.0.3 dev eth0`

`pc3.startup`  
`  ifconfig eth0 192.168.1.10/24 up`  
`  route add default gw 192.168.1.20 dev eth0`

`r1.startup`  
`  ifconfig eth0 192.168.0.3/24 up`  
`  ifconfig eth1 192.168.1.20/24 up`

Iniciar rede do laboratório:

`kathara lstart`

### Protocolo ARP

O **protocolo ARP**, permite encontrar o endereço físico a partir do endereço IP da máquina alvo. Para tal, o protocolo usa um mecanismo de difusão (*broadcast*) na rede local, enviando uma solicitação a todas as máquinas da rede, sendo que a máquina alvo responde indicando o par **endereço IP/endereço físico**.

Memória *cache*  
Para melhorar a performance do protocolo ARP, cada máquina possui uma **memória *cache*** com as últimas consultas realizadas, evitando múltiplos *broadcasts*.

Verificação da tabela **arp** (memória *cache*) no pc1:

`arp`

**Ping** em dispositivo da mesma rede:

`ping 192.168.0.2`

Verificação da tabela **arp** no pc1:

`arp`

**Ping** em dispositivo da outra rede:

`ping 192.168.2.10`

Verificação da tabela **arp** no pc1:

`arp`

### Captura de pacotes ARP

Reiniciar a rede para limpar as tabelas ARP:

`kathara lclean`  
`kathara lstart`

Inicie captura de **pacotes arp** no pc2 usando **tcpdump** e salvando em arquivo:

`tcpdump arp -e -i eth0 -w /hosthome/arp.ncap`

  
arp: captura somente pacotes arp

-e: mostra endereço físico do enlace

Teste a conectividade com **ping** pc1 -\> pc2 (mesma rede):

  
No pc1 execute:

`ping 192.168.0.2`

  
Verifique no pc2 as mensagens arp trocadas e as correspondências entre endereços IP e endereços físicos.

Teste a conectividade com **ping** pc1 -\> pc3 (outra rede):

  
No pc1 execute:

`ping 192.168.1.10`

  
Verifique no pc2 as mensagens arp trocadas e as correspondências entre endereços IP e endereços físicos.

Verifique no roteador r1 e nos demais dispositivos as tabelas **arp**.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 14h50min de 25 de fevereiro de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: <https://github.com/KatharaFramework/Kathara-Labs/blob/master/Basic%20Topics/ARP/005-kathara-lab_arp.pdf>
