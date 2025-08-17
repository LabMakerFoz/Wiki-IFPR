# Laboratório: Projeto de relógio digital

Para este laboratório será utilizado o <a href="Simulador_de_Circuitos_Lógicos_-_Logisim" class="wikilink" title="Simulador de Circuitos Lógicos - Logisim">Simulador de Circuitos Lógicos - Logisim</a>  
Veja no *link* as instruções para *download* e instalação do programa.

## Objetivo

Construir um **relógio digital**, com mostradores de hora:minuto:segundo, utilizando o contador presente no Logisim.

## Fundamentação

Fazer a leitura da **página de ajuda** do Logisim relativa ao **contador**.

## Especificações e passos para o projeto do relógio

- O *clock* do contador de segundos deve ter frequência de 1 Hz.
- Cada contador deve ser de **4 bits** e realizará a contagem de cada **dígito** do mostrador de horas/minutos/segundos.
- Utilizar como mostradores de hora/minuto/segundo ***displays hexadecimais***, os quais tem entrada de 4 bits.
- Como a contagem realizada pelos contadores é em **hexadecimal** o contador das **unidades de segundo** deve contar de 0 a 9, portanto, configurar a contagem máxima até 9.
- Utilizar o ***carry*** do contador das unidades de segundo como entrada de *clock* para o contador das dezenas de segundo.
- Os **contadores de segundos** devem contar de **00 a 59**, portanto, configurar a contagem do contador das **dezenas de segundo** para contagem máxima até 5.
- Utilizar o ***carry*** do contador de segundos como entrada de *clock* para o contador de unidades de minutos.
- O **contador de minutos** deve contar de **00 a 59**, portanto, portanto, configurar a contagem máxima para cada um dos dígitos do contador de minutos de forma similar ao de segundos.
- Utilizar o ***carry*** do contador de dezenas de minutos como entrada de *clock* para o contador de horas.
- O **contador de horas** deve contar de **00 a 23**, portanto, configurar a contagem máxima para cada um dos dígitos do contador de horas:
  - Note que o contador das **unidades de hora** deve contar de 0 a 9, pois temos as horas de 0 a 19 horas e depois de 20 a 23 horas. Portanto, configurar a contagem máxima até 9.
  - O contador de **dezenas de horas** deve contar de 0 a 2, portanto, configurar a contagem do deste contador para contagem máxima até 2.
  - Vocês devem resolver o problema de zerar o relógio quando passar das 23h59m59s. Sugestão:
    - Usar **portas lógicas** para identificar quando o relógio chegar em 24h00m00s.
    - Utilizar o ***clear* assíncrono** para zerar os contadores.
- Utilizar o ponto dos ***displays hexadecimais*** para separar as contagens de horas/minutos/segundos.

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 08h51min de 16 de junho de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Sistemas_Digitais" class="wikilink" title="Categoria:Sistemas Digitais">Categoria:Sistemas Digitais</a>
