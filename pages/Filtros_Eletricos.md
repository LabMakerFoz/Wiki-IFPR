# Fundamentos sobre Filtros Elétricos RC

## Objetivos

Conhecer o princípio de funcionamento dos **filtros elétricos RC passa baixa e passa alta**.

## Fundamentos sobre Filtros Elétricos

**Filtros elétricos** são circuitos que permitem **filtrar** determinadas **frequências** de um **sinal CA** permitindo a passagem de algumas frequências e limitando a passagem de outras. A frequência de transição entre as frequências permitidas e as não permitidas é chamada **frequência de corte** (f<sub>c</sub>).

Um filtro que permite a passagem de frequências abaixo da **frequência de corte** é chamado de **filtro passa baixa** e um filtro que permite a passagem de frequências a acima **frequência de corte** é chamado de **filtro passa alta**.

Os **filtros elétricos** mais simples podem ser construídos com elementos passivos, como **resistores** e **capacitores** (**filtros RC**) ou **resistores** e **indutores** (**filtros RL**).

## Filtros RC

**Com**circuitos RC série**é possível construir filtros elétricos**passa baixa**e**passa alta**. Os**filtros**operam sobre o**divisor de tensão**entre o**resistor**(R) e a**reatância**do**capacitor''' (C).

A **reatância** é a oposição a passagem de corrente elétrica de **capacitores** e **indutores** em circuitos de corrente alternada. A **reatância** é um parâmetro que depende da **frequência** do sinal de corrente alternada.

Para um **capacitor** (C) **reatância** é dada por

**`1/2πfC`**

Pela expressão pode-se ver que a **reatância capacitiva** varia **inversamente** proporcional a **frequência** (f), ou seja, se a frequência aumenta a reatância diminui e vice versa. Para **corrente contínua** (frequência zero) a **reatância capacitiva** tende ao infinito, ou seja, o **capacitor** se comporta como um **circuito aberto**. Já para **altas frequências** o **capacitor** se comporta como um **curto circuito**.

Na análise do **divisor de tensão** do **filtro RC passa baixa**, verificamos que a medida que a frequência aumenta, a reatância do capacitor diminui, portanto, diminui a componente de tensão sobre o capacitor, consequentemente, a tensão de saída do filtro diminui. Para o **filtro RC passa alta** verificamos o contrário, a medida que a frequência aumenta, aumenta a tensão na saída do filtro.

<a href="Arquivo:FiltrosRC.png" class="wikilink" title="500px">500px</a>

A **frequência de corte** (f<sub>c</sub>) é definida como a frequência na qual a **reatância capacitiva** é igual a **resistência**, ou seja

`R = 1/2πf`<sub>`c`</sub>`C`

que resulta:

`f`<sub>`c`</sub>` = 1 / 2πRC`

Na **frequência de corte** (f<sub>c</sub>) a amplitude da tensão de saída, tanto no **filtro passa baixa** quanto no **passa alta**, cai a cerca de **70,7%** (√2/2) da tensão de entrada.

## Filtros RL

**Com**circuitos RL série**é possível construir filtros elétricos**passa baixa**e**passa alta**. Os**filtros**operam sobre o**divisor de tensão**entre o**resistor**(R) e a**reatância**do**indutor''' (L).

Para um **indutor** (L) **reatância** é dada por

**`2πfL`**

Pela expressão pode-se ver que a **reatância indutiva** varia **diretamente** proporcional a **frequência** (f), ou seja, se a frequência aumenta a reatância aumenta e vice versa. Para **corrente contínua** (frequência zero) a **reatância indutiva** tende a zero, ou seja, o **indutor** se comporta como um **curto circuito**. Já para **altas frequências** o **indutor** se comporta como um **circuito aberto**.

Na análise do **divisor de tensão** do **filtro RL passa alta**, verificamos que a medida que a frequência aumenta, a reatância do indutor aumenta, portanto, aumenta a componente de tensão sobre o indutor, consequentemente, a tensão de saída do filtro aumenta. Para o **filtro RL passa baixa** verificamos o contrário, a medida que a frequência aumenta, diminui a tensão na saída do filtro.

<a href="Arquivo:FiltrosRL.png" class="wikilink" title="500px">500px</a>

A **frequência de corte** (f<sub>c</sub>) é definida como a frequência na qual a **reatância indutiva** é igual a **resistência**, ou seja

`R = 2πf`<sub>`c`</sub>`L`

que resulta:

`f`<sub>`c`</sub>` = R / 2πL`

Na **frequência de corte** (f<sub>c</sub>) a amplitude da tensão de saída, tanto no **filtro passa baixa** quanto no **passa alta**, cai a cerca de **70,7%** (√2/2) da tensão de entrada.

## Laboratório

<a href="Laboratorio:_Filtros_Eletricos" class="wikilink" title="Laboratório: Filtros Elétricos">Laboratório: Filtros Elétricos</a>  

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 16h38min de 1 de outubro de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>
