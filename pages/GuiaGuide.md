<a href="Arquivo:Guiaguide1.png" class="wikilink" title="200px|thumb|right|Guia Guide">200px|thumb|right|Guia Guide</a>

   
=Equipe=

Professores/Orientadores  

- Alcione Benacchio
- Wellington Oliveira

Alunos  

- Ederson Luiz Knoll
- Gustavo Mendes Ferreira
- Rodrigo Dantas Teixeira

# Introdução

O turismo no Brasil vem destacando-se no cenário mundial. De acordo com Oliveira (2017), em uma comparação entre 136 países em que foram analisadas 14 dimensões do turismo o Brasil aparece na 27º colocação, segundo o Ranking de Competitividade de Viagens e Turismo divulgado em 2017 pelo Fórum Econômico Mundial, sendo o primeiro da América do Sul na pesquisa, e o primeiro do mundo no quesito recursos naturais. Concomitante a divulgação deste relatório segundo a Agência de Notícias do Turismo (2017), o Governo Federal anunciou um pacote de medidas para desenvolver o setor de turismo no país implantando assim o programa Brasil + Turismo que busca principalmente um melhor aproveitamento de nosso potencial turístico tendo como uma de suas metas alcançar 12 milhões de turistas estrangeiros anuais até 2022, além de incentivar também o turista local.

Neste cenário em expansão, um profissional imprescindível para consolidação desse crescimento é o Guia de Turismo. Conforme o artigo primeiro da Lei 8.623 (BRASIL, 1993) o exercício da profissão de Guia de Turismo é regulamentada e o profissional deve possuir curso técnico de formação em Guia de Turismo além de estar habilitado no Cadastro dos Prestadores de Serviços Turísticos - CADASTUR.

Dentre as principais atribuições deste profissional podemos destacar: atividades de acompanhamento, orientação e transmissão de informações a pessoas ou grupos, em visitas, excursões urbanas, municipais, estaduais, interestaduais, internacionais ou especializadas, dentre outras.

# Problemas

- Escassez de informações de regiões turísticas regionais e seus atrativos, segmentadas por cidade, ponto turístico e/ou categoria;
- Falta de informações sobre profissionais Guias de Turismo que atuem em determinadas regiões ou pontos turísticos;
- Dificuldade de encontrar um Guia de Turismo que não seja por intermédio de empresas;
- Dificuldade em contratar pequenos serviços prestados por Guias de Turismo;
- Escassez de ferramenta web dedicada ao profissional Guia de Turismo, para a divulgação de seus serviços;

# Objetivo Geral

O objetivo deste trabalho foi o desenvolvimento de um sistema web com uma ferramenta de busca que traga em seu resultado uma lista de profissionais que atuem em determinados pontos turísticos ou regiões na prestação de serviços de Guias de Turismo.

## Objetivos Específicos

Como objetivos específicos este projeto busca:

- Disponibilizar uma base de dados de profissionais que atuem como de Guias de Turismo.
- Disponibilizar um sistema de busca pelos atrativos turísticos mais visitados por cidades e suas principais informações como: localização, descrição do atrativo e horários de funcionamento.
- Possibilitar aos usuários Turistas que através das buscas disponíveis no sistema encontrem facilmente profissionais que atuem como Guia de Turismo nas regiões ou atrativos turísticos de seu interesse.
- Possibilitar aos profissionais Guias de Turismo que disponibilizem um perfil com suas informações de atuação profissional e de contato, para que usuários interessados possam eventualmente contratar seus serviços.

# Metodologia de Desenvolvimento

Tecnologias a serem utilizadas no projeto:

[`PhpStorm`](https://jetbrains.com/phpstorm)  
`- Versão: 2018.2.1`

[`Apache HTTPD`](http://apache.org)  
`- Versão: 2.4.18`

[`PHP`](http://php.net)  
`-Versão: 7.0.32`

[`Foundation`](https://foundation.zurb.com)  
`- Versão: 6.5.0`

[`JQuery`](https://jquery.com)  
`- Versão: 3.3.1`

[`PostgreSQL`](https://postgresql.org)  
`- Versão: 9.5.14 - x86_64`

[`ViaCEP`](https://viacep.com.br)  
`- Webservice de consulta de CEPs.`

# Trabalhos Relacionados

## Cadastur

O cadastur é um sistema de cadastro do Ministério do Turismo para pessoas físicas e jurídicas que atuam no setor de turismo nacional. É de carácter obrigatório para: guias de turismo, agências de turismo, meios de hospedagem, organizadores de eventos, acampamentos turísticos, parques temáticos e transportadoras turísticas. Mas é opcional para outras atividades como: casas de espetáculo, restaurantes, cafeterias, bares e similares, entre outras.

O sistema dispõe de uma funcionalidade de busca pelos prestadores cadastrados e possibilita que um usuário possa escolher uma cidade e selecionar outros filtros para visualizar algumas informações das empresas ou dos profissionais aptos a prestação de serviços na área de interesse do usuário.

Uma busca por guia de turismo por exemplo, retorna uma lista dos profissionais cadastrados em uma determinada cidade com algumas informações básicas sendo: nome completo, número de cadastro, idiomas, município de atuação, categoria, website, telefone e o período de validade da atividade do profissional.

## Fenagtur

A Federação Nacional dos Guias de Turismo reúne cerca de 18 entidades sindicais representativas da classe de Guias de Turismo de diversos estados brasileiros. Em seu website <http://www.fenagtur.org.br> há uma opção de menu chamada “ache um guia” em que direciona o usuário para uma lista dos sindicatos filiados nos estados com os dados de contato como endereço, telefone e e-mail das entidades e sugere que o usuário interessado em contratar um Guia de turismo, entre em contato com a entidade do estado ou da região de interesse e solicite a indicação de um profissional. Não há no website opção que seja possível visualizar ou consultar os guias cadastrados.

## MeeTrip.com

O site meetrip.com oferece um sistema para reserva de guias de turismos e visitas guiadas ou pacote de visitas oferecidos pelos profissionais ou empresas de turismo cadastrados no sistema. É disponibilizada uma funcionalidade de busca em que o usuário pode optar por selecionar uma visita guiada ou um profissional prestador dos serviços de guia de turismo, além de poder selecionar as cidades mais visitadas. Todos os guias de turismo cadastrados no sistema são profissionais certificados nos países em que atuam, esse é um requisito do sistema para que o profissional ofereça seus serviços no site. Para que seja possível contratar qualquer serviço ou entrar em contato com qualquer profissional o usuário deve realizar seu cadastro no sistema, após isso é possível enviar mensagens a algum guia escolhido e solicitar mais informações. O site faz a intermediação do pagamento pelos serviços disponibilizados pelos profissionais cadastrados no sistema, ou seja, o usuário pode contratar qualquer serviço e efetuar pagamentos direto para o site e que após o serviço finalizado pelo profissional contratado o site repassa o pagamento ao profissional caso não haja nenhuma objeção do usuário referente a prestação do serviço. A empresa detentora do sistema tem sua sede na cidade de Paris na França.

## Considerações sobre os trabalhos relacionados

A busca e contratação de prestadores de serviços através da Internet é um fato corriqueiro na atualidade. Profissionais de diversas áreas têm feito uso da tecnologia para divulgar suas habilidades e com isso encontrar novos clientes, assim como, usuários comuns têm usado a facilidade de realizar uma busca na internet a procura de profissionais que prestam serviços nos mais variados segmentos.

Foram realizadas diversas buscas na internet no intuito de listar sites em que fosse possível encontrar guias de turismo que de alguma forma estejam dispostos a oferecer seus serviços e iniciar uma troca de informações online com clientes interessados em contratar um guia de turismo, além de possibilitar aos usuários navegar entre os atrativos turísticos mais conhecidos e visitados do país, e também como premissa adicional fosse possível que nos atrativos turísticos houvesse ligação com os profissionais atuantes na região do próprio atrativo visitado.

Para encontrar um guia de turismo no Brasil e visualizar suas principais informações o melhor sistema encontrado foi o site Cadastur que é mantido pelo Governo Federal sendo de responsabilidade do Ministério do Turismo. Nele é possível realizar buscas refinadas por cidade e nos resultados encontrar diversos guias de turismo cadastrados, podendo escolher um resultado e após selecionar o profissional visualizar um pequeno perfil com suas principais informações. Já a segunda opção o site da Federação Nacional dos Guias de Turismo não disponibiliza e nem fornece uma lista dos guias de turismo cadastrados na federação muito menos fornece informações sobre atrativos turísticos cabendo ao interessado entrar em contato via telefone e solicitar a indicação de profissionais. Porquanto a terceira opção encontrada é um site estrangeiro, mas que traz opções mais parecidas com as que se desenvolve no projeto GuiaGuide, como realizar buscas por guias de turismo e pelas cidades mais visitadas por turistas que utilizam o sistema. Também há opção de entrar em contato com os profissionais e trocar mensagens com a finalidade de realizar a contratação de serviços, sendo o site MeeTrip um intermediador do pagamento pelos serviços a serem prestados e que posteriormente repassa os valores ao profissional que prestou o serviço ao cliente pagador. Não foram encontrados outros produtos de maior relevância para o seguimento.

Nos três casos identificados anteriormente, não foram encontradas opções que possibilitassem ao usuário navegar pelos principais atrativos turísticos e colher informações sobre a localização, particularidades do atrativo, o período que está disponível ao público ou imagens do local, consequentemente não há associação dos guias de turismo que atuem nesses atrativos turísticos. A escassez de informações sobre a atuação dos guias de turismo profissionais como por exemplo: em quais regiões ou atrativos atuam, quais as suas principais especialidades, os idiomas falados, e principalmente uma lista de profissionais com um ranking dos melhores colocados, sendo essa classificação gerada pelos votos dos próprios clientes que foram atendidos por estes profissionais. Estas são algumas das soluções que o sistema GuiaGuide se propõe a oferecer.

# Modelagem

## Levantamento de Requisitos

O levantamento de requisitos é realizado na fase inicial do desenvolvimento de software e deve abranger o levantamento de dados e informações sobre o contexto das atividades que serão suportadas pelo sistema. De acordo com Silva (2008): “requisito é uma especificação de uma característica ou propriedade que um sistema deve possuir ou fazer, assim como sua restrição de operação”. No presente trabalho foram definidos os Requisitos Funcionais, Requisitos Não Funcionais Tecnológicos e Regras de Negócio.

### Requisitos Funcionais

A necessidade de atender determinadas funcionalidades do software é concretizada através de funções desenvolvidas a partir do levantamento dos requisitos funcionais a seguir descritos:

<table border="1" cellpadding="2">

<tr>

<th>

Código

</th>

<th>

Requisito Funcional

</th>

</tr>

<tr>

<td>

RF 01

</td>

<td>

O sistema deve manter “Guias” com os seguintes dados: usuário, nome, data de nascimento, data de cadastro, sexo, número de certificado CADASTUR, foto, endereço (país, estado, cidade, bairro, cep, rua, numero), e-mail, telefones para contato, senha, idiomas, redes sociais (opcional), categoria, empresas que trabalhou, e um pequeno texto (sobre mim) onde o profissional possa detalhar mais sobre sua experiência e histórico profissional (breve currículo).

</td>

</tr>

<tr>

<td>

RF 02

</td>

<td>

O sistema deve manter “Turistas” com os seguintes dados: usuário, nome, data de nascimento, data de cadastro, sexo, endereço (país, estado, cidade, cep, bairro, rua, número), e-mail, telefones para contato, senha, redes sociais (opcional) e regiões ou pontos turísticos de interesse (opcional).

</td>

</tr>

<tr>

<td>

RF 03

</td>

<td>

O sistema deve manter Categoria de Guia de Turismo.

</td>

</tr>

<tr>

<td>

RF 04

</td>

<td>

O sistema deve manter Idiomas.

</td>

</tr>

<tr>

<td>

RF 05

</td>

<td>

O sistema deve permitir a busca de “Guias” por cidade, ponto turístico, categoria e idioma.

</td>

</tr>

<tr>

<td>

RF 06

</td>

<td>

O sistema deve permitir um comparativo (Ranking) entre os Guias cadastrados, com pontuação expressa na escala likert de 5 níveis, resultantes da média das avaliações feitas pelo “Turista”.

</td>

</tr>

<tr>

<td>

RF 07

</td>

<td>

O sistema deve manter a avaliação do turista para o guia. A avaliação ficará visível para todos usuários do sistema.

</td>

</tr>

<tr>

<td>

RF 08

</td>

<td>

O sistema deve manter a avaliação do guia para o turista. A avaliação ficará visível somente para outro guia.

</td>

</tr>

<tr>

<td>

RF 09

</td>

<td>

O sistema deve manter e permitir a troca de mensagens entre guia e turista.

</td>

</tr>

<tr>

<td>

RF 10

</td>

<td>

O sistema deve manter Países, Estados e Cidades cadastrados pelo administrador do sistema.

</td>

</tr>

<tr>

<td>

RF 11

</td>

<td>

O sistema deve controlar o acesso dos usuários por meio de login e senha.

</td>

</tr>

<tr>

<td>

RF 12

</td>

<td>

O sistema deve manter Ponto Turístico, com os seguintes dados: nome, fotos, endereço (estado, cidade , cep, bairro, numero, rua), horário de funcionamento. A serem cadastrados pelo administrador do sistema.

</td>

</tr>

<tr>

<td>

RF 13

</td>

<td>

O sistema deve permitir a troca de idiomas em momento de execução.

</td>

</tr>

<tr>

<td>

RF 14

</td>

<td>

O sistema deve manter Negociação. A negociação deve possuir sempre um "Guia", um "Turista", um ou mais pontos turísticos, data de abertura, data de encerramento e status.

</td>

</tr>

</table>

### Lista de Requisitos Não Funcionais Tecnológicos

Os requisitos não funcionais foram levantados a partir de necessidades externas para o desenvolvimento do projeto como a infraestrutura, as ferramentas necessárias e a organização. No quadro a seguir foram elencados alguns requisitos não funcionais tecnológicos:

<table border="1" cellpadding="2">

<tr>

<th>

Código

</th>

<th>

Requisito Não Funcional Tecnológico

</th>

</tr>

<tr>

<td>

RNFT 01

</td>

<td>

O sistema deve ser compatível com os principais navegadores web, e possuir layout responsivo.

</td>

</tr>

<tr>

<td>

RNFT 02

</td>

<td>

Deve ser desenvolvido em linguagem JAVA para o servidor de serviços (WebService), PHP para controles de sessão, utilizando-se elementos JQuery e o Framework Foundation para o Front End além de folhas de estilos em CSS e bibliotecas Java Script. As IDEs Eclipse e PHPStorm serão utilizadas para auxiliar no desenvolvimento.

</td>

</tr>

<tr>

<td>

RNFT 03

</td>

<td>

O sistema deve utilizar o banco de dados PostgreSQL.

</td>

</tr>

<tr>

<td>

RNFT 04

</td>

<td>

Todo o sistema deve ser mantido e hospedado em um servidor físico para o gerenciamento dos serviços e do banco de dados.

</td>

</tr>

</table>

### Lista de Regras de Negócio

Em complementação aos requisitos funcionais e não funcionais existem as regras de negócio que, de acordo com Ventura (2016) referem-se a premissas ou restrições do negócio propriamente dito e devem atender as expectativas comerciais da empresa ou do setor para o qual o software está sendo desenvolvido, neste contexto no quadro abaixo foram elencadas as regras de negócio do sistema Guia Guide:

<table border="1" cellpadding="2">

<tr>

<th>

Código

</th>

<th>

RF

</th>

<th>

Regra de Negócio

</th>

</tr>

<tr>

<td>

RN 01

</td>

<td>

01

</td>

<td>

O guia deve concordar em divulgar seus dados para o público do sistema.

</td>

</tr>

<tr>

<td>

RN 02

</td>

<td>

01

</td>

<td>

O guia deve informar obrigatoriamente o seu registro no CADASTUR.

</td>

</tr>

<tr>

<td>

RN 03

</td>

<td>

02

</td>

<td>

O turista deve concordar em divulgar seus dados para os guias como os quais manter contato pelo sistema.

</td>

</tr>

<tr>

<td>

RN 04

</td>

<td>

09

</td>

<td>

O envio de mensagens somente poderá ser iniciado pelo turista.

</td>

</tr>

<tr>

<td>

RN 05

</td>

<td>

12

</td>

<td>

Uma negociação somente poderá ser iniciada se o turista escolher no mínimo um ponto turístico.

</td>

</tr>

<tr>

<td>

RN 06

</td>

<td>

14

</td>

<td>

O guia somente terá acesso aos dados de um turista caso esteja em status de negociação aberto com o mesmo.

</td>

</tr>

<tr>

<td>

RN 07

</td>

<td>

14

</td>

<td>

O guia deve aceitar abrir uma negociação, somente mediante solicitação prévia do turista.

</td>

</tr>

</table>

## Diagramas de Análise e Modelagem do Sistema

Os diagramas de análise e modelagem do sistema são concebidos na linguagem UML e tem por objetivo representar o sistema em níveis diferentes de detalhes. Segundo o IBM Knowledge Center os diagramas UML ilustram os aspectos qualificáveis de um sistema que podem ser descritos visualmente, como relacionamentos, comportamento, estrutura e funcionalidade.

### Diagrama de Caso de Uso Geral

<a href="Arquivo:Pi2guiaguideucgeral.jpg" class="wikilink" title="600px|">600px|</a>

## Diagramas do Projeto

### Diagrama Entidade Relacionamento (Workbench)

Para que o sistema possa armazenar e manipular dados e informações foi necessária a criação de um banco de dados, o qual foi implementado na linguagem PostgreSQL na sua versão 10. A figura a seguir demonstra a representação gráfica das tabelas do banco de dados, seus atributos e o relacionamento existente entre elas.

<a href="Arquivo:Workbench_guiaguide.png" class="wikilink" title="800px|">800px|</a>

# Conclusão e Trabalhos Futuros

Segundo dados do Ministério do Turismo atualmente o Brasil conta com pouco mais de 20 mil Guias de Turismo profissionais com cadastro ativo no Cadastur e aptos a exercer a profissão.

A atuação focada do profissional para atender as demandas específicas de clientes com necessidades e desejos peculiares através de uma segmentação do mercado visa contribuir para o sucesso no seu ramo de negócios, contribuindo para que o profissional atue dentro de um nicho de mercado. Neste contexto, Kotler (1997) diz que nicho de mercado é “um grupo definido mais estritamente, um mercado pequeno cujas necessidades não estão sendo totalmente satisfeitas”.

Como forma de atrair usuários e a fim de fomentar as atividades dentro do sistema, é disponibilizado um banco de dados com diversos atrativos turísticos naturais, históricos e culturais acessíveis através de buscas já na página inicial do website, e nos resultados são apresentados os dados principais do atrativo com imagens que corroboram as informações textuais e também são usadas como ferramenta de marketing para aguçar o interesse do usuário naquele determinado atrativo.

Portanto a principal proposta apresentada neste projeto é fornecer um sistema de apoio para esta classe de profissionais, com ferramentas tecnológicas capazes de proporcionar a aproximação entre cliente e prestador de serviços, contribuindo para a consolidação do crescimento do setor turístico nas regiões que detém esses atrativos e principalmente onde os guias de turismo atuem. Como trabalhos futuros, planeja-se implementar na plataforma um módulo destinado ao uso pela administração pública, para que esta possa sugerir a inclusão de novos atrativos turísticos localizados nas áreas de sua administração. O intuito desta implementação será o de fomentar a divulgação de novos locais com potencial turístico, mas que ainda são pouco conhecidos.

No perfil de profissionais será disponibilizado opções para criar galerias com imagens de excursões ou dos atendimentos realizados, bem como a inclusão de mídia audiovisual com pequenos filmes, produções relacionadas as atividades do profissional ou ligadas aos atrativos turísticos da sua região. E por fim planeja-se a implementação da intermediação de pagamentos do sistema através de gateways de pagamento que oferecerão opções facilitadas como o pagamento por cartões de crédito.

# Referências

**OLIVEIRA, MARIANA.** Brasil avança no ranking de Competitividade em turismo do Fórum Econômico Mundial. Disponível em: \<<http://www.turismo.gov.br/últimas-notícias/7673-brasil-avança-no-ranking-de-competitividade-em-turismo-do-fórum-econômico-mundial.html>\>. Acesso em: 06 mar. 2018.

**MINISTÉRIO DO TURISMO.** Governo Federal anuncia o Brasil + Turismo, pacote de medidas para desenvolver o setor no país. Disponível em: \<<http://www.turismo.gov.br/últimas-notícias/7691-governo-federal-anuncia-o-brasil-turismo,-pacote-de-medidas-para-desenvolver-o-setor-no-país.html>\>. Acesso em: 06 mar. 2018.

**SITE PRESIDÊNCIA DA REPÚBLICA.** LEI Nº 8623, DE 28 DE JANEIRO DE 1993. Disponível em: \< <http://www.planalto.gov.br/ccivil_03/leis/l8623.htm/>\>. Acesso em: 28 mar. 2018.

**GAMMA, Erich et al.** Padrões de Projeto: soluções reutilizáveis de software Orientado a Objetos. Porto Alegre: Bookman, 2000.

**SILVA, MARCIO A.** Brasil A importância do levantamento de requisitos no sucesso dos projetos de software. Disponível em: \< <http://www.linhadecodigo.com.br/artigo/1685/a-importancia-do-levantamento-de-requisitos-no-sucesso-dos-projetos-de-software.aspx>\>. Acesso em: 13 jun. 2018.

**VENTURA, PLÍNIO.** O que é Regra de Negócio? Disponível em: \<<https://www.ateomomento.com.br/o-que-e-regra-de-negocio/>\>. Acesso em: 03 jul. 2018.

**MINISTÉRIO DO TURISMO.** Guias de Turismo - 3º Trimestre/2018. Disponível em: \< <http://www.turismo.gov.br/dadosabertos/cadasturpf/201803TrimestrePF.csv>\>. Acesso em: 14 nov. 2018.

**KOTLER, Philip.ARMSTRONG, Gary.** Princípios de Marketing.LTC.1997.
