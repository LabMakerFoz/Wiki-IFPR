# Projeto de Automação de Semáforo

  
Ano: 2013

Alunos: Andrey L. Garcia, Bruna Pardinhos, Michelli R. Teixeira e Nathiely M. Moraes

Curso Integrado em Informática

Orientador: Prof. Evandro Cantú

<!-- -->

Objetivo  
O projeto de automação de Semáforo foi desenvolvido com o intuito de melhorar o tráfego urbano nas grandes cidades. Ele tem os objetivos de melhorar a segurança em vias movimentadas, diminuir os congestionamentos e evitar acidentes e transtornos.

<!-- -->

Desenvolvimento  

O Projeto foi desenvolvido com uma placa de arduino e um micro-controlador ligado a um circuito composto por transistores, resistores, leds e cabos, como está representado na figura:

O arduino e o circuito foram programados através do S4A (*Scratch for arduino*),uma linguagem de programação gráfica, de fácil entendimento e montagem.

- Vídeo: {{#ev:youtube\|6lO-F5IO6EY}}

## Acionamentos de vários leds para os semáforos com uma única saída do Arduíno

Problema  
Acionar cada leds com corrente de 15mA sem sobrecarregar a saída do Arduíno.

<!-- -->

Solução  
Circuito com <a href="Transistores" class="wikilink" title="transistor como chave">transistor como chave</a>.

<a href="Arquivo:TransistorChave-Leds.png" class="wikilink" title=" 400px"> 400px</a>

Transistor utilizado  
BC547 -\> Β = 110-800

<a href="Mídia:DatasheetTransistorBC546-547-548.pdf" class="wikilink" title=" Datasheet Transistor BC546-547-548"> Datasheet Transistor BC546-547-548</a>

<!-- -->

Saída do Arduíno = 0 (0V)  
**Leds apagados**

Transistor no corte (circuito aberto):

`Ib = 0`  
`Vce -> circuito aberto`  
`Ic = 0`

Saída do Arduíno = 1 (5V)  
**Leds acesos**

Transistor na saturação (curto circuito)

`Vce -> circuito fechado`  
`Ic = [Vcc-(2+2+2)]/Rc; Rc = 200Ω -> Ic = [9-(2+2+2)]/200 = 15mA (corrente nos leds)`

  
Led do protoboard

`I = (5 - 2)/200 = 15mA`

Saturação forçada e cálculo de Rb  

`Ic`<sub>`sat`</sub>` = [Vcc-(2+2+2)]/Rc = [9-(2+2+2)]/200 = 15mA`  
`Ib`<sub>`sat`</sub>` = Ic`<sub>`sat`</sub>`/Β`<sub>`min`</sub>` = 15/110 = 0,14mA`

  
Forçar:

`Ib = 2 a 10 . Ib`<sub>`sat`</sub>

`Ib = 10.Ib`<sub>`sat`</sub>` = 10 . 0,14 = 1,4mA`  
`Ib = (Vb - Vbe)/Rb `  
`Rb = (Vb - Vbr)/Ib = (5 - 0,7)/1,4 = 3kΩ -> Comercial: 3k3`

------------------------------------------------------------------------

<a href="Categoria:Arduíno" class="wikilink" title="Categoria:Arduíno">Categoria:Arduíno</a> <a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a>
