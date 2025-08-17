# Laboratório: Introdução aos Resistores e Divisores de Tensão

## Objetivos

Conhecer os **resistores elétricos**, que são dispositivos que se opõem a passagem de **corrente elétrica** e controlam a relação instantânea entre a **tensão** e a **corrente**.

Conhecer os **divisores de tensão**, que são circuitos formados por **resistores**, capazes de dividir uma **tensão elétrica** em tensões menores, dependendo do tamanho dos resistores utilizados.

Conhecer a diferença entre **tensões contínuas** e **tensões alternadas**.

Utilizar **equipamentos para medidas elétricas**, como **voltímetro**, **amperímetro** e **osciloscópio**.

## Equipamento e Materiais

Equipamentos  

- **Bancada de Eletrônica** com **fonte de tensão**, **gerador de funções**, **multímetro** e **osciloscópio**.

ou

- **Simulador de circuitos eletrônicos**: **[SimulIDE](https://www.simulide.com)**.

Componentes Eletrônicos  

- Resistores: 68 Ω, 100 Ω, 330kΩ, 1kΩ, 1k5Ω, 2K2 Ω, 4K7 Ω e 1 M Ω.

## Instalação do SimulIDE

Baixar a versão compatível do **[SimulIDE](https://www.simulide.com)** com seu sistema operacional e proceder a instalação.

Instalação do SimulIDE no Ubuntu 20.04  

- Baixar a versão compatível o Linux e extrair o conteúdo do arquivo .tar.gz.
- Instalar as dependências necessárias para o programa, as quais estão descritas no arquivo README.md.
    
  Podem ser instaladas com o comando:

`sudo apt-get install libqt5core5a libqt5gui5 libqt5xml5 libqt5svg5 libqt5widgets5 libqt5concurrent5 libqt5multimedia5 libqt5multimedia5-plugins libqt5serialport5 libqt5script5 libelf1`

- O diretório "SimulIDE_x.x.x" tem tudo o que precisa para rodar o programa, ir até ele e executar:

`./simulide`

## Procedimentos Práticos

### <a href="Resistores" class="wikilink" title="Resistores">Resistores</a>

1.  Monte no **SimulIDE** um circuito com uma fonte de **tensão constante** com 5 V alimentando um **resistor** de 100 Ω.
      
    <a href="Arquivo:Circuito.png" class="wikilink" title="Arquivo:Circuito.png">Arquivo:Circuito.png</a> <a href="Arquivo:Resistor100R.jpeg" class="wikilink" title="100px">100px</a>

    V = 5V; R = 100 Ω
2.  Utilize o **voltímetro** para medir a tensão sobre o resistor.
3.  Utilize o **amperímetro** para medir a corrente circulando no resistor.
    - O amperímetro deve ser conectado em série com o resistor.
    - Verifique se o valor da corrente medido corresponde ao valor calculado pela Lei de Ohm.
4.  Modifique o circuito utilizando dois **resistores em série** de 100 Ω. Aplique sobre eles uma **tensão constante** de 5V e verifique a **corrente** circulando no circuito. Calcule o resistor série resultante e o valor da corrente e compare com o valor medido.
5.  Modifique o circuito utilizando dois dois **resistores em paralelo** de 100 Ω. Aplique sobre eles uma **tensão constante** de 5V e verifique a **corrente** circulando no circuito e também a corrente em um dos resistores. Calcule o resistor paralelo resultante e o valor da corrente e compare com o valor medido.
6.  Utilizando o circuito com apenas um resistor, substitua a fonte de tensão constante por um **gerador de funções**, configurando o mesmo para gerar uma **onda senoidal** com 5 Vpp (pico a pico) e frequência de 1 kHz.
7.  Utilize o **osciloscópio** para observar a **forma de onda** da tensão sobre o resistor.
8.  Altere no **gerador de sinais** a forma de onda para **triangular**, **quadrada** e **dente de serra**. Verifique com o osciloscópio a forma da onda resultante sobre o resistor.

### <a href="Divisor_de_Tensao" class="wikilink" title="Divisor de Tensão">Divisor de Tensão</a>

1.  Monte o circuito **divisor de tensão** da figura usando resistores de 1kΩ e 1k5Ω:
      
    <a href="Arquivo:DivisorTensao.png" class="wikilink" title="Arquivo:DivisorTensao.png">Arquivo:DivisorTensao.png</a> <a href="Arquivo:Resistor1K.jpeg" class="wikilink" title="100px">100px</a> <a href="Arquivo:Resistor1K5.jpeg" class="wikilink" title="60px">60px</a>

    V = 5V; R1 = 1kΩ; R2 = 1k5Ω
2.  Utilize o **voltímetro** para medir a tensão sobre os resistores R1 e R2 e verifique se corresponde ao valor calculado.
3.  Utilize o **amperímetro** para medir a corrente circulando no divisor de tensão e verifique se corresponde ao valor calculado.
4.  Utilize no circuito divisor de tensão dois resistores iguais a 1kΩ e repita os procedimentos anteriores.
5.  No circuito divisor de tensão, substitua a fonte de tensão constante por um **gerador de funções**, configurando o mesmo para gerar uma **onda senoidal** com 5 Vpp (pico a pico) e frequência de 1 kHz.
6.  Utilize o canal 1 do **osciloscópio** para observar a **formas de onda** da tensão no topo do divisor de tensão e o canal 2 no centro do divisor de tensão (entre os resistores). Observe a diferença entre as formas de onda.

### Potenciômetros

1.  Monte o circuito com **potenciômetro** da figura usando potenciômetro de 1kΩ:
      
    <a href="Arquivo:Potenciometro.png" class="wikilink" title="Arquivo:Potenciometro.png">Arquivo:Potenciometro.png</a> <a href="Arquivo:potenciometro.jpg" class="wikilink" title="150px">150px</a>

    - V = 5V; R = 1kΩ
2.  Utilize o **voltímetro** para medir a tensão sobre o centro do potenciômetro e o terra.
3.  Varie a resistência relativa do potenciômetro de um estremo a outro e verifique a variação da tensão medida pelo multímetro.
4.  Utilize o **amperímetro** para medir a corrente circulando no potenciômetro e verifique se corresponde ao valor calculado. Há variação da corrente no circuito quando varia a resistência relativa do potenciômetro?

## Observações e Conclusões

- **Resistores** são elementos **passivos**, utilizados para **limitar a corrente elétrica** em **circuitos elétricos e eletrônicos**.
- A **voltagem** sobre um **resistor** em um **circuito série** é uma fração da voltagem total sobre o circuito.
- A **voltagem** sobre um **resistor** em um **circuito série** pode ser determinada pela regra do **divisor de tensão**.
- A **corrente** sobre um **resistor** em um **circuito paralelo** é uma fração da corrente total sobre o circuito.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 12h24min de 10 de setembro de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Eletrônica" class="wikilink" title="Categoria:Eletrônica">Categoria:Eletrônica</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>
