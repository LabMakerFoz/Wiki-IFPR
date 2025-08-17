# Gerenciador de Reuniões Flex Meeting

## Introdução

Atualmente o gerenciamento operacional e estratégico das organizações, todo o processo de tomada de decisão é definido por meio de execução de reuniões. Frequentemente, estas não são devidamente planejadas, nem obtêm-se os resultados esperados, pois as informações simplesmente se perdem, ou são de difícil acesso por serem registradas manualmente, dificultando ou inviabilizando sua reutilização em novas tomadas de decisão. A partir deste cenário, estamos desenvolvendo um sistema que visa auxiliar na solução dos problemas citados, através de um sistema web, que irá gerenciar as reuniões visando evitar a dispersão do tempo e do foco que por vezes é ocasionado por falta de organização. O sistema será responsável por gerenciar o cadastro e a manutenção de informações de usuários, bem como o de reuniões como um todo, abordando todos os aspectos necessários para que ocorra uma reunião com um melhor nível de desempenho e aproveitamento, desde a sua convocação e distribuição de papéis e avisos, até a geração da ata e sua finalização.

## Objetivo Geral

Desenvolver um sistema web capaz de gerenciar reuniões, desde o processo de agendamento, envio de comunicados aos participantes, e acompanhamento durante as reuniões, sendo possível fazer anotações conforme a reunião decorre, para que no final a ata seja gerada, até a possível marcação de reuniões futuras com temas similares ou não. visando assim um maior nível de aproveitamento do tempo utilizado em reuniões acadêmicas e visando agilizar todo o processo de reuniões em geral.

## Objetivos Específicos

- O sistema possibilita o gerenciamento de agendamento de reuniões.
- O sistema deve gerenciar pautas de reunião.
- O sistema deve gerenciar o comparecimento dos participantes.
- Preenchimento e geração da Ata de reunião durante a sua execução, por ponto de pauta e disponibilizá-la em formato PDF.

## Equipe

Professores orientadores  

- Alcione Benacchio
- Wellington Oliveira

Alunos  

- Pablo Lima Flores
- Tiago Marins de Queiroz

## Escopo do projeto

O sistema de gerenciamento de reuniões tem o foco de facilitar e agilizar todo o processo que envolve reuniões, visando também padronizá-las em um formato que melhor atenda às necessidades dos envolvidos. Para que isso se realize, o sistema contará com uma série de mecanismos que possibilitarão organizar e acompanhar uma reunião desde o planejamento inicial até a sua finalização e possível marcação de reuniões futuras, ligadas ao tema já discutido ou não. O sistema seguirá um padrão para melhor atender as necessidades, que foram levantadas em pesquisas. O sistema contará com cadastro de usuários, que serão divididos em dois perfis, o **perfil administrador**, com acesso global às funcionalidades do sistema, responsável pela sua manutenção e o **perfil usuário**, que é o usuário padrão, que possuirá restrições às telas administrativas(cadastros, por exemplo). Este também será responsável pela manutenção das reuniões, em todo o seu “ciclo de vida”, desde o agendamento, definição da pauta, a execução da reunião, finalizando com a geração da ata. Em termos teóricos, uma reunião, poderá ter diferentes tipos de participantes, sendo estes: um **facilitador** (conduz a discussão, assegurando-se de que todos os lados da questão são levantados), um **anotador** (anota as ideias e decisões principais e distribui anotações), um **controlador** (que ajuda na evolução da discussão de modo eficiente), um **colaborador** (necessário para manter o foco e a discussão ativa) e um **especialista** (compartilha conhecimento sobre o assunto a ser tratado). Dependendo do tipo de reunião definida, alguns destes tipos podem não ser necessários ou uma mesma pessoa pode exercer as funções de mais de um tipo. Em relação ao **agendamento**, o sistema disponibilizará opções que incluem algumas particularidades a serem seguidas, tais como:

- Título
- Data
- Local
- Hora início
- Hora término
- Objetivo
- Tipo
- Possui pré-requisito? Qual?
- Solicitante
- Mediador
- Secretário
- Integrantes

Por padrão, será estipulado o **tempo** máximo de uma hora. Caso necessário, a partir de uma justificativa, pode-se aumentar esse período. O **objetivo** é uma descrição breve do que se pretende ser alcançar com a reunião. Em relação ao **tipo**, o sistema possibilitará cadastro de novos registros, mas possuirá alguns tipos primários como base, sendo estes:

- Brainstorm: Onde cada pessoa sugere alternativas para cada fase, ou etapa, do problema definido, sem que haja discriminações ou críticas por parte dos outros envolvidos.
- Consultiva: Deve apresentar tema relativo à decisão em outras instâncias e que afetam direta ou indiretamente os envolvidos.
- Deliberativa: Deve apresentar o tema de consulta aos integrantes, devendo considerar tempo extra para debates, para que todos os integrantes possam ter o mesmo tempo para se pronunciar.
- Trabalho: Deve ser focado na realização de uma atividade ou demanda em tempo determinado, idealmente duas horas.
- Mista: situação a qual a tipificação será dada por cada tópico.

Caso seja marcada a obrigatoriedade de **pré-requisito**, pode-se especificá-lo, como por exemplo, ter participado de uma reunião anterior, ou ter um conhecimento sobre um assunto específico. Nos casos em que o participante é permitido o comparecimento, mesmo sem cumprir o pré-requisito, este não terá “voz ativa”, ou seja, só estará lá para ouvir e ficar ciente do assunto, mas não poderá debater, opinar ou votar em nada relacionado à reunião). As atribuições entre os participantes, no sistema, podem ser:

- Solicitante: que é a pessoa responsável por agendar e informar todos os dados necessários para marcar a reunião.
- Mediador: é quem conduzirá a reunião (poderá ser a mesma pessoa que solicitou a reunião ou não). Engloba a funções de facilitador e colaborador.
- Secretário: possui a função de anotador e é responsável por registrar sobre o andamento da reunião e fazer a ata de reunião.
- Integrantes que serão as demais pessoas que irão compor a reunião e discutir sobre a mesma.

Após a reunião ser agendada com sucesso, haverá um prazo para o usuário que a cadastrou submeta a pauta(por exemplo até 24h antes do horário previsto). A pauta será dividida por tópicos. Cada tópico será composto por:

- Peso ou ordem de discussão/importância.
- Responsável pelo tópico.
- Descrição do que será abordado.
- Tipo (caso o tipo da reunião for definido como Misto). Segue a mesma tipificação da reunião.
- Tempo que deverá ser acompanhado pelo sistema para evitar problemas de excesso de tempo de um tema e falta de outros.
- E se é aberto a debates pois dependendo do tipo de reunião debates não são necessários.

O sistema deverá avisar os participantes que foram convocados para a reunião através de um e-mail e também deverá marcar no google agenda (calendar) o dia e horário que ocorrerá. Ao decorrer da reunião, serão exibidos todos os tópicos. Haverá área específica para registro de anotações por tópico. Ao término será permitido a criação da **ata de reunião**, onde serão descritas as informações tratadas, como a **ordem** dos tópicos, seu **responsável**, o **tempo** executado, o que foi discutido e **definido**, por tópico. Haverá a possibilidade de se registrar, apenas a nível informativo, as **ações** a serem tomadas, com os respectivos **responsáveis**. Ao final de cada reunião, deverá ser possível disponibilizar a ata em formato PDF, para que todos os participantes tenham acesso ao que foi decidido em reunião e ficarem cientes das escolhas. Também ao término da reunião, deverá ser possível fazer um agendamento para as próximas reuniões, com periodicidade a ser escolhida pelo mediador da reunião.

## Lista de Requisitos

<table>
<tbody>
<tr>
<td><div style="text-align: center;">
<p><strong><em>Código</em></strong></p>
</div></td>
<td><div style="text-align: center;">
<p><strong><em>Requisito Funcional</em></strong></p>
</div></td>
</tr>
<tr>
<td><p>RF 1</p></td>
<td><p>O sistema deve manter pessoas.</p></td>
</tr>
<tr>
<td><p>RF 2</p></td>
<td><p>O sistema deve permitir (ou não) que pessoas tenham a possibilidade acessar o sistema.</p></td>
</tr>
<tr>
<td><p>RF 3</p></td>
<td><p>O sistema deve permitir tipificar o acesso da pessoa em: administrador e usuário.</p></td>
</tr>
<tr>
<td><p>RF 4</p></td>
<td><p>O sistema deve manter reuniões.</p></td>
</tr>
<tr>
<td><p>RF 5</p></td>
<td><p>O sistema deve manter integrantes.</p></td>
</tr>
<tr>
<td><p>RF 6</p></td>
<td><p>O sistema deve manter tipos.</p></td>
</tr>
<tr>
<td><p>RF 7</p></td>
<td><p>O sistema deve manter tipos de participante.</p></td>
</tr>
<tr>
<td><p>RF 8</p></td>
<td><p>O sistema deve permitir o agendamento de reunião.</p></td>
</tr>
<tr>
<td><p>RF 9</p></td>
<td><p>Cada tipo de reunião deve ter um tempo de execução padrão.</p></td>
</tr>
<tr>
<td><p>RF 10</p></td>
<td><p>O sistema deve manter pontos de pauta.</p></td>
</tr>
<tr>
<td><p>RF 11</p></td>
<td><p>O sistema deve manter atas de reunião.</p></td>
</tr>
<tr>
<td></td>
<td></td>
</tr>
</tbody>
</table>

<table>
<tbody>
<tr>
<td><div style="text-align: center;">
<p><strong><em>Código</em></strong></p>
</div></td>
<td><div style="text-align: center;">
<p><strong><em>Requisito Não Funcional Tecnológico</em></strong></p>
</div></td>
</tr>
<tr>
<td><p>RNFT 1</p></td>
<td><p>O sistema deve ser executado em ambiente web.</p></td>
</tr>
<tr>
<td><p>RNFT 2</p></td>
<td><p>O sistema deve ser desenvolvido utilizando a linguagem Java.</p></td>
</tr>
<tr>
<td><p>RNFT 3</p></td>
<td><p>O sistema deve utilizar as ferramentas do “ecossistema” Spring, como o Spring Security e o Spring Data.</p></td>
</tr>
<tr>
<td><p>RNFT 4</p></td>
<td><p>O sistema deve ser construído utilizando o thymeleaf e o bootstrap como ferramentas de desenvolvimento front-end</p></td>
</tr>
<tr>
<td><p>RNFT 5</p></td>
<td><p>O sistema utilizará o sistema de banco de dados relacional PostgreSQL.</p></td>
</tr>
<tr>
<td><p>RNFT 6</p></td>
<td><p>O sistema utilizará o framework Hibernate para acesso e persistência dos dados.</p></td>
</tr>
<tr>
<td><p>RNFT 7</p></td>
<td><p>O sistema deverá utilizar a API do google calendar(Agenda).</p></td>
</tr>
<tr>
<td></td>
<td></td>
</tr>
</tbody>
</table>

<table>
<tbody>
<tr>
<td><div style="text-align: center;">
<p><strong><em>Código</em></strong></p>
</div></td>
<td><div style="tex-align: center;">
<p><strong><em>RF</em></strong></p>
</div></td>
<td><div style="text-align: center;">
<p><strong><em>Regras de Negócio</em></strong></p>
</div></td>
</tr>
<tr>
<td><p>RN1</p></td>
<td><p>RF1, RF2</p></td>
<td><p>O e-mail da pessoa deve ser único e, caso seja marcado como usuário, será utilizado como login ao sistema.</p></td>
</tr>
<tr>
<td><p>RN 2</p></td>
<td><p>RF1, RF6, RF7</p></td>
<td><p>Somente pessoas com permissão de acesso do tipo administrador poderão acessar a tela de cadastros.</p></td>
</tr>
<tr>
<td><p>RN 3</p></td>
<td><p>RF2</p></td>
<td><p>Pessoa que possuir acesso do tipo 'usuario' não terão permissão de acesso às rotinas administrativas (cadastros de pessoas, tipos e tipo participante).</p></td>
</tr>
<tr>
<td><p>RN 4</p></td>
<td><p>RF7</p></td>
<td><p>No agendamento, deve-se preencher as seguintes informações: título, data, local, hora início, hora fim, objetivo, tipo, pré-requisito, solicitante, mediador, secretario e integrantes.</p></td>
</tr>
<tr>
<td><p>RN 5</p></td>
<td><p>RF9</p></td>
<td><p>Caso a reunião necessitar possuir um período maior do que o estipulado pelo seu tipo, deve-se adicionar uma justificativa.</p></td>
</tr>
<tr>
<td><p>RN 6</p></td>
<td><p>RF10</p></td>
<td><p>A reunião deve, obrigatoriamente, possuir pelo menos um ponto de pauta associado.</p></td>
</tr>
<tr>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

## Diagrama de Classes

<a href="Arquivo:DiagramaDeClasseReuniao2.png" class="wikilink" title="900px">900px</a>

## Diagrama de Caso de Uso

<a href="Arquivo:DiagramaDeCasoDeUso.png" class="wikilink" title="900px">900px</a>

## Modelo Entidade e Relacionamento(MER)

<a href="Arquivo:MerReuniaoFinals.jpg" class="wikilink" title="Arquivo:MerReuniaoFinals.jpg">Arquivo:MerReuniaoFinals.jpg</a>

## Dicionário de Dados

  
**Tabela Participante**  
<a href="Arquivo:participante3.png" class="wikilink" title="Arquivo:participante3.png">Arquivo:participante3.png</a>

<hr>

  
**Tabela Pessoa**  
<a href="Arquivo:pessoa2.png" class="wikilink" title="Arquivo:pessoa2.png">Arquivo:pessoa2.png</a>

<hr>

  
**Tabela PontoPauta**  
<a href="Arquivo:pontoPauta2.png" class="wikilink" title="Arquivo:pontoPauta2.png">Arquivo:pontoPauta2.png</a>

<hr>

  
**Tabela Reuniao**  
<a href="Arquivo:reuniao2.png" class="wikilink" title="Arquivo:reuniao2.png">Arquivo:reuniao2.png</a>

<hr>

  
**Tabela Tipo**  
<a href="Arquivo:tipo2.png" class="wikilink" title="Arquivo:tipo2.png">Arquivo:tipo2.png</a>

<hr>

  
**Tabela tipoParticipante**  
<a href="Arquivo:tipoParticipante2.png" class="wikilink" title="Arquivo:tipoParticipante2.png">Arquivo:tipoParticipante2.png</a>

## Tecnologias utilizadas

[`Eclipse`](https://www.eclipse.org/oxygen/)  
`  -Versão: Oxygen.1a (4.7.1a)`

[`Java`](https://www.oracle.com/technetwork/pt/java/javase/downloads/jdk8-downloads-2133151.html)  
`    -Versão: 8`

[`Maven`](https://maven.apache.org/)  
`   -Versão:4.0.0`

[`Spring Boot`](http://spring.io/projects/spring-boot/)  
`   -Versão: 2.0.5`

[`Tomcat`](https://tomcat.apache.org/download-90.cgi)  
`   -Versão: 9.0.12`

[`PostgreSQL`](https://www.postgresql.org/)  
`   -Versão: 9.6.10`

[`Hibernate`](https://hibernate.org/)  
`   -Versão: 5.2.17`

[`Lombok`](https://projectlombok.org/)  
`   -Versão: 1.18.2`

`[HTML]`  
`   -Versão: 5`

`[CSS]`  
`   -Versão: 3`

[`Thymeleaf`](https://www.thymeleaf.org/)  
`   -Versão: 3.0.9`

[`Bootstrap`](http://getbootstrap.com)  
`   -Versão: 4.1.3`

## Trabalhos Relacionados

### Meeting king

O meeting king é um sistema web voltado para a criação e edição de atas de reunião, visando automatizá-las. O sistema também é capaz de enviar e-mails a todos os participantes, além de fornecer diversos modelos de atas, tais como o de **reuniões rotativas**, **vendas** dentre outros modelos, e possibilita também que o próprio usuário crie um modelo de ata personalizado

<a href="Arquivo:MeetingKing2.png" class="wikilink" title="1000px">1000px</a>

<div style="text-align: center;">

Menu Principal.

</div>

<hr>

  
  
<a href="Arquivo:MeetingKing3.png" class="wikilink" title="1000px">1000px</a>

<div style="text-align: center;">

Tela de agendamento de reunião.

</div>

<hr>

[Link para o site do Meeting King](https://meetingking.com/)

  
  
  

### GMinutes

O GMinutes é um sistema web e mobile voltado para o gerenciamento de reuniões de forma profissional. Possui uma série de de funções, tais como:

- Agendamento e envio de convites aos participantes.
- Atribuição de papéis aos participantes.
- Criar, editar e visualizar atas de um modelo pré-definido.
- Reagendar reuniões se necessário.

<a href="Arquivo:GMinutes.png" class="wikilink" title="1000px">1000px</a>

<div style="text-align: center;">

Menu Principal.

</div>

<hr>

  
  
<a href="Arquivo:Gminutes2.png" class="wikilink" title="1000px">1000px</a>

<div style="text-align: center;">

Tela de agendamento de reunião.

</div>

<hr>

[Link para o site do GMinutes](http://gminutes.com/)

## Telas do sistema Flex Meeting

<a href="Arquivo:listaReuniao.png" class="wikilink" title="1000px">1000px</a>

<div style="text-align: center;">

Tela de listagem de Reuniões.

</div>

- **Descrição do funcionamento da página**

O botão **buscar** localizado na parte superior direita da tela trabalha em conjunto com a barra de pesquisa, que tem como finalidade solicitar a busca utilizando um filtro que retorna as informações da reunião que foi inserida na barra de pesquisa, facilitando a procura por uma reunião específica. O botão **limpar** localizado ao lado do botão buscar, tem como finalidade limpar o campo de buscas e os resultados retornados da pesquisa, e assim listar todas as reuniões novamente. O botão **novo** tem como finalidade inserir uma nova reunião no sistema. O botão **editar** localizado um pouco abaixo dos botões já citados, tem como finalidade possibilitar a edição das informações de uma reunião já cadastrada. O botão **excluir** tem como finalidade deletar uma reunião do sistema. O botão **pautas** tem como finalidade redirecionar para a tela de cadastro de pautas pertinentes a reunião que está alinhada com os botões. O botão **executar** tem como finalidade direcionar para a tela de execução da reunião, na qual é possível tomar notas em cada pauta. Os botões na parte inferior da tela tem como finalidade fazer a transição de páginas dos registros.  
  

<hr>

<a href="Arquivo:cadastroReuniaoFinal.png" class="wikilink" title="1000px">1000px</a>

<div style="text-align: center;">

Tela de Cadastro de Reuniões.

</div>

- **Descrição do funcionamento da página**

O lado esquerdo da tela apresenta um formulário com todas as informações necessárias para agendar uma reunião, o lado direito da tela apresenta a lista de todas as pessoas cadastradas no sistema e que podem ser escolhidas como participantes da reunião, através da marcação do checkbox de cada pessoa a ser convocada.  
  

<hr>

<a href="Arquivo:pauta.png" class="wikilink" title="1000px">1000px</a>

<div style="text-align: center;">

Tela de Pautas.

</div>

- **Descrição do funcionamento da página**

O lado esquerdo da tela possui as informações da reunião cujo a pauta foi cadastrada, visando oferecer uma melhor contextualização das informações. O lado direito possui a lista de pautas cadastradas na reunião, com dois botões, o verde para editar as informações da pauta e o vermelho para deletar a pauta da reunião. O botão **cadastrar** abre uma janela modal para cadastrar uma nova pauta da reunião.  
  

<hr>

<a href="Arquivo:main.png" class="wikilink" title="1000px">1000px</a>

<div style="text-align: center;">

Tela do Usuário.

</div>

- **Descrição do funcionamento da página**

O lado esquerdo da tela ficam listadas as reuniões que já ocorreram, com o botão **detalhes** para acessar os detalhes de cada reunião. O lado direito da tela ficam listadas as reuniões que ainda irão ocorrer.

## Referencias Bibliográficas

- Tecnologias utilizadas:

**Spring security** Framework voltado para a segurança e controle de login do sistema. Disponível em: <https://grokonez.com/spring-framework/spring-security/use-spring-security-jdbc-authentication-mysql-spring-boot>. Acesso em: Setembro de 2018.  
**Spring security** Framework voltado para a segurança e controle de login do sistema. Disponível em:<https://www.mkyong.com/spring-boot/spring-boot-spring-security-thymeleaf-example/>. Acesso em: Setembro de 2018.  
**Spring security** Framework voltado para a segurança e controle de login do sistema. Disponível em: <https://blog.algaworks.com/spring-security/>. Acesso em: Setembro de 2018. **Spring Boot e Bootstrap** Como configurar e utilizar. Disponível em: <https://www.baeldung.com/spring-boot-start>. Acesso em: Setembro de 2018.

<hr>

- Materiais teóricos para gestão de reuniões:

**Como organizar uma reunião** Material teórico para embasamento do projeto relacionado a como organizar uma reunião focada nas questões importantes. Disponível em: <https://www.siteware.com.br/reunioes/como-organizar-uma-reuniao/>. Acesso em Agosto de 2018.  
**Reunião: como planejar e organizar** Material teórico para embasamento do projeto relacionado a como planejar e organizar uma reunião. Disponível em: <https://efetividade.net/2012/05/reuniao-planejamento-ata-pauta-convite-mensagens.html>. Acesso em Agosto de 2018.  
**Como fazer uma reunião produtiva** Material teórico para embasamento do projeto relacionado a como realizar uma reunião produtiva com funcionários em 5 passos. Disponível em:<https://blog.convenia.com.br/como-fazer-uma-reuniao-produtiva-com-funcionarios-em-5-passos/>. Acesso em: Agosto de 2018.  
**Dicas para registrar os pontos importantes de uma reunião** Material teórico para embasamento do projeto relacionado a como registrar os pontos importantes de uma reunião. Disponível em: <http://www.blogdaqualidade.com.br/5-dicas-para-voce-registrar-os-pontos-importantes-da-reuniao/>. Acesso em: Agosto de 2018.  
**Check-list para planejar a sua próxima grande reunião** Material teórico para embasamento do projeto. Disponível em: <https://hbrbr.uol.com.br/check-list-para-planejar-sua-proxima-grande-reuniao/>. Acesso em: Agosto de 2018.

<hr>

- Trabalhos acadêmicos:

**Sistema de gerenciamento de reuniões** De: Ludmar Gomes Silva, Patrick Pessanha Brito e Thiago Lessa Martins. Disponível em: <http://bd.centro.iff.edu.br/handle/123456789/996>. Acesso em: Setembro de 2018.  
**Modelagem e Protótipo de um Sistema para Gerenciamento de Reuniões.** De: Eduardo Simões Nascimento. Disponível em: <https://www.formiga.ifmg.edu.br/documents/2017/PublicacoesTCCsBiblioteca/eduardo_nascimento_VERSAO-FINAL.pdf>. Acesso em: Setembro de 2018. '''

<hr>

- Sistemas similares:

**Qualiex** Disponível em: <https://qualiex.com/gestao-de-pautas-e-atas-de-reuniao/>. Acesso em: Setembro de 2018.  
**Cisko Spark Meeting Notes** Disponível em: <https://notes.ciscospark.com/>. Acesso em: Setembro de 2018.  
**Doodle** Disponível em: <https://doodle.com/pt_BR/>. Acesso em: Setembro de 2018.  
**Meeting King** Disponível em: <https://meetingking.com/>. Acesso em: Setembro de 2018.  
**GMinutes** Disponível em: <http://gminutes.com/>. Acesso em: Setembro de 2018.
