# Estudos sobre Hidrometeorologia

Responsável: Matheus Santos (Licenciatura em Física)

### Tópicos para estudo:

## Instalação de uma Estação Meteorológica Automática

Uma estação meteorológica é composta por diversos sensores de monitoramento de variáveis como direção e velocidade dos ventos, umidade relativa, pressão atmosférica, temperatura do ar, orvalho, precipitação, radiação solar, entre outras [^1].

**Vento**: deslocamento de ar de uma área de alta pressão atmosférica para uma região de pressão atmosférica mais baixa, normalmente expressado pela sua velocidade e direção.

**Pressão Atmosférica**: é a força exercida por uma coluna de ar sob uma área. No nível do mar, a pressão corresponde a 1 atm.

**Umidade relativa**: em vez da “quantidade de vapor de água no ar” a umidade relativa indica o quão próximo o ar está da saturação, expressada em %. Dessa forma, a razão entre o percentual (em número de moléculas) de água no ar pelo percentual que corresponde à SATURAÇÃO naquela temperatura do ambiente determina a umidade relativa.

**Temperatura do ar**: é uma das variáveis de maior influência nos fenômenos climáticos que acontecem na Terra. Tanto o calor absorvido pela atmosfera quanto o calor emitido pela superfície da terra podem variar a temperatura do ar, e esta por sua vez, tem influência direta em processos como solubilidade, pressão do vapor, densidade e condutividade elétrica, por exemplo. Assim, a temperatura elevada faz com que aumente as taxas de evapotranspiração das plantas.

**Precipitação**: mais conhecida como chuva, consiste na condensação do vapor de água e é responsável pela alimentação do ciclo hidrológico.

**Radiação solar**: energia que dá origem ao ciclo hidrológico, influencia a temperatura do ar e proporciona a circulação atmosférica.

As estações meteorológicas automáticas devem seguir uma série de recomendações para que sua instalação seja adequada para que as futuras medidas sejam mais precisas. Dessa forma, segue algumas precauções a serem tomadas [^2]:

- Obstáculos muito próximos que possam interferir na circulação de ar, causar turbulências, sombrear sensores de temperatura ou coisas do tipo devem ser evitados. Obstáculos devem estar situados a uma distância de 10 vezes a altura do mesmo ou mais;
- A construção da estação em solo impermeável pode gerar altas taxas de radiação, interferindo nas medições, logo, é preferível que a estação se instale em uma região com grama baixa, de forma que não acumule água, evitando encostas ou declives. Um terreno plano é a melhor opção;
- Uma grande rede elétrica pode gerar fortes ondas eletromagnéticas que também interferem nos sensores e devem ser evitados;
- A rede de telemetria deve ter um alcance adequado;
- Locais com previsão próxima para construções não são preferíveis, de modo que terá que mover a estação de lugar caso isso ocorra;
- O norte geográfico deve ser indicado, a fim de se instalar o piranômetro nessa face, minimizando os riscos de sombreamento no sensor;
- A estação deve ser instalada em uma área de aproximadamente 300m² em forma de um octógono, com seu centro situado à 10m de cada face, cerca de 1,5m de altura e o portão na face sul.

Essas recomendações e conceituações são feitas pela Epagri, Empresa de Pesquisa Agropecuária e Extensão Rural de Santa Catarina, onde são feitas pesquisas com mais equipamentos e, consequentemente, uma maior abrangência. Porém, com os equipamentos e espaço que temos à nossa disposição no campus Foz do Iguaçu do IFPR, propomos a ideia de uma estação hidrometeorológica móvel. Dessa forma, pretendemos seguir o maior número de recomendações possíveis para que os dados coletados sejam confiáveis e no futuro desenvolver nossas próprias recomendações para outros pesquisadores que tenham condições de pesquisas similares às nossas.

## Sensação Térmica

Comumente, em dias frios, ouvimos dizer que a temperatura do ar é X e que a sensação térmica é Y \< X, mas como é determinada essa temperatura aparente do ar?

A sensação térmica depende basicamente da temperatura do ar, da velocidade do vento e da umidade do ar.

Existem várias tabelas que constam a sensação térmica em determinadas velocidades do vento e temperatura do ar e também fórmulas para realizar o cálculo dessa grandeza.

De acordo com o National Weather Service, órgão americano responsável pelos estudos meteorológicos e climáticos do país, a sensação térmica pode ser calculada pela fórmula:

<a href="Arquivo:sensacaotermica.jpg" class="wikilink" title="Arquivo:sensacaotermica.jpg">Arquivo:sensacaotermica.jpg</a> [^3] [^4]

onde,

- Twc = sensação térmica (windchill temperature) (ºC);
- Ta = temperatura do ar (ºC);
- V = velocidade do vento (km/h);

É importante dizer que a sensação térmica só é perceptível para organismos vivos, mais especificamente organismos de sangue quente, como os humanos. Por exemplo, a água em um copo não irá congelar apenas por que a velocidade do vento é alta e gera uma sensação térmica abaixo de 0º C. A água só congelará caso a temperatura do ar esteja a º0 C.

## Pressão

Para nossos estudos será necessário definir alguns conceitos relativos à pressão. Essa grandeza é medida levando em consideração o lugar em que se faz a análise, pois, fatores como temperatura, altitude ou até mesmo a quantidade de moléculas presentes num determinado espaço pode variar o valor da pressão.

Caso haja um aumento de temperatura as moléculas ficam mais agitadas, logo, o espaço entre elas aumenta, fazendo com que sua densidade diminua e assim, afetando diretamente a pressão. Observando um aumento de altitude nota-se que a massa de ar sobre o local avaliado é menor, devido a isso, a força que a atmosfera exerce sobre a área é proporcionalmente menor, diminuindo o valor da pressão.

Dessa forma, existem alguns "tipos" de pressão que são comumente utilizados quando se estuda meteorologia:

**Pressão Absoluta**: é medida com relação ao vácuo absoluto, onde a pressão é zero, ou seja, é a região cuja escala inicia com a ausência absoluta de pressão.

**Pressão atmosférica ou barométrica**: é a força exercida pelas massas de gases que envolvem a Terra sobre determinada área em sua a superfície, normalmente avaliada por colunas de ar. A pressão atmosférica equivale à aproximadamente 1.10⁵ Pa ou 1 atm no nível do mar e varia com a altura. Quanto mais alto menor é a pressão atuante nessa região.

**Pressão manométrica ou relativa**: é a pressão interna de um sistema, medida com relação à pressão atmosférica. Dessa forma, o “zero” da pressão manométrica equivale à pressão atmosférica local. Caso o valor mostrado no manômetro seja positivo a pressão é maior que a pressão atmosférica, caso seja negativo, a pressão é menor que a atmosférica. Por ser um equipamento mais barato, o manômetro é utilizado para realizar medidas mais simples de pressão.

Devido à fatores como a inclinação do eixo da Terra, seu movimento de rotação ou as massas de ar que se deslocam de um ponto ao outro o valor da pressão nunca será constante, assim, deve se atentar muito no momento de fazer os cálculos quando se trabalha com pressão para que as aproximações não tragam grandes erros e interfira nos estudos realizados.

## Ponto de Orvalho

O **ponto de orvalho** pode ser definido como, a **temperatura** que o **vapor de água** deve atingir para que sua **umidade** atinja 100%. Ele depende basicamente de três fatores:

- Temperatura da massa de ar (T);
- Umidade relativa da massa de ar (UR);
- Pressão atmosférica (P).

A pressão atmosférica se relaciona com o ponto de orvalho de forma que, em um dado espaço, existe uma quantidade de moléculas de água, ou uma fração molar de vapor de água, que está relacionada com a umidade específica do ar.

Independente da temperatura em que esse processo ocorra, se a pressão aumenta sem variar a fração molar dentro desse espaço, o ar fica mais úmido e o ponto de orvalho aumenta (vamos considerar “aumentar” com o sentido de estar mais próximo de ocorrer). Caso a pressão diminua, o ponto de orvalho diminui na mesma proporção. Porém, pode-se obter uma aproximação para o ponto de orvalho desconsiderando os efeitos da pressão e é dada pela relação a seguir:

`Tpo ≈ T – (100 – UR) / 5`

Onde:

- Tpo = temperatura do ponto de orvalho (oC)
- T = temperatura da massa de ar (oC)
- UR = umidade relativa do ar (%)

A temperatura do ponto de orvalho nunca será maior que a temperatura do ar, caso contrário, poderíamos estar submersos neste momento.

## Norte Geográfico X Norte Magnético

Por muito tempo acreditou-se que o norte magnético e o norte geográfico correspondiam à mesma localização, porém, por volta de 1831, ao viajar para o Alasca o explorador inglês James Ross notou que a agulha de sua bússola só ficava estável quando estava na posição vertical, apontando para o centro da Terra, dessa forma pôde concluir que os nortes não correspondiam à mesma localização.

O **Norte Geográfico ou Norte Real** é aquele referente à localização que corresponde ao eixo de rotação da Terra. Por uma convenção física, os polos magnéticos seriam o inverso dos polos geográficos, assim, o polo norte geográfico corresponderia ao polo sul magnético e vice-versa, porém, a fim evitar confusões foi estabelecido que o norte magnético seria aquele próximo ao norte geográfico.

É dito próximo ao norte real pois, as propriedades magnéticas da Terra são decorrentes do ferro fundido (magma) em seu interior, que apresenta uma rotação um pouco maior que a rotação da própria Terra. Devido à essa movimentação existe uma **deflexão** entre esses dois nortes e deve ser descontada ao realizar alguns estudos e análises.

<a href="Arquivo:DeflexaoMag.jpg" class="wikilink" title="600px">600px</a>

(imagem representando a deflexão entre os polos geográficos e magnéticos)

Dessa forma, o **Norte Magnético** pode ser definido como a direção em que a bússola aponta.

<a href="Arquivo:magnetic_declination_negativa.gif" class="wikilink" title="Arquivo:magnetic_declination_negativa.gif">Arquivo:magnetic_declination_negativa.gif</a>

(Deflexão referente ao norte real e magnético)

Caso a deflexão seja positiva a mesma ocorre para o sentido horário ou para leste, caso contrário, para uma deflexão negativa temos que esta se deslocará para oeste.

De acordo com os estudos do Prof. Dr. Mário Garrido, a cidade de Foz do Iguaçu apresenta uma deflexão magnética de aproximadamente -13º, ou 13º a partir do norte real para oeste, informação muito útil a ser utilizada na instalação de nossa estação meteorológica.

Para encontrar qual a posição mais próxima possível do norte real devemos nos atentar à essa deflexão. Interferências nas medições podem acontecer caso sejam aferidas com uma bússola. Dependendo da região situada, rochas magnetizadas influenciam em seu funcionamento. Para uma maior precisão o uso de um GPS ou giroscópio podem ser uma opção mais confiável.

## Outras Questões

Dando continuidades aos estudos sobre meteorologia, em uma fase de pré implementação da nossa estação hidrometeorológica automática, alguns tópicos para orientar futuras pesquisas surgiram:

- Com que frequência os dados meteorológicos devem ser coletados?
- Quais são os dados comuns solicitados por pesquisadores em um banco de dados meteorológicos?
- Quais dados guardar no histórico?
- Quanto tempo manter os dados no histórico?

De acordo com o INMET – Instituto Nacional de Meteorologia, os dados são coletados de minuto a minuto e são integralizados a cada hora para serem enviados via satélite ou telefonia celular para a sede do INMET em Brasília, os dados são avaliados e guardados em um banco.[^5]

Os dados mais comuns a serem coletados pelas Estações Meteorológicas Automáticas (EMA) são:

- Temperatura Instantânea do Ar
- Temperatura Máxima do Ar
- Temperatura Mínima do Ar
- Umidade Relativa Instantânea do Ar
- Umidade Relativa Máxima do Ar
- Umidade Relativa Mínima do Ar
- Temperatura Instantânea do Ponto de Orvalho
- Temperatura Máxima do Ponto de Orvalho
- Temperatura Mínima do Ponto de Orvalho
- Pressão Atmosférica Instantânea do Ar
- Pressão Atmosférica Máxima do Ar
- Pressão Atmosférica Mínima do Ar
- Velocidade Instantânea do Vento
- Direção do Vento
- Intensidade da Rajada do Vento
- Radiação Solar
- Precipitação acumulada no período

Outros dados podem ser coletados dependendo da implementação dos sensores em cada estação.

Sobre o “descarte” de dados não há nenhuma informação, logo, podemos considerar que os dados são mantidos desde o inicio do funcionamento da estação sem previsão para serem apagados.

## Grupos em outras instituições

- Grupo de Meteorologia e Climatologia - Universidade de Aveiro [CliM@UA](http://climetua.fis.ua.pt/weather)

## Materiais de Referência

- CARVALHO, L. R. M; AMORIM, H. S. [Observando as marés atmosféricas: Uma aplicação da placa Arduino com sensores de pressão barométrica e temperatura](http://www.scielo.br/pdf/rbef/v36n3/13.pdf), Revista Brasileira de Ensino de Física, v. 36, n. 3, 2014.

## Referências

<references />

------------------------------------------------------------------------

<a href="Categoria:_LabMaker" class="wikilink" title="Categoria: LabMaker">Categoria: LabMaker</a>

[^1]: BLAINSKI, E.; POSPISSIL, L. H.; ANTUNES, G. E. N. Estações hidrometeorológicas automáticas: recomendações técnicas para instalação, Epagri, Florianópolis, 2012. <http://ciram.epagri.sc.gov.br/recomendacoes_tecnicas_para_instalacao_de_estacoes.pdf>

[^2]:

[^3]: NWS - National Wether Serevice, National Oceanic and Atmospheric Administration. <http://www.nws.noaa.gov/om/winter/windchill.shtml>

[^4]: Free MATH Help. <http://www.freemathhelp.com/wind-chill.html>

[^5]: INMET - Instituto Nacional de Meteorologia. <http://www.inmet.gov.br/portal/css/content/topo_iframe/pdf/Nota_Tecnica-Rede_estacoes_INMET.pdf>
