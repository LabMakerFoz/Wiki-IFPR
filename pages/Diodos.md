# Diodos

Os **diodos** são dispositivos **semicondutores** que conduzem corrente elétrica somente em um sentido [^1], fluindo do **anodo** para o **catodo**:

<a href="Arquivo:Diodo-simbolo.jpg" class="wikilink" title="Arquivo:Diodo-simbolo.jpg">Arquivo:Diodo-simbolo.jpg</a> [^2]

  
O componente físico **diodo** tem uma **faixa** em uma das extremidades para indicar o terminal correspondente ao **catodo**.

Polarização de um diodo:

- Se uma tensão positiva (em relação a terra) for aplicada ao diodo ele conduz (**polarização direta**);
- Se uma tensão negativa (em relação a terra) for aplicada ao diodo ele não conduz (**polarização reversa**), se comportando como um circuito aberto.

<a href="Arquivo:Diodo-polarizacao-direta.jpg" class="wikilink" title="Arquivo:Diodo-polarizacao-direta.jpg">Arquivo:Diodo-polarizacao-direta.jpg</a> <a href="Arquivo:Diodo-polarizacao-reversa.jpg" class="wikilink" title="Arquivo:Diodo-polarizacao-reversa.jpg">Arquivo:Diodo-polarizacao-reversa.jpg</a> [^3]

## Análise de circuitos com diodo

Quando o diodo de silício esta com **polarização direta** ele conduz, entretanto, apresenta uma **queda de tensão direta** sobre ele de **0,7 V**.

<a href="Arquivo:CircuitoDiodo.png" class="wikilink" title=" 150px"> 150px</a>

Pela **Lei de Kirchhoff das Malhas**

`V = 0,7 + R.I`  
`I = (V - 0,7)/R`

Se, por exemplo, **V = 5 V** e **R = 1 kΩ**, a corrente no circuito será: **I = (5 - 0,7)/1 = 4,3 mA**

## Tipos de diodos

### Diodo Zener

O **diodo zener** é um diodo especial que opera com **polarização reversa**. No caso, a polarização reversa em um diodo, sem condução de corrente, pode ser mantida até um nível máximo de tensão chamado **tensão de ruptura**, a partir da qual o diodo conduz. Desta forma, os **diodos zener** são construídos para operarem em tensão de ruptura específicas, com diferentes valores, sendo muito utilizados para construir **reguladores de tensão**.

<a href="Arquivo:diodo-zener.jpg" class="wikilink" title="Arquivo:diodo-zener.jpg">Arquivo:diodo-zener.jpg</a> [^4]

  
Exemplo de regulador de tensão com diodo zener:

<a href="Arquivo:Zener.png" class="wikilink" title="350px">350px</a> [^5]

### Foto Diodo

O **foto diodo** é um diodo que conduz recebe luz sobre sua junção de silício. É utilizado em sensores detectores de luz.

<a href="Arquivo:foto-diodo.jpg" class="wikilink" title="Arquivo:foto-diodo.jpg">Arquivo:foto-diodo.jpg</a> [^6]

### <a href="Leds" class="wikilink" title="Led">Led</a>

Um **led** é um **diodo emissor de luz** (*light emitting diode*). Ele se comporta como um **<a href="Diodos" class="wikilink" title="diodo">diodo</a>**, conduzindo apenas quanto polarizado diretamente.

<a href="Arquivo:led-simbolo.gif" class="wikilink" title="Arquivo:led-simbolo.gif">Arquivo:led-simbolo.gif</a> [^7]

## Aplicações dos Diodos

### Retificadores de meia onda

Uma das aplicações importantes dos **diodos** são os **retificadores de tensão**, que permitem converter a tensão alternada em tensão continua.

O **retificador de meia onda** é um circuito com um diodo apenas, que permite a passagem somente da parte positiva de uma onda senoidal a ser aplicada sobre uma carga.

<a href="Arquivo:diodo-rectificador-meia-onda.jpg" class="wikilink" title="200px">200px</a> [^8]

<a href="Arquivo:fases-meia-onda.jpg" class="wikilink" title="Arquivo:fases-meia-onda.jpg">Arquivo:fases-meia-onda.jpg</a> [^9]

### Retificador de onda completa

O **retificador de onda completa** é um circuito com uma **ponte de diodos**, que permite a passagem a passagem da parte positiva e da parte negativa de uma onda senoidal a ser aplicada sobre uma carga. No caso, a parte negativa da onda senoidal é rebatida para o lado positivo, ficando, portanto, ambos os lados da senoide atuando sobre a carga.

<a href="Arquivo:rectificador-onda-completa.jpg" class="wikilink" title="Arquivo:rectificador-onda-completa.jpg">Arquivo:rectificador-onda-completa.jpg</a> [^10]

#### Fonte de tensão contínua

A partir da uma **fonte de tensão alternada**, como a tensão fornecida pelas concessionárias de energia, pode-se construir uma **fonte de tensão contínua**. Para isto, primeiro usa-se um **transformador** para abaixar a tensão alternada para um valor desejável, em seguida a tensão é retificada por um circuito **retificador de onda completa**, e por último, a ondulação da onda retificada é filtrada por um **capacitor**.

<a href="Arquivo:PonteRetificadora.png" class="wikilink" title="450px">450px</a>

Regulador de tensão  
Uma **fonte de tensão** mais elaborada pode utilizar um **regulador de tensão**, o qual permite manter um nível de tensão constante automaticamente, independente das variações de corrente, tensão e temperatura. As tensões de saída mais usuais dos **reguladores de tensão** para sistemas de baixa tensão são 3,3V, 5V, 9V e 12V. 

<a href="Arquivo:ReguladorTensao.jpeg" class="wikilink" title="80px">80px</a>

### Detector de pico

O circuito **detector de pico** gera um valor de **tensão CC** igual ao **pico** do **sinal CA** de entrada.

<a href="Arquivo:DetectorPico.png" class="wikilink" title="Arquivo:DetectorPico.png">Arquivo:DetectorPico.png</a>

Funcionamento  
Quando a **tensão de entrada CA** (v<sub>in</sub>) está **crescendo**, o **diodo** conduz e provoca a **carga** do **capacitor** (C). Quando a tensão de entrada atinge o **valor de pico** o capacitor estará carregado com o **valor máximo da tensão** (V<sub>pico</sub>). Quando o sinal CA começa a decrescer a tensão da entrada ficará menor que a tensão no capacitor e o diodo passa a não conduzir, ficando a tensão armazenada na **carga do capacitor**. Parte da **carga do capacitor** é descarregada sobre o **resistor de carga** (R<sub>L</sub>). Se o **resistor de carga** for suficientemente grande, será observada apenas uma pequena oscilação na tensão contínua de saída, chamado ***ripple***.

## Laboratório

<a href="Laboratorio:_Diodos_e_Leds" class="wikilink" title="Laboratório: Diodos e Leds">Laboratório: Diodos e Leds</a>  

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 08h41min de 21 de setembro de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a>

[^1]: SEDRA /SMITH. Microeletrônica, Vol.1, Makron Books, 1995.

[^2]: <https://www.electronica-pt.com/diodo>

[^3]:

[^4]:

[^5]:

[^6]:

[^7]:

[^8]:

[^9]:

[^10]:
