# Laboratório: Transistor como Chave Eletrônica

## Objetivos

Conhecer o princípio de funcionamento de um **transistor** operando como **chave eletrônica**.

## Equipamento e Materiais

- Modulo **Analog Devices M1K** e software **Pixelpulse**
- Componentes Eletrônicos:
  - Resistores: 220 Ω e 6,8 KΩ
  - Transistor NPN BC337 ou similar

## Necessidade de uma chave eletrônica a transistor

Problema  
Suponha que precise acionar **cinco leds** utilizando uma **saída digital** (0 V ou 5V) que fornece no máximo 20 mA de corrente. Para cada **led** será configurada uma corrente de 13 mA, resultando numa corrente total de 65 mA para acionar os cinco leds, ultrapassando, portanto, o limite da corrente fornecida pela saída digital.

<!-- -->

Solução  
Construir uma **chave com transistor** para acionar os **cinco leds** em paralelo, demandando corrente mínima da saída digital.

<a href="Arquivo:TransistorChave-LedsParalelo.png" class="wikilink" title="Arquivo:TransistorChave-LedsParalelo.png">Arquivo:TransistorChave-LedsParalelo.png</a>

## Procedimentos Práticos

1.  Usando a **matriz de contatos** e fios, monte o circuito com o **transistor** BC337 (ou similar), **leds** e **resistores**, como ilustrado na figura anterior.
2.  Selecione o **canal A** do módulo **Analog Devices M1K** para **Gerar Tensão/Medir Corrente** e o **canal B** para **Medir Voltagem**.
3.  Configure o **canal A** para gerar uma **tensão constante** de 5.0 V.
4.  Utilize o **canal A** como se fosse a **saída digital**, monitorando o valor da **corrente** quando os **leds** estiverem acesos.
5.  Com o **canal B** monitore a tensão V<sub>ce</sub> do transistor e também os níveis de tensão sobre os resistores de cada led.

## Fundamentos Teóricos

### <a href="Transistores" class="wikilink" title="Transistores">Transistores</a>

### Cálculos para construção da chave a transistor

Leds  

Corrente de cada led:

`I`<sub>`led`</sub>` = (5 V - 2 V)/220 Ω = 3/220 = 13,6 mA`

Transistor  
O transistor utilizado BC337 pode atuar com corrente de coletor de até 800 mA. Para uma corrente em torno de 60 mA o ganho é Β = 110 (Fonte: Datasheet do BC337)

Corrente do coletor do transistor:

`I`<sub>`c`</sub>` = 5 I`<sub>`led`</sub>` = 68 mA`

Corrente de base do transistor:

`I`<sub>`b`</sub>` = I`<sub>`c`</sub>`/Β = 68 mA/110 = 0,62 mA`

Forçar saturação:

`I`<sub>`bsat`</sub>` = 10 I`<sub>`b`</sub>` = 6,2 mA`

Cálculo de I<sub>b</sub>:

`I`<sub>`b`</sub>` = (v`<sub>`b`</sub>` - v`<sub>`be`</sub>`)/R`<sub>`b`</sub>` = (v`<sub>`b`</sub>` - 0,7)/R`<sub>`b`</sub>` = (5 - 0,7)/R`<sub>`b`</sub>

`R`<sub>`b`</sub>` = 4,3 V/6,2 mA = 6,9 KΩ = 68 KΩ (valor comercial)`

## Observações Conclusões

- Uma **chave a transistor** é uma solução simples quando se deseja acionar um dispositivo demandando o mínimo de corrente elétrica.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 09h49min de 7 de julho de 2020 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>
