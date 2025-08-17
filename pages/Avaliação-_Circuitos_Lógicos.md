# Avaliação: Circuitos Lógicos

Instruções para avaliação  

- A avaliação será **individual** ou em **duplas**;
- Podem ser consultados os materiais da **Wiki** ou da **Internet**;
- Será utilizado o <a href="Simulador_de_Circuitos_Lógicos_-_Logisim" class="wikilink" title="Simulador de Circuitos Lógicos - Logisim">Simulador de Circuitos Lógicos - Logisim</a>;
- A resposta dos exercícios deverá ser postada na **Pasta Compartilhada GoogleDrive**: <https://drive.google.com/folderview?id=0B4oNxt3g19DfbzlXSWVVbE51V0k&usp=sharing>;
- Antes de postar as respostas, cada aluno ou dupla deverá organizar todas elas em uma **Pasta com o nome do aluno ou da dupla** (Exemplo: Joao&Maria).
- As respostas poderão ser **circuitos do Logisim** (**.circ**) ou **arquivos de texto** (**.txt**) (Use o editor **Gedit** para edição de textos).
- Os arquivos com as respostas devem ser identificado com um nome apropriado, identificando as respostas.
- Não utilize acentos ou espaços no nome dos arquivos e pastas.

## Exercícios

Circuitos com portas lógicas  

1.  Monte no Logisim o circuito com portas lógicas da figura e em seguida:
      
    <a href="Arquivo:Circuito1.png" class="wikilink" title="Arquivo:Circuito1.png">Arquivo:Circuito1.png</a>

    - Verifique a tabela verdade do circuito na opção **Projeto/Analisar Circuito** do Logisim;
    - Escreva a expressão lógica equivalente do circuito.
2.  Monte no Logisim o circuito dado pela expressão lógica: S = /A.B.C./(A + D) e em seguida:
    - Verifique a tabela verdade do circuito na opção **Projeto/Analisar Circuito** do Logisim;

Circuitos aritméticos  

1.  Construa um circuito para **subtrair** dois números binários com sinal de 8 bits, utilizando os circuitos **somador** e **negador** presentes no Logisim, em seguida:
    - Detalhe um exemplo (modo texto) de uma operação mostrando os cálculos do **complemento de 2** para o "número negativo" e da operação de soma.
2.  Construa um somador de 16 bits interligando dois somadores de 8 bits, utilizando o circuito **somador** presente no Logisim.

Circuitos sequenciais  

1.  Construa um contador assíncrono de 4 bits utilizando flip-flops JK;
    - Monte a tabela verdade (modo texto) do contador verificando a contagem realizada.
    - Verifique qual a próxima contagem após 1111.
2.  Pesquise na Internet como modificar o contador assíncrono de 4 bits para que o mesmo somente conte de 0 a 9 (contagem BCD de 0000 a 1001). Verifique que deverá ser utilizada as entradas *clear* dos flip-flops (estas entradas resetam os flip-flops de forma assíncrona).
3.  Pesquise e responda qual a diferença entre um contador síncrono e um assíncrono.

Projeto  
Utilize a opção do Logisim **Projeto/Analisar Circuito** para resolver o problema.

Projetar um sistema para organizar o atendimento dos caixas em um banco. Suponha que banco tenha 6 caixas de atendimento. Cada caixa tem um botão que deverá ser pressionado quando o caixa está disponível para atender um novo cliente. O sistema deverá ter um mostrador para indicar o caixa cujo botão foi pressionado, juntamente com um sinal sonoro.

1.  Utilize a opção **Projeto/Analisar Circuito** para construir um circuito para resolver o problema. Assuma que dois botões não possam ser acionados ao mesmo tempo.
2.  Uma vez que o circuito esteja construído, utilize a opção **Acrescentar circuito** para fazer um teste do componente gerado. Para o teste, utilize os **botões** e **leds** disponíveis como dispositivos de Entrada/Saída no Logisim.
3.  Aprimore o circuito para que o mostrador mantenha o último número pressionado. Utilize para isto um **registrador** controlado por um *clock* que seja acionado quando o botão for solto (**borda negativa**, que ocorre quando o botão é solto, passando de 1 para 0).
4.  Pesquise como funciona o **display de 7 segmentos** e construa, com a opção **Projeto/Analisar Circuito**, um decodificador de BCD para 7 segmentos para mostrar a numeração de cada caixa do banco em um display.
