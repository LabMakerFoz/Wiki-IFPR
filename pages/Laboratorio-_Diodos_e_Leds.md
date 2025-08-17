# Laboratório: Introdução aos Diodos e Leds

## Objetivos

Conhecer o funcionamento básico dos **diodos de sinal** e dos **leds** (**diodos emissores de luz**).

## Equipamento e Materiais

Equipamentos  

- **Bancada de Eletrônica** com **fonte de tensão**, **gerador de funções**, **multímetro** e **osciloscópio**.

ou

- **Simulador de circuitos eletrônicos**: **[SimulIDE](https://www.simulide.com)**.

<!-- -->

- Componentes Eletrônicos:
  - Resistores
  - Leds
  - Diodo

## Procedimentos Práticos

### Funcionamento dos Diodos

1.  Monte no **SimulIDE** um circuito com um **gerador de funções**, configurado para gerar uma **onda triangular** com **amplitude** oscilando entre 0V e 5V e **frequência** de 100Hz, alimentando um circuito com um **resistor** de 100 Ω em série com um **diodo**.
      
    <a href="Arquivo:CircuitoDiodo3.png" class="wikilink" title="Arquivo:CircuitoDiodo3.png">Arquivo:CircuitoDiodo3.png</a>
2.  Utilize o canal 1 **osciloscópio** para observar a **forma de onda** gerada pelo **gerador de funções** e o canal 2 para observar a forma de onda sobre o **diodo**.
3.  Analise as formas de onda e verifique a tensão na qual o diodo entra em condução. Note que, quando o diodo está conduzindo, a queda de tensão sobre ele permanece constante.
4.  Substitua o gerador de funções por uma **fonte de tensão** constante de 5 V e use um amperímetro para medir a corrente circulando no circuito. Compare com o valor teórico da corrente.
5.  Substitua o diodo por um led e repita os procedimentos anteriores.

Análises dos dados  

- Tanto os **diodos** quanto os **leds** conduzem quando polarizados diretamente a partir de uma **tensão de condução**, de 0,7 V e 2 V, respectivamente.
- Quando em condução o **diodo**, ou o **led**, apresenta uma **queda de tensão direta** e se comporta como um curto circuito, portanto, é obrigatório conectar um **resistor** em **série** com o mesmo para **limitar a corrente**. Caso contrário o diodo, ou o led, poderá queimar.

### Retificador de meia onda

1.  Monte no **SimulIDE** um circuito **retificador de meia onda**, alimentado por **gerador de funções**, configurado para gerar uma **onda senoidal** com **amplitude** oscilando entre -5 V e 5 V e **frequência** de 100Hz, utilizando como carga um **resistor** de 1 kΩ.
    - Para ajustar a amplitude da onda gerada entre -5 V e 5 V, defina a voltagem como 5 V e a voltagem base 0 V.

      
    <a href="Arquivo:RetificadorMeiaOnda.png" class="wikilink" title="Arquivo:RetificadorMeiaOnda.png">Arquivo:RetificadorMeiaOnda.png</a>
2.  Utilize o canal 1 **osciloscópio** para observar a **forma de onda** gerada pelo **gerador de funções** e o canal 2 para observar a forma de onda sobre o **resistor**.
3.  Analise as formas de onda e verifique a forma de onda retificada sobre a carga.
4.  Acrescente um capacitor de 10 uF em paralelo com o resistor e verifique a forma de onda sobre a carga. Altere o capacitor para 100 uF e verifique novamente a forma de onda sobre a carga.

Análises dos dados  

- Note que o circuito com o capacitor em paralelo com a carga é o **detector de pico**.
- No caso de circuitos retificadores um capacitor também pode ser utilizado como **filtro**, visando alisar a onda retificada. Quanto maior o capacitor, menor a ondulação da onda retificada.

## Observações e Conclusões

- **Diodos** (ideais) conduzem **corrente** em um único sentido e se comportam como um circuito aberto no sentido contrário.
- **Diodos de silício** têm a tensão de condução em torno de 0,7 V. **Diodos de germânio** têm a tensão de condução em torno de 0,2 V.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 12h29min de 6 de julho de 2020 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>
