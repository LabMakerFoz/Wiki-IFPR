# Corrente Contínua e Corrente Alternada

## Corrente Contínua (CC)

É caracterizada pelo fluxo contínuo de elétrons em um condutor, sempre na mesma direção.

A corrente contínua é gerada por **fontes de tensão contínua**, como pilhas ou baterias. Por exemplo, uma **pilha AA** fornece tensão contínua de **1,5 V** entre seus terminais positivo e negativo. Um **Arduíno** é alimentado por uma fonte de tensão contínua de **5 V**. Um **ESP32** é alimentado por uma fonte de tensão contínua de **3,3 V**. Um **carregador USB** fornece tensão contínua de **5 V**. A **bateria de um carro** fornece tensão contínua de **12 V** entre seus terminais positivo e negativo.

<a href="Arquivo:PilhaAA.png" class="wikilink" title="150px">150px</a>

## Corrente Alternada (CA)

É uma corrente elétrica cujo sentido oscila no tempo.

A corrente alternada é gerada por **fontes de tensão alternada**, como geradores eletromecânicos. A forma de onda usual da tensão e da corrente alternada é **senoidal**.

<a href="Arquivo:CorrenteAlternada.png" class="wikilink" title="Arquivo:CorrenteAlternada.png">Arquivo:CorrenteAlternada.png</a>

A **tensão secundária** fornecida pelas concessionárias de energia elétrica é **tensão alternada**, de 127V/220V (fase-neutro/fase-fase) ou 220V/380V (fase-neutro/fase-fase), dependendo da região.

### Frequência e período da corrente alternada

A relação entre **frequência** (**f**) em **Hertz** e o **período** (**T**) em **segundos** é:

$`f = \frac{1}{T}`$

A **corrente alternada** na rede de distribuição de energia elétrica no Brasil utiliza uma **frequência** de **60 Hz**. Logo, o **período** de um ciclo completo da **corrente alternada** é de **16,67 ms**.

Para visualizar a forma de onda senoidal é necessário um equipamento chamado **osciloscópio**.

### Corrente eficaz e corrente de pico

A **corrente eficaz** é a corrente que equivaleria a uma **corrente contínua** sobre uma carga. Esta corrente pode ser calculada de maneira simplificada para uma **onda senoidal** pela expressão:

$`I_{eficaz} = I_{pico} / \sqrt{2}`$` `

Para a tensão uma tensão de 127 V da rede de distribuição, o valor de pico é 127 √2 V:

<a href="Arquivo:TensaoAC.png" class="wikilink" title="300px">300px</a>

### Corrente RMS

Um cálculo mais preciso do **valor eficaz** de uma **corrente alternada** pode ser obtido pelo cálculo do valor chamado **RMS** (***root mean square***).

O valor **RMS** é uma medida estatística calculada a partir da **raiz do valor quadrático médio** da forma de onda, dada pela expressão:

$`x_{\mathrm{rms}} =
 \sqrt {{1 \over N} \sum_{i=1}^{N} x_i^2} =
 \sqrt {{x_1^2 + x_2^2 + \cdots + x_N^2} \over N}`$

## Conversão de corrente alternada em corrente contínua

A **tensão e corrente alternada** é o tipo de energia elétrica fornecido pela rede de distribuição das concessionárias de energia, nas tensões de 127 V ou 220 V, dependendo da região. Este nível de tensão é utilizado diretamente pelos eletrodomésticos residenciais, como refrigeradores, aparelhos de ar condicionado, fornos elétricos, chuveiros elétricos, etc.

Equipamentos eletrônicos, utilizam **tensão e corrente contínua** para alimentar seus circuitos integrados, em níveis mais baixos, como 12 V, 9 V, 5 V, 3,3 V ou outros valores.

A conversão da tensão alternada da rede de distribuição para tensão contínua, envolve dois tipos de equipamentos:

- **Transformadores**: Permitem abaixar as tensões da rede de energia para valores menores;
- **Retificadores**: São circuitos eletroeletrônicos, construídos com <a href="Diodos" class="wikilink" title="diodos"><strong>diodos</strong></a>, capazes de retificar o sinal de tensão alternada, convertendo o mesmo em tensão continua.

Em equipamentos, como por exemplo um computador pessoal, a **fonte de alimentação** implementa estas funções. A mesma função é realizada pelos carregadores de celulares e outros aparelhos eletrônicos.

## Gerador de sinais

Na **eletrônica**, muitos circuitos são utilizados para amplificar ou processar sinais periódicos analógicos. Para testar estes circuitos, um equipamento muito comum é o **gerador de sinais**, ou **gerador de ondas**, o qual pode gerar diferentes tipos de ondas alternadas com diferentes valores frequências. As formas de onda mais comum geradas por um gerador de sinais são as ondas **senoidais**, **quadradas**, **triangulares** e **dente de serra**.

<a href="Arquivo:Formas_de_onda.jpeg" class="wikilink" title="400px">400px</a>

## Prefixos do Sistema Internacional de Unidades

Muitas **unidades** utilizadas em **eletricidade** ou *eletrônica* são precedidas de **[Prefixos do Sistema Internacional de Unidades](https://pt.wikipedia.org/wiki/Prefixos_do_Sistema_Internacional_de_Unidades)**, seja para para indicar um múltiplo ou submúltiplo da unidade.

### Exemplos

Eletrotécnica residencial  
Geralmente as tensões são da ordem de uma ou duas centenas de Volts (127 V ou 220 V), as correntes na ordem de dezenas de Amperes (Disjuntores entre 5 A e 40 A) e potências até poucos milhares de Watts (lâmpada 15 W, Televisor 100 W, Chuveiro 5000 W).

<!-- -->

Eletrônica  
Geralmente encontramos tensões na ordem de poucos Volts (3,3 V, 5V ou 12 V), correntes na ordem de mili Amperes (1 mA a 100 mA) e potências até poucos Watts (1 mW a 5 W).

Na eletrônica algumas unidades muito grandes, como a Faraday, assim, usa-se submúltiplos para especificar a maioria dos capacitores utilizados em circuitos eletrônicos, como μF, nF e pF.

<!-- -->

Distribuição de Energia Elétrica  
Distribuição em baixa tensão (monofásico 127 V ou 220 V ou trifásico 220 V ou 380 V) e média tensão 13,8 KV.

<!-- -->

Geração e transmissão de Energia  
Alta tensão (trifásica 138 KV, 230 KV, 440 KV, 500 KV, 750 KV) e alta potência (uma turbina de Itaipu 700 MW; a usina toda 14 GW).

<!-- -->

  
**Curiosidade**:

  
**Itaipu** distribui a energia gerada para o Brasil através das linhas de transmissão de **Furnas**. São três linhas de transmissão de **corrente alternada trifásicas** de 750 KV (60 Hz) e duas linhas de **corrente contínua** ±600 KV.

As linhas de corrente contínua transmitem a energia que foi gerada pelas turbinas paraguaias, que geram energia trifásica na frequência de 50 Hz e são retificadas na subestação de Furnas para serem transmitidas ao Brasil. Em São Paulo a corrente contínua é transformada novamente em alternada, agora em 60 Hz, para ser incorporada ao sistema elétrico brasileiro.

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 18h50min de 14 de setembro de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a>
