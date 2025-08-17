# Dispositivos Lógicos Programáveis

## Linguagem VHDL

A linguagem **VHDL** (***V**ery high speed integraded circuits* (VHSIC) ***H**ardware **D**escription **L**anguage*) permite descrever na forma de uma linguagem textual **circuitos lógicos**.

A linguagem **VHDL** pode ser utilizada para programar **Dispositivos Lógicos Programáveis**.

Linguagem VHDL x Linguagem de Programação  
Uma linguagem de descrição de hardware descreve a configuração de hardware de um circuito, ao passo que uma linguagem de programação descreve uma sequência de instruções a serem executadas por um computador para realizar um tarefa.

A execução de um programa em um computador segue uma ordem sequencial, por exemplo, caso o programa precise analisar o estado de quatro entradas, ele deve analisar uma entrada de de cada vez, a passo que um circuito lógico considera a atuação das entradas em paralelo [^1] <sup>(p. 85)</sup>.

### Sintaxe VHDL

O formato de uma descrição de hardware envolve dois elementos fundamentais [^2] <sup>(p. 88)</sup>:

- Definição das entradas e saídas (bloco ENTITY);
- Definição de como as saídas respondem as entradas (bloco ARCHITECTURE).

Exemplo de uma porta AND:

``` vhdl
ENTITY and_gate IS 
  PORT(
    A, B :  IN   BIT;
    S    :  OUT  BIT);
  END and_gate;
ARCHITECTURE ckt OF and_gate IS 
  BEGIN 
    S <= A AND B;
  END ckt;
```

Sinais intermediários  
São **nós internos** de um circuito lógico. São utilizados no VHDL para definir entradas e saídas de um bloco de circuito [^3] <sup>(p. 90)</sup>.

Exemplo de um **circuito lógico** dado pela **expressão lógica**:

`S = AB + C `

``` vhdl
ENTITY logic_circuit IS 
  PORT(
    A, B, C :  IN   BIT;
    S       :  OUT  BIT);
  END logic_circuit;
ARCHITECTURE ckt OF logic_circuit IS 
  SIGNAL m :BIT;
  BEGIN 
    m <= A AND B;
    S <= m OR  C;
  END ckt;
```

### Dados em VHDL

Dados numéricos representados em **binário**, **hexadecimal** e **decimal** [^4] <sup>(p. 148)</sup>:

``` vhdl
B"11001" --Binário
X"19"    --Hexadecimal
25       --Decimal
```

Vetores de bits  
Exemplo **porta p** definida como uma **entrada** de **8 bits**:

``` vhdl
PORT(p :IN BIT_VECTOR(7 DOWNTO 0);
```

Tipos de dados em VHDL  

|  |  |  |  |
|----|----|----|----|
| **Tipo de dados** | **Declaração** | **Valores possíveis** | **uso** |
| BIT | y: OUT BIT; | '0', '1' | y \<= '0' |
| BIT_VECTOR | bcd: OUT BIT_VECTOR (3 DOWNTO 0); | '0101', '1001', '0000' | bcd \<= '0000'; |
| STD_LOGIC | y: OUT STD_LOGIC; | '0', '1', 'x', 'z' | y \<= 'z' |
| STD_LOGIC_VECTOR | dbus: OUT STD_LOGIC_VECTOR (3 DOWNTO 0); | '0z1x' | dbus \<= 'zzzz'; |
| INTEGER | SIGNAL z:INTERGER_RANGE 0 TO 31; | 0,1,2,...,31 | z \<= 31; |
|  |  |  |  |

Tipos de dados:

- '0' -\> Logico 0
- '1' -\> Logico 1
- 'z' -\> Alta Impedância
- 'x' -\> Desconhecido

### Circuitos lógicos construídos a partir da tabela verdade

Uma **tabela verdade** permite expressar o funcionamento de um **circuito lógico combinacional**.

Exemplo de uma **porta AND** descrita como **tabela verdade** em **VHDL** [^5] <sup>(p. 152)</sup>:

``` vhdl
ENTITY and IS
PORT(
  a,b: IN BIT;
  s: OUT BIT);
END and;
ARCHITECTURE tabelaVerdade OF and IS
  SIGNAL in_bits: BIT_VECTOR (1 DOWNTO 0);
  BEGIN
    in_bits <= a & b;  --concatena bits
    WITH in_bits SELECT
     S <= '0' WHEN "00",
          '0' WHEN "01",
          '0' WHEN "10",
          '1' WHEN "11";
  END tabelaVerdade;
```

### Estruturas de Controle em VHDL

A linguagem VHDL possui **estruturas de controle de decisão** que são interpretadas de forma **sequencial**, como numa linguagem de programação.

IF/THEN/ELSE  
Exemplo de uso de IF/THEN/ELSE para comparar uma entrada inteira de 4 bits[^6] <sup>(p. 157)</sup>:

``` vhdl
ENTITY teste IS
PORT(
  valor_digital: IN INTEGER RANGE 0 TO 15; --entrada de 4 bits
  z: OUT BIT);
END teste;
ARCHITECTURE desisao OF teste IS
  BEGIN
    PROCESS (valor_digital)
      BEGIN
        IF (valor_digital > 6) THEN
          z <= '1';
        ELSE
          z <= '0';
        END IF;
      END PROCESS;
  END desisao;
```

IF/THEN/ELSEIF/THEN/ELSE  
Permite construir IFs aninhados.

<!-- -->

CASE  
Estrutura que permite percorrer uma lista de possíveis valores a serem avaliados[^7] <sup>(p. 159)</sup>.

``` vhdl
ENTITY caso IS
PORT(
  p,q,r: IN BIT;
  s: OUT BIT);
END caso;
ARCHITECTURE copia OF caso IS
  SIGNAL status: BIT_VECTOR (2 DOWNTO 0);
  BEGIN
    status <= p & q & r;  --concatena bits
    PROCESS (status)
      BEGIN
        CASE status IS
      WHEN "100"  => s <= '0';
      WHEN "101"  => s <= '0';
      WHEN "110"  => s <= '0';
      WHEN OTHERS => s <= '1';
        END CASE;
      END PROCESS;
  END copia;
```

### Flip-Flops e Latchs em VHDL

O Quartus possui blocos primitivos de biblioteca para **flip-flops** e **latchs** [^8] <sup>(p. 230-235)</sup>.

Estes componentes possuem as portas de entrada e saída com identificação padrão em bloco primitivo, conforme a tabela:

|                        |                   |
|------------------------|-------------------|
| **Função da porta**    | **Identificação** |
| Clock                  | clk               |
| Preset assíncrono      | prn               |
| Clear assíncrono       | clr               |
| Entradas J, K, S, R, D | j, k, r, s, d     |
| Saída Q                | q                 |
|                        |                   |

**Flip-flops** e **latchs** também podem ser implementados em VHDL, como segue:

Latch D em VHDL  

``` vhdl
LIBRARY ieee;
USE ieee.std_logic_1164.all; 
LIBRARY work;
ENTITY latchD IS 
       PORT
       (
         D :  IN  STD_LOGIC;
         Clock :  IN  STD_LOGIC;
         Qlatch :  OUT  STD_LOGIC
       );
END latchD;
ARCHITECTURE bdf_type OF latchD IS 
BEGIN 
  PROCESS(Clock,D)
  BEGIN
    IF (Clock = '1') THEN
    Qlatch <= D;
    END IF;
  END PROCESS;
END bdf_type;
```

Flip-flop D em VHDL  

``` vhdl
LIBRARY ieee;
USE ieee.std_logic_1164.all; 
LIBRARY work;
ENTITY flipflopD IS 
       PORT
       (
         D :  IN  STD_LOGIC;
         Clock :  IN  STD_LOGIC;
         Qff :  OUT  STD_LOGIC
       );
END flipflopD;
ARCHITECTURE bdf_type OF flipflopD IS 
BEGIN 
  PROCESS(Clock)
  BEGIN
    IF (RISING_EDGE(Clock)) THEN
       Qff <= D;
    END IF;
  END PROCESS;
END bdf_type;
```

### Somador em VHDL

Um **somador** pode ser facilmente implementado em VHDL, no qual o número de bits dos operandos pode ser atribuído na declaração das variáveis de entrada e saída [^9] <sup>(p. 294)</sup>.

``` vhdl
ENTITY somador IS
PORT (a :IN  INTEGER RANGE 0 TO 255; -- primeira parcela (8 bits)
      b :IN  INTEGER RANGE 0 TO 255; -- segunda parcela (8 bits)
      s :OUT INTEGER RANGE 0 TO 511  -- soma (9 bits)
);
END somador;
ARCHITECTURE soma OF somador IS
BEGIN
      s <= a + b; -- operaçao soma
END soma;
```

Exemplo de simulação  
Realizada no Simulation Waveform do Quartus

<a href="Arquivo:somadorQuatus.png" class="wikilink" title="600px">600px</a>

### Contador em VHDL

Método de transição de estados  
Baseia-se em tabelas que relacionam o estado ATUAL/PRÓXIMO estado [^10] <sup>(p. 350-351)</sup>.

``` vhdl
ENTITY contador IS
PORT (clock :IN  BIT;
      q     :OUT BIT_VECTOR (2 DOWNTO 0) 
);
END contador;
ARCHITECTURE conta5 OF contador IS
BEGIN
 PROCESS (clock)
 VARIABLE conta: BIT_VECTOR (2 DOWNTO 0);
 BEGIN
   IF (clock = '1' AND clock'EVENT) THEN
       CASE conta IS
          WHEN "000"  => conta := "001";
          WHEN "001"  => conta := "010";
          WHEN "010"  => conta := "011";
          WHEN "011"  => conta := "100";
          WHEN "100"  => conta := "000";
          WHEN OTHERS => conta := "000";
      END CASE;
   END IF;
    q <= conta;
 END PROCESS;
END conta5;
```

Método de descrição comportamental  
Baseia-se na descrição do comportamento que se aproxima da linguagem natural. Por exemplo, quando ocorrer uma transição no clock a saída é aumentada de 1. [^11] <sup>(p. 353-354)</sup>.

``` vhdl
LIBRARY IEEE;
use ieee.std_logic_1164.all;
ENTITY contador IS
PORT (clock :IN  BIT;
      q     :OUT INTEGER RANGE 0 TO 15);
END ENTITY;

ARCHITECTURE contaN OF contador IS
BEGIN
 PROCESS (clock)
 CONSTANT N : NATURAL := 10;
 VARIABLE conta: INTEGER range 0 to N := 0;
 BEGIN
   IF (clock = '1' AND clock'EVENT) THEN
       IF conta = N THEN
            conta := 0;
        ELSE 
         conta := conta + 1;
        END IF;
   END IF;
    q <= conta;
 END PROCESS;
END ARCHITECTURE;
```

Contadores com recursos completos  
Um contador pode contar com recursos completos, como *clear*, *load*, *carry*. Ver [^12] <sup>(p. 357)</sup>.

## Máquina de Estados Finita

Uma **máquina de estados finita** é um modelo matemático usado para representar programas de computadores ou circuitos lógicos.

No projeto de **circuitos lógicos** uma **máquina de estados** sequencia um conjunto de **estados** predeterminados controlados por um ***clock*** e outros **sinais de entrada** [^13] <sup>(p. 367)</sup>.

Há duas variação para as **máquinas de estado** no projeto de circuitos lógicos:

- **Modelo Mealy**: A saída também é controlada por sinais de entrada adicionais;
- **Modelo Moore**: A saída é função apenas do estado atual.

A saída de um circuito que seque o **modelo Moore** é **síncrona**, ao passo que no **modelo Mealy** podem também mudar **assincronamente**.

Uma **máquina de estados** pode ser representada por um **diagrama de transição de estados**.

Em termos de hardware uma máquina de estados pode ser construída com um bloco formado por **circuitos combinacionais**, que recebem as **entradas** e a informação do **estado atual** do sistema e fornecem as **saídas** e o **próximo estado** do sistema. E, um bloco formado por **circuitos sequenciais** que armazenam os **estados**, implementados por **flip-flops tipo D**.

<a href="Arquivo:ModeloMaquinaEstados.png" class="wikilink" title="Arquivo:ModeloMaquinaEstados.png">Arquivo:ModeloMaquinaEstados.png</a>

A abordagem de **máquina de estados** para modelar **circuitos lógicos** é vantajosa em sistemas cujas tarefas se constituem de uma lista bem estruturada, não muito longa, de **estados** que possam ser devidamente nomeados e especificados [^14] <sup>(p. 350)</sup>

### Projeto de Máquinas de Estado

**Passos para o**projeto de circuitos lógicos**com**máquinas de estados''' [^15]<sup>(p. 351)</sup>:

1.  Desenhar o **diagrama de transição de estados**.
2.  Com base no diagrama, construir a **tabela verdade** para as **saídas** e **próximos estados**, substituindo o nome dos estados pelo **código binário** correspondente, incluindo as entradas.
3.  Determinar as **expressões booleanas** para as **saídas** e **próximos estados**.
4.  Construir o **circuito lógico** correspondente.

## Projeto de Circuitos Lógicos com VHDL

[Etapas do Projeto de Circuitos Lógicos com VHDL](http://200.17.101.9:8080/rid=1RGR4YLC8-1H5VVQN-3G2/ProjetoVHDL.cmap)  
Link com Mapa Conceitual ilustrando os passos de um Projeto de Circuitos Lógicos com VHDL.

## Dispositivos Lógicos Programáveis

Um **Dispositivo Lógico Programável** (**PLD**) pode ser configurado eletronicamente para formar um **circuito lógico**. Normalmente são construídos como uma matriz de comutação com chaves que podem ser programadas [^16] <sup>(p. 143)</sup>.

A programação de um **PLD** utiliza **software de desenvolvimento**, com o qual o programador define como o dispositivo deve ser programado.

A descrição de um **circuito lógico** em um **software de desenvolvimento** pode ser realizada de diferentes maneiras, incluindo:

- Captura Esquemática;
- Expressão Lógica;
- Tabela Verdade;
- Linguagem VHDL.

O **QUARTUS II** é um **software de desenvolvimento** da **Altera**, com o qual é possível descrever um **diagrama lógico** como uma arquivo de **descrição de bloco** (**.bdf)** ou utilizando a **linguagem VDHL** (**.vhd**).

## Quartus II

Software para desenvolvimento de circuitos lógicos digitais.

### Instalação do Quartus II Web Edition no Linux

1.  Acessar [Download Center Altera](https://www.altera.com/downloads/download-center.html):
    - [Quick Start Guide](http://dl.altera.com/static/quick_start_guide/quick_start_guide_13.0sp1_en.pdf)
2.  Selecionar **Quartus Prime software Lite edition** - FREE, no license file required
3.  Selecionar versão **13.osp1**: **Quartus II Web Edition**
    - Versão compatível com MAX7000S
4.  Selecionar o DOWNLOAD do arquivo:
    - Quartus-web-13.0.1.232-linux.tar
    - Link: <http://download.altera.com/akdlm/software/acdsinst/13.0sp1/232/ib_tar/Quartus-web-13.0.1.232-linux.tar>
5.  Descompactar o arquivo.
6.  Executar 0 script

`./setup.sh`

### Teste e possíveis erros

Testar o Quartus  

`/opt/altera/13.0sp1/quartus/bin/quartus &`

Testar o ModelSim  

`/opt/altera/13.0sp1/modelsim_ase/bin/vsim &`

Possível **ERRO 1**  

`/opt/altera/13.0sp1/modelsim_ae/bin/vsim`  
`** Fatal: Read failure in vlm process (0,0)`  
`Falha de segmentação (imagem do núcleo gravada)`

  
Isto ocorre porque várias ferramentas usadas pelo Quartus são 32 bits, para solucionar:

- Obtenha os arquivos abaixo e os armazene em uma pasta do Quartus com o nome **lib32**.

`libfreetype.so`  
`libfreetype.so.6`  
`libfreetype.so.6.10.2`

  
  
Estes arquivos podem ser obtidos através da biblioteca **freetype2**.

Definir uma variável em /etc/bash.bashrc:

`export LD_LIBRARY_PATH=/opt/altera/13.0sp1/lib32`

  
Instalar suporte para compactação **bzip2** utilizado pelo Quartus 32 bits:

`sudo apt-get install bzip2:i386`

Possível **ERRO 2**  

`$ vsim `  
`Error: cannot find "/opt/altera/13.0sp1/modelsim_ase/bin/../linux_rh60/vsim" `

:;Solução: edite o arquivo vco na linha 206, diretório /opt/altera/13.0sp1/modelsim_ase/

`*)                vco="linux_rh60" ;;`

  
para

` *)                vco="linux" ;;`

### Exemplo de utilização do Quartus II

Circuito de uma porta E constuída no Quartus II  
Block Diagram/Schematic File

<a href="Arquivo:portaE.jpg" class="wikilink" title="Arquivo:portaE.jpg">Arquivo:portaE.jpg</a>

VHDL de uma porta E gerada pelo Quartus II  

``` vhdl
-- PROGRAM      "Quartus II 32-bit"
-- VERSION      "Version 13.0.1 Build 232 06/12/2013 Service Pack 1 SJ Full Version"
-- CREATED      "Fri May 12 15:17:16 2017"
LIBRARY ieee;
USE ieee.std_logic_1164.all; 
LIBRARY work;
ENTITY portaE IS 
  PORT(
    A :  IN  STD_LOGIC;
    B :  IN  STD_LOGIC;
    S :  OUT  STD_LOGIC);
END portaE;
ARCHITECTURE bdf_type OF portaE IS 
  BEGIN 
    S <= A AND B;
  END bdf_type;
```

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 14h03min de 12 de maio de 2017 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Sistemas_Digitais" class="wikilink" title="Categoria:Sistemas Digitais">Categoria:Sistemas Digitais</a>

[^1]: TOCCI, R.J.; WIDMER, N.S.; MOSS, G.L. Sistemas Digitais: princípios e aplicações, São Paulo: Pearson, 2011.

[^2]: TOCCI, R.J.; WIDMER, N.S.; MOSS, G.L. Sistemas Digitais: princípios e aplicações, São Paulo: Pearson, 2011.

[^3]: TOCCI, R.J.; WIDMER, N.S.; MOSS, G.L. Sistemas Digitais: princípios e aplicações, São Paulo: Pearson, 2011.

[^4]: TOCCI, R.J.; WIDMER, N.S.; MOSS, G.L. Sistemas Digitais: princípios e aplicações, São Paulo: Pearson, 2011.

[^5]: TOCCI, R.J.; WIDMER, N.S.; MOSS, G.L. Sistemas Digitais: princípios e aplicações, São Paulo: Pearson, 2011.

[^6]: TOCCI, R.J.; WIDMER, N.S.; MOSS, G.L. Sistemas Digitais: princípios e aplicações, São Paulo: Pearson, 2011.

[^7]: TOCCI, R.J.; WIDMER, N.S.; MOSS, G.L. Sistemas Digitais: princípios e aplicações, São Paulo: Pearson, 2011.

[^8]: TOCCI, R.J.; WIDMER, N.S.; MOSS, G.L. Sistemas Digitais: princípios e aplicações, São Paulo: Pearson, 2011.

[^9]: TOCCI, R.J.; WIDMER, N.S.; MOSS, G.L. Sistemas Digitais: princípios e aplicações, São Paulo: Pearson, 2011.

[^10]: TOCCI, R.J.; WIDMER, N.S.; MOSS, G.L. Sistemas Digitais: princípios e aplicações, São Paulo: Pearson, 2011.

[^11]: TOCCI, R.J.; WIDMER, N.S.; MOSS, G.L. Sistemas Digitais: princípios e aplicações, São Paulo: Pearson, 2011.

[^12]: TOCCI, R.J.; WIDMER, N.S.; MOSS, G.L. Sistemas Digitais: princípios e aplicações, São Paulo: Pearson, 2011.

[^13]: TOCCI, R.J.; WIDMER, N.S.; MOSS, G.L. Sistemas Digitais: princípios e aplicações, São Paulo: Pearson, 2011.

[^14]: PEDRONI, V. A. Eletrôica Digital Moderna e VHDL: Princípios Digitais, Eletrônica Digital, Projeto Digital, Microeletrônica e VHDL, Rio de Janeiro: Elsevier, 2010.

[^15]:

[^16]: TOCCI, R.J.; WIDMER, N.S.; MOSS, G.L. Sistemas Digitais: princípios e aplicações, São Paulo: Pearson, 2011.
