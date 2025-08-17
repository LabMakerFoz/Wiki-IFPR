# Laboratório: Introdução aos Amplificadores Operacionais

## Objetivos

Conhecer um **amplificador operacional**, configurado como **amplificador inversor**, observando o **ganho** real e comparando com o valor calculado.

Conhecer a montagem de um **terra virtual** visando obter uma alimentação simétrica virtual (V+ e V-) ao **amplificador operacional**.

## Equipamento e Materiais

- Modulo **Analog Devices M1K** e software **Pixelpulse**
- Componentes Eletrônicos:
  - Resistores: 1 KΩ e 2,2 KΩ
  - Amplificador Operacional OP37

## Procedimentos Práticos

1.  Verifique a pinagem do **amplificador operacional** OP37, ilustrada na figura: <a href="Arquivo:AmpopOP37.png" class="wikilink" title="Arquivo:AmpopOP37.png">Arquivo:AmpopOP37.png</a>
2.  Usando a **matriz de contatos** e fios, monte o circuito com o **amplificador inversor** da figura abaixo, utilizando o OP37, R1 = 1 KΩ e R2 = 2,2 KΩ. No circuito será utilizado para **alimentação positiva** (V+) 5 V, **alimentação negativa** (V-) 0 V e um **terra virtual** na referência de tensão de 2,5 V (no circuito o **terra virtual** será conectado ao terminal não inversor). Com isto, tanto o sinal de entrada como o sinal de saída vão excursionar em torno desta referência de **terra virtual**. <a href="Arquivo:AmplificadorInversor.png" class="wikilink" title="Arquivo:AmplificadorInversor.png">Arquivo:AmplificadorInversor.png</a>
3.  Selecione o **canal A** do módulo **Analog Devices M1K** para **Gerar Tensão/Medir Corrente** e o **canal B** para **Medir Voltagem**.
4.  Configure o **canal A** para gerar uma **onda senoidal** variando entre 2,0 V e 3.0 V e **frequência** de 1000 Hz (centro da senoide na referência de 2,5 V).
5.  Observe e analise o **sinal de saída** no **canal B**, verificando o **ganho de amplitude** e a **fase da onda** em relação ao sinal de entrada.
6.  Compare os valores de **ganho** e **fase** do amplificador com os valores teóricos.

## Fundamentos sobre Amplificadores Operacionais

- **<a href="Amplificadores_Operacionais" class="wikilink" title="Amplificadores Operacionais">Amplificadores Operacionais</a>**

<!-- -->

- **Terra Virtual**:

  
Os **amplificadores operacionais** geralmente operam utilizando **fontes simétricas** para as **alimentações positiva** (V+) e **negativa** (V-).

Caso não se disponha de uma fonte simétrica, exitem diferentes estruturas que permitem implementar um **terra virtual**.

<!-- -->

  
Uma das soluções mais simples, caso não seja demandada muita potência no circuito a ser alimentado, é utilizar um **divisor de tensão** e um **capacitor paralelo** à referência de tensão a ser utilizada. Por exemplo, para uma fonte simples de 5 V, poderíamos montar o **terra virtual** na tensão de 2,5 V, como ilustrado na figura:

<a href="Arquivo:TerraVirtual.png" class="wikilink" title="Arquivo:TerraVirtual.png">Arquivo:TerraVirtual.png</a>

  
Caso o sinal de entrada seja um **sinal CA** excursionando em relação a referência 0 V (**terra real**), será necessário adicionar a entrada um **capacitor de desacoplamento**, visando isolar a sinal CA da alimentação CC. Entretanto, o sinal CA amplificado na saída vai excursionar em torno do **terra virtual**.

## Observações e Conclusões

- O **amplificador operacional** é um circuito integrado analógico utilizado para montar amplificadores e outros circuitos eletrônicos de precisão.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 15h52min de 15 de julho de 2020 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>
