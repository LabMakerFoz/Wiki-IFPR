# Indutores

## Fundamentos sobre o Indutor

Os **indutores**, como os capacitores, também **armazenam energia elétrica**, mas em um **campo magnético**.

Os **indutores** permitem um maior fluxo de corrente a medida que a frequência do sinal diminui, se comportando como um **curto circuito** na presença de uma **corrente contínua**. Para um **sinal senoidal**, a **fase da corrente** é **atrasada** de **90 graus** em relação a **tensão**.

A tensão nos terminais de um indutor é proporcional a variação temporal da corrente. Assim, cabe aqui duas observações importantes [^1]:

- Primeiro, se a corrente for constante, a tensão sobre o indutor ideal será igual a zero, se comportando como um curto-circuito.
- Segundo, é que a corrente sobre o indutor não pode variar instantaneamente, pois se isto acontecesse produziria uma tensão infinita entre seus terminais. Por exemplo, quando alguém desliga um interruptor de um circuito com carga indutiva, inicialmente a corrente continua fluindo produzindo um centelhamento, evitando que a corrente caia a zero instantaneamente. Este é um problema sério na operação de motores elétricos nas indústrias, cuja operação de liga a desliga deve ser controlada para evitar centelhamentos e surtos de tensão, que podem danificar os equipamentos e colocar em risco os operadores.

Um **indutor** é geralmente construído como uma **bobina** de **material condutor**, como um fio de cobre isolado. Caso a bobina tenha um núcleo de material ferromagnético, isto aumenta a indutância concentrando as linhas de força de campo magnético que fluem pelo interior das espiras.

<a href="Arquivo:Indutores.jpeg" class="wikilink" title=" 150px"> 150px</a>

Nos circuitos elétricos o **indutor** é representado pela letra **L** e é medido em **Henry (H)**.

O símbolo do indutor lembra uma bobina.

<a href="Arquivo:Simbolo_Indutor.png" class="wikilink" title="Arquivo:Simbolo_Indutor.png">Arquivo:Simbolo_Indutor.png</a>

Dentre as aplicações importantes dos **indutores** em circuitos eletrônicos está a implementação de **filtros de sinal** e circuitos de **sintonia de frequência**.

### Tensão e corrente sobre um indutor

A **tensão elétrica** sobre um **indutor** é proporcional a **indutância** (L) multiplilada pela variação temporal da **corrente elétrica**.

$`v(t) =  L \frac{di(t)}{dt}`$

ou seja, a **tensão** no indutor é função da **derivada da corrente no tempo**, multiplicada pela **indutância**.

A derivada indica que a tensão elétrica no indutor é maior quanto maior for a variação da corrente. Desta forma, para uma **corrente senoidal**, quanto maior a **frequência** da onda, maior a **tensão** em um indutor. Para uma **corrente constante**, a **tensão** no indutor é **zero**.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 14h02min de 20 de setembro de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>

[^1]: Nilsson, J.W.; Riedel, S.A. Circuitos Elétricos, 10<sup>a</sup> Ed., p. 191, Pearson, 2015.
