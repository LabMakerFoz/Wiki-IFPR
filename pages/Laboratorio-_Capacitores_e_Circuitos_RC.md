# Laboratório: Introdução aos Capacitores e Circuitos RC

## Objetivos

Conhecer os **capacitores**, que são dispositivos que **armazenam energia elétrica** em um campo elétrico.

Conhecer o princípio de funcionamento dos **circuitos RC** de forma a poder explicar como um **capacitor** é carregado quando um degrau de tensão é aplicado em seus terminais.

## Equipamento e Materiais

Equipamentos  

- **Bancada de Eletrônica** com **fonte de tensão**, **gerador de funções**, **multímetro** e **osciloscópio**.

ou

- **Simulador de circuitos eletrônicos**: **[SimulIDE](https://www.simulide.com)**.

<!-- -->

- Componentes Eletrônicos:
  - Resistores: 1kΩ e 100KΩ
  - Capacitores: 1uF e 47uF

## Procedimentos Práticos

### Tempo de carga/descarga do capacitor

1.  Monte no **SimulIDE** um circuito com uma fonte de **tensão constante** com 5 V alimentando um circuito RC série, com resistor de 100 kΩ e capacitor de 47 μF.
      
    <a href="Arquivo:CircuitoRC.png" class="wikilink" title="Arquivo:CircuitoRC.png">Arquivo:CircuitoRC.png</a>

    V = 5V; R = 100 kΩ; C = 47 μF
2.  Utilize o osciloscópio para observar o crescimento da tensão sobre o **capacitor** no momento em que a fonte de tensão for ligada. O crescimento da tensão sobre o capacitor indica que o mesmo está sendo **carregado**.
3.  Desligue a fonte de tensão (0 V) e meça o **tempo** para a **tensão** sobre o **capacitor** chegar próximo a zero.
4.  Ligue novamente a fonte de tensão (5 V) e meça o **tempo** para a **tensão** sobre o **capacitor** chegar próximo 5V. Repita quantas vezes achar necessário para ter uma média do **tempo de carga/descarga** do **capacitor**.
5.  Confira se o valor do tempo de carga/descarga do capacitor está de acordo com o valor teórico. No caso, C = 47 μF e R = 100 KΩ a **constante de tempo** calculada é de 4.7 segundos. Desta forma, a **carga/descarga** do capacitor fica em cerca de 23,5 segundos.

### Forma de onda da carga/descarga do capacitor

1.  Modifique o **circuito RC** usando o resistor de 1KΩ e o capacitor de 1μF.
2.  Substitua a fonte de tensão por um **gerador de funções**, configurado para gerar uma **onda quadrada** com **amplitude** oscilando entre 0V e 5V e **frequência** de 100Hz.
3.  Utilize o canal 1 osciloscópio para observar a **forma de onda** gerada pelo **gerador de funções** e o canal 2 para observar a forma de onda sobre o **capacitor**.
4.  Aumente gradualmente a **frequência** da **onda quadrada** e observe a **forma de onda** sobre o **capacitor**.

## Observações e Conclusões

- **Capacitores** armazenam **energia elétrica**.
- Quando **capacitores** estão sendo **carregados** usando uma fonte de **tensão** em **série** com um **resistor**, a taxa da carga do capacitor **desacelera exponencialmente**.
- Um **circuito RC** é caracterizado pelo **produto RC**, chamado **constante de tempo**.
- Em **uma constante de tempo** o capacitor é carregado com **63%** da tensão aplicada sobre o circuito RC.
- Comumente se aceita que o **capacitor** está **totalmente** carregado em **5 constantes de tempo**.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 15h39min de 10 de setembro de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>
