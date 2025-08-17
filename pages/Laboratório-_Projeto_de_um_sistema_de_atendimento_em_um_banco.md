# Projeto de um sistema de atendimento em um banco

Para este laboratório será utilizado o <a href="Simulador_de_Circuitos_Lógicos_-_Logisim" class="wikilink" title="Simulador de Circuitos Lógicos - Logisim">Simulador de Circuitos Lógicos - Logisim</a>  
Veja no *link* as instruções para *download* e instalação do programa.

## Objetivo

Construir um **sistema para organizar o atendimento dos caixas em um banco** utilizando circuitos combinacionais e um mostrador digital para mostrar o caixa disponível para atendimento.

## Especificações e passos para o projeto do sistema

Suponha que **banco** tenha **7 caixas** de atendimento. Cada caixa tem um **botão** que deverá ser pressionado quando o caixa está disponível para atender um novo cliente. O sistema deverá ter um ***display* digital** para indicar o caixa cujo botão foi pressionado.

<a href="Arquivo:CaixasBanco.png" class="wikilink" title="Arquivo:CaixasBanco.png">Arquivo:CaixasBanco.png</a>

## Parte I: Codificadores e Decodificadores

### Projeto de circuitos construídos a partir da tabela verdade

Utilizar a opção **Projeto/Analisar circuito** disponível no **Logisim** para **projetar circuitos** a partir de uma **tabela verdade**.

Divida o **projeto do sistema** em duas partes  

1\) A partir do **botão** pressionado por um dos caixas, construir um **circuito codificador** para converter para um **número binário** de **3 bits** correspondente ao caixa cujo botão foi pressionado.

  
Como temos somente 7 botões, o binário correspondente tem só três bits, logo o código BCD de entrada do decodificador pode considerar o bit mais significativo igual a zero (A=0).

|     |     |     |     |     |     |     |     |     |     |
|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|
| C1  | C2  | C3  | C4  | C5  | C6  | C7  | B   | C   | D   |
| 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   |
| 1   | 0   | 0   | 0   | 0   | 0   | 0   |     |     |     |
| 0   | 1   | 0   | 0   | 0   | 0   | 0   |     |     |     |
| 0   | 0   | 1   | 0   | 0   | 0   | 0   |     |     |     |
| 0   | 0   | 0   | 1   | 0   | 0   | 0   |     |     |     |
| 0   | 0   | 0   | 0   | 1   | 0   | 0   |     |     |     |
| 0   | 0   | 0   | 0   | 0   | 1   | 0   |     |     |     |
| 0   | 0   | 0   | 0   | 0   | 0   | 1   |     |     |     |

2\) A partir do **número binário** de **3 bits** correspondente ao caixa cujo botão foi pressionado, construir um circuito **decodificador de BCD para 7 segmentos** para apresentar o valor no ***display*** (ver <a href="Codigos_Digitais" class="wikilink" title=" Código BCD"> <strong>Código BCD</strong></a>).

  
Considerando como entrada o **BCD** correspondente ao caixa selecionado (1 a 7) e a saída a pinagem correspondente do ***display*** (a b c d e f g):

|     |     |     |     |     |     |     |     |     |     |
|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|
| B   | C   | D   | a   | b   | c   | d   | e   | f   | g   |
| 0   | 0   | 0   |     |     |     |     |     |     |     |
| 0   | 0   | 1   |     |     |     |     |     |     |     |
| 0   | 1   | 0   |     |     |     |     |     |     |     |
| 0   | 1   | 1   |     |     |     |     |     |     |     |
| 1   | 0   | 0   |     |     |     |     |     |     |     |
| 1   | 0   | 1   |     |     |     |     |     |     |     |
| 1   | 1   | 0   |     |     |     |     |     |     |     |
| 1   | 1   | 1   |     |     |     |     |     |     |     |

<a href="Arquivo:Display7Segmentos.png" class="wikilink" title="Arquivo:Display7Segmentos.png">Arquivo:Display7Segmentos.png</a>

## Parte II: Memória com Registrador

Aprimore o projeto do **sistema para organizar o atendimento dos caixas em um banco**, incluindo circuitos de memória, como **flip-flop tipo D**, de forma que, uma vez pressionado o botão correspondente a um caixa, o mesmo fique registrado no *display* até que o botão correspondente a outro caixa seja pressionado.

### Acionamento da borda do clock para armazenar no dispositivo de memória

Para acionar o **clock** do dispositivo de memória tome como referência o momento em que o botão correspondente a um caixa seja liberado.

Use um circuito com **portas lógicas** do tipo **OU** de modo que, para qualquer botão de caixa que seja pressionado, o **clock** seja acionado no dispositivo de memória .

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 20h06min de 2 de junho de 2016 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Sistemas_Digitais" class="wikilink" title="Categoria:Sistemas Digitais">Categoria:Sistemas Digitais</a>
