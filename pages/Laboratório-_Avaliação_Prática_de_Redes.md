# Laboratório: Avaliação Prática de Redes

## Exercício Core Network

Considere que você dispõe do **bloco de endereços** (**dado pelo professor**) e precisa alocar endereços para montar a rede da figura abaixo conforme segue:

- Sub-rede 1: 32 IPs;
- Sub-rede 2: 32 IPs;
- Sub-rede 3: 16 IPs.

<a href="Arquivo:RedesCIDR2.png" class="wikilink" title="Arquivo:RedesCIDR2.png">Arquivo:RedesCIDR2.png</a>

Antes de iniciar a montagem da rede no **Core Network** escolha através da guia **Tools/IP Addresses** endereçamento IP de acordo com a faixa que recebeu do professor para facilitar o posterior ajuste dos endereços.

1.  Faça uma nova **alocação de endereços IP** para cada sub-rede (sub-rede 1, 2 e 3), segundo seus cálculos;
2.  Para os **enlaces ponto a ponto** (AB, AC e BC) utilize endereços com prefixo **10.0.0.0** e deixe que o próprio Core faça a alocação dos IP;
3.  Verifique a configuração do **endereçamento IP** de cada host com **ifconfig**.
4.  Verifique as **tabelas de roteamento** nos hosts e no roteador com o comando **route -n**;
5.  Teste conectividade com **ping** entre os *hosts* da mesma rede e de redes diferentes;
6.  Verifique as rotas seguidas pelos pacotes entre os *hosts* de redes diferentes com o comando **traceroute**.

Avaliação  
Montar o experimento no computador, testar o que foi pedido e em seguida chamar o professor para apresentar os seguintes itens:

1.  Apresentar a **distribuição dos endereços IP** utilizadas no exemplo, utilizando o comando **ifconfig** em cada host;
2.  Mostrar a partir de um host quem é o **roteador padrão** da rede em questão, utilizando o comando **route -n**;
3.  Explicar a **tabela de roteamento** do roteador;
4.  Explicar um teste de conectividade com **ping**;
5.  Explicar as rotas traçadas com **traceroute**.

## Captura de pacotes com Wireshark

Utilizar dois computadores e realizar o experimento apresentado em:

<a href="Laboratório:_Comparativo_TCP_e_UDP_utilizando_nc_e_wireshark" class="wikilink" title="Laboratório: Comparativo TCP e UDP utilizando nc e wireshark">Laboratório: Comparativo TCP e UDP utilizando nc e wireshark</a>  
Realizar somente os experimentos relativos a:

- Conexão TCP
- Comunicação UDP

<!-- -->

Avaliação  
Realizar as capturas de pacotes **TCP** e **UDP** solicitadas com o **Wireshark** e em seguida chamar o professor para apresentar os seguintes itens:

1.  Mostrar a captura de pacotes **TCP** e mostrar a **abertura de conexão** TCP, **troca de dados e reconhecimentos** e **encerramento de conexão** TCP;
2.  Mostrar a troca de dados **UDP** e mostrar as diferenças entre a troca de dados TCP.

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 15h35min de 5 de dezembro de 2017 (BRST)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>
