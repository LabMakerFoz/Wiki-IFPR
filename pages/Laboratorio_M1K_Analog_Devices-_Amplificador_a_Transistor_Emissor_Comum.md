# Laboratório: Amplificador a Transistor Emissor Comum

Este laboratório foi baseado no material disponibilizado pela **Analog Devices**, fabricante do módulo educacional **M1K Analog Devices**: [^1]

## Objetivos

Montar, testar e analisar o circuito de **amplificador a transistor emissor comum**. O amplificador foi projetado com **ganho** 5 e é capaz de alimentar uma **carga** de 1 KΩ com um **sinal senoidal** de 2 Vpp e **acoplamento AC**.

O experimento permitirá observar o **sinal senoidal de entrada** (vin) e o **sinal senoidal de saída** (vout) acrescido do **ganho de amplificação**.

## Equipamento e Materiais

- Modulo **Analog Devices M1K** e software **Pixelpulse**
- Componentes Eletrônicos:
  - Resistores: 10 Ω, 47 Ω, 100 Ω, 470 Ω, 1 k KΩ, 1,5 KΩ e 6,8 KΩ
  - Capacitores: 47 uF e 220 uF
  - Transistor NPN 2N3904

## Procedimentos Práticos

1.  Usando a **matriz de contatos** e fios, monte o **circuito amplificador emissor** comum, usando o **transistor 2N3904**, como ilustrado na figura: <a href="Arquivo:lab_amplificador_ec.png" class="wikilink" title="600px">600px</a> [^2]
2.  Configure o módulo **Analog Devices M1K** para **Gerar Voltagem/Medir Corrente** no **canal A** e **Medir Voltagem** no **canal B**.
3.  Configure o **canal A** para gerar um **sinal senoidal** variando entre 2,3 V e 2,7 V e **frequência** de 100 Hz.
4.  Observe no **canal B** a a **forma de onda senoidal** da voltagem sobre a **carga** de 1 KΩ oscilando +/- 1 V em torno da tensão base de 2,5 V e com defasagem de 180 graus em relação ao sinal de entrada. A onda senoidal está em torno de 2,5 V devido a referência da carga ter sido colocada nesta tensão.
5.  Remova o **sinal de entrada** e meça as tensões DC na **base**, **emissor** e **coletor** do transistor. Estas foram as tensões de projeto do amplificador.
6.  **Analise** o projeto do circuito e verifique os valores calculados em função dos valores práticos medidos.

### Gráficos das entradas e saídas do amplificador

<a href="Arquivo:AnaliseAmplificadorEC.png" class="wikilink" title="800px">800px</a>

## Cálculos teóricos

Fundamentos sobre Transistores  
**<a href="Transistores" class="wikilink" title="Transistores">Transistores</a>**

Cálculos utilizados no projeto do laboratório:

- Cálculo de Vb usando divisor de tensão:

`Vb = Rb2 / (Rb1 + Rb2) Vcc = 1,7 kΩ / (6,8 kΩ + 1,7  kΩ) . 5 V = 0,2 (5 V) = 1,0 V`

- Cálculo de Ib a partir da corrente Ie e do ganho:

`Ie = (1 V - 0,7 V) / 57 Ω = 5,3 mA`  
`Β = 200`  
`Ib = Ie / Β = 26,5 uA`

  
Esta corrente Ib, todavia, provoca uma queda na tensão Vb, uma vez que flui pelo paralelo dos resistores Rb1 e Rb2 da base. Portanto, pode-se ajustar este valor, calculando esta queda de tensão:

`Ib (Rb1 // Rb2) = (26.5 uA)(6.8 KΩ||1.7 KΩ) ≈ 36 mV`

  
Assim, podemos recalcular Vb e Ie:

`Vb = 1,0 V - 0,036 V = 0,96 V`  
`Ie = (0,96 - 0,7) / 57 Ω = 4.6 mA`

- Cálculo de Ic usando Ic ≈ Β Ib ≈ Ie:

`Ic = 4,6 mA`

- Cálculo de Vce a partir da análise das tensões na malha sobre Rc e Re:

`Vcc = Rc Ic + Vce + Re Ic`  
`Vce = Vcc - Rc Ic - Re Ic`  
`Vce = 5 V - (470 Ω 4,6 mA) - (57 Ω 4,6 mA)  = 5 V - 2,16 V - 0,26 V =  2,58 V`

`Vc = 2,84 V`  
`Ve = 0,26 V`

## Observações e Conclusões

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 17h04min de 8 de julho de 2020 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>

[^1]: <https://wiki.analog.com/university/courses/engineering_discovery/lab_10>

[^2]:
