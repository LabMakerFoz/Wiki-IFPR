# Amplificadores Operacionais

**Amplificadores Operacionais** (ou **AmpOp**) são **circuitos integrados analógicos** que permitem implementar **amplificadores de sinal**, **filtros**, **integradores**, **comparadores** e outros circuitos eletrônicos de precisão.

Terminais e simbologia  
Os **Amplificadores Operacionais** são circuitos ativos e possuem cinco terminais principais:

- alimentação positiva (**V+**)
- alimentação negativa (**V-**)
- entrada não inversora (**v<sub>p</sub>**)
- entrada inversora (**v<sub>n</sub>**)
- saída (**v<sub>out</sub>**)

<a href="Arquivo:AmpopIdeal.png" class="wikilink" title="Arquivo:AmpopIdeal.png">Arquivo:AmpopIdeal.png</a>

Características de um amplificador operacional ideal  

- impedância de entrada infinita;
- impedância de saída nula;
- ganho infinito;
- não existe corrente nas entradas;
- diferença de tensão nula entre as entradas.

Relações fundamentais para análise de circuitos com AmpOp  

**`v`<sub>`p`</sub>` = v`<sub>`n`</sub>**  
**`i`<sub>`p`</sub>` = i`<sub>`n`</sub>` = 0`**

## Amplificador Inversor

O **amplificador inversor** tem polaridade do sinal da tensão de saída oposto ao sinal de entrada, ou seja, para um sinal senoidal a saída é **defasada em 180 graus** em relação a entrada.

<a href="Arquivo:AmplificadorInversor.png" class="wikilink" title="Arquivo:AmplificadorInversor.png">Arquivo:AmplificadorInversor.png</a>

Análise do circuito  
Como as **tensões** nos terminais **inversor** e **não inversor** são **iguais** e as **correntes** em cada um destes terminais são **nulas**, temos no **terminal inversor** um **terra virtual**, uma vez que o **terminal não inversor** está **aterrado**.

Assim, utilizando a **Lei de Ohm**, a corrente sobre R<sub>1</sub> será

`i`<sub>`1`</sub>` = v`<sub>`in`</sub>` / R`<sub>`1`</sub>

e a corrente sobre R<sub>2</sub> será

`i`<sub>`2`</sub>` = - v`<sub>`out`</sub>` / R`<sub>`2`</sub>

Como não há correntes entrando no AmpOp, pela **Lei de Kirchhoff dos Nós**, temos

`i`<sub>`1`</sub>` = i`<sub>`2`</sub>

`v`<sub>`in`</sub>` / R`<sub>`1`</sub>` = - v`<sub>`out`</sub>` / R`<sub>`2`</sub>

O **ganho do amplificador** é dado pela razão entre a saída e a entrada, expresso por:

`G = v`<sub>`out`</sub>` / v`<sub>`in`</sub>

logo

**`G = - R`<sub>`2`</sub>` / R`<sub>`1`</sub>**

## Amplificador Não Inversor

O **amplificador não inversor** tem polaridade do sinal da tensão de saída igual ao sinal de entrada, ou seja, para um **sinal senoidal** a saída está em **fase** em relação a entrada.

<a href="Arquivo:AmplificadorNaoInversor.png" class="wikilink" title="Arquivo:AmplificadorNaoInversor.png">Arquivo:AmplificadorNaoInversor.png</a>

Análise do circuito  
As tensões nos terminais inversor e não inversor são iguais e as correntes em cada um destes terminais são nulas.

Assim, usando a **Lei de Ohm**, a corrente sobre R<sub>1</sub> será

`i`<sub>`1`</sub>` = - v`<sub>`in`</sub>`/R`<sub>`1`</sub>

e a corrente sobre R<sub>2</sub> será

`i`<sub>`2`</sub>` = (v`<sub>`in`</sub>` - v`<sub>`out`</sub>`)/R`<sub>`2`</sub>

Como não há corrente entrando no AmpOp, pela **Lei de Kirchhoff dos Nós**, temos

`i`<sub>`1`</sub>` = i`<sub>`2`</sub>

`- v`<sub>`in`</sub>`/R`<sub>`1`</sub>` = (v`<sub>`in`</sub>` - v`<sub>`out`</sub>`)/R`<sub>`2`</sub>

ou

`- v`<sub>`in`</sub>`/R`<sub>`1`</sub>` = v`<sub>`in`</sub>`/R`<sub>`2`</sub>` - v`<sub>`out`</sub>`/R`<sub>`2`</sub>

`v`<sub>`in`</sub>` (1/R`<sub>`1`</sub>` + 1/R`<sub>`2`</sub>`) = v`<sub>`out`</sub>`/R`<sub>`2`</sub>

O **ganho do amplificador** é dado por

`G = v`<sub>`out`</sub>` / v`<sub>`in`</sub>

logo

`G = (1/R`<sub>`1`</sub>` + 1/R`<sub>`2`</sub>`) / R`<sub>`2`</sub>

**`G = 1 + R`<sub>`2`</sub>`/R`<sub>`1`</sub>**

## Seguidor de Tensão

<a href="Arquivo:SeguidorTensao.png" class="wikilink" title="Arquivo:SeguidorTensao.png">Arquivo:SeguidorTensao.png</a>

Um **seguidor de tensão** (também chamado ***buffer***) é um circuito com amplificador operacional que possui um ganho de tensão de 1.

Um circuito com amplificador operacional é um circuito com uma **impedância de entrada** muito alta. Esta alta impedância de entrada é a razão pela qual os seguidores de tensão são usados.

## Amplificador Somador Inversor

O **amplificador somador inversor** realiza a soma e amplificação de diferentes entradas.

<a href="Arquivo:AmplificadorSomador.png" class="wikilink" title="Arquivo:AmplificadorSomador.png">Arquivo:AmplificadorSomador.png</a>

A saída do amplificador somador é

**`v`<sub>`out`</sub>` = - (R`<sub>`f`</sub>`/R`<sub>`1`</sub>` v`<sub>`1`</sub>` + R`<sub>`f`</sub>`/R`<sub>`2`</sub>` v`<sub>`2`</sub>` + R`<sub>`f`</sub>`/R`<sub>`3`</sub>` v`<sub>`3`</sub>`)`**

  
Se todos os resistores forem iguais a saída será a soma das entradas.

## Laboratório

<a href="Laboratorio:_Amplificadores_Operacionais" class="wikilink" title="Laboratorio: Amplificadores Operacionais">Laboratorio: Amplificadores Operacionais</a>  

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 18h12min de 14 de julho de 2020 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a>
