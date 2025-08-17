# Contadores Assíncronos

Os **contadores assíncronos**[^1] são **contadores binários** construídos a partir do encadeamento de **<a href="Flip-Flops" class="wikilink" title="Flip-Flops">Flip-Flops</a>**.

Um exemplo simples de circuito **contador assíncrono** de quatro bits é mostrado na figura. O circuito é formado por quatro flip-flops JK, todos com as entradas J=K=1, o que fará com que comutem a saída a cada vez que o pulso na entrada de *clock* passar de ALTO para BAIXO.

Exemplo  
Contador assíncrono e divisor de frequência de 4 bits.

<a href="Arquivo:ContadorAssincrono.png" class="wikilink" title=" 700px"> 700px</a>

Este circuito é dito **assíncrono**, pois os pulsos do *clock* são aplicados apenas na entrada do primeiro flip-flop. A saída Q<sub>0</sub> do primeiro flip-flop está conectada a entrada de *clock* do segundo flip-flop, e assim por diante.

Exercício  

Considere que na entrada de *clock* do primeiro flip-flop é aplicado uma onda quadrada de frequência **f**:

<a href="Arquivo:DiagramaTempo7.png" class="wikilink" title=" 700px"> 700px</a>

1.  Construa as formas de onda das saídas Q<sub>0</sub>, Q<sub>1</sub>, Q<sub>2</sub> e Q<sub>3</sub> do circuito.
2.  Verifique a frequência das ondas resultantes nas saídas Q<sub>0</sub>, Q<sub>1</sub>, Q<sub>2</sub> e Q<sub>3</sub>.
3.  Verifique a contagem binária produzida nas saídas Q<sub>0</sub>, Q<sub>1</sub>, Q<sub>2</sub> e Q<sub>3</sub>.

## Contadores Síncronos

Nos **contadores síncronos** todos os flip-flops são acionados paralelamente pelo mesmo pulso de *clock*, o que elimina possíveis atrasos de propagação entre as contagens dos flip-flops.

Os circuitos de contadores síncronos utilizam flip-flops combinados com portas lógicas. São circuitos mais elaborados que os contadores assíncronos e não estudaremos neste momento.

Pesquisa  

1.  Pesquise sobre o circuito contador binário síncrono.
2.  Pesquise os contadores disponíveis nos [Circuitos Integrados da série 7400](http://pt.wikipedia.org/wiki/Anexo:Lista_dos_circuitos_integrados_da_s%C3%A9rie_7400)

## Laboratório e Exercícios de Simulação

Para este laboratório será utilizado o <a href="Simulador_de_Circuitos_Lógicos_-_Logisim" class="wikilink" title="Simulador de Circuitos Lógicos - Logisim">Simulador de Circuitos Lógicos - Logisim</a>  
Veja no *link* as instruções para *download* e instalação do programa.

### Contadores

1.  Construa um contador binário de 4 bits com flip-flop JK.
2.  Conecte a saída do contador do exercício anterior em um display hexadecimal.
3.  Construa um contador binário de 4 bits, com o contador presente no Logisim, e compare com o circuito anterior.
4.  Construa um contador binário de 8 bits interligando dois contadores de 4 bits.
5.  Modifique os contadores para mostrar nos *displays* contagem decimal (0-9) e não hexadecimal (0-A)

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 15h00min de 15 de junho de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Sistemas_Digitais" class="wikilink" title="Categoria:Sistemas Digitais">Categoria:Sistemas Digitais</a>

[^1]: TOCCI, R.J.; WIDMER, N.S.; MOSS, G.L. Sistemas Digitais: princípios e aplicações, São Paulo: Pearson, 2011.
