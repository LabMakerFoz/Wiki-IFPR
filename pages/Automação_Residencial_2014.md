## Automação Residencial com Microcontrolador Arduino

### Introdução

Este projeto tem por objetivos estudar, aplicar e experimentar a plataforma de prototipagem de hardware Arduino, buscando o desenvolvimento e integração de conceitos ligados a programação de computadores e eletrônica.

### Definição

Arduino é uma placa microcontroladora básica criada na Itália, que possui componentes complementares, como motores e sensores para a construção de circuitos eletrônicos. É um projeto de código aberto, ou seja, pode ser copiado e modificado conforme o desejo e que não exige grandes conhecimentos em eletrônica. Trata-se uma plataforma de prototipagem eletrônica de hardware livre e de placa única.

<a href="image:Figura_01–_Arduino_Uno.jpg" class="wikilink" title="200px | center | Figura 01 – Arduino Uno | thumb |Figura 01– Arduino Uno‎">200px | center | Figura 01 – Arduino Uno | thumb |Figura 01– Arduino Uno‎</a>

Possui uma linguagem de programação própria, baseada em C/C++, devido a possuir funções que basicamente não fazem parte de outras linguagens como por exemplo a codificação, “pinMode(13,OUTPUT)” que define a porta 13 do Arduino como saída, função essa que inicialmente não existirá em outras linguagens de programação por se tratar de uma função específica para a placa controladora.

<a href="image:IDE.jpg" class="wikilink" title="800px | center | Figura 02 – IDE do Arduino | thumb |Figura 02 – IDE do Arduino">800px | center | Figura 02 – IDE do Arduino | thumb |Figura 02 – IDE do Arduino</a>

Essa tecnologia busca criar ferramentas acessíveis, de baixo custo, flexíveis e fáceis de se usar por qualquer pessoa interessada no desenvolvimento. A placa possui algumas limitações, por exemplo, não possui qualquer recurso de rede, porém é comum combiná-la com extensões chamadas de shields. Essas expansões buscam disponibilizar várias funções específicas, como a ligação em redes sem fio até a manipulação de motores.

<a href="image:Figura_03_–_Shield_Ethernet.jpg" class="wikilink" title="200px | center | Figura 03 – Shield Ethernet | thumb |Figura 03 – Shield Ethernet ">200px | center | Figura 03 – Shield Ethernet | thumb |Figura 03 – Shield Ethernet </a> <a href="image:Figura_04_–_Shield_Motor.jpg" class="wikilink" title="200px | center | Figura 04 – Shield Motor | thumb |Figura 04 – Shield Motor">200px | center | Figura 04 – Shield Motor | thumb |Figura 04 – Shield Motor</a>

Por se tratar de uma tecnologia que está constantemente crescendo, diversas placas e Shields foram desenvolvidos. Para conhecimento de algumas dessas placas acesse: [www.arduino.cc/en/Main/Products](http://www.arduino.cc/en/Main/Products).

<a href="image:Figura_05.png" class="wikilink" title="700px | center | Figura 05 – Site do Arduino | thumb |Figura 05 – Site do Arduino">700px | center | Figura 05 – Site do Arduino | thumb |Figura 05 – Site do Arduino</a>

Atualmente diversos projetos estão sendo desenvolvidos com essa tecnologia, como controle de sistemas interativos, em diversos níveis desde doméstico até industrial. Os campos de atuação para o controle de sistemas são imensos, podendo ter aplicações em áreas como robótica, domótica, engenharia agronômica, impressão 3D, entre outros.

<a href="image:Figura_06_–_Robo_construído_com_Arduino.jpg" class="wikilink" title="200px | center | Figura 06 – Robô feito com Arduino | thumb |Figura 06 – Robô feito com Arduino">200px | center | Figura 06 – Robô feito com Arduino | thumb |Figura 06 – Robô feito com Arduino</a>

### Desenvolvimento

Inicialmente devemos instalar a IDE do Arduino no computador, para isso faça o download no site: [www.arduino.cc](http://www.arduino.cc) conforme o sistema operacional desejado.

<figure>
<img src="Figura_07_–_Figura_da_página_de_downloads_do_Site_do_Arduino.png" title=" 700px | center | Figura 07 – Site do Arduino | thumb |Figura 07 – Site do Arduino" />
<figcaption> 700px | center | Figura 07 – Site do Arduino | thumb |Figura 07 – Site do Arduino</figcaption>
</figure>

Para conhecimento inicial do desenvolvimento de circuitos passaremos pelo componente mais básico: o led que será implementado em um Arduino Uno. Componentes necessários para montar o LED:

`1 LED`  
`1 Resistor de 220 ohms`  
`Fios de jumper`  
`1 Arduino Uno`  
`1 Protoboard`

![ 400px \| center \| Figura 08 – Sketch da ligação do led no Arduino \| thumb \| Figura 08 – Sketch da ligação do led no Arduino](Figura_08_–_Sketch_da_ligação_do_led_no_arduino.jpg " 400px | center | Figura 08 – Sketch da ligação do led no Arduino | thumb | Figura 08 – Sketch da ligação do led no Arduino") ![ 900px \| center \| Figura 09 – Codificação do led \| thumb \|Figura 09 – COdificação do led](Figura_09_–_Codificação_do_led.png " 900px | center | Figura 09 – Codificação do led | thumb |Figura 09 – COdificação do led")

Passamos ao monitoramento de sensores, como por exemplo o LM35 que faz o monitoramento da temperatura:

Componentes necessários para montar o LM35:

`1 sensor LM35`  
`Fios de jumper`  
`1 Arduino Uno`  
`1 Protoboard`

![ 400px \| center \| Figura 10 – Sketch da ligação do LM35 no Arduino \| thumb \| Figura 10 – Sketch da ligação do LM35 no Arduino](Figura_10_–_Sketch_da_ligação_sensor_LM35.jpg " 400px | center | Figura 10 – Sketch da ligação do LM35 no Arduino | thumb | Figura 10 – Sketch da ligação do LM35 no Arduino") ![ 900px \| center \| Figura 11 – Codificação do LM35 \| thumb \|Figura 11 – Codificação do LM35](Figura_11_–_Codificação_do_LM35.png " 900px | center | Figura 11 – Codificação do LM35 | thumb |Figura 11 – Codificação do LM35")

Existem alguns sensores, como por exemplo o DHT11 que possuem uma biblioteca específica para o controle. Para isso faça o download dessa biblioteca em [DHT11](http://www.seucurso.com.br/downloads/DHT11.zip).

E adicione esse arquivo em: Sketch \> Import Library... \> Add Library...

<figure>
<img src="Figura_12_–_Instalação_de_nova_biblioteca_no_Arduino.jpg" title=" 600px | center | Figura 12 – Instalação de nova biblioteca | thumb |Figura 12 – Instalação de nova biblioteca" />
<figcaption> 600px | center | Figura 12 – Instalação de nova biblioteca | thumb |Figura 12 – Instalação de nova biblioteca</figcaption>
</figure>

Componentes necessários para montar o DHT11:

`1 Sensor DHT11`  
`Fios de jumper`  
`1 Arduino Uno`  
`1 Protoboard`

![ 400px \| center \| Figura 13 – Sketch da ligação do sensor DHT11 \| thumb \| Figura 13 – Sketch da ligação do sensor DHT11](Figura_13_–_Sketch_da_ligação_do_sensor_DHT11.jpg " 400px | center | Figura 13 – Sketch da ligação do sensor DHT11 | thumb | Figura 13 – Sketch da ligação do sensor DHT11") ![ 900px \| center \| Figura 14 – Codificação do DHT11.png \| thumb \|Figura 14 – Codificação do DHT11.png](Figura_14_–_Codificação_do_DHT11.png " 900px | center | Figura 14 – Codificação do DHT11.png | thumb |Figura 14 – Codificação do DHT11.png")

### Projeto

Posteriormente ao período de testes e conhecimento da tecnologia, passamos a escolher um projeto de aplicação. Após um estudo feito sobre qual seria o projeto que melhor descreveria todos os princípios básicos da prototipação com Arduino, escolhemos a Automação Residencial, também conhecida como Domótica. Para isso passamos a criação de uma maquete que simularia todas as funcionalidades básicas de uma residência, como controle de climatização, iluminação, acesso, segurança, entre outros. Desenvolvemos uma planta básica da maquete com a divisão dos cômodos e passamos a construção da maquete que será explanada resumidamente abaixo, para visualização detalhada da construção da maquete acesse: [Video](https://www.youtube.com/watch?v=HT8Vlly_jdc&feature=youtu.be) / <a href="Mídia:Projeto_de_Automação_de_Residêncial.pptx" class="wikilink" title=" Projeto de Automação de Residêncial.pptx"> Projeto de Automação de Residêncial.pptx</a>

<table>
<tbody>
<tr>
<td><figure>
<img src="Figura_15.jpg" title="Figura 15 – Fase Inicial da construção da maquete" width="300" />
<figcaption>Figura 15 – Fase Inicial da construção da maquete</figcaption>
</figure></td>
<td><figure>
<img src="Figura_16.jpg" title="Figura 16 – Passagem dos fios da iluminação interna e externa" width="300" />
<figcaption>Figura 16 – Passagem dos fios da iluminação interna e externa</figcaption>
</figure></td>
<td><figure>
<img src="Figura_17.jpg" title="Figura 17 – Fase Final da cobertura externa da residência." width="300" />
<figcaption>Figura 17 – Fase Final da cobertura externa da residência.</figcaption>
</figure></td>
</tr>
<tr>
<td><figure>
<img src="Figura_18.jpg" title="Figura 18 – Vista frontal da maquete arquitetônica concluída com todos os aspectos decorativos" width="300" />
<figcaption>Figura 18 – Vista frontal da maquete arquitetônica concluída com todos os aspectos decorativos</figcaption>
</figure></td>
<td><figure>
<img src="Figura_19.jpg" title="Figura 19 – Ligação dos controles de iluminação interna no Arduino" width="300" />
<figcaption>Figura 19 – Ligação dos controles de iluminação interna no Arduino</figcaption>
</figure></td>
<td><figure>
<img src="Figura_20.jpg" title="Figura 20 – Conclusão da passagem do cabeamento de iluminação, colocação dos sensores e do portão eletrônico" width="300" />
<figcaption>Figura 20 – Conclusão da passagem do cabeamento de iluminação, colocação dos sensores e do portão eletrônico</figcaption>
</figure></td>
</tr>
<tr>
<td><figure>
<img src="Figura_21.jpg" title="Figura 21 – Colocação da Piscina acionada por um interruptor e pelo sistema web" width="300" />
<figcaption>Figura 21 – Colocação da Piscina acionada por um interruptor e pelo sistema web</figcaption>
</figure></td>
<td><figure>
<img src="Figura_22.jpg" title="Figura 22 – Posicionamento Final dos Arduinos e sensores" width="300" />
<figcaption>Figura 22 – Posicionamento Final dos Arduinos e sensores</figcaption>
</figure></td>
<td><figure>
<img src="Figura_23.jpg" title="Figura 23 – Vista frontal da maquete concluída e ligada" width="300" />
<figcaption>Figura 23 – Vista frontal da maquete concluída e ligada</figcaption>
</figure></td>
</tr>
<tr>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

## Preparação do ambiente

Para instalação do Arduino acesse <http://arduino.cc/en/Main/Software> e escolha sua versão de preferência para seu sistema operacional. Para Windows siga os passos comuns de instalação de programa, após isso execute a IDE conforme a imagem:

<a href="image:arduino_ide.jpg" class="wikilink" title="400px | center | IDE do Arduino no Windows | thumb |IDE do Arduino no Windows‎">400px | center | IDE do Arduino no Windows | thumb |IDE do Arduino no Windows‎</a>

No linux, ensinaremos na distribuição Ubuntu:

Abra o terminal, e localize o arquivo Arduino descompactado.

No nosso caso está em:

<a href="image:localização.jpg" class="wikilink" title="500px | center ‎| localização do arquivo">500px | center ‎| localização do arquivo</a>

Para instalação do PHP no Ubuntu, abra o terminal(Ctrl + Alt + t) e instale o pacote LAMP(Linux Apache Mysql PHP) com permissão de super usuário : sudo apt-get install lamp-server^

Para Windows basta instalar o programa WAMP ou o XAMPP conforme sua preferência.

|  |  |
|----|----|
| <a href="image:WAMP.png" class="wikilink" title="300px | left | WAMP server | thumb | WAMP server">300px | left | WAMP server | thumb | WAMP server</a> | <a href="image:xampp.png" class="wikilink" title="300px | right | XAMPP | thumb | XAMPP">300px | right | XAMPP | thumb | XAMPP</a> |
|  |  |

------------------------------------------------------------------------

<a href="Categoria:LabMaker" class="wikilink" title="Categoria:LabMaker">Categoria:LabMaker</a> <a href="Categoria:Arduíno" class="wikilink" title="Categoria:Arduíno">Categoria:Arduíno</a>
