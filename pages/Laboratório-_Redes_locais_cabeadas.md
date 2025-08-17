# Laboratório: Cabeamento de rede

Objetivos  
Conhecer os padrões mais utilizados para cabeamento de rede e motar um cabo de rede.

<!-- -->

Equipamentos físicos para montar uma rede  
Os componentes básicos do **hardware de rede** para montagem de **rede local Ethernet** cabeada são as **placas de rede** em cada computador, os **cabos de rede e conectores**, e os equipamentos de comunicação, como ***hubs**'' ou***switches**''.

<a href="Arquivo:RedeEthernet.png" class="wikilink" title=" 400px"> 400px</a>

## Cabeamento para Redes locais Ethernet[^1]

As redes locais **Ethernet** são padronizadas pelo **IEEE** como **802.3** e são as tecnologias de rede mais utilizadas atualmente.

Principais tecnologias de redes locais Ethernet  

- Ethernet 10Mbps: Transmite a 10 Mbits/s (Cabeamento com cabos coaxiais) (**obsoleta**)
- Fast Ethernet: Transmite a 100 Mbits/s. (Cabeamento com cabos Categoria 5)
- Gibabit Ethernet: Transmite a 1 Gbits/s. (Cabeamento com cabos Categoria 6)
- 10 Gibabit Ethernet: Transmite a 10 Gbits/s. (Cabeamento com cabos Categoria 6)

A tecnologia mais barata e mais usada atualmente é a **Ethernet 100Mbps**.

### Cabos e conectores

Para redes Ethernet 100 Mbps, o padrão mínimo para cabeamento de rede deve ser o **cabo categoria 5** ou superior[^2]:

- Categoria 5: Requisito mínimo para redes Ethernet 100 Mbps;
- Categoria 5e: Versão aperfeiçoada da categoria 5, com especificações para reduzir a interferência entre os cabos e a perda de sinal;
- Categoria 6: Requisito para redes Gigabit Ethernet.

<a href="Arquivo:CaboCat5.jpg" class="wikilink" title=" 300px"> 300px</a>

Os cabos de rede possuem **4 pares trançados de fios** e necessitam como terminação de um **conector RJ45**.

<a href="Arquivo:RJ45.jpg" class="wikilink" title=" 150px"> 150px</a>

Para montagem do cabo, é necessário ferramentas para **descascar o cabo** e um **alicate para crimpar** o cada fio no conector.

<a href="Arquivo:AlicateCrimpar.jpg" class="wikilink" title=" 300px"> 300px</a>

### Padrões de montagens dos conectores

Existem dois padrões para montagem dos conectores RJ45, o padrão EIA 568A e EIA 568B.

Não há diferença entre os padrões, entretanto, toda a instalação deve utilizar o mesmo padrão. A maioria das instalações utiliza o EIA 568B.

<a href="Arquivo:EIA568.gif" class="wikilink" title=" 400px"> 400px</a>

Para a montagem do conector RJ45 com o padrão EIA 568B, os fios devem ser encaixados na ordem de numeração, com a trava do conector virada para baixo.

<a href="Arquivo:MontagemRJ45-568B.png" class="wikilink" title=" 300px"> 300px</a>

Depois de encaixados os fios no conector deve-se usar o alicate para crimpar os conectores, fazendo o contato elétrico entre cada fio do cabo e os terminais do conector.

<a href="Arquivo:Crimpar.jpg" class="wikilink" title=" 300px"> 300px</a>

#### Cabos crossover

São usados para conectar diretamente dois computadores, sem usar *hub* ou *switch*.

Para montar um cabo **crossover** deve usar em uma ponta o padrão **EIA 568A** e na outra o padrão **EIA 568B**.

<a href="Arquivo:Crossover.png" class="wikilink" title=" 300px"> 300px</a>

#### Teste do cabo

Depois da montagem o cabo deve ser testado para verificar se todas as conexões elétricas estão funcionando, para isto, é necessário um **testador de cabo**.

<a href="Arquivo:TestadorCabo.jpg" class="wikilink" title=" 300px"> 300px</a>

Vídeo  
Paulo Moraes: Como montar um cabo de rede.

{{#ev:youtube\|KWrjBnTZpnU}}

#### Exercício 1

Montar um cabo de rede com 1m de comprimento, segundo o padrão EIA 569B. Em seguida testar o cabo com o testador de cabo.

## Configuração e teste dos equipamentos de rede[^3]

A montagem de uma **rede local Ethernet** necessita de **equipamentos físicos**, como **placas de rede** em cada computador, **cabos de rede e conectores**, e equipamentos de comunicação, como ***hubs**'' ou***switches**''.

<a href="Arquivo:RedeEthernet.png" class="wikilink" title=" 400px"> 400px</a>

<a href="Arquivo:Switch.jpeg" class="wikilink" title=" 300px"> 300px</a>

Além da parte física, é necessário a **configuração lógica** da rede, especificando e configurando os **protocolos de comunicação** a serem utilizados.

### Parâmetros para configuração dos protocolos da arquitetura Internet, TCP/IP

<a href="Endereçamento_IP" class="wikilink" title="Endereçamento IP">Endereçamento IP</a>  
Os **endereços IP** identificam cada computador, ou *host*, da rede. Cada computador da rede local deve ter um endereço IP específico, mas todos devem pertencer a mesma rede, o que é definido pela **máscara de rede**.

<!-- -->

Máscara de rede  
Permite definir a parte do endereço IP que identifica a rede, bem como seu tamanho.

<!-- -->

Roteador padrão (*Default gateway*)  
Identifica o endereço da máquina da rede local que está configurada para rotear pacotes para a Internet.

<!-- -->

Servidor DNS  
Identifica o endereço da máquina que está habilitada para traduzir **nomes de domínio**, como www.ifpr.edu.br, em **endereços IP**.

#### Exercício 2

Em equipe, montar uma rede local, usando um switch de 8 portas e realizar a configuração do TCP/IP para que as máquinas se comuniquem.

- Usar **endereços IP privados** na faixa 192.168.x.y e máscara 255.255.255.0, diferenciando cada rede local que for montada pelo terceiro byte do IP;

` sudo ifconfig eth0 192.168.y.x netmask 255.255.255.0`

  
As máquinas da mesma **rede local** devem ter o mesmo y e cada uma um x diferente.

- Testar a conectividade em rede com **ping**.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 17h45min de 13 de setembro de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: MORIMOTO, C. E. Redes, Guia Prático 2ª Ed., 2008. <http://www.hardware.com.br/livros/hardware/pouco-sobre-redes.html>

[^2]: MORIMOTO, C. E. Redes, Guia Prático 2ª Ed., 2008. <http://www.hardware.com.br/livros/redes/categorias-cabos.html>

[^3]: MORIMOTO, C. E. Hardware, O Guia Definitivo, 2007. <http://www.hardware.com.br/livros/hardware/configuracao-rede.html>
