# Eletricidade Básica

## Fundamentos e definições

Conhecer os princípios da eletricidade é fundamental para compreender o funcionamento dos dispositivos eletroeletrônicos.

Nestes disposistivos, a eletricidade é controlada por meio de **circuitos elétricos**, envolvendo grandezas como **tensão** e **corrente elétrica** e uma série de componentes eletroeletrônicos, como **fontes de tensão**, **resistores**, **capacitores**, **transistores**, **diodos**, **leds**, **chaves**, etc.

## Circuito elétrico

Um **circuito elétrico** básico é formado por uma **fonte de tensão** (como uma bateria), uma **carga** (ou resistência) e **fios condutores**. Nestes elementos, três grandezas elétricas estão envolvidas:

- **Tensão elétrica**: É a diferença de potencial elétrico entre dois pontos, medida em **Volts (V)**;
- **Corrente elétrica**: É a energia elétrica em movimento em um condutor de eletricidade, medida em **Amperes (A)**;
- **<a href="Resistores" class="wikilink" title="Resistência elétrica">Resistência elétrica</a>**: É a oposição a passagem de corrente elétrica, exercida pelos fios condutores e outros dispositivos, como resistores, medida em **Ohms (Ω)**.

Circuito elétrico elementar  

<a href="Arquivo:Circuito.png" class="wikilink" title="Arquivo:Circuito.png">Arquivo:Circuito.png</a>

## Lei de Ohm

Estabelece a relação entre **tensão**, **corrente** e **resistência** elétrica.

`V = R . I`

ou

`R = V / I`  
`I = V / R`

## Leis de Kirchhoff

Baseadas no **princípio da conservação da energia**, estabelecem princípios fundamentais para a análise de **circuitos elétricos**.

Lei de Kirchhoff das Malhas  
A **soma das tensões** (ou quedas de tensões) ao longo de uma **malha** é igual a **zero**.

Ao percorrer uma malha de um circuito, consideramos as **tensões** das **fontes de tensão** e as **quedas de tensão** sobre os resistores, estas últimas dadas pela **Lei de Ohm** aplicadas em cada resistor.

<a href="Arquivo:LeiDasMalhas.png" class="wikilink" title="Arquivo:LeiDasMalhas.png">Arquivo:LeiDasMalhas.png</a>

`-V + R`<sub>`1`</sub>`I + R`<sub>`2`</sub>`I + R`<sub>`3`</sub>`I = 0`

  
Percorrendo a malha do circuito no sentido horário, que é o sentido indicado da corrente, encontramos a fonte de tensão pelo polo negativo, portanto esta tensão é marcada como negativa. Já as quedas sobre os resistores são marcadas como positivas, pois se dão no sentido da corrente. Como todos os resistores estão em série a corrente que percorre os mesmos é a mesma.

ou isolando V:

`V = R`<sub>`1`</sub>`I + R`<sub>`2`</sub>`I + R`<sub>`3`</sub>`I`

Lei de Kirchhoff dos Nós  
A **soma das correntes** que entram em um **nó** é igual a soma das correntes que saem.

<a href="Arquivo:LeiDosNos.png" class="wikilink" title="Arquivo:LeiDosNos.png">Arquivo:LeiDosNos.png</a>

`I`<sub>`1`</sub>` + I`<sub>`2`</sub>` = I`<sub>`3`</sub>

ou

`I`<sub>`1`</sub>` + I`<sub>`2`</sub>` - I`<sub>`3`</sub>` = 0`

As **Leis de Kirchhoff** são utilizadas para a **análise de circuitos**. Por exemplo, um circuito com duas malhas a **Lei de Kirchhoff das Malhas** de vai gerar um sistema de equações com duas equações e duas incógnitas. Já a **Lei de Kirchhoff dos Nós** é mais indicada na análise de circuitos que apresentam **fontes de corrente**.

## Potência elétrica

A **potência elétrica** indica a quantidade de energia utilizada em um dado tempo em um circuito. É medida em **Watts (W)** e é dada pelo produto entre a tensão e a corrente elétrica.

`P = V . I `

ou

`P = V`<sup>`2`</sup>` / R`  
`P = R . I`<sup>`2`</sup>

## Energia elétrica

A **energia elétrica** é a potência elétrica demandada por uma carga durante uma unidade de tempo.

No sistema internacional a unidade de energia é o **Joule** (J).

`1 J = 1 W . s `

Entretanto, as concessionárias de energia normalmente medem a energia elétrica consumida em **kWh**. No caso, o consumo de 1 kWh significa que a carga com potência de 1 kW ligada durante 1 hora.

## Exercícios

1.  Determine a corrente elétrica que flui por um resistor de 1 kΩ quando ele é submetido a uma tensão de 5 V.
2.  Um resistor de 100 Ω é percorrido por uma corrente elétrica de 20 mA. Qual a tensão entre os terminais do resistor, em volts?
3.  Os valores nominais de uma lâmpada incandescente, usada em uma lanterna, são: 6,0 V; 20 mA. Qual o valor da resistência elétrica do seu filamento? Qual a potência elétrica da lâmpada?
4.  Suponha que uma lanterna seja alimentada por duas pilhas de 1,5 V cada, organizadas em série, e alimente uma lâmpada de 3 W. Qual a corrente elétrica que irá circular pela resistência da lâmpada. Qual a resistência da lâmpada?
5.  Suponha que um chuveiro elétrico tenha potência de 4.000 W e será alimentado por tensão elétrica de 127 V. Qual a corrente que irá circular pela resistência elétrica do chuveiro? Qual o valor da resistência do chuveiro? Qual o valor adequado para a corrente do disjuntor para proteger o chuveiro de sobre-correntes?
6.  Recalcule o exercício anterior supondo que a tensão de alimentação seja 220V. Responda qual nível de tensão seria mais adequado para a instalação elétrica deste chuveiro. Por que?
7.  Para o(s) chuveiro(s) do(s) exercício(s) anterior(es), calcule a energia elétrica consumida por um banho de 15 minutos.
8.  Um curto circuito ocorre quando conectamos (involuntariamente ou acidentalmente) os terminais positivo e negativo de uma fonte de tensão. Qual o valor teórico que tende corrente resultante de um curto circuito, considerando que a resistência dos fios condutores é próxima de zero?
9.  Explique porque num curto circuito temos aquecimento dos fios condutores, o que muitas vezes pode provocar incêndios.
10. Explique a função do fio terra, ou aterramento, necessário na carcaça de equipamentos elétricos e eletrônicos.

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 14h59min de 30 de agosto de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:Eletrotécnica" class="wikilink" title="Categoria:Eletrotécnica">Categoria:Eletrotécnica</a> <a href="Categoria:Energia_Eletrica" class="wikilink" title="Categoria:Energia Eletrica">Categoria:Energia Eletrica</a>
