# KICAD

O [KICAD](https://kicad.org/) é um editor de **diagramas esquemáticos** para **circuitos eletrônicos** e geração de leiaute para **placas de circuito impresso**.

Instalação no Ubuntu  

`sudo add-apt-repository --yes ppa:kicad/kicad-7.0-releases`  
`sudo apt update`  
`sudo apt install --install-recommends kicad`

## Aplicativo KICAD

A janela principal do KICAD mostra os ícones de acesso as ferramentas do sistema:

<a href="Arquivo:Kicad.png" class="wikilink" title="600px">600px</a>

Principais ferramentas:

- **Editor de Esquemático**: Permite e edição do diagrama esquemático do circuito que se deseja confeccionar a placa de circuito impresso;
- **Editor de PCI**: Permite e edição da placa de circuito impresso, utilizando como base o diagrama esquemático do circuito.
- **Editor de símbolos**: Permite editar e criar símbolos para a biblioteca do esquemático.
- **Editor de *footprints***: Permite editar *footprints* de componentes.
- **Ferramenta de cálculo**: Calculadora com diversas funções para cálculos elétricos, incluindo código de cores de resistores, cálculo de corrente, dimensões de trilhas na placa de circuitos e outros.

## Passos para criação de um leiaute de circuito impresso

1.  Criação de um **projeto** para o circuito impresso.
2.  Edição do **diagrama esquemático** (arquivo.**kicad.sch**):
    - Escolher e inserir os componentes no diagrama;
    - Caso não tenha o símbolo na biblioteca o mesmo pode ser construído (ver ex. [^1]);
    - Posicionar os componentes de acordo com o circuito;
    - Realizar as conexões elétricas no circuito;
    - Atribuir os valores aos componentes;
    - Utilizar o **Verificador de Regras Elétricas** para verificar o circuito.
3.  Escolha dos ***footprints*** para cada componente do esquemático:
    - Escolher na biblioteca os *footprints* de acordo com o componente físico que for utilizar;
    - Caso não tenha o *footprints* na biblioteca o mesmo pode ser construído.
4.  Edição do leiaute da **placa de circuito impresso** (arquivo.**kicad.pcb**).
    - Reposicione os componentes na placa de circuito para diminuir ou eliminar os cruzamentos;
    - Realizar as conexões das trilhas na placa de circuito;
    - Utilizar o **Visualizador 3D** para visão da placa com os componentes em três dimensões.
5.  Finalmente pode utilizar as funções das **Saídas para Fabricação**, exportando os arquivos para confecção da placa, realizar a furação, lista de materiais e outros.

## Exemplo: Placa de circuito para um módulo de acionamento de relé

Para utilização de um **relé eletromagnético** é necessário um **circuito para acionamento** e **proteção da bobina**, com uma **chave com transistor** para acionar a bobina e um **diodo** em paralelo com a bobina para evitar sobre tensões quando a chave for fechada.

<a href="Arquivo:releCircuito.png" class="wikilink" title="Arquivo:releCircuito.png">Arquivo:releCircuito.png</a> [^2]

O **diodo de proteção** é importante, pois a bobina é uma **carga indutiva** e pode gerar altas tensões quando a corrente for interrompida sobre a mesma. Assim, quando o transistor corta a corrente, o diodo fica polarizado diretamente e mantem a corrente circulando por instantes na bobina, suprimindo o surto de tensão. Caso não se utilize esta proteção, o surto de tensão pode danificar o transistor ou o microcontrolador que aciona o circuito de comando.

### Construção da placa de circuito impresso no KICAD

Vamos neste exemplo construir uma **placa de circuito** para um **módulo de acionamento de relé** utilizando o circuito acima e acrescentando também um led para indicar quando o relé for acionado.

1.  Edição do **diagrama esquemático**
      
    <a href="Arquivo:Kicad_esquematico.png" class="wikilink" title="600px">600px</a>
2.  Escolha dos ***footprints***
      
    <a href="Arquivo:Kicad_footprint.png" class="wikilink" title="600px">600px</a>
3.  Edição do leiaute da **placa de circuito impresso**:
      
    <a href="Arquivo:Kicad_pcb.png" class="wikilink" title="600px">600px</a>

    - Utilizar o **Visualizador 3D**

      
    <a href="Arquivo:Kicad_3D.png" class="wikilink" title="600px">600px</a>

    <a href="Arquivo:Kicad_trilhas.png" class="wikilink" title="600px">600px</a>

## Referências

<references />

Alguns links com introdução ao KICAD:

- <https://www.embarcados.com.br/introducao-ao-kicad/>
- <https://www.embarcados.com.br/captura-de-esquematico-no-kicad/>
- <https://www.embarcados.com.br/pcb-no-kicad/>

Vídeos:

- <https://www.youtube.com/watch?v=X2N5CMPHbk4>
- <https://www.youtube.com/watch?v=2Z_Uf8UlDlY>
- <https://www.youtube.com/watch?v=IUSiyyuk_TA>
- <https://www.youtube.com/watch?v=TVxmzVsW-j8>

<a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 11h15min de 16 de maio de 2022 (-03)

------------------------------------------------------------------------

[^1]: <https://www.embarcados.com.br/captura-de-esquematico-no-kicad/>

[^2]: <http://wiki.foz.ifpr.edu.br/wiki/index.php/Arduino:_Sensores_e_Atuadores>
