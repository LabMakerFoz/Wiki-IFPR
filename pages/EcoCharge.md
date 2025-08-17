## Equipe

Professores orientadores  

- Alcione Benacchio
- Wellington Oliveira

Alunos  

- Kaio Rocha Aguiar
- Luis Felipe Miglioli de Oliveira

## Introdução

A problemática do aumento progressivo do consumo de energia elétrica vem preocupando a sociedade. Esse projeto, portanto, visa reverter essa situação gradualmente. EcoCharge utiliza de um dispositivo desenvolvido com a placa arduino para monitoramento da energia elétrica de um ponto de consumo utilizando um microcontrolador, enviando dados via rede sem fio a um Servidor Web, juntamente com uma interface disponível para Android e Web, onde o usuário pode visualizar seus gastos e consequentemente, monitorar seu consumo.Entregar ao usuário uma forma simples e precisa de controle, do consumo elétrico dos aparelhos que utiliza no seu cotidiano, fazendo uso de tecnologias capazes de monitorar o consumo de um aparelho ligado diretamente na tomada, apresentando informações atualizadas e reais sobre gastos prevendo uma possível re-educação sobre os gastos do usuário.

## Objetivo Geral

Impulsionados em conscientizar nossos usuários, o presente projeto fornece uma ferramenta de monitoramento de gastos elétricos. O sistema web juntamento com o dispositivo medidor irá monitorar em tempo real o consumo do aparelho e enviar os dados coletados ao sistema, que ficarão disponíveis ao usuário a partir da web.

## Objetivo Especifico

Monitorar o consumo elétrico por meio de um medidor e mostrar os resultados no sistema web.

- Cadastro de placas de monitoramento.
- Registrar todos os dados monitorados pela placa.
- Agendamento do horário de funcionamento do aparelho.
- Permitindo o usuário cadastrar aparelhos e cômodos para uma melhor filtragem dos dados recolhidos.
- Preenchimento de configurações do usuário.

## Principais Funcionalidades

- Cadastro, edição, listagem e solicitação da exclusão de aparelhos monitorados. (Presente na versão Android)
- Cadastro, edição, listagem e solicitação da exclusão de cômodos. (Presente na versão Android)
- Consulta do histórico de consumo. (Presente na versão Android)
- Consulta e edição das configurações referente aos cálculos. (Presente na versão Android)
- Consulta e cadastro do dispositivo medidor. (Presente na versão Android)
- Ativar/Desativar corrente de energia elétrica do aparelho monitorado (Ligar/Desligar). (Previsto em atualizações futuras)
- Agendar datas/horários de funcionamento do aparelho monitorado. (Previsto em atualizações futuras)

## Público Alvo

### Primário

- Empresas de médio e grande porte.
- Industrias de qualquer rumo.

### Secundário

Concerne de um público amplo de jovens adultos á idosos, devido a praticidade da interface desenvolvida, para qualquer pessoa com interesse em monitorar e diminuir custos em energia elétrica pode ser considerado público alvo.

## Métodologia

Utilizando os conceitos do sistema feito anteriormente como base (EcoCharge, 2018/1°Semestre, TADS, 5° Período), e levando em conta a ausência de um membro, identificaram-se as principais necessidades dos alunos desenvolvedores do projeto, daqui em diante chamado de EcoCharge, de rever toda sua infraestrutura para tornar possível a sequência do mesmo. Em primeira instância, não foi possível dar continuidade ao WebService, bem como seu desenvolvedor, e, portanto, surge a necessidade de uma ferramenta mais viável para prosseguir com seu desenvolvimento, sendo escolhida a linguagem C#, onde desenvolvedores já possuem conhecimento empírico com utilização da mesma. O banco de dados será feito na linguagem PostgreSQL, mais uma vez, por motivos empíricos, bem como a utilização de uma variação própria de MVC. No front-end do EcoCharge, será utilizada páginas HTML para o layout da página, CSS para a estilização e Javascript para fluência das mesmas, esta utilizando uma biblioteca de acesso gratuito chamada de Jquery. As Frameworks utilizadas no desenvolvimento são as seguintes: Visual Studio, Visual Code, PgAdmin. As tecnologias utilizadas no WebService para o desenvolvimento são EntityFramework e Npgsql, que são respectivamente, uma das principais ferramentas de persistência do .NET, e um provedor de dados voltado para conexão com banco PostgreSQL. Não está sendo utilizada nenhuma ferramenta auxiliadora no desenvolvimento do Front-End, por mais que esteja presente num projeto do Visual Studio que usa persistência do EntityFramework.

## Trabalhos relacionados

[Simulador de consumo de energia elétrica](https://www.copel.com/hpcopel/simulador/)  
<a href="Arquivo:copel.jpg" class="wikilink" title="600px">600px</a>  
Simulador de consumo de energia elétrica e uma aplicação desenvolvida pela empresa de distribuição de energia paranaense copel, foi desenvolvido com uma tecnologia antiga o reprodutor de multimídia adobe flash player para navegadores. Falando em monitoramento de energia os cálculos do simulador da copel calcula tudo com uma boa aptidão, porem depende totalmente do preenchimento dos dados pelo usuário, deixando exaustivo o usuário preencher todos os aparelhos de sua residencia e lembrando que se trata de um simulador onde seus resultados tem uma grande margem de diferença do real, porem com uma interface bem interativa, ela proporciona uma sensação de estar jogando um simulador no vídeo game, que alivia um pouco a massiva jornada de inserção de dados. Alem de ser bem interativo e cheio de animações a aplicação da copel deixa a desejar sendo que foi desenvolvida em uma tecnologia tao antiga que não tem suporte para dispositivos moveis.  
  
[Medidor inteligente da GreenAnt](https://www.greenant.com.br/)  
<a href="Arquivo:greenant.jpg" class="wikilink" title="600px">600px</a>  
GreenAnt e uma empresa carioca que busca soluções inovadoras orientadas à gestão energética tanto residencial quanto empresarial. Com seu produto medidor inteligente que monitora o consumo de energia elétrica em tempo real de uma residencia, acoplado ao disjuntor seu aparelho que bem compacto, utiliza do seu wifi para mandar seus dados a nuvem. A interface do usuário e tanto mobile quanto web trazendo um certo conforto para acessar seus dados independente de onde estiver. Com funções adicionais de monitoramento de gastos atípicos, balancos automáticos e fazendo identificação de aparelhos automáticamente. GreenAnt realiza o monitoramento com toda eficiência trazendo dados muito bem avaliados pelos seus usuários, falha somente em questao de instalação que depende que o usuário tenha cuidado e o minimo de conhecimento sobre energia para não ocorrer problemas na rede elétrica.  
  
[Ecomonitor \| Monitoramento do consumo de energia e água](http://ecomonitor.com.br/)  
<a href="Arquivo:ecomonitor.png" class="wikilink" title="600px">600px</a>  
Ecomonitor e um produto da empresa rede industrial que promete monitoramento de energia, água e luz. Utilizando sensores que são praticamente como pregadores que são simplesmente pregar ao fio elétrico ou no cano de água ou de gás deixando a instalação do ecomonitor bem pratica. Com uma interface web e mobile o sistema provem de alto suporte da parte da empresa quanto aos seus usuários trazendo confiança ao produto. Demostrando os dados coletados com ótima filtragem gerando bons gráficos ecomonitor traz boas vantagens ao usuário que deseja saber o quanto esta gastando.  
Os três sistemas possuem suas vantagens e desvantagens. Para o desenvolvimento do projeto ecocharge muito se foi baseado nesses trabalhos, tentamos solucionar os erros cometidos em cada um, e aprimorar suas vantagem para trazer ao usuário a melhor experiencia posivel.

## Cronograma do projeto

<table border="1">

<tr>

<th>

<span style="font-weight:bold;color:rgb(0, 0, 0)">Atividade</span>

</th>

<th>

<span style="font-weight:bold;color:rgb(0, 0, 0)">Data / Período</span>

</th>

<th>

Observações

</th>

</tr>

<tr>

<td>

Definição dos padrões de projeto.

</td>

<td>

21/08/2018 a 26/08/2018

</td>

<td>

Início do ciclo de desenvolvimento.

</td>

</tr>

<tr>

<td>

Definição do layout.

</td>

<td>

27/08/2018 a 29/08/2018

</td>

<td>

\-

</td>

</tr>

<tr>

<td>

Criação do layout do CRUD do usuário.

</td>

<td>

30/08/2018 a 09/09/2018

</td>

<td>

Login e Cadastro incluídos.

</td>

</tr>

<tr>

<td>

Criação do filtro de autenticação.

</td>

<td>

10/09/2018

</td>

<td>

Filtrar acesso em algumas páginas

</td>

</tr>

<tr>

<td>

Criação do log de ações dos usuários.

</td>

<td>

10/09/2018

</td>

<td>

\-  

</td>

</tr>

<tr>

<td>

Criação do layout do CRUD do cômodo.

</td>

<td>

10/09/2018 a 19/09/2018

</td>

<td>

\-

</td>

</tr>

<tr>

<td>

Adição de paginação e ordenação nos templates de listagem.

</td>

<td>

20/09/2018 a 21/09/2018

</td>

<td>

\-

</td>

</tr>

<tr>

<td>

Criação do layout do CRUD do serial.

</td>

<td>

22/09/2018 a 25/09/2018

</td>

<td>

\-

</td>

</tr>

<tr>

<td>

Criação do layout do CRUD do aparelho.

</td>

<td>

26/09/2018 a 30/09/2018

</td>

<td>

\-

</td>

</tr>

<tr>

<td>

Criação do layout do CRUD do ecosense.

</td>

<td>

03/10/2018 a 06/10/2018

</td>

<td>

\-

</td>

</tr>

<tr>

<td>

Criação do layout do CRUD do agendamento.

</td>

<td>

10/10/2018 a 18/10/2018

</td>

<td>

\-

</td>

</tr>

<tr>

<td>

Criação do layout do CRUD do consumo.

</td>

<td>

24/10/2018 a 07/11/2018

</td>

<td>

</td>

</tr>

<tr>

<td>

Correções Gerais

</td>

<td>

08/11/2018 a 21/11/2018

</td>

<td>

</td>

</tr>

</table>

## Lista de Requisitos

### Requisitos Funcionais

<table border="1">

<tr>

<td>

<center>

Código

</center>

</td>

<td>

<center>

Requisito Funcional

</center>

</td>

</tr>

<tr>

<td>

<center>

RF1

</center>

</td>

<td>

 Manter usuários - criar, editar 

</td>

</tr>

gastanto

<tr>

<td>

<center>

RF2

</center>

</td>

<td>

 Manter cômodos - criar, listar, editar, excluir 

</td>

</tr>

<tr>

<td>

<center>

RF3

</center>

</td>

<td>

 Manter aparelhos - criar, listar, editar, excluir 

</td>

</tr>

<tr>

<td>

<center>

RF4

</center>

</td>

<td>

 Manter sensores - criar, listar 

</td>

</tr>

<tr>

`   gastanto    `

<td>

<center>

RF5

</center>

</td>

<td>

 Manter histórico de consumo - listar 

</td>

</tr>

<tr>

<td>

<center>

RF6

</center>

</td>

<td>

 Manter agendamento - criar, listar, editar, excluir 

</td>

</tr>

<tr>

<td>

<center>

RF7

</center>

</td>

<td>

 Manter configuração - criar, listar, editar 

</td>

</tr>

</table>

### Regras de Negócio

<table border="1">

<tr>

<td>

Código

</td>

<td>

Requisito Funcional

</td>

<td>

Regra de Negócio

</td>

</tr>

<tr>

<td>

\-

</td>

<td>

\-

</td>

<td>

\-

</td>

</tr>

</table>

### Requisitos Não Funcionais Tecnológicos

<table border="1">

<tr>

<td>

<center>

Código

</center>

</td>

<td>

<center>

Requisito Não Funcional Tecnológico

</center>

</td>

</tr>

<tr>

<td>

<center>

RNF 1

</center>

</td>

<td>

 O sistema deve executar na linguagem C#. 

</td>

</tr>

<tr>

<td>

<center>

RNF 2

</center>

</td>

<td>

 O sistema deve executar em ambiente web. 

</td>

</tr>

<tr>

<td>

<center>

RNF 3

</center>

</td>

<td>

 O sistema deve ser capaz de se comunicar com o banco PostgreSQL. 

</td>

</tr>

<tr>

<td>

<center>

RNF 4

</center>

</td>

<td>

 o sistema deve manter o log de ação dos usuários. 

</td>

</tr>

</table>

## Diagrama de Casos de Uso

<a href="Arquivo:Diagrama_de_Caso_de_Uso_Geral_EcoCharge.png" class="wikilink" title="500px">500px</a>  
Obs: Ainda há correções pendentes.

## Modelo de entidade relacional

<a href="Arquivo:NovoBancoEcoCharge.png" class="wikilink" title="800px">800px</a>  
Obs: Ainda há correções pendentes.

## Dicionário de Dados

<table border="1">

<tr>

<td colspan="3">

 <b>TABELA:</b> public.usuario  

</td>

<td colspan="4">

<center>

<b>Tabela dos usuários do sistema</b>

</center>

</td>

</tr>

<tr>

<td>

<center>

Campo Lógico

</center>

</td>

<td>

<center>

Campo Físico

</center>

</td>

<td>

<center>

Tipo

</center>

</td>

<td>

<center>

PK

</center>

</td>

<td>

<center>

FK (Tabela.Campo)

</center>

</td>

<td>

<center>

Restrições

</center>

</td>

<td>

<center>

Observações

</center>

</td>

</tr>

<tr>

<td>

<center>

Id

</center>

</td>

<td>

<center>

id

</center>

</td>

<td>

<center>

Inteiro (64 bits)

</center>

</td>

<td>

<center>

Sim

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Único

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

Nome

</center>

</td>

<td>

<center>

nome

</center>

</td>

<td>

<center>

Texto

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Limite de (60) caracteres

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

Sobrenome

</center>

</td>

<td>

<center>

sobrenome

</center>

</td>

<td>

<center>

Texto

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Limite de (60) caracteres

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

Email

</center>

</td>

<td>

<center>

email

</center>

</td>

<td>

<center>

Texto

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Limite de (50) caracteres

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

Senha

</center>

</td>

<td>

<center>

senha

</center>

</td>

<td>

<center>

Texto

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Limite de (32) caracteres

</center>

</td>

<td>

<center>

Senha encriptada

</center>

</td>

</tr>

<tr>

<td>

<center>

GoogleId

</center>

</td>

<td>

<center>

google_id

</center>

</td>

<td>

<center>

Texto

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Limite de (21) caracteres

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

FacebookId

</center>

</td>

<td>

<center>

facebook_id

</center>

</td>

<td>

<center>

Texto

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Limite de (20) caracteres

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

Tarifa

</center>

</td>

<td>

<center>

tarifa

</center>

</td>

<td>

<center>

Decimal

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Valor padrão (0)

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

DataCriacao

</center>

</td>

<td>

<center>

data_criacao

</center>

</td>

<td>

<center>

Data

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Valor padrão (Data Atual)

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

DataAtualizacao

</center>

</td>

<td>

<center>

data_atualizacao

</center>

</td>

<td>

<center>

Data

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Valor padrão (nulo)

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

</table>

  

<table border="1">

<tr>

<td colspan="3">

 <b>TABELA:</b> public.comodo  

</td>

<td colspan="4">

<center>

<b>Tabela dos comodos do usuário</b>

</center>

</td>

</tr>

<tr>

<td>

<center>

Campo Lógico

</center>

</td>

<td>

<center>

Campo Físico

</center>

</td>

<td>

<center>

Tipo

</center>

</td>

<td>

<center>

PK

</center>

</td>

<td>

<center>

FK (Tabela.Campo)

</center>

</td>

<td>

<center>

Restrições

</center>

</td>

<td>

<center>

Observações

</center>

</td>

</tr>

<tr>

<td>

<center>

Id

</center>

</td>

<td>

<center>

id

</center>

</td>

<td>

<center>

Inteiro (64 bits)

</center>

</td>

<td>

<center>

Sim

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Único

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

Nome

</center>

</td>

<td>

<center>

nome

</center>

</td>

<td>

<center>

Texto

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Limite de (32) caracteres

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

UsuarioId

</center>

</td>

<td>

<center>

usuario_id

</center>

</td>

<td>

<center>

Inteiro (64 bits)

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Sim (public.usuario.id)

</center>

</td>

<td>

<center>

Não-Nulo

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

DataCriacao

</center>

</td>

<td>

<center>

data_criacao

</center>

</td>

<td>

<center>

Data

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Valor padrão (Data Atual)

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

DataAtualizacao

</center>

</td>

<td>

<center>

data_atualizacao

</center>

</td>

<td>

<center>

Data

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Valor padrão (nulo)

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

</table>

  

<table border="1">

<tr>

<td colspan="3">

 <b>TABELA:</b> public.serial_aparelho  

</td>

<td colspan="4">

<center>

<b>Tabela dos seriais do sistema</b>

</center>

</td>

</tr>

<tr>

<td>

<center>

Campo Lógico

</center>

</td>

<td>

<center>

Campo Físico

</center>

</td>

<td>

<center>

Tipo

</center>

</td>

<td>

<center>

PK

</center>

</td>

<td>

<center>

FK (Tabela.Campo)

</center>

</td>

<td>

<center>

Restrições

</center>

</td>

<td>

<center>

Observações

</center>

</td>

</tr>

<tr>

<td>

<center>

Id

</center>

</td>

<td>

<center>

id

</center>

</td>

<td>

<center>

Inteiro (64 bits)

</center>

</td>

<td>

<center>

Sim

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Único

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

Serial

</center>

</td>

<td>

<center>

serial

</center>

</td>

<td>

<center>

Texto

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Limite de (12) caracteres

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

DataCriacao

</center>

</td>

<td>

<center>

data_criacao

</center>

</td>

<td>

<center>

Data

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Valor padrão (Data Atual)

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

DataAtualizacao

</center>

</td>

<td>

<center>

data_atualizacao

</center>

</td>

<td>

<center>

Data

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Valor padrão (nulo)

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

</table>

  

<table border="1">

<tr>

<td colspan="3">

 <b>TABELA:</b> public.ecosense  

</td>

<td colspan="4">

<center>

<b>Tabela dos aparelhos medidores do usuário</b>

</center>

</td>

</tr>

<tr>

<td>

<center>

Campo Lógico

</center>

</td>

<td>

<center>

Campo Físico

</center>

</td>

<td>

<center>

Tipo

</center>

</td>

<td>

<center>

PK

</center>

</td>

<td>

<center>

FK (Tabela.Campo)

</center>

</td>

<td>

<center>

Restrições

</center>

</td>

<td>

<center>

Observações

</center>

</td>

</tr>

<tr>

<td>

<center>

Id

</center>

</td>

<td>

<center>

id

</center>

</td>

<td>

<center>

Inteiro (64 bits)

</center>

</td>

<td>

<center>

Sim

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Único

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

SerialId

</center>

</td>

<td>

<center>

serial_id

</center>

</td>

<td>

<center>

Inteiro (64 bits)

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Sim (public.serial_aparelho.id)

</center>

</td>

<td>

<center>

Não-Nulo

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

UsuarioId

</center>

</td>

<td>

<center>

usuario_id

</center>

</td>

<td>

<center>

Inteiro (64 bits)

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Sim (public.usuario.id)

</center>

</td>

<td>

<center>

Não-Nulo

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

StatusAparelho

</center>

</td>

<td>

<center>

status_aparelho

</center>

</td>

<td>

<center>

Boolean

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Valor padrão (false))

</center>

</td>

<td>

<center>

Defini se o aparelho medidor está possibilitado a medição ou não

</center>

</td>

</tr>

<tr>

<td>

<center>

DataCriacao

</center>

</td>

<td>

<center>

data_criacao

</center>

</td>

<td>

<center>

Data

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Valor padrão (Data Atual)

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

DataAtualizacao

</center>

</td>

<td>

<center>

data_atualizacao

</center>

</td>

<td>

<center>

Data

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Valor padrão (nulo)

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

</table>

  

<table border="1">

<tr>

<td colspan="3">

 <b>TABELA:</b> public.log  

</td>

<td colspan="4">

<center>

<b>Tabela de log das ações dos usuários</b>

</center>

</td>

</tr>

<tr>

<td>

<center>

Campo Lógico

</center>

</td>

<td>

<center>

Campo Físico

</center>

</td>

<td>

<center>

Tipo

</center>

</td>

<td>

<center>

PK

</center>

</td>

<td>

<center>

FK (Tabela.Campo)

</center>

</td>

<td>

<center>

Restrições

</center>

</td>

<td>

<center>

Observações

</center>

</td>

</tr>

<tr>

<td>

<center>

Id

</center>

</td>

<td>

<center>

id

</center>

</td>

<td>

<center>

Inteiro (64 bits)

</center>

</td>

<td>

<center>

Sim

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Único

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

Acao

</center>

</td>

<td>

<center>

acao

</center>

</td>

<td>

<center>

Texto

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Limite de (30) caracteres

</center>

</td>

<td>

<center>

Ação do usuário

</center>

</td>

</tr>

<tr>

<td>

<center>

Controlador

</center>

</td>

<td>

<center>

controlador

</center>

</td>

<td>

<center>

Texto

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Limite de (30) caracteres

</center>

</td>

<td>

<center>

Url da navegação do usuário

</center>

</td>

</tr>

<tr>

<td>

<center>

Email

</center>

</td>

<td>

<center>

email

</center>

</td>

<td>

<center>

Texto

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Limite de (50) caracteres

</center>

</td>

<td>

<center>

Email do usuário

</center>

</td>

</tr>

<tr>

<td>

<center>

Ip

</center>

</td>

<td>

<center>

ip

</center>

</td>

<td>

<center>

Texto

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Limite de (20) caracteres

</center>

</td>

<td>

<center>

Ip da máquina onde estão sendo feitas as ações

</center>

</td>

</tr>

<tr>

<td>

<center>

DataCriacao

</center>

</td>

<td>

<center>

data_criacao

</center>

</td>

<td>

<center>

Data

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Valor padrão (Data Atual)

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

DataAtualizacao

</center>

</td>

<td>

<center>

data_atualizacao

</center>

</td>

<td>

<center>

Data

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Valor padrão (nulo)

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

</table>

  

<table border="1">

<tr>

<td colspan="3">

 <b>TABELA:</b> public.aparelho  

</td>

<td colspan="4">

<center>

<b>Tabela dos aparelhos do usuário</b>

</center>

</td>

</tr>

<tr>

<td>

<center>

Campo Lógico

</center>

</td>

<td>

<center>

Campo Físico

</center>

</td>

<td>

<center>

Tipo

</center>

</td>

<td>

<center>

PK

</center>

</td>

<td>

<center>

FK (Tabela.Campo)

</center>

</td>

<td>

<center>

Restrições

</center>

</td>

<td>

<center>

Observações

</center>

</td>

</tr>

<tr>

<td>

<center>

Id

</center>

</td>

<td>

<center>

id

</center>

</td>

<td>

<center>

Inteiro (64 bits)

</center>

</td>

<td>

<center>

Sim

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Único

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

Voltagem

</center>

</td>

<td>

<center>

voltagem

</center>

</td>

<td>

<center>

Inteiro (32 bits)

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

Cor

</center>

</td>

<td>

<center>

cor

</center>

</td>

<td>

<center>

Texto

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Limite de (7) caracteres

</center>

</td>

<td>

<center>

A cor que o medidor irá emitir quando estiver monitorando este aparelho

</center>

</td>

</tr>

<tr>

<td>

<center>

EcoSenseId

</center>

</td>

<td>

<center>

ecosense_id

</center>

</td>

<td>

<center>

Inteiro (64 bits)

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Sim (public.ecosense.id)

</center>

</td>

<td>

<center>

Não-Nulo

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

ComodoId

</center>

</td>

<td>

<center>

comodo_id

</center>

</td>

<td>

<center>

Inteiro (64 bits)

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Sim (public.comodo.id)

</center>

</td>

<td>

<center>

Não-Nulo

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

DataCriacao

</center>

</td>

<td>

<center>

data_criacao

</center>

</td>

<td>

<center>

Data

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Valor padrão (Data Atual)

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

DataAtualizacao

</center>

</td>

<td>

<center>

data_atualizacao

</center>

</td>

<td>

<center>

Data

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Valor padrão (nulo)

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

</table>

  

<table border="1">

<tr>

<td colspan="3">

 <b>TABELA:</b> public.consumo  

</td>

<td colspan="4">

<center>

<b>Tabela do consumo dos aparelhos</b>

</center>

</td>

</tr>

<tr>

<td>

<center>

Campo Lógico

</center>

</td>

<td>

<center>

Campo Físico

</center>

</td>

<td>

<center>

Tipo

</center>

</td>

<td>

<center>

PK

</center>

</td>

<td>

<center>

FK (Tabela.Campo)

</center>

</td>

<td>

<center>

Restrições

</center>

</td>

<td>

<center>

Observações

</center>

</td>

</tr>

<tr>

<td>

<center>

Id

</center>

</td>

<td>

<center>

id

</center>

</td>

<td>

<center>

Inteiro (64 bits)

</center>

</td>

<td>

<center>

Sim

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Único

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

Serial

</center>

</td>

<td>

<center>

serial

</center>

</td>

<td>

<center>

Texto

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Limite de (12) caracteres

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

PotenciaWatts

</center>

</td>

<td>

<center>

potencia_watts

</center>

</td>

<td>

<center>

Decimal

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo

</center>

</td>

<td>

<center>

A quantia de watts monitorada no período

</center>

</td>

</tr>

<tr>

<td>

<center>

Quilowatts

</center>

</td>

<td>

<center>

quilowatts

</center>

</td>

<td>

<center>

Decimal

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

Ciclos

</center>

</td>

<td>

<center>

ciclos

</center>

</td>

<td>

<center>

Inteiro (64 bits)

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo

</center>

</td>

<td>

<center>

O período (em segundos) que esteve monitorando

</center>

</td>

</tr>

<tr>

<td>

<center>

AparelhoId

</center>

</td>

<td>

<center>

aparelho_id

</center>

</td>

<td>

<center>

Inteiro (64 bits)

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Sim (public.aparelho.id)

</center>

</td>

<td>

<center>

Não-Nulo

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

DataCriacao

</center>

</td>

<td>

<center>

data_criacao

</center>

</td>

<td>

<center>

Data

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Valor padrão (Data Atual)

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

DataAtualizacao

</center>

</td>

<td>

<center>

data_atualizacao

</center>

</td>

<td>

<center>

Data

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Valor padrão (nulo)

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

</table>

  

<table border="1">

<tr>

<td colspan="3">

 <b>TABELA:</b> public.agendamento  

</td>

<td colspan="4">

<center>

<b>Tabela de agendamento do horário de funcionamento do aparelho</b>

</center>

</td>

</tr>

<tr>

<td>

<center>

Campo Lógico

</center>

</td>

<td>

<center>

Campo Físico

</center>

</td>

<td>

<center>

Tipo

</center>

</td>

<td>

<center>

PK

</center>

</td>

<td>

<center>

FK (Tabela.Campo)

</center>

</td>

<td>

<center>

Restrições

</center>

</td>

<td>

<center>

Observações

</center>

</td>

</tr>

<tr>

<td>

<center>

Id

</center>

</td>

<td>

<center>

id

</center>

</td>

<td>

<center>

Inteiro (64 bits)

</center>

</td>

<td>

<center>

Sim

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Único

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

Detalhes

</center>

</td>

<td>

<center>

detalhes

</center>

</td>

<td>

<center>

Texto

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Limite de (300) caracteres

</center>

</td>

<td>

<center>

Será armazenado (no formato JSON) os dados referentes ao dia e horário de funcionamento, possibilitando multiplos horarios num mesmo dia, com várias combinações de dias. (Possui um array de dias 0 a 6 (7 dias da semana), e cada dia podendo ter um array infinito de horarios.)

</center>

</td>

</tr>

<tr>

<td>

<center>

UsuarioId

</center>

</td>

<td>

<center>

usuario_id

</center>

</td>

<td>

<center>

Inteiro (64 bits)

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Sim (public.usuario.id)

</center>

</td>

<td>

<center>

Não-Nulo

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

EcoSenseId

</center>

</td>

<td>

<center>

ecosense_id

</center>

</td>

<td>

<center>

Inteiro (64 bits)

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Sim (public.ecosense.id)

</center>

</td>

<td>

<center>

Não-Nulo

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

DataCriacao

</center>

</td>

<td>

<center>

data_criacao

</center>

</td>

<td>

<center>

Data

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Não-Nulo, Valor padrão (Data Atual)

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

<tr>

<td>

<center>

DataAtualizacao

</center>

</td>

<td>

<center>

data_atualizacao

</center>

</td>

<td>

<center>

Data

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

\-

</center>

</td>

<td>

<center>

Valor padrão (nulo)

</center>

</td>

<td>

<center>

\-

</center>

</td>

</tr>

</table>

## Layout/Telas

--
