# Comutação de pacotes x Comutação de mensagens

Na **comutação de pacotes**, o computador que vai transmitir uma mensagem longa, fragmenta esta mensagem em pacotes menores antes de enviá-la pela rede. O receptor, por sua vez, reagrupa os pacotes recebidos para formar a mensagem original. Este processo é realizado visando melhorar a performance da rede.

Caso a mensagem original não fosse fragmentada, o processo seria chamada de **comutação de mensagens**.

## Taxa e Atraso de Transmissão

A **taxa de transmissão** de um enlace indica quantos **bits de dados** o enlace consegue transmitir por **unidade de tempo**. Normalmente é indicada em **bits por segundo** (**bps**).

O **atraso de transmissão** é o **tempo** (s) que um dado leva para ser transmitido sobre um enlace. É dado pelo quociente entre o **tamanho do dado** (bits) pela **taxa de transmissão** do enlace (bps).

`Atraso de transmissão = tamanho do pacote / taxa de transmissão (s)`

## Comutação de Mensagens

Na **comutação de mensagens** a informação original não é fragmentada, sendo transmitida de forma completa em cada enlace de comunicação.

Veja exemplo descrito por KUROSE (2010)[^1], onde uma mensagem de 7,5 Mbits é enviada entre um computador origem e um destino, passando por dois roteadores e três enlaces. Considere ainda que cada enlace tem taxa de transmissão de 1,5 Mbps, conforme a figura:

<a href="Arquivo:PacoteXMensagem1.png" class="wikilink" title="700px">700px</a>

- Note que em cada roteador a mensagem deve ser recebida de forma completa para poder ser retransmitida ao próximo destino.
- Note que o **atraso de transmissão** (s) para a mensagem ser transmitida em cada enlace é dado pelo quociente entre o **tamanho do pacote** (bits) e a **taxa de transmissão** (bps):

`Atraso`<sub>`Enlace`</sub>` = 7,5 M / 1,5 M = 5 s`

- O tempo total para a transmissão da mensagem da origem até o destino será a soma dos atrasos de transmissão em cada enlace:

`Atraso`<sub>`Total`</sub>` = 5 + 5 + 5 = 15 s`

## Comutação de Pacotes

Na **comutação de pacotes**, o computador que vai transmitir uma mensagem longa, fragmenta esta mensagem em pacotes menores antes de enviá-la pela rede. O receptor, por sua vez, reagrupa os pacotes recebidos para formar a mensagem original. Este processo é realizado visando melhorar a performance da rede.

Veja exemplo descrito por KUROSE (2010)[^2] a **mensagem original** de 7,5 M bits é fragmentada em 5000 pacotes com 1,5 K bits cada um.

<a href="Arquivo:PacoteXMensagem2.png" class="wikilink" title="700px">700px</a>

- Note que o **atraso de transmissão** (s) para cada pacote ser transmitid0 em cada enlace é dado pelo quociente entre o **tamanho do pacote** (bits) e a **taxa de transmissão** (bps):

`Atraso`<sub>`Enlace`</sub>` = 1,5 K / 1,5 M = 1 ms`

- Note que o pacote 1 levou apenas 3 ms para chegar ao destino.
- Note que após 5 s (5000 x 1 ms) o pacote 5000 já havia sido transmitido no primeiro enlace. E que após mais 2 ms chegou ao destino final.
- Portanto, note que toda a informação da mensagem original, ou seja, os 7,5 Mbits chegaram ao destino em apenas 5,002 ms. Veja que o **atraso de transmissão** foi quase três vezes menor que na comutação de mensagens.

**Qual a explicação para esta redução drástica no atraso de transmissão na comutação de pacotes?**

Exercícios  

1.  Sobre a técnica de **comutação de mensagens**, responda quanto tempo leva uma mensagem de 5 MBytes para ser transmitido em um enlace de 1 Mbps? (Lembre da diferença entre bit e Byte)
2.  Considere que o pacote da questão anterior deverá percorrer 5 enlaces idênticos ao da questão anterior (passando por 4 roteadores intermediários). Calcule o tempo total para a mensagem ser transmitida da origem ao destino.
3.  Considere que a mensagem anterior seja fragmentada em pacotes de 800 Bytes, calcule o tempo total de transmissão dos pacotes da origem ao destino.

### Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h18min de 27 de março de 2018 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: KUROSE, J.F; ROSS K. W. Redes de Computadores e a Internet: Uma abordagem *top-down*, São Paulo: Pearson, 2010.

[^2]:
