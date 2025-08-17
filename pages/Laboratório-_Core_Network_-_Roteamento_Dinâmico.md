# Laboratório: Core Network - Roteamento Dinâmico

O emulador **Core Network** (*Common Open Research Emulator*) é uma ferramenta que permite construir **redes virtuais**.

Diferente dos simuladores, as **redes virtuais funcionam como redes reais**, rodando protocolos e serviços reais. Também é possível conectar as redes virtuais a redes e roteadores físicos [^1].

## Objetivos

O objetivo deste experimento é observar a construção dinâmica das **tabelas roteamento** em uma rede com vários roteadores. No emulador do Core as tabelas são construídas pelo **Protocolo de Roteamento OSPF**.

## Exercício 1 - Rede com vários roteadores

Montar no **Core** a rede experimental mostrada na figura:

<a href="Arquivo:Sub-redes.png" class="wikilink" title="Arquivo:Sub-redes.png">Arquivo:Sub-redes.png</a>

Montagem da rede  

1.  Utilizar os seguintes componentes:
    - **network-layer virtual nodes**: router e host
    - **link-layer nodes**: ethernet hub
2.  Antes de iniciar a montagem da rede escolha através da guia **Tools/IP Addresses** endereçamento IP do tipo **192.168.0.0**.
3.  Usar somente endereçamento **IPv4** para cada rede (remover endereços **IPv6**).

Teste de conectividade com ping  

1.  Envie pacotes **ping** entre os *hosts* da mesma rede e de redes diferentes. Verifique se há conectividade entre as redes das extremidades dos roteadores (Rede 1, Rede 2 e Rede 3).

Roteamento  

1.  Verifique a **tabela de roteamento** nos **hosts** com o comando **route -n**;
2.  Verifique a **tabela de roteamento** nos três **roteador** com o comando **route -n**. Analise todas as rotas disponíveis e verifique como é realizado o acesso a cada rede;
3.  Use o comando **traceroute** para verificar a **rota** percorrida pelos pacotes entre *hosts* situados nas redes das extremidades dos roteadores.

Tarefa - Parte I  

1.  Ilustrar o relatório a imagem da rede em teste;
2.  Apresentar as tabelas de roteamento dos três roteadores e explicar a rota tomada por cada pacote que circula entre as redes conectadas nas extremidades dos roteadores.

## Exercício 2 - Funcionamento do roteamento dinâmico

O objetivo deste experimento é a observação do funcionamento do **roteamento dinâmico** em redes de computadores. No caso do Core, está ativo o **Protocolo de Roteamento OSPF**.

Neste exercício será utilizada a mesma rede montada no Exercício 2.

Roteamento dinâmico  
Verificação das **rotas default** e das **rotas dinâmicas** construídas pelo **protocolo de roteamento OSPF**:

1.  Após a montagem completa da rede (Exercício 2), cliclar em **stop the session**. Com a rede parada, verifique a configuração de cada sub-rede anotando as seguintes informações:
    - Nome de cada **roteador** e quais **sub-redes** estão diretamente conectadas a eles.
    - Escolha um **roteador** para observar a **construção dinâmica** da **tabela de roteamento**.
2.  Clique em **start the session** e imediatamente abra um terminal do roteador escolhido para observar as rotas e execute o comando **route -n**: Anote as rotas apresentadas.
3.  Em seguida, execute continuamente o comando **route -n** (use a tecla **seta para cima**) a fim de verificar as mudanças na tabela de roteamento, anotando cada nova rota que aparece.
    - Observação: Os **protocolos de roteamento** levam alguns segundos para construírem as rotas.
4.  Depois que a **tabela de roteamento** se estabilizar, testar a **conectividade** entre as diversas usando o comando **ping**.
5.  Trace as **rotas** entre as diversas redes usando o comando **traceroute**.
    - Anote todos os dados!
    - Caso não conseguir observar/anotar as mudanças, pare a rede com **stop the session** e reinicie novamente.

Emulação de queda de enlace  
Simulação de **queda de enlace** e verificação das novas **rotas construídas dinamicamente** pelo **protocolo de roteamento OSPF**:

1.  Pare a rede com **stop the session** e elimine o enlace correspondente a sub-rede AB.
    - Escolha o **roteador A** para observar a **construção dinâmica** da **tabela de roteamento**.
2.  Clique em **start the session** e imediatamente abra um terminal do roteador escolhido para observar as rotas e execute o comando **route -n**: Anote as rotas apresentadas.
3.  Em seguida, execute continuamente o comando **route -n** (use a tecla **seta para cima**) a fim de verificar as mudanças na tabela de roteamento, anotando cada nova rota que aparece.
4.  Depois que a **tabela de roteamento** se estabilizar, testar a **conectividade** entre as diversas usando o comando **ping**.
5.  Trace as **rotas** entre as diversas redes usando o comando **traceroute**.

Tarefa - Parte II  

1.  Pesquisar sobre **protocolo de roteamento dinâmico**;
2.  Ilustrar o relatório a imagem da rede em teste;
3.  Explicar a **construção dinâmica das tabelas de roteamento**, indicando a sequência de criação das rotas nos dois casos emulados;
4.  Explicar as **rotas** que os pacotes seguiram entre as redes nos dois casos;
5.  Mostrar a **diferença do percurso** tomado pelos pacotes em cada rede emulada.
6.  Incluir no relatório a imagem de cada rede em teste.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h00min de 30 de outubro de 2015 (BRST)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: <http://downloads.pf.itd.nrl.navy.mil/docs/core/core-html/>
