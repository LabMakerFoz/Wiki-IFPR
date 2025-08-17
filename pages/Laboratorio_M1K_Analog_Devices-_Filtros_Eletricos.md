# Laboratório: Introdução aos filtros elétricos

Este laboratório foi baseado no material disponibilizado pela **Analog Devices**, fabricante do módulo educacional **M1K Analog Devices**: [^1]

## Objetivos

Conhecer o princípio de funcionamento dos **filtros elétricos RC passa baixa e passa alta**.

Conhecer e testar um circuito **detector de pico**, com diodo e capacitor, visando detectar a **máxima amplitude** do sinal de saída de um **filtro elétrico**.

Conhecer e testar um circuito **comparador de tensão** com saída binária, visando acionar um dispositivo quando uma dada tensão for atingida.

## Equipamento e Materiais

- Modulo **Analog Devices M1K** e software **Pixelpulse**
- Componentes Eletrônicos:
  - Resistores: 68Ω,100Ω 10KΩ, 200KΩ
  - Capacitores: 10uF, 22uF e 47uF
  - Leds
  - Diodo 1N914
  - Circuito Integrado AD8561

## Procedimentos Práticos

### Filtro passa baixa

1.  Identifique os **resistores** e **capacitores** a serem utilizados no experimento. Observe que os **capacitores eletrolíticos** tem polaridade, portanto, devem ser montados no circuito considerando os terminais positivo e negativo.
2.  Monte na **matriz de contatos** o **filtro RC** da figura, usando o resistor de 68Ω e o capacitor de 22uF: <a href="Arquivo:lab_filtroRC_PB.png" class="wikilink" title="400px">400px</a> [^2]
3.  Selecione o **canal A** do módulo **Analog Devices M1K** para **Gerar Tensão/Medir Corrente** e o **canal B** para **Medir Voltagem**.
4.  Configure o **canal A** para gerar uma **onda senoidal** com 10 Hz de frequência e tensão variando de 0 V a 5 V. Observe no **canal B** a forma de onda sobre o capacitor.
5.  Gradualmente aumente a **frequência** da **onda senoidal** até 1000 Hz e observe no **canal B** a redução da amplitude da forma de onda sobre o capacitor.
6.  Ajuste a frequência da **onda senoidal** no **canal A** até que a amplitude da onda no **canal B** seja 3,5 V, ou seja, 70,7% da amplitude da entrada (5 . 0,707 ≈ 3,5).

### Filtro passa alta

1.  Monte na **matriz de contatos** o **filtro RC** da figura, usando o resistor de 68Ω e o capacitor de 10uF. Observe que o **resistor** está conectado a tensão de 2,5 V e não ao terra: <a href="Arquivo:lab_filtroRC_PA.png" class="wikilink" title="400px">400px</a> [^3]
2.  Configure o **canal A** para gerar uma **onda senoidal** com 10 Hz de frequência e tensão variando de 0 V a 5 V. Observe no **canal B** a forma de onda sobre o capacitor.
3.  Gradualmente aumente a **frequência** da **onda senoidal** até 1000 Hz e observe no **canal B** o aumento da amplitude da forma de onda sobre o capacitor.
4.  Ajuste a frequência da **onda senoidal** no **canal A** até que a amplitude da onda no **canal B** seja 3,5 V.

Análise do circuito  
É importante notar que o **resistor** no **filtro passa alta** está conectado a referência de tensão de 2,5 V e não ao terra. Isto é necessário pois o **filtro passa alta** não permite a passagem de **corrente contínua** (CC), podendo ser visto como um circuito que remove a componente de corrente contínua do sinal. O nível tensão CC (2,5 V) do outro lado do resistor ajusta a componente CC da saída do filtro para o valor médio da excursão do sinal de saída, uma vez que não há componente contínua no sinal de saída. Se o resistor fosse referenciado ao terra, a saída alternada oscilaria com valores positivos e negativos em torno da referência zero.

### Detector de pico

1.  Modifique o circuito do **filtro RC passa baixa**, acrescentando o **diodo**, o **capacitor** de 47uF e o **resistor** de 200KΩ a saída do filtro, conforme a figura: <a href="Arquivo:lab_detector_pico.png" class="wikilink" title="800px">800px</a> [^4]
2.  Monitore a amplitude da **tensão de saída** do circuito no **canal B** a medida que a frequência do sinal senoidal de entrada varia de 10 Hz até 1 KHz.

Analise do circuito  
O **diodo** e **capacitor paralelo** (capacitor shunt) conectados a saída do filtro funcionam como **detector de pico** do sinal na saída. Com isto é possível monitorar através de uma **tensão contínua** a amplitude máxima da tensão na saída do filtro. Desta forma, este valor de tensão contínua pode ser utilizado em **circuitos** comparadores visando o acionamento de algum dispositivo, como um led, para indicar a banda passante do sinal.

O circuito **detector de pico** também pode ser aplicado ao **filtro passa altas**.

### Comparador

1.  Acrescente a saída do **filtro RC passa baixa** com o circuito **detector de pico** o **circuito integrado** AD8561 que é um **comparador de tensão** com saída **binária**: <a href="Arquivo:lab_comparador.png" class="wikilink" title="500px">500px</a> [^5]
2.  Utilize o **canal B** para ajustar a **tensão** no centro do **potenciômetro** em 3,5 V, que é a **tensão** na saída do **filtro** na **frequência de corte** do mesmo.
3.  Monitore a amplitude da **tensão de saída** do circuito **detector de pico** no **canal B** a medida que a frequência do sinal senoidal de entrada varia de 10 Hz até 1 KHz. Observe quando o **led** conectado a saída **binária** do **comparador** acende ou apaga.

## Fundamentos sobre Filtros Elétricos

**Filtros elétricos** são circuitos que permitem **filtrar** determinadas **frequências** de um **sinal CA** permitindo a passagem de algumas frequências e limitando a passagem de outras. A frequência de transição entre as frequências permitidas e as não permitidas é chamada **frequência de corte** (f<sub>c</sub>).

Um filtro que permite a passagem de frequências abaixo da **frequência de corte** é chamado de **filtro passa baixa** e um filtro que permite a passagem de frequências a acima **frequência de corte** é chamado de **filtro passa alta**.

Os **filtros elétricos** mais simples podem ser construídos com elementos passivos, como **resistores** e **capacitores** (**filtros RC**) ou **resistores** e **indutores** (**filtros RL**).

### Filtros RC

**Com**circuitos RC série**é possível construir filtros elétricos**passa baixa**e**passa alta**. Os**filtros**operam sobre o**divisor de tensão**entre o**resistor**(R) e a**reatância**do**capacitor''' (C).

A **reatância** é a oposição a passagem de corrente elétrica de **capacitores** e **indutores** em circuitos de corrente alternada. A **reatância** é um parâmetro que depende da **frequência** do sinal de corrente alternada.

Para um **capacitor** (C) **reatância** é dada por **1/2πfC**. Pela expressão pode-se ver que a **reatância capacitiva** varia **inversamente** proporcional a **frequência** (f), ou seja, se a frequência aumenta a reatância diminui e vice versa. Para **corrente contínua** (frequência zero) a **reatância capacitiva** tende ao infinito, ou seja, o **capacitor** se comporta como um **circuito aberto**. Já para **altas frequências** o **capacitor** se comporta como um **curto circuito**.

Na análise do **divisor de tensão** do **filtro RC passa baixa**, verificamos que a medida que a frequência aumenta, a reatância diminui, portanto, diminui a componente de tensão sobre o capacitor, consequentemente, a tensão de saída do filtro diminui. Para o **filtro RC passa alta** verificamos o contrário, a medida que a frequência aumenta, aumenta a tensão na saída do filtro.

<a href="Arquivo:FiltrosRC.png" class="wikilink" title="500px">500px</a>

A **frequência de corte** (f<sub>c</sub>) é definida como a frequência na qual a **reatância capacitiva** é igual a **resistência**, ou seja R = 1/2πf<sub>c</sub>C, que resulta:

`f`<sub>`c`</sub>` = 1 / 2πRC`

Na **frequência de corte** (f<sub>c</sub>) a amplitude da tensão de saída, tanto no **filtro passa baixa** quanto no **passa alta**, cai a cerca de **70,7%** (√2/2) da tensão de entrada.

## Fundamentos sobre o Detector de Pico

O circuito **detector de pico** gera um valor de **tensão CC** igual ao **pico** do **sinal CA** de entrada.

<a href="Arquivo:DetectorPico.png" class="wikilink" title="Arquivo:DetectorPico.png">Arquivo:DetectorPico.png</a>

Funcionamento  
Quando a **tensão de entrada CA** (v<sub>in</sub>) está **crescendo**, o **diodo** conduz e provoca a **carga** do **capacitor** (C). Quando a tensão de entrada atinge o **valor de pico** o capacitor estará carregado com o **valor máximo da tensão** (V<sub>pico</sub>). Quando o sinal CA começa a decrescer a tensão da entrada ficará menor que a tensão no capacitor e o diodo passa a não conduzir, ficando a tensão armazenada na **carga do capacitor**. Parte da **carga do capacitor** é descarregada sobre o **resistor de carga** (R<sub>L</sub>). Se o **resistor de carga** for suficientemente grande, será observada apenas uma pequena oscilação na tensão contínua de saída, chamado ***ripple***.

## Observações e Conclusões

- **Filtros elétricos** são circuitos que permitem a passagem de terminadas **frequências** e limitam outras.
- Filtros simples podem ser construídos com componentes passivos, como os **filtros RC** e **filtros RL**.
- Na **frequência de corte** dos filtros a tensão da saída atinge 70,7% da tensão da entrada.
- **Detectores de pico** podem ser utilizados para verificar a amplitude máxima da tensão de saída de um filtro.
- **Circuitos comparadores** podem ser utilizados para obter uma **saída binária** indicando quando a tensão de um sinal de entrada está acima ou abaixo de uma dada referência.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h03min de 13 de julho de 2020 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>

[^1]: <https://wiki.analog.com/university/courses/engineering_discovery/lab_5>

[^2]:

[^3]:

[^4]:

[^5]:
