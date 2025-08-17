# Flip-Flops e Elementos de Memória[^1]

**Elementos de memória** são circuitos que permitem armazenar valores para uso posterior. O elemento de memória mais elementar é o **flip-flop**, o qual é comporto por um conjunto portas lógicas e é capaz de armazenar 1 bit.

## Flip-flop SR com portas NOR

Este é um dos mais simples circuitos de **flip-flop**, construído com portas NOR. Note na figura que, além das entradas, as saídas das portas NOR realimentam o circuito, dando a ele a característica de memória. O Flip-flop SR é comumente chamado de ***Latch* SR**.

<a href="Arquivo:Flip-flopSR.png" class="wikilink" title=" 200px"> 200px</a> Símbolo:<a href="Arquivo:LatchSR-NOR.png" class="wikilink" title=" 150px"> 150px</a>

Características  

- As saídas do circuito são denominadas **Q** e **/Q**, e em condições normais, são sempre uma o inverso da outra.
- O flip-flop SR possui duas entradas: a entrada **Set** que seta a saída Q para 1 e a entrada **Reset** que reseta a saída Q para 0.
- As entradas Set e Reset devem estar normalmente em estado BAIXO (0), somente quando se deseja setar ou resetar a saída do flip-flop, uma delas é pulsada ao estado ALTO (1).

Análise das saídas do flip-flop SR com portas NOR  

- Verifique que quando Set=Reset=0 há dois estados de saída possíveis e estáveis, tanto com Q=0 e /Q=1, como com Q=1 e /Q=0.
- Quando Set=1 e Reset=0 o latch é **setado**, fazendo com que Q=1 e /Q=0.
- Quando Set=0 e Reset=1 o latch é **resetado**, fazendo com que Q=0 e /Q=1.
- As entradas Set=Reset=1, simultaneamente, são **proibidas**.
- Verifique que, uma vez setado (ou resetado) o *latch*, ele mantém os dados armazenados na saída enquanto Set=Reset=0.

Vídeo  
[Flip-Flop SR portas NOR](https://www.youtube.com/watch?v=8piKnuad73g)

<!-- -->

Exercícios  
Sobre o flip-flop SR com portas NOR

1.  Para a análise das saídas do flip-flop SR, construa desenhos com os diversos **estados** possíveis para as entradas e saídas;
2.  Construa a **tabela verdade** do flip-flop SR;
3.  Determine as **formas de onda** das saídas do flip-flop SR, considerando que as formas de onda mostradas na figura sejam aplicadas nas entradas.

<a href="Arquivo:DiagramaTempo2.png" class="wikilink" title=" 400px"> 400px</a>

Observação  
O flip-flop SR também pode ser construído com portas NAND: <a href="Latch_SR_com_portas_NAND" class="wikilink" title=" Flip-flop SR com portas NAND"> Flip-flop SR com portas NAND</a>.

## Circuitos Sequenciais ou Circuitos com Clock

**Circuitos sequenciais** são circuitos cujo nível lógico da(s) saída(s) depende da combinação dos níveis lógicos das entradas e também de elementos de memória. Além disto, os circuitos sequenciais geralmente operam de modo síncrono, cadenciados por sinais de relógio (ou pulsos de ***clock***). Neste caso, os pulsos do *clock* determinam o momento em que as saídas podem mudar de estado.

<a href="Clock" class="wikilink" title=" Sinais de Clock"> <strong>Sinais de Clock</strong></a>

## Flip-flops com *clock*

Cada **flip-flop** tem uma entrada de *clock*, a qual normalmente é **disparada pela borda** (positiva ou negativa).

Normalmente, chama-se de ***latch*** os flip-flop sem *clock* disparado pela borda. Quando há presença de *clock* para sincronismo disparado pela borda, chama-se de **flip-flop**.

### Flip-flop SR

Flip-flop SR com *clock* disparado pela borda de subida  

<a href="Arquivo:LatchSRclk.png" class="wikilink" title=" 200px"> 200px</a>

Tabela verdade:

|     |       |         |                 |
|-----|-------|---------|-----------------|
| Set | Reset | CLK     | Q<sub>n</sub>   |
| X   | X     | Sem CLK | Q<sub>n-1</sub> |
| 0   | 0     | ^       | Q<sub>n-1</sub> |
| 1   | 0     | ^       | 1               |
| 0   | 1     | ^       | 0               |
| 1   | 1     | ^       | Proibido        |

Obs:

  
^:Indica borda de subida do *clock*;

Q<sub>n</sub> : Estado atual da saída;

Q<sub>n-1</sub> : Estado anterior da saída (mantém estado).

<!-- -->

Exercício  

Determine as formas de onda das saídas do flip-flop SR com *clock* disparado pela borda de subida, considerando que as formas de onda mostradas na figura sejam aplicadas nas entradas:

<a href="Arquivo:DiagramaTempo-clock.png" class="wikilink" title=" 300px"> 300px</a>

Flip-flop SR com *clock* disparado pela borda de descida  

<a href="Arquivo:LatchSRclk2.png" class="wikilink" title=" 200px"> 200px</a>

### Flip-flop JK

Flip-flop JK *clock* disparado pela borda de subida  
Há também flip-flop JK com *clock* disparado pela borda de descida

<a href="Arquivo:Flip-flopJK.png" class="wikilink" title=" 200px"> 200px</a>

Tabela verdade:

|     |     |     |                           |
|-----|-----|-----|---------------------------|
| J   | K   | CLK | Q<sub>n</sub>             |
| 0   | 0   | ^   | Q<sub>n-1</sub> (mantém)  |
| 1   | 0   | ^   | 1                         |
| 0   | 1   | ^   | 0                         |
| 1   | 1   | ^   | /Q<sub>n-1</sub> (comuta) |

### Flip-flop D

Flip-flop D com *clock* disparado pela borda de subida  
Há também flip-flop D com *clock* disparado pela borda de descida

<a href="Arquivo:Flip-flopD.png" class="wikilink" title=" 200px"> 200px</a> = <a href="Arquivo:Flip-flopJK-D.png" class="wikilink" title=" 200px"> 200px</a>

Tabela verdade:

|     |     |               |
|-----|-----|---------------|
| D   | CLK | Q<sub>n</sub> |
| 0   | ^   | 0             |
| 1   | ^   | 1             |
|     |     |               |

### Exercícios

1\) Determine as formas de onda das saídas do **flip-flop JK com *clock* disparado pela borda de subida**, considerando que as formas de onda mostradas na figura sejam aplicadas nas entradas:

<a href="Arquivo:Flip-flopJK.png" class="wikilink" title=" 200px"> 200px</a>

Diagrama de tempo:

<a href="Arquivo:DiagramaTempo4.png" class="wikilink" title=" 300px"> 300px</a>

2\) Determine as formas de onda das saídas do **flip-flop D com *clock* disparado pela borda de descida**, considerando que as formas de onda mostradas na figura sejam aplicadas nas entradas:

<a href="Arquivo:Flip-flopD2.png" class="wikilink" title=" 200px"> 200px</a>

Diagrama de tempo:

<a href="Arquivo:DiagramaTempo5.png" class="wikilink" title=" 300px"> 300px</a>

## Laboratório e Exercícios de Simulação

Para este laboratório será utilizado o <a href="Simulador_de_Circuitos_Lógicos_-_Logisim" class="wikilink" title="Simulador de Circuitos Lógicos - Logisim">Simulador de Circuitos Lógicos - Logisim</a>  
Veja no *link* as instruções para *download* e instalação do programa.

### Flip-flops

1.  Construir e simular o circuito do Latch SR, construído com portas NOR, conforme a figura: <a href="Arquivo:Flip-flopSR.png" class="wikilink" title=" 200px"> 200px</a>
    - Construa a tabela verdade;
2.  Simule o funcionamento do Latch SR presente no Logisim e compare sua tabela verdade com o circuito do Latch SR construído com portas NOR.
3.  Simule o funcionamento do Flip-flop JK presente no Logisim.
4.  Simule o funcionamento do Flip-flop D presente no Logisim.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h48min de 12 de junho de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Sistemas_Digitais" class="wikilink" title="Categoria:Sistemas Digitais">Categoria:Sistemas Digitais</a>

[^1]: TOCCI, R.J.; WIDMER, N.S.; MOSS, G.L. Sistemas Digitais: princípios e aplicações, São Paulo: Pearson, 2011.
