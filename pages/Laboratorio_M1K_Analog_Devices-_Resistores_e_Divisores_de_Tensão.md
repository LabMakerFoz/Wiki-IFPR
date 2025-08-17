# Laboratório: Introdução aos Resistores e Divisores de Tensão

Este laboratório foi baseado no material disponibilizado pela **Analog Devices**, fabricante do módulo educacional **M1K Analog Devices**: [^1], [^2]

## Objetivos

Conhecer os **resistores elétricos**, que são dispositivos que se opõem a passagem de **corrente elétrica** e controlam a relação instantânea entre a **tensão** e a **corrente** de acordo com a **<a href="Eletricidade_Basica" class="wikilink" title="Lei de Ohm">Lei de Ohm</a>**. A unidade de **resistência elétrica (R)** é o **Ohm (Ω)**.

Conhecer os **divisores de tensão**, que são circuitos formados por **resistores**, capazes de dividir uma **tensão elétrica** em tensões menores, dependendo do tamanho dos resistores utilizados.

## Equipamento e Materiais

- Modulo **Analog Devices M1K** e software **Pixelpulse**
- Componentes Eletrônicos:
  - Resistores: 68 Ω, 100 Ω, 330kΩ, 1kΩ 1k5Ω 2K2 Ω, 4K7 Ω e 1 M Ω.

## Procedimento para teste do módulo Analog Devices M1K e software Pixelpulse

1.  Rodar o software **Pixelpulse** e conectar o módulo **Analog Devices M1K** usando cabo USB.
2.  Ativar a **medição de sinais/geração de sinais** com a o botão **flecha** (*play*).
3.  Observe que o módulo pode **Medir Voltagem**, **Gerar Voltagem/Medir Corrente** e **Gerar Corrente/Medir Voltagem**.
4.  Configure o equipamento para **Gerar Voltagem/Medir Corrente** no **canal A** e **Medir Voltagem** no **canal B** usando fios para conexão.
5.  Selecione o **canal A** para gerar uma **onda senoidal**.
6.  Observe no **canal B** a onda gerada.
7.  Observe a **amplitude** a a **frequência** do sinal. Altere **amplitude** a a **frequência** do sinal e observe o resultado.
8.  Teste as outras formas de onda disponíveis: **triangular**, **quadrada** e **dente de serra**.

## Procedimentos Práticos

### <a href="Resistores" class="wikilink" title="Resistores">Resistores</a>

1.  Identifique usando o **<a href="Resistores" class="wikilink" title="código de cores">código de cores</a>** os seguintes **resistores**: 68 Ω, 100 Ω, 330kΩ, 1kΩ 1k5Ω 2K2 Ω, 4K7 Ω e 1 M Ω.
2.  Selecione o **canal A** do módulo **Analog Devices M1K** para gerar uma **'tensão constante** com 5 V e o **canal B** para **Medir Voltagem**.
3.  Use a **matriz de contatos** para montar um circuito com um **resistor** de 100 Ω e aplique a **tensão constante** sobre o resistor. Observe o valor da **corrente** sobre o resistor no Canal A.
4.  Usando a **<a href="Eletricidade_Basica" class="wikilink" title="Lei de Ohm">Lei de Ohm</a>** verifique se o valor da **corrente** medido corresponde ao valor calculado.
5.  Selecione o **canal A** do módulo para gerar uma **onda senoidal** com 5 Vpp e o **canal B** para **Medir Voltagem**.
6.  Observe a **forma de onda** da **tensão** sobre o resistor no **canal B** e a **forma de onda** da **corrente** consumida pelo resistor no **canal** A. Verifique que as formas de onda são idênticas e em fase, diferindo apenas na amplitude.
7.  Monte na **matriz de contatos** dois **resistores em série** de 100 Ω. Aplique sobre eles uma **tensão constante** de 5V e verifique a **corrente** circulando no circuito. Calcule o <a href="Resistores" class="wikilink" title="resistor série">resistor série</a> resultante e o valor da corrente e compare com o valor medido.
8.  Monte na **matriz de contatos** dois **resistores em paralelo** de 100 Ω. Aplique sobre eles uma **tensão constante** de 5V e verifique a **corrente** circulando no circuito. Calcule o <a href="Resistores" class="wikilink" title="resistor paralelo">resistor paralelo</a> resultante e o valor da corrente e compare com o valor medido.

### <a href="Divisor_de_Tensao" class="wikilink" title="Divisor de Tensão">Divisor de Tensão</a>

1.  Monte na **matriz de contatos** o circuito **divisor de tensão** da figura usando resistores de 1kΩ e 1k5Omega;: <a href="Arquivo:lab_div_tensao1.png" class="wikilink" title="300px">300px</a> [^3]
2.  Selecione o **canal A** do módulo **Analog Devices M1K** para gerar uma **tensão constante** com 5 V e o **canal B** para **Medir Voltagem**.
3.  Observe a **tensão** no **<a href="Divisor_de_Tensao" class="wikilink" title="divisor de tensão">divisor de tensão</a>** mostrada no **canal B** e verifique se corresponde ao valor calculado.
4.  Observe o valor da **corrente** sobre o circuito divisor de tensão no **canal A** e verifique se corresponde ao valor calculado.
5.  Utilize no **circuito divisor** de tensão **dois resistores iguais** a 1kΩ e repita os procedimentos anteriores.

## Observações e Conclusões

- **Resistores** são elementos **passivos**, utilizados para **limitar a corrente elétrica** em **circuitos elétricos e eletrônicos**.
- A **voltagem** sobre um **resistor** em um **circuito série** é uma fração da voltagem total sobre o circuito.
- A **voltagem** sobre um **resistor** em um **circuito série** pode ser determinada pela regra do **divisor de tensão**.
- A **corrente** sobre um **resistor** em um **circuito paralelo** é uma fração da corrente total sobre o circuito.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 15h40min de 26 de junho de 2020 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>

[^1]: <https://wiki.analog.com/university/courses/engineering_discovery/lab_1>

[^2]: <https://wiki.analog.com/university/courses/engineering_discovery/lab_13>

[^3]:
