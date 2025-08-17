# Laboratório: Introdução aos Amplificadores Operacionais

## Objetivos

Conhecer um **amplificador operacional**, configurado como **amplificador inversor**, observando o **ganho** real e comparando com o valor calculado.

Conhecer a montagem de um **terra virtual** visando obter uma alimentação simétrica virtual (V+ e V-) ao **amplificador operacional**.

## Equipamento e Materiais

**Simulador de circuitos eletrônicos**: **[SimulIDE](https://www.simulide.com)**.

- Componentes Eletrônicos:
  - Resistores: 1 KΩ e 2,2 KΩ
  - Amplificador Operacional

## Procedimentos Práticos

<a href="Arquivo:741-pinout.jpg" class="wikilink" title="250px">250px</a>

1.  Monte no **SimulIDE** o circuito com o **amplificador inversor** da figura abaixo, utilizando um **Ampop**, R1 = 1 KΩ e R2 = 2,2 KΩ.
2.  Configure o Ampop com **alimentação positiva** (V+) 5 V e **alimentação negativa** (V-) -5 V.
      
    <a href="Arquivo:AmplificadorInversor.png" class="wikilink" title="Arquivo:AmplificadorInversor.png">Arquivo:AmplificadorInversor.png</a>
3.  Configure como **entrada do amplificador inversor** (v<sub>in</sub>) um **gerador de funções**, configurado para gerar uma **onda senoidal** com **amplitude** de 2 V e voltagem base de -1 V (senoide variando de -1 V a 1 V) e **frequência** de 1000Hz.
4.  Utilize o canal 1 osciloscópio para observar a **forma de onda** gerada pelo **gerador de funções** (v<sub>in</sub>) e o canal 2 para observar a forma de onda sobre a **saída do amplificador inversor** (v<sub>out</sub>), verificando o **ganho de amplitude** e a **fase da onda** em relação ao sinal de entrada.
5.  Compare os valores de **ganho** e **fase** do amplificador com os valores teóricos.
6.  Modifique a resistência do resistor R2 para 3,3 KΩ e depois para 4,7 KΩ e verifique o **ganho de amplitude** para cada caso, comparando com os valores teóricos.
7.  Monte no **SimulIDE** o circuito com o **amplificador não inversor**, escolhendo os resistores R1 e R2 para um ganho de 3. Utilize a mesma alimentação e a mesma entrada utilizada no circuito anterior. Compare e forma de onda amplificada com a do amplificador inversor.

## Terra Virtual

Os **amplificadores operacionais** geralmente operam utilizando **fontes simétricas** para as **alimentações positiva** (V+) e **negativa** (V-).

Caso não se disponha de uma fonte simétrica, exitem diferentes estruturas que permitem implementar um **terra virtual**.

Uma das soluções mais simples, caso não seja demandada muita potência no circuito a ser alimentado, é utilizar um **divisor de tensão** e um **capacitor paralelo** à referência de tensão a ser utilizada. Por exemplo, para uma fonte simples de 5 V, poderíamos montar o **terra virtual** na tensão de 2,5 V, como ilustrado na figura:

<a href="Arquivo:TerraVirtual.png" class="wikilink" title="Arquivo:TerraVirtual.png">Arquivo:TerraVirtual.png</a>

Caso o sinal de entrada seja um **sinal CA** excursionando em relação a referência 0 V (**terra real**), será necessário adicionar a entrada um **capacitor de desacoplamento**, visando isolar a sinal CA da alimentação CC. Entretanto, o sinal CA amplificado na saída vai excursionar em torno do **terra virtual**.

## Observações e Conclusões

- O **amplificador operacional** é um circuito integrado analógico utilizado para montar amplificadores e outros circuitos eletrônicos de precisão.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h16min de 30 de setembro de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>
