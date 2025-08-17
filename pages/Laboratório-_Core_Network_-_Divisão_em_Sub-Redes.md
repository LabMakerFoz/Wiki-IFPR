# Laboratório: Core Network - Divisão em Sub-Redes

O emulador **Core Network** (*Common Open Research Emulator*) é uma ferramenta que permite construir **redes virtuais**.

Diferente dos simuladores, as **redes virtuais funcionam como redes reais**, rodando protocolos e serviços reais. Também é possível conectar as redes virtuais a redes e roteadores físicos [^1].

Instalação do Core  
No Ubuntu o **Core Network** pode ser instalado diretamente com o comando:

`sudo apt-get install core-network`

Execução do Core  
Procure o aplicativo Core ou use no terminal o comando:

`core`

## Exercício 1 - Rede Básica

Montar no **Core Network** a rede experimental da figura:

<a href="Arquivo:RedesComRoteador.png" class="wikilink" title="Arquivo:RedesComRoteador.png">Arquivo:RedesComRoteador.png</a>

Montagem da rede  

1.  Utilizar os seguintes componentes:
    - **network-layer virtual nodes**: router e host
    - **link-layer nodes**: ethernet hub
2.  Antes de iniciar a montagem da rede escolha através da guia **Tools/IP Addresses** endereçamento IP do tipo **192.168.0.0**.
3.  Usar somente endereçamento **IPv4** para cada rede (remover endereços **IPv6**);
4.  Inserir em cada **rede local** pelo menos três *hosts*.

Emulação da rede e verificação do endereçamento IP  

1.  Clique em **start the section** para iniciar a execução da rede;
2.  Abra um terminal para cada **host** e para o **roteador** e verifique a configuração do **endereçamento IP** com **ifconfig**;

Teste de conectividade com ping  

1.  Envie pacotes **ping** entre os *hosts* da mesma rede e de redes diferentes. Verifique o parâmetro **ttl** para os ping na mesma rede e de redes diferentes;

Roteamento  

1.  Verifique a **tabela de roteamento** nos **hosts** com o comando **route -n**;
2.  Verifique a **tabela de roteamento** no **roteador** com o comando **route -n**;
3.  Use o comando **traceroute** para verificar a **rota** percorrida pelos pacotes entre *hosts* da mesma rede e de redes diferentes.

## Exercício 2 - Divisão de IP em sub-redes

Montar no **Core** a rede experimental mostrada na figura: <a href="Arquivo:RedesCIDR1.png" class="wikilink" title="Arquivo:RedesCIDR1.png">Arquivo:RedesCIDR1.png</a>

Considere que você dispõe do bloco de endereços IP 192.168.0.0/24 e precisa alocar endereços para montar a rede mostrada na figura conforme segue:

- Sub-rede 1: 32 IPs;
- Sub-rede 2: 16 IPs;
- Sub-rede 3: 8 IPs.

  
Ver [exercício sobre sub-redes](http://wiki.foz.ifpr.edu.br/wiki/index.php/CIDR#Exerc.C3.ADcios_Sub-Redes).

1.  Faça uma **alocação de endereços IP** para cada sub-rede (sub-rede 1, 2 e 3);
2.  Verifique as **tabelas de roteamento** em todos os roteadores com o comando **route -n**;
3.  Abra um terminal em hosts de redes diferentes e verifique a configuração do **endereçamento IP** com **ifconfig**.
4.  Envie pacotes **ping** entre os *hosts* da mesma rede e de redes diferentes para testar conectividade;
5.  Execute o comando **traceroute** entre os *hosts* de redes diferentes e verifique a rota seguida pelos pacotes.

Tarefa - Parte I  
Prepare um **relatório** (em duplas) com os seguintes itens:

1.  Imagem da rede montada no **Core**;
2.  Descrição da **distribuição dos endereços IP** utilizadas no exemplo;
3.  Descrição das **tabelas de roteamento** definidas para cada roteador:
    - Para entender as tabelas de roteamento veja o link <a href="Roteamento_IP" class="wikilink" title="Roteamento IP">Roteamento IP</a>
4.  Ilustração e descrição do teste de conectividade com **ping** e rotas com **traceroute**.

## Exercício 3 - Divisão de IP em sub-redes e roteamento

Montar no **Core** a rede experimental mostrada na figura: <a href="Arquivo:RedesCIDR3.png" class="wikilink" title="Arquivo:RedesCIDR3.png">Arquivo:RedesCIDR3.png</a>

Alocação de endereços IP:

- Rede 1: 172.16.0.0/24
- Rede 2: 172.16.1.0/24
- Rede 3: 172.16.2.0/24, o qual deve ser dividido para as sub-redes 3.1, 3.2 e 3.3, cada uma com 64 IPs (62 IP para *hosts* + ID rede e *broadcast*)

1.  Abra um terminal em um **host** de cada sub-rede e verifique o **endereçamento IP** com o comando **ifconfig**.
2.  Abra um terminal em cada **roteador** e verifique as **tabelas de roteamento** com o comando **route -n**;
3.  Envie pacotes **ping** entre os *hosts* da mesma sub-rede e para todas as demais sub-redes para testar conectividade;
4.  Execute o comando **traceroute** entre os *hosts* de redes diferentes e verifique a **rota** seguida pelos pacotes.

Tarefa - Parte II  
Prepare um **relatório** (em duplas) com os seguintes itens:

1.  Imagem da rede montada no **Core**;
2.  Descrição da **distribuição dos endereços IP** utilizadas no exemplo, incluindo para a sub-rede 3 os seguintes itens:
    - **Endereço de rede** de cada sub-rede;
    - **Máscara de rede** de cada sub-rede;
    - **Faixa de endereços** de *host* possíveis para cada sub-rede;
    - **Endereço de *broadcast*** de cada sub-rede.
3.  Descrição das **tabelas de roteamento** definidas para cada **roteador**:
    - Para entender as tabelas de roteamento veja o link <a href="Roteamento_IP" class="wikilink" title="Roteamento IP">Roteamento IP</a>
4.  Ilustração e descrição do teste de conectividade com **ping** e rotas com **traceroute**.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h00min de 30 de outubro de 2015 (BRST)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: <http://downloads.pf.itd.nrl.navy.mil/docs/core/core-html/>
