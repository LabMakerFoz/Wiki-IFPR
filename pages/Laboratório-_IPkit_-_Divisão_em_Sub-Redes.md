# Laboratório: IPkit - Divisão em Sub-Redes

O **IPkit** é um software de **Simulação de Roteamento IP**[^1]. Utilizaremos uma versão traduzida para o português [^2] .

[Link para acesso ao simulador IPkit](http://tele.sj.ifsc.edu.br/~msobral/IER/ipkit/)  
O IPkit é uma aplicação Java.

- Verifique as instruções sobre como utilizar o simulador;
- Clique com o botão direito para inserir dispositivos na rede.

## Objetivos

Experimentar em uma rede simulada o processo de **distribuição de endereços IP em sub-redes**.

Construir **tabelas de roteamento** e simular o **encaminhamento de pacotes** em uma rede IP.

## Exercício 1

Montar no IPkit a rede experimental da figura: <a href="Arquivo:Rede.png" class="wikilink" title="Arquivo:Rede.png">Arquivo:Rede.png</a>

- Use endereçamento Classe C para cada rede;
- Use endereços IP privados (192.168.x.y);
- Insira pelo menos dois hosts para cada rede;
- Defina a tabela de roteamento para o roteador;
- Envie pacotes entre os *hosts* da mesma rede e de redes diferentes;
- Observe o TTL (*time to live*) de cada pacote quando passa pelo roteador.

## Exercício 2

Montar no IPkit a rede experimental mostrada na figura: <a href="Arquivo:Sub-redes.png" class="wikilink" title="Arquivo:Sub-redes.png">Arquivo:Sub-redes.png</a>

- Considere que você dispõe do bloco de endereços IP 192.168.10.0/24 para ser utilizado no endereçamento da rede experimental;
- Faça uma alocação de endereços IP para cada sub-rede (rede 1, 2 e 3), alocando para a sub-rede 1 32 IPs e nas sub-redes 2 e 3 alocar 16 IPs;
- Faça também uma alocação de endereços IP para cada enlace ponto a ponto (rede AB, AC e AB).
- Defina as tabelas de roteamento entre para que os *hosts* possam trocar pacotes entre si.
- Envie pacotes entre os *hosts*.

Avaliação  
Prepare um **relatório** (em duplas) com os seguintes itens:

1.  **Imagem da rede** montada no IPkit, a qual pode ser obtida o comando Alt-PrntScrn.
2.  Descrição da **distribuição dos endereços IP** utilizadas no exemplo.
3.  Descrição das **tabelas de roteamento** definidas para cada roteador.
4.  Descrição dos possíveis problemas verificados no **envio de datagramas** entre hosts e a forma como foram resolvidos.
5.  Descrição do comportamento do campo TTL presente nos datagramas IP durante a passagem em cada roteador.

## Exercício 3

Montar no IPkit a rede experimental mostrada na figura: <a href="Arquivo:RedesCIDR3.png" class="wikilink" title="Arquivo:RedesCIDR3.png">Arquivo:RedesCIDR3.png</a>

Alocação de endereços IP:

- Rede 1: 172.16.0.0/16
- Rede 2: 172.17.0.0/24
- Rede 3: 172.17.1.0/24, o qual deve ser dividido para as sub-redes 3.1, 3.2 e 3.3, cada uma com 64 IPs (62 IP para *hosts* + ID rede e *broadcast*)
- Defina as tabelas de roteamento entre para que os *hosts* possam trocar pacotes entre si.
- Envie pacotes entre os *hosts*.

Relatório  
Prepare um relatório (em duplas) com os seguintes itens:

1.  **Imagem da rede** montada no IPkit, a qual pode ser obtida o comando Alt-PrntScrn.
2.  Descrição da **distribuição dos endereços IP** para cada rede do exemplo, incluindo:
    - **Endereço de rede** de cada sub-rede;
    - **Máscara de rede** de cada sub-rede;
    - **Faixa de endereços** de *host* possíveis para cada sub-rede;
    - **Endereço de *broadcast*** de cada sub-rede.
3.  Descrição das **tabelas de roteamento** definidas para cada roteador.
4.  Descrição dos possíveis problemas verificados no **envio de datagramas** entre hosts e a forma como foram resolvidos.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h38min de 12 de junho de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: MESSERMAN, G; KARNI, G.; BRAUM, U. IP Routing Simulation. Written for Protocols and Computer Networks course, given by Dr. Debby Koren, at Tel Aviv University.[1](http://cisx1.uma.maine.edu/~wbackman/cis341/sims/ip/ip.html)

[^2]: SOBRAL, M. M. IPkit traduzido para o português, IFSC, São José, SC.[2](http://tele.sj.ifsc.edu.br/~msobral/IER/ipkit/)
