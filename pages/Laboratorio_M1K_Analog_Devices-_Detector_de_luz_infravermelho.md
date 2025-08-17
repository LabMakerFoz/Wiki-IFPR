# Laboratório: Detector de luz infravermelho

Este laboratório foi baseado no material disponibilizado pela **Analog Devices**, fabricante do módulo educacional **M1K Analog Devices**: [^1]

## Objetivos

Conhecer o princípio de funcionamento dos **fototransistores** e usá-los para construir um **detector de luz infravermelho**.

## Equipamento e Materiais

- Modulo **Analog Devices M1K** e software **Pixelpulse**
- Componentes Eletrônicos:
  - Resistor: 470 Ω e 1 kΩ
  - Led Infravermelho QED123
  - Fototransistor Infravermelho QSD123

## Procedimentos Práticos

1.  Monte na **matriz de contatos** o circuito **detector de luz infravermelho** da figura, usando o **fotodiodo**, **fototransistor** e **resistores** indicados: <a href="Arquivo:lab_fototransistor.png" class="wikilink" title="400px">400px</a> [^2]
2.  Selecione o **canal A** do módulo **Analog Devices M1K** para **Medir Voltagem**.
3.  Monitore com o **canal A** a tensão no **coletor** do **fototransistor**.
4.  Aproxime um objeto opaco entre o **fotodiodo** e o **fototransistor** e observe a mudança na tensão no **canal A**.

Comparador de tensão  
Um circuito **comparador de tensão** com saída **binária** pode ser utilizado em conjunto com o **fototransistor** para acionar um dispositivo em função da detecção da luz realizada.

## Fundamentos sobre Fotodiodos e Fototransistores

O **led QED123** é um **fotodiodo** que converte corrente elétrica em **luz infravermelho**. O **fototransistor QSD123** converte os **fótons de luz infravermelho** que incidem sobre o transistor em uma **corrente de base** efetiva que controla a **corrente do coletor** do transistor. Este transistor opera nas **regiões do corte e saturação**, atuando como uma **chave eletrônica**. Se não há **luz infravermelho** incidindo sobre o transistor não há corrente de base e o **transistor não conduz** (região do corte). Se há **luz infravermelho** o transistor há corrente de base e o **transistor conduz** corrente do coletor ao emissor (região da saturação). Quando saturado a tensão V<sub>CE</sub> cai a aproximadamente 0,2 V. Quando no corte a tensão V<sub>CE</sub> vai a 5 V, que é a tensão aplicada sobre o resistor.

Este **fototransistor** possui encapsulamento com plástico escuro que filtra a luz visível, podendo, portanto, operar em ambientes iluminados.

## Observações e Conclusões

- Um **fototransistor** opera de modo similar a um **transistor bipolar**, contudo, utiliza a **luz infravermelho** que incide sobre o transistor para ativar a **corrente de base** do transistor.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 16h30min de 14 de julho de 2020 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>

[^1]: <https://wiki.analog.com/university/courses/engineering_discovery/lab_7>

[^2]:
