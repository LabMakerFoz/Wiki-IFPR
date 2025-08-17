# Laboratório: Introdução aos Diodos e Leds

Este laboratório foi baseado no material disponibilizado pela **Analog Devices**, fabricante do módulo educacional **M1K Analog Devices**: [^1]

## Objetivos

Conhecer o funcionamento básico dos **diodos de sinal** e dos **leds** (**diodos emissores de luz**).

## Equipamento e Materiais

- Modulo **Analog Devices M1K** e software **Pixelpulse**
- Componentes Eletrônicos:
  - Resistor: 100 Ω e 470 Ω
  - Leds vermelho, verde e amarelo
  - Diodo 1N914

## Procedimentos Práticos

### Funcionamento dos Leds

1.  Identifique os **leds** e o **diodo** que serão utilizados no experimento. Observe a **polaridade**, **anodo** (positivo) e **catodo** (negativo), dos **leds** e do **diodo**. Tanto **leds** quanto **diodos** somente **conduzem corrente** somente quando **polarizados diretamente**, ou seja, do anodo para o catodo.
2.  Na configuração do módulo **Analog Devices M1K**, desabilite *Repeated Mode* e habilite *X-Y plots*.
3.  Selecione o **canal A** para gerar uma **onda triangular** variando entre 0 V e 2.0 V e **frequência** de 10 Hz.
4.  Usando a **matriz de contatos** e fios, conecte o **terra** ao catodo e o **canal A** ao anodo do **led amarelo**
5.  Ajuste a escala do **eixo Y** do **gráfico X-Y** para medir corrente na faixa de 0.00 A até 0.09 A (90 mA), usando o botão direito do mouse.
6.  Observe o **led piscando**, a forma de **onda triangular** aplicada sobre o **led**, a **forma de onda** da **corrente** e também o **gráfico X-Y**, que mostra a **corrente versus tensão** sobre o led.
7.  Varie a tensão de pico da **onda triangular** de 1,8 V até 2,4 V e observe na **forma de onda** da **corrente** o ponto em que o **led** começa a conduzir (próximo de 2 V). Analise também o **gráfico X-Y** e identifique a **tensão** em que a **corrente** sobre o **led** começa a aumentar.
8.  Repita os procedimentos para o **led vermelho** e **verde** e compare os resultados.

Análises dos dados  

- A análises da **formas de onda** da **corrente** e dos **gráfico X-Y** mostram que os **leds amarelo, vermelho e verde** começam a conduzir em tensões diferentes, entre 1,7 e 2,2 V. Isto é devido ao espectro de frequência da luz emitida pelo led. Na prática considera-se a **tensão de condução** dos **leds** em **2 V**.
- Outra questão que as curvas características da **corrente versus tensão** mostram é um aumento rápido da corrente com a tensão a partir do ponto de condução. Portanto, é obrigatório conectar um **resistor** em **série** com o **led** para limitar a corrente. Caso contrário o **led** poderá queimar.

### Funcionamento dos Diodos

1.  Altere a **onda triangular** gerada pelo **canal A** variar entre 0 V e 0,6 V e e troque o led pelo **diodo 1N914**, observando a polaridade do diodo.
2.  Ajuste a escala do **eixo Y** do **gráfico X-Y** para medir corrente na faixa de 0.00 A até 0.09 A (90 mA).
3.  Varie a tensão de pico da **onda triangular** de 0,5 V até 0,9 V e observe na **forma de onda** da **corrente** o ponto em que o **diodo** começa a conduzir (próximo de 0,7 V). Analise também o **gráfico X-Y** e identifique a **tensão** em que a **corrente** sobre o **diodo** começa a aumentar.

Análises dos dados  

- A análise do **gráfico X-Y** para o **diodo de sinal** mostra que o mesmo é mais preciso que as **curvas I versus V** dos **leds**, pois estes componentes são construídos justamente para operarem em circuitos de precisão.

### Resistor de proteção dos Leds

1.  Selecione o **canal A** para gerar uma **tensão constante** de 5 V e o **canal B** para **Medir Tensão**.
2.  Monte na matriz de contatos o circuito com **resistor** de 100 Ω e **led amarelo** da figura: <a href="Arquivo:lab_led.png" class="wikilink" title="300px">300px</a> [^2]
3.  Verifique a **tensão** sobre o **led** no **canal B** e a **corrente** no circuito no **canal A**. Compare o valor da corrente com o valor teórico calculado.
4.  Repita o procedimento para os leds vermelho e verde.
5.  Troque o **resistor** por um de 470 Ω, verifique a diferença no **brilho** do **led** e também a nova **corrente** no circuito.

## Fundamentos sobre Diodos e Leds

- **<a href="Diodos" class="wikilink" title="Diodos">Diodos</a>**
- **<a href="Leds" class="wikilink" title="Leds">Leds</a>**

## Observações e Conclusões

- **Diodos** e **leds** (ideais) conduzem **corrente** em um único sentido e se comportam como um circuito aberto no sentido contrário.
- Os **diodos** são construídos de **junções pn** de materiais **semicondutores** e apresentam uma característica **exponencial** na **relação I/V**, conduzindo corrente a partir da tensão de condução.
- As **junções pn** emitem **fótons** e são utilizados para produzirem **leds** de várias cores.
- Quando em condução **leds** (ou diodos) apresentam resistência muito baixa, portanto, necessitam de **resistores** para **limitar** a corrente sobre o **led** (ou diodo).
- **Diodos de silício** têm a tensão de condução em torno de 0,7 V. **Diodos de germânio** têm a tensão de condução em torno de 0,2 V.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 12h29min de 6 de julho de 2020 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>

[^1]: <https://wiki.analog.com/university/courses/engineering_discovery/lab_8>

[^2]:
