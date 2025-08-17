# Laboratório: Introdução aos Transistores

Este laboratório foi baseado no material disponibilizado pela **Analog Devices**, fabricante do módulo educacional **M1K Analog Devices**: [^1]

## Objetivos

Conhecer o princípio de funcionamento de um **transistor de junção bipolar**, observando a **corrente do coletor** (Ic) versus a **tensão do coletor ao emissor** (Vce), para diferentes valores da **corrente de base** (Ib). Calcular o **ganho** (Β) aproximado do transistor para os valores observados.

## Equipamento e Materiais

- Modulo **Analog Devices M1K** e software **Pixelpulse**
- Componentes Eletrônicos:
  - Resistores: 200 KΩ
  - Transistor NPN 2N3904

## Procedimentos Práticos

1.  Usando a **matriz de contatos** e fios, monte o circuito com o **transistor 2N3904**, como ilustrado na figura: <a href="Arquivo:lab_transistor.png" class="wikilink" title="400px">400px</a> [^2]
2.  Selecione o **canal A** do módulo **Analog Devices M1K** para **Gerar Tensão/Medir Corrente** e o **canal B** para **Medir Voltagem**.
3.  Configure o **canal A** para gerar uma **onda triangular** variando entre 0 V e 5.0 V e **frequência** de 20 Hz.
4.  Habilite **X-Y plots**.
5.  Ajuste a escala do **eixo Y** do **gráfico X-Y** para medir corrente na faixa de 0.000 A até 0.009 A (9 mA), usando o botão direito do mouse.
6.  Ajuste a escala da **forma de onda da voltagem** em torno de 0,7 V, de forma que pequenas variações possam ser observadas com boa resolução no **canal B**.
7.  Observe a característica **Ic versus Vce** do transistor com um resistor de 200 KΩ na base do circuito.
8.  Observe a corrente **Ic** ao longo do tempo no **canal A** e note as amplas regiões onde a **corrente** é relativamente constante com a variação de **Vce**, quando o transistor está operando na região **ativa**, e os mergulhos quando o transistor está operando na região de **saturação**.
9.  Meça a **corrente** na região onde ela permanece constante.
10. Observe que a **tensão base-emissor**, **Vbe**, é aproximadamente 0,7 V na região **ativa** e mergulha quando o transistor está operando na região de **saturação**.
11. A **corrente Ib** pode ser determinada a partir da voltagem sobre Rb, que é 2,5 V menos a tensão Vbe, ou seja aproximadamente 1,8 V. Aplicando a Lei de Ohm, obtemos Ib ≈ (1,8 V)/(200 KΩ) ≈ 9 μA.
12. Calcule o **ganho** do transistor **Β = Ic / Ib**.
13. Acrescente outro resistor de 200 KΩ em paralelo ao resistor de **Rb** e refaça as observações. Como ficou a corrente **Ic** na região ativa?
14. Acrescente mais um resistor de 200 KΩ em paralelo ao resistor de **Rb** e refaça as observações.

Análise dos dados  

<a href="Arquivo:AnaliseTransistorNPN.png.png" class="wikilink" title="800px">800px</a>

Considerando Rb = 200 KΩ:

- Ic = 4 mA na região ativa
- Vbe = 0,7 V na região ativa
- Ib ≈ 9 μA
- Β = Ic / Ib = 444

Considerando Rb = 100 KΩ (dois resistores de 200 KΩ em paralelo):

- Ic = 8 mA na região ativa
- Vbe = 0,71 V na região ativa

## Fundamentos sobre Transistores

- **<a href="Transistores" class="wikilink" title="Transistores">Transistores</a>**

## Observações e Conclusões

- O **transistor bipolar** funciona como um **amplificador de corrente** com ganho definido por **Β**.
- Para um **ganho** alto (**Β \> 100**) podemos ignorar a **corrente de base** (Ib ≈ 0) e dizer que a **corrente do emissor** é igual a **corrente do coletor** (**Ie ≈ Ic**).
- Na região ativa a **tensão base emissor** é aproximadamente **0,7 V**.
- O **transistor bipolar**, na região ativa, produz uma **corrente de coletor** (**Ic**) constante independente do valor da **tensão coletor emissor** (**Vce**).

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 09h49min de 7 de julho de 2020 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>

[^1]: <https://wiki.analog.com/university/courses/engineering_discovery/lab_9>

[^2]:
