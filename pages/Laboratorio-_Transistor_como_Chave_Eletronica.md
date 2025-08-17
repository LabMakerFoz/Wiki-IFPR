# Laboratório: Transistor como Chave Eletrônica

## Objetivos

Montar, testar e analisar um circuito com **transistor operando como chave**.

## Equipamento e Materiais

Equipamentos  

- **Bancada de Eletrônica** com **fonte de tensão**, **gerador de funções**, **multímetro** e **osciloscópio**.

ou

- **Simulador de circuitos eletrônicos**: **[SimulIDE](https://www.simulide.com)**.

<!-- -->

- Componentes Eletrônicos:
  - Resistores: 120 Ω e 1 KΩ (Valores comerciais)
  - Transistor NPN 2N3904

## Especificação da chave transistorizada

Parâmetros de projeto  

- Acionar uma **carga** alimentada por uma **fonte de 12 V** e **corrente de 100 mA**.
- O **comando** da carga deverá ser realizado por uma **saída digital** de um **microcontrolador**, operando de **0 V a 5 V** com **corrente máxima de 5 mA**.

<a href="Arquivo:TransistorChave.png" class="wikilink" title="Arquivo:TransistorChave.png">Arquivo:TransistorChave.png</a>

Condições de operação da chave transistorizada:

- Corte (**chave aberta**):

`Vb < 0,5V`  
`Ib = 0 ; Ic = 0 ; Vc = Vce = Vcc`

- Saturação (**chave fechada**):

`Vb >> 0,7V`  
`Vc = Vce = 0 ; Ic = Vcc/Rc`

Cálculos:

- Carga (Resistor Rc):

`Vcc =  12 V`  
`Ic  = 100 mA`  
`Rc  = 12/100m = 120 Ω`

- Chave transistorizada:

`Ic = Vcc/Rc = 12/120 = 100 mA`  
`Ib = Ic/βmin; βmin = 50`  
` Ib = 100m/50 = 2mA`  
` Forçar Ib maior para garantir saturação do transistor:`  
` Ib`<sub>`sat`</sub>` = (2 a 10) . Ib `  
` Ib`<sub>`sat`</sub>` = 2,5 . 2m = 5 mA`  
`Ib`<sub>`sat`</sub>` = (Vb - Vbe)/Rb = (5 - 0,7)/Rb `  
`Rb = (5 - 0,7)/5m = 940 -> Comercial 1 kΩ`

## Procedimentos Práticos

1.  Monte no **SimulIDE** um circuito com **transistor operando como chave** com Rc = 120 Ω e Rb = 1 kΩ e com as tensões de 12 V a ser aplicada sobre a carga (Vcc = 12 V) e comandada por uma **saída digital** de 0 V a 5 V (Vb = 5 V).
2.  Use **amperímetros** para medir as **correntes** Ib e Ic (**corrente na carga**) e compare com os valores teóricos.
3.  Use **pontas de prova** para medir as **tensões** Vb e Vc e compare com os valores teóricos.

## Observações e Conclusões

- Na operação como chave o transistor opera nas **regiões do corte** (chave aberta) ou **saturação** (chave fechada).

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 13h35min de 27 de setembro de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>
