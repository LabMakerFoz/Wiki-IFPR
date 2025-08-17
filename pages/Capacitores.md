# Capacitores

## Fundamentos sobre o Capacitor

Os **Capacitores** são dispositivos que **armazenam energia elétrica** em um **campo elétrico**.

<a href="Arquivo:Capacitores.jpeg" class="wikilink" title=" 150px"> 150px</a>

Os **Capacitores** permitem um maior fluxo de corrente a medida que a frequência do sinal elétrico aumenta, se comportando como um **circuito aberto** na presença de uma **corrente contínua**. Para um **sinal senoidal**, a **fase da corrente** é **adiantada** de **90 graus** em relação a **tensão**.

Nos circuitos elétricos o **capacitor** é representado pela letra **C** e é medido em **Faraday (F)**. O Faraday é uma unidade muito grande, portanto, é muito comum usar submúltiplos para especificar a maioria dos capacitores utilizados em circuitos eletrônicos, como **μF**, **nF** e **pF**.

Um **capacitor** é formado por duas **placas condutoras** separadas por um material isolante, chamado **dielétrico**. A **carga** de um **capacitor** é criada pela acumulação ou depleção de elétrons livres em cada placa condutora, produzindo um **campo elétrico** no **dielétrico**, e, por consequência, produzindo um **tensão elétrica** entre as placas.

O símbolo do capacitor nos faz lembrar que a capacitância ocorre sempre que as placas condutoras estiverem separadas por um material dielétrico.

<a href="Arquivo:Simbolo_Capacitor.png" class="wikilink" title="Arquivo:Simbolo_Capacitor.png">Arquivo:Simbolo_Capacitor.png</a>

Entre outras aplicações, os **capacitores** são utilizados em circuitos eletrônicos para **acoplamento CA**, isolando o circuito de polarização dos circuitos alimentados por fontes CC, do sinal CA manipulado pelo circuito. Outra aplicação importante dos capacitores é para implementar **filtros de sinal**.

### Carga elétrica, tensão e corrente sobre um capacitor

Uma quantidade **carga elétrica** (Q), medida em Coulombs, sobre um **capacitor**, produz uma **tensão** (V) entre as placas, em função da **capacitância** (C), segundo a relação:

$`V = \frac{Q}{C}`$

ou, isolando a carga elétrica:

$`Q = C V`$

A definição de **corrente elétrica** é dada como a quantidade de **carga elétrica** (Coulomb) que circula em um condutor por unidade de **tempo** (segundos). É expressa matematicamente como a **derivada da carga elétrica no tempo**:

$`i(t) =  \frac{dq(t)}{dt}`$

ou, usando a expressão da carga em função da tensão em um capacitor, podemos expressar a corrente no capacitor como:

$`i(t) =  C \frac{dv(t)}{dt}`$

ou seja, a **corrente** no capacitor é função da **derivada da tensão no tempo**, multiplicada pela **capacitância**.

A derivada indica que a corrente elétrica no capacitor é maior quanto maior for a variação da tensão. Desta forma, para uma **tensão senoidal**, quanto maior a **frequência** da onda, maior o fluxo da **corrente** em um capacitor. Para uma **tensão constante**, a **corrente** no capacitor é **zero**.

## Fundamentos sobre o Circuito RC

Num **circuito RC** série, quando um **degrau de tensão** é aplicado, inicialmente toda **tensão** aparece toda sobre o **resistor**, pois o **capacitor** está descarregado e a tensão sobre ele é zero. A corrente inicial que fluirá no circuito será dada pela **Lei de Ohm** (I = V / R) e vai ser responsável por iniciar a **carga** do **capacitor**. A medida que o **capacitor** vai sendo **carregado**, a **tensão** sobre ele vai aumentando, diminuindo a tensão resultante sobre o **resistor**, segundo a **Lei de Kirchhoff das Malhas**, e, consequentemente, diminuindo também a **corrente** no circuito. Quanto o **capacitor** se **carregar** totalmente, a tensão de 5V estará toda sobre o capacitor e a **corrente** no circuito será reduzida a **zero**.

<a href="Arquivo:CircuitoRC.png" class="wikilink" title="Arquivo:CircuitoRC.png">Arquivo:CircuitoRC.png</a>

O processo de **carga do capacitor** segue uma curva que **desacelera exponencialmente** a medida que a tensão sobre o capacitor aumenta. A **taxa de crescimento** da **carga do capacitor** depende do produto **RC**, chamado de **constante de tempo**, dada em segundos, e é representado pela letra grega tau (τ). No tempo de uma **constante de tempo** o **capacitor** é carregado com **63%** de sua **carga**. Em cinco **constantes de tempo** a carga do capacitor chega a 99.3%. O tempo da carga total tende ao infinito, entretanto, na prática, considera-se que em cinco **constantes de tempo** o capacitor está carregado.

Num **circuito RC** série, a **tensão sobre o capacitor** (V<sub>C</sub>), em função da tensão total aplicada no circuito (V<sub>T</sub>) é dada pela expressão:

$`V_C(t) = V_T (1 - e^{-t/\tau})`$

<a href="Arquivo:Carga_descarga_capacitor.png" class="wikilink" title="300px">300px</a>

A figura mostra as exponenciais da carga e descarga de um capacitor num circuito RC (traço verde) em função de uma onda quadrada aplicada ao circuito (traço amarelo). Neste exemplo temos um circuito com C = 1 μF e R = 1 KΩ, a **constante de tempo** calculada é de 1 ms. Desta forma, a carga (ou descarga) do capacitor, em cinco constantes de tempo, fica em cerca de 5 ms. A onda quadrada utilizada tem frequência de 100 Hz, portanto com período de 10 ms (5 ms para cada meio período), que equivale exatamente ao tempo de cinco constantes de tempo.

## Laboratório

<a href="Laboratorio:_Capacitores_e_Circuitos_RC" class="wikilink" title="Laboratório: Capacitores e Circuitos RC">Laboratório: Capacitores e Circuitos RC</a>  

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 13h53min de 10 de setembro de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>
