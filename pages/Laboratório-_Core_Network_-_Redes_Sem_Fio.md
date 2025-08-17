# Laboratório: Core Network - Redes Sem Fio

O emulador **Core Network** (*Common Open Research Emulator*) é uma ferramenta que permite construir **redes virtuais**.

Diferente dos simuladores, as **redes virtuais funcionam como redes reais**, rodando protocolos e serviços reais. Também é possível conectar as redes virtuais a redes e roteadores físicos [^1].

## Exercício - Rede Local Sem Fio

O objetivo deste experimento é a observação do funcionamento de **redes locais sem fio** interligadas a outras redes.

Montar no **Core** a rede experimental mostrada na figura:

<a href="Arquivo:RedeSemFio.png" class="wikilink" title="Arquivo:RedeSemFio.png">Arquivo:RedeSemFio.png</a>

Montagem da rede  

1.  Antes de iniciar a montagem da rede no **Core**, escolha através da guia **Tools/IP Addresses** endereçamento IP do tipo **172.16.0.0**.
2.  Inicie a rede incluindo dois **roteadores**.
3.  No primeiro **roteador** conecte uma rede cabeada com **hub** e alguns **hosts**.
4.  **Conecte** os dois **roteadores**.
5.  Inclua uma **rede sem fio** no ambiente e configure seu **endereçamento IP** para funcionar com a **máscara de rede** /24 (255.255.255.0).
6.  Associe a **rede sem fio** ao **roteador**, logo uma antena vai aparecer junto ao ícone do roteador.
7.  Associe os **laptops** a **rede sem fio**.

Emulação da rede  

1.  Coloque a rede em execução com o comando **start the session**.
2.  Inspecione cada **nó** da rede através do aplicativo **lupa**, selecionando **ifconfig**. Uma vez selecionado o comando com a lupa basta passar o mouse sobre o nó para ver as configurações das **interfaces de rede**.
3.  Inspecione cada **nó** da rede através do aplicativo **lupa**, selecionando **IPv4 routes**. Verifique as **tabelas de roteamento** de cada nó.
4.  Teste **conectividade** entre nós de diferentes redes usando **ping**.
5.  Movimente os **laptops** em torno do raio de ação do **roteador sem fio** e verifique quando o nó perde conectividade com hosts da rede cabeada. Use o **ping** para testar a conectividade.
6.  Verifique se quando o **laptop** está **fora do alcance do roteador**, mas no alcance de outro **laptop** se há algum tipo de conectividade.

### Relatório

Escrever relatório sobre o experimento realizado, incluindo os seguintes tópicos:

1.  Descrever o experimento que será realizado e os objetivos do mesmo.
2.  Ilustrar o relatório a **imagem da rede** em teste.
3.  Ilustrar e descrever as **tabelas de roteamento** em cada um dos roteadores da rede em teste.
4.  Ilustrar e descrever os teste de conectividade com **ping** realizados entre os hosts das diferentes redes.
5.  Explicar como fica a conectividade de um **laptop** que se movimenta fora do **raio de alcance** do **roteador sem fio** e dentro do alcance de outros **laptops**.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h00min de 30 de outubro de 2015 (BRST)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: <http://downloads.pf.itd.nrl.navy.mil/docs/core/core-html/>
