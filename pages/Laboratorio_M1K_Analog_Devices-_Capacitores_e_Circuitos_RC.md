# Laboratório: Introdução aos Capacitores e Circuitos RC

Este laboratório foi baseado no material disponibilizado pela **Analog Devices**, fabricante do módulo educacional **M1K Analog Devices** : [^1]

## Objetivos

Conhecer os **capacitores**, que são dispositivos que **armazenam energia elétrica** em um campo elétrico.

Conhecer o princípio de funcionamento dos **circuitos RC** de forma a poder explicar como um **capacitor** é carregado quando um degrau de tensão é aplicado em seus terminais.

## Equipamento e Materiais

- Modulo **Analog Devices M1K** e software **Pixelpulse**
- Componentes Eletrônicos:
  - Resistores: 1kΩ e 100KΩ
  - Capacitores: 1uF e 47uF

## Procedimentos Práticos

### Tempo de carga/descarga do capacitor

1.  Identifique os **resistores** e **capacitores** a serem utilizados no experimento. Observe que os **capacitores eletrolíticos** tem polaridade, portanto, devem ser montados no circuito considerando os terminais positivo e negativo.
2.  Monte na **matriz de contatos** o **circuito RC** da figura, usando o resistor de 100KΩ e o capacitor de 47uF: <a href="Arquivo:lab_circuitoRC1.png" class="wikilink" title="300px">300px</a> [^2]
3.  Selecione o **canal A** do módulo **Analog Devices M1K** para **Gerar Tensão/Medir Corrente** e o **canal B** para **Medir Voltagem**.
4.  Configure o **canal A** para gerar uma **tensão constante** com 5 V.
5.  Conecte o fio do **canal A** no terminal desconectado do **resistor** de 100KΩ enquanto observa o crescimento da **tensão** medida sobre o **capacitor**, mostrada no **canal B**. O crescimento da tensão sobre o capacitor indica que o mesmo está sendo **carregado**.
6.  Mude a **tensão** gerada pelo **canal A** para 0V e meça o **tempo** para a **tensão** sobre o **capacitor** chegar próximo a zero.
7.  Mude a **tensão** gerada pelo **canal A** para 5V e meça o **tempo** para a **tensão** sobre o **capacitor** chegar próximo 5V. Repita quantas vezes achar necessário para ter uma média do **tempo de carga/descarga** do **capacitor**.

### Forma de onda da carga/descarga do capacitor

1.  Monte na **matriz de contatos** o **circuito RC** da figura, usando o resistor de 1KΩ e o capacitor de 1uF: <a href="Arquivo:lab_circuitoRC2.png" class="wikilink" title="300px">300px</a> [^3]
2.  Configure o **canal A** para gerar uma **onda quadrada** com **amplitude** oscilando entre 0V e 5V e **frequência** de 100Hz.
3.  Observe no **canal B** a **forma de onda** sobre o **capacitor**.
4.  Aumente a **frequência** da **onda quadrada** e observe a **forma de onda** sobre o **capacitor**

## Fundamentos sobre o Capacitor

**Capacitores** são dispositivos que **armazenam energia elétrica** em um **campo elétrico**. Permitem maior fluxo de corrente a medida que a frequência do sinal elétrico aumenta. Para um **sinal senoidal**, a **fase da corrente** é **adiantada** de **90 graus** em relação a **tensão**. A unidade de **capacitância** é o **Faraday (F)**.

Um **capacitor** é formado por duas **placas condutoras** separadas por um material isolante, chamado **dielétrico**. A **carga** de um **capacitor** é criada pela acumulação ou depleção de elétrons livres em cada placa condutora, produzindo um **campo elétrico** no **dielétrico**, e, por consequência, produzindo um **tensão elétrica** entre as placas.

Uma **carga elétrica** (Q) sobre um **capacitor**, produz uma **tensão** (V) entre as placas, em função da **capacitância** (C), segundo a relação:

$`V (Voltz) = \frac{Q (Coulomb)}{C (Faraday)}`$

ou, isolando a carga elétrica:

$`Q = C V`$

A **corrente elétrica** é definida como a quantidade de **carga elétrica** por unidade de **tempo**. É expressa matematicamente como a **derivada da carga elétrica no tempo**:

$`I(t) =  \frac{dQ(t)}{dt} = C \frac{dV(t)}{dt}`$

ou seja, a **corrente** no capacitor é função da **derivada da tensão no tempo**, multiplicada pela capacitância.

A derivada indica que a corrente elétrica no capacitor é maior quanto maior for a variação da tensão. Desta forma, para uma **tensão senoidal**, quanto maior a **frequência**, maior o fluxo da **corrente**. Para uma **tensão constante**, a **corrente** no capacitor é **zero**.

## Fundamentos sobre o Circuito RC

Num **circuito RC** série, quando um **degrau de tensão** é aplicado, inicialmente toda **tensão** aparece toda sobre o **resistor**, pois o **capacitor** está descarregado e a tensão sobre ele é zero. A corrente inicial que fluirá no circuito será dada pela **Lei de Ohm** (I = V / R) e vai ser responsável por iniciar a **carga** do **capacitor**. A medida que o **capacitor** vai sendo **carregado**, a **tensão** sobre ele vai aumentando, diminuindo a tensão resultante sobre o **resistor**, segundo a **<a href="Eletricidade_Básica" class="wikilink" title="Lei de Kirchhoff das Malhas">Lei de Kirchhoff das Malhas</a>**, e, consequentemente, diminuindo também a **corrente** no circuito. Quanto o **capacitor** se **carregar** totalmente, a tensão de 5V estará toda sobre o capacitor e a **corrente** no circuito será reduzida a **zero**.

<a href="Arquivo:CircuitoRC.png" class="wikilink" title="Arquivo:CircuitoRC.png">Arquivo:CircuitoRC.png</a>

O processo de **carga do capacitor** segue uma curva que **desacelera exponencialmente** a medida que a tensão sobre o capacitor aumenta. A **taxa de crescimento** da **carga do capacitor** depende do produto **RC**, chamado de **constante de tempo** (segundos) e é representado pela letra grega tau (τ). Numa **constante de tempo** o **capacitor** é carregado com **63%** de sua **carga**. Em cinco **constantes de tempo** a carga do capacitor chega a 99.3%. O tempo da carga total tende ao infinito, entretanto, na prática, considera-se que em cinco **constantes de tempo** o capacitor está carregado.

Num **circuito RC** série, a **tensão sobre o capacitor** (V<sub>C</sub>), em função da tensão total aplicada (V<sub>T</sub>) é dada pela expressão:

$`V_C(t) = V_T (1 - e^{-t/\tau})`$

No primeiro circuito, a **constante de tempo** era de (100 KΩ)\*(47 μF) = 4.7 segundos, fazendo com que a **carga/descarga** total do capacitor fosse de cerca de 23,5 segundos.

## Observações e Conclusões

- **Capacitores** armazenam **energia elétrica**.
- Quando **capacitores** estão sendo **carregados** usando uma fonte de **tensão** em **série** com um **resistor**, a taxa da carga do capacitor **desacelera exponencialmente**.
- Um **circuito RC** é caracterizado pelo **produto RC**, chamado **constante de tempo**.
- Em **uma constante de tempo** o capacitor é carregado com **63%** da tensão aplicada sobre o circuito RC.
- Comumente se aceita que o **capacitor** está **totalmente** carregado em **cinco constantes de tempo**.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 15h40min de 3 de julho de 2020 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>

[^1]: <https://wiki.analog.com/university/courses/engineering_discovery/lab_2>

[^2]:

[^3]:
