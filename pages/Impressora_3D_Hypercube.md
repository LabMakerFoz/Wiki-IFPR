## Resumo

  
Este projeto objetiva a construção de uma impressora 3D de fonte aberta de baixo custo que tem a capacidade de construir grande parte das peças de plástico que a constituem. Assim sendo, a partir do momento que se constrói a primeira impressora, a segunda será construída pela primeira, a um preço mais econômico.

<!-- -->

  
O projeto é de grande relevância para o IFPR, pois permite a aquisição de know how crítico no que respeita à construção e funcionamento de uma impressora 3D que se consegue autorreplicar.

<!-- -->

  
O modelo de referência da nossa impressora será a [Hypercube](https://www.thingiverse.com/thing:1752766), um modelo avançado de impressora do tipo coreXY, sendo as peças necessárias para a montagem de plástico, alumínio e aço.

<!-- -->

  
Objetivamos com este projeto demostrar a possibilidade de construir uma tecnologia de ponta a baixo custo, diminuindo a barreira de acesso a este tipo de tecnologias por potenciais criadores e empreendedores.

<!-- -->

  
Escolhemos esta tecnologia por ter um potencial de transformação econômica e social alto. Pretendemos posteriormente abrir ao público tanto o conhecimento adquirido com este projeto, através de um wiki, como o acesso as máquinas que forem construídas, de forma a estimular o potencial criativo e de livre-empreendedorismo das comunidades da nossa região.

## Objetivos

  
Este projeto tem como objetivo a construção de uma impressora 3D do modelo Hypercube no Laboratório Maker do Campus Foz do Iguaçu do IFPR.

## Equipe

- Vasco Neves (coordenador)
- Alcione Benacchio (vice-coordenador)
- Evandro Cantú (colaborador)
- Lyncon Baez (bolsista PRADI)

## Introdução ao Modelo Hypercube

  
O Modelo de Impressora 3D ou CNC HyperCube foi criado e documentado pela equipe Tech2C no site [Thingiverse](https://www.thingiverse.com/) no dia 4 de setembro de 2016. Muitas pessoas ao redor do mundo foram capazes de construir esse modelo, provando assim a competência e garantia do mesmo.

Foi criado também um modelo derivado da Hypercube chamado Hypercube Evoltion.

Esse modelo utiliza os princípios do mecanismo de core xy onde 2 motores movem o extrusor através polias e roldanas pelos eixos x e y, enquanto a base movimenta o eixo z.

<a href="Arquivo:CoreXY.jpg" class="wikilink" title="400px">400px</a>

## Materiais

**Frame:** *Barra de Aluminio T-Slot 2020 (Slot/Type 6) para a área de impressão de X200 x Y200 x Z155*

- 4 x 340mm (X)
- 4 x 303mm (Y)
- 4 x 350mm (Z)
- 2 x 285mm (Base)
- 1 x 135mm (Base)

*Fixação*

- 60 x Parafusos cabeça de botão M5 x 8mm
- 60 x Parafusos cabeça de botão M5 x 10mm
- 200 x T-Slot M5 hammer nuts
- 30 x Cantoneiras de alumínio

**CoreXY + Z + Sistema Bowden Drive :**

- 2 x Haste de aço endurecido 8mm x 300mm para o eixo Y
- 2 x Haste de aço endurecido 8mm x 350mm para o eixo Z
- 2 x Tubo de aluminio anodizado ou fibra de carbono 10mm x 360mm para o eixo X
- 10 x Buchas auto lubrificadas
- 4 x Rolamento linear LM8UU para eixo Z
- 2 x Rolamento linear LM8LUU para eixo Y
- 1 x Parafuso de avanço T8 300mm
- 1 x Acoplador de eixo flexível de alumínio 5x8mm
- 20 x Rolamento de flange F623ZZ
- 1 x Correia 5M GT2
- 2 x Polia de temporização de dentes 2GT-20
- 1 x Tubo de Teflon PTFE
- 1 x Engrenagem do extrusor MK7
- 1 x Conector de Ajuste M5

*Fixação*

- 45 x parafuso de cabeça aberta M3 x 10mm
- 45 x Parafuso de cabeça aberta M3 x 20mm
- 2 x Parafuso de cabeça aberta M3 x 6mm
- 2 x Parafuso de cabeça aberta M3 x 35mm
- 35 x Porcas nyloc M3
- 35 x Porcas hexM3

**Motores, Eletrônicos e Acessórios:**

- 4 x Motor de passso NEMA17
- 3 x Endstop Switch
- 1 x RAMPS 1.4 + MEGA2560 R3 + LCD&SD + A4988 com Kit dissipador de calor
- 1 x Cooler resfriador 12V DC 50mm
- 1 x Mesa aquecida de Alumínio MK3 12V 24V
- 1 x Fonte 12V 30A 360W
- 1 x Termistor 100K com cabo 1M para mesa aquecida
- 1 x Fio de energia DC (14AWG)
- 1 x Pino de cobre estanhado 10M 22AWG 2
- 5 x parafuso / mola / botão de nivelamento da mesa
- 1 x Genuine E3Dv6 ou Clone (1.75mm long)
- 1 x Sensor de proximidade indutiva - PNP

## Montagem Mecânica

**Impressão das Peças**

  
Para começarmos a montagem da Impressora, primeiros precisamos imprimir suas pecas que podem ser impressas, para isso usaremos a Impressora 3D modelo Prusa I3, presente no Lab Maker do Instituto.

Todos as pecas que serão Impressos possuem seus modelos 3dD disponíveis para serem baixados por qualquer pessoa na pagina da [HyperCube](https://www.thingiverse.com/thing:1752766).

Usaremos as configurações de Impressão recomendadas pelos desenvolvedores da impressora, essas configurações são:

- 3 Perimentro
- 3 camadas cima/baixo
- Altura da camada de 0.25mm(ou melhor)
- 50% de infill

  
As fotos de cada peça com seus devidos nomes estarão disponíveis na própria wiki do IFPR.

<a href="Arquivo:Imprimindo.jpeg" class="wikilink" title="300px">300px</a>

<!-- -->

  
<a href="Arquivo:Cantoneira.jpeg" class="wikilink" title="300px|thumb|left|Cantoneira impressa na Impressora Prusa I3">300px|thumb|left|Cantoneira impressa na Impressora Prusa I3</a>

<a href="Arquivo:Barra.jpeg" class="wikilink" title="300px|thumb|rigth|Barra de Alumínio T-Slot 20x20">300px|thumb|rigth|Barra de Alumínio T-Slot 20x20</a> **Frame**

  
A próxima etapa da montagem da Impressora consiste na montagem da estrutura ou frame, onde serão colocados todas as outras pecas da Impressora, para isso serão utilizados as barras de Alumínio T-Slot 20x20, parafusos juntamente com os os hammer nuts e cantoneiras impressas em nossa impressora Modelo Prusa I3(também seria possível usar cantoneiras de aço compradas em qualquer loja, mas a utilização das cantoneiras feitas em nossa impressora servirá como teste de qualidade da mesma). As barras de alumínio serão cortadas nas medidas propostas pelos desenvolvedores da impressora e então fixadas com os parafusos e hammer nuts, que com a própria torção da chave se prendem perfeitamente as fissuras das das barras.

**Eixo X**

  
Na próxima etapa montaremos o eixo X da Impressora, sendo assim encaixaremos os tubos de alumínio anodizado, a 2 peças de grande importância, os [XY Joiner](http://wiki.foz.ifpr.edu.br/wiki/index.php/Arquivo:XY_Joiner.jpeg), que como o próprio nome sugere, servem para posteriormente unir os eixos X e Y.

Em seguida passaremos 2 buchas de bronze autolubrificadas no tubo de cima e 1 no tubo de baixo, para assim prender com fitas plásticas a peca que servirá de estrutura para a cabeça onde o extrusor ficará.

Para garantir maior deslizamento das buchas nos tubos será preciso colocar uma capa de plástico também impressa no Instituto ao redor das 2 buchas de cima para garantir que ficarão paralelas e não haverá folga gerando atrito entre as buchas.

**União do Eixo X com o Eixo Y**

  
Para Unir o Eixo x ao Y sera preciso primeiro acoplar as 2 haste de aço endurecido 8mm x 300mm em dois lados paralelos da parte de cima do frame (para a fixação dessas hastes serão usadas mais pecas impressas), com 1 rolamento linear LM8LUU em cada haste.

Assim que colocadas as hastes, sera colocado nos XY Joiners rolamentos de flange F623ZZ nos locais destinados a eles, esses rolamentos servirão de polias para as correias passadas futuramente.

Com os 2 eixos prontos, a próxima coisa a se fazer e encaixar o eixo X nos rolamentos do eixo Y, prendendo com mais 2 pecas impressas.

**Motores, Polias e Correias dos Eixos X e Y**

  
Com os eixos X e Y prontos, começaremos a fixar as 2 peças impressas que sustentarão os motores, essas peças serão fixadas no frame, paralelamente, utilizando parafusos e hammer nuts, assim que colocadas, os motores serão acoplados nessas peças.

Depois disso, ainda serão colocadas 2 outras peças nas outras 2 extremidades paralelas do frame,

essas peças utilizam 4 rolamentos cada com um parafuso de eixo para servirem de polias para as correias.

  
Com tudo pronto, será necessário passar as correias pelos motores, pelas polias e terminando na cabeça que está no eixo X, prendendo-as com fitas plásticas em um determinado lugar da peça da cabeça.

**End-Stops X e Y**

  
A colocação dos end-stops do eixo x e y é bem simples.

Para o eixo Y deve-se fixar um end-stop em uma peça impressa e logo em seguida encaixar essa peça no na própria haste do eixo Y.

Para o eixo X deve-se fixar um end-stop em um dos lados da própria cabeça do extrusor, finalizando assim a montagem do core XY.

**Eixo Z**

  
Para a montagem do eixo Z cortaremos as barras de Alumínio na medida recomendada fixando 2 barras em 1 com as cantoneiras usadas na montagem do frame,logo depois usaremos 2 peças com 2 rolamentos lineares LM8UU em cada peça, fixando-as na peça de alumínio que acabamos de montar.

O próximo passo será fixar a peça que sustentará o motor que guiará o eixo Z na parte de cima do frame, fixando o motor logo depois.

Para a colocação das 2 haste de aço endurecido 8mm x 350mm usaremos 4 peças impressas fixadas no frame(2 na parte de cima e 2 na parte de baixo), antes de colocar as hastes nas peças, passaremos a peça com barras de alumínio nessas hastes, fazendo com que esta peça possa se mover para cima e para baixo livremente fazendo os rolamentos percorrerem as hastes.

Para fazer o motor controlar esse eixo, será usado o acoplador de eixo flexível de alumínio 5x8mm para acoplar o parafuso de avanço T8 300mm ao motor.

E por ultimo, será usada mais uma pela impressa que será fixada à porca do parafuso de avanço e também encaixada a peça de barras de alumínio.

**End-Stop Z**

  
Para a instalação do end-stop do eixo Z será necessário a utilização de 2 peças.

Primeiro fixaremos o end-stop á [primeira peça](http://wiki.foz.ifpr.edu.br/wiki/index.php/Arquivo:Z_EndStop.jpeg) e posteriormente fixaremos essa peça á uma coluna do frame na parte de baixo.

Em seguida, fixaremos a [segunda peça](http://wiki.foz.ifpr.edu.br/wiki/index.php/Arquivo:Z_EndStop_Adjust.jpeg) á peça de barras de alumínio junto com um parafuso que será colocado na peça impressa para podermos regular a altura mínima do eixo Z.

**Mesa Aquecida**

  
A partir de agora serão implementadas poucas peças para a finalização da impressora, a próxima parte que instalaremos é a mesa aquecida, que serve para dar mais adesão as peças que será feitas pela impressora.

Com isso em mente, utilizaremos 4 peças impressas que serão fixadas à peça de barras de alumínio usando parafusos e porcas martelo, depois disso colocaremos a mesa aquecida fixando com parafusos, porcas e molas para podermos ajustar a altura de mesa.

**Sistema Bowden Drive**

  
O Sistema Bowden Drive é um sistema onde o motor de passo que puxa o filamento nao fica próximo ao hotend (peça que derrete o filamento), sendo assim o filamento é direcionado ao hotend por um tubo, diferente do sistema direto onde o motor que puxa o filamento esta logo acima do hotend.

Para a montagem desse sistema começaremos a montar a parte com o hotend, que ficará na cabeça da impressora, para isso usaremos 3 peças, primeiro fixaremos o cooler resfriador em uma peça, juntamento com outra peça impressa que servirá como tubo para o refriamento, sendo assim o proximo passo será fixar o hotend e o termistor com mais [uma peça impressa](http://wiki.foz.ifpr.edu.br/wiki/index.php/Arquivo:E3D_clamp.jpeg).

Feito isso passaremos para a parte com o motor que puxará o filamento. Usaremos uma peça impressa que será fixada ao frame para segurar o rolo de filamento, que será usado posteriormente, e então colocaremos outra peça no mesmo lado do frame que colocamos a peça anterior para segurar o motor que puxará o filamento. Esse motor estará fixado à uma peça com um rolamento.

Para completar esse sistema basta acoplar o tubo de teflon na peça que segura o motor e na entrada da peça que esta na cabeça da impressora, para que o filamento seja guiado por esse tubo.

## Montagem Eletrônica

## Desenvolvimento

- [Bill of materials (BOM)](https://docs.google.com/spreadsheets/d/1wwzYcWkDilSlukoy9v5i6H-2lYjDJjieJFXuUOxKVW0/edit?usp=sharing)

<!-- -->

- [Página da Hypercube](https://www.thingiverse.com/thing:1752766)

<!-- -->

- <a href="Vídeos" class="wikilink" title="Vídeos">Vídeos</a>

<!-- -->

- <a href="Pesquisa_sobre_materiais_de_impressão" class="wikilink" title="Pesquisa sobre materiais de impressão">Pesquisa sobre materiais de impressão</a>

<!-- -->

- <a href="Pesquisa_sobre_reciclagem_de_plásticos" class="wikilink" title="Pesquisa sobre reciclagem de plásticos">Pesquisa sobre reciclagem de plásticos</a>

<!-- -->

- <a href="LOGS" class="wikilink" title="LOGS">LOGS</a>

## Referências

<references />

------------------------------------------------------------------------

<a href="Categoria:LabMaker" class="wikilink" title="Categoria:LabMaker">Categoria:LabMaker</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>
