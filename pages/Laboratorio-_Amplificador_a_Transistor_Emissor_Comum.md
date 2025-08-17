# Laboratório: Amplificador a Transistor Emissor Comum

Este laboratório foi baseado no material disponibilizado pela **Analog Devices**, fabricante do módulo educacional **M1K Analog Devices**: [^1]

## Objetivos

Montar, testar e analisar o circuito de **amplificador a transistor emissor comum**. O amplificador foi projetado com **ganho 5** e é capaz de alimentar uma **carga** de 1 KΩ com um **sinal senoidal** de 2,5 Vpp e **acoplamento AC**.

O experimento permitirá observar o **sinal senoidal de entrada** (vin) e o **sinal senoidal de saída** (vout) acrescido do **ganho de amplificação**.

## Equipamento e Materiais

Equipamentos  

- **Bancada de Eletrônica** com **fonte de tensão**, **gerador de funções**, **multímetro** e **osciloscópio**.

ou

- **Simulador de circuitos eletrônicos**: **[SimulIDE](https://www.simulide.com)**.

<!-- -->

- Componentes Eletrônicos:
  - Resistores: 10 Ω, 47 Ω, 100 Ω, 470 Ω, 1 k KΩ, 1,5 KΩ e 6,8 KΩ (Valores comerciais)
  - Capacitores: 47 uF e 220 uF
  - Transistor NPN 2N3904

## Procedimentos Práticos

1.  Monte no **SimulIDE** um circuito **Amplificador EC**, polarizado com uma fonte de tensão constante de 5 V.

<a href="Arquivo:AmplificadorEC.png" class="wikilink" title="Arquivo:AmplificadorEC.png">Arquivo:AmplificadorEC.png</a>

`Vcc =  5 V`  
`Rb1 = 6,8 kΩ`  
`Rb2 = 1,7 kΩ`  
`Rc  = 470 Ω`  
`Re  = 57 Ω`  
`Rl  = 1 kΩ`  
`Cin = Cout = 47 µF (Capacitores eletrolíticos -> polaridade + voltada ao transistor)`  
`Não utilizar Cd`

1.  Configure como **entrada do amplificador** (v<sub>in</sub>) um **gerador de funções**, configurado para gerar uma **onda senoidal** com **amplitude** de 500 mV e voltagem base de -250 mV (senoide variando de -250 mV a 250 mV) e **frequência** de 100Hz.
2.  Utilize o canal 1 osciloscópio para observar a **forma de onda** gerada pelo **gerador de funções** (v<sub>in</sub>) e o canal 2 para observar a forma de onda sobre a **saída do amplificador** (v<sub>out</sub>).
      
    Observe que a senoide de saída varia de -1,25 V a 1,25 V, ganho 5, e com defasagem de 180 graus em relação ao sinal de entrada.
3.  Varie o valor do **resistor Rc** para valores ligeiramente acima e abaixo do valor e verifique como se comporta o **ganho do amplificador**.
      
    Observe que a partir de um certo valor do ganho, o amplificador não consegue amplificar, pois ultrapassa a excursão máxima do sinal, que é dada pela alimentação de 5 V.
4.  Remova o **sinal de entrada** e meça as tensões DC na **base**, **emissor** e **coletor** do transistor.
5.  **Analise** o projeto do circuito e verifique os valores calculados em função dos valores práticos medidos. Os valores de projeto do amplificador estão dados abaixo.

### Gráficos das entradas e saídas do amplificador

<a href="Arquivo:Anplicicador_EC-entradas_saidas.png" class="wikilink" title="500px">500px</a>

## Cálculos teóricos

Fundamentos sobre Transistores  
**<a href="Transistores" class="wikilink" title="Transistores">Transistores</a>**

Cálculos utilizados no projeto do laboratório:

- Cálculo de Vb usando divisor de tensão:

`Vb = Rb2 / (Rb1 + Rb2) Vcc = 1,7 kΩ / (6,8 kΩ + 1,7  kΩ) . 5 V = 0,2 (5 V) = 1,0 V`

- Cálculo de Ib a partir da corrente Ie e do ganho:

`Ie = (1 V - 0,7 V) / 57 Ω = 5,3 mA`  
`β = 200`  
`Ib = Ie / β = 26,5 uA`

  
Esta corrente Ib, todavia, provoca uma queda na tensão Vb, uma vez que flui pelo paralelo dos resistores Rb1 e Rb2 da base. Portanto, pode-se ajustar este valor, calculando esta queda de tensão:

`Ib (Rb1 // Rb2) = (26.5 uA)(6.8 KΩ||1.7 KΩ) ≈ 36 mV`

  
Assim, podemos recalcular Vb e Ie:

`Vb = 1,0 V - 0,036 V = 0,96 V`  
`Ie = (0,96 - 0,7) / 57 Ω = 4.6 mA`

- Cálculo de Ic usando Ic ≈ β Ib ≈ Ie:

`Ic = 4,6 mA`

- Cálculo de Vce a partir da análise das tensões na malha sobre Rc e Re:

`Vcc = Rc Ic + Vce + Re Ic`  
`Vce = Vcc - Rc Ic - Re Ic`  
`Vce = 5 V - (470 Ω 4,6 mA) - (57 Ω 4,6 mA)  = 5 V - 2,16 V - 0,26 V =  2,58 V`

`Vc = 2,84 V`  
`Ve = 0,26 V`

## Observações e Conclusões

- A **excursão do sinal amplificado** é limitada pela tensão de alimentação da polarização do transistor.
- Os **capacitores de acoplamento** permitem isolar a alimentação CC do circuito de polarização do sinal CA que será amplificado.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h10min de 27 de setembro de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>

[^1]: <https://wiki.analog.com/university/courses/engineering_discovery/lab_10>
