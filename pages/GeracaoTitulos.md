# Sistema de Geração de Títulos Bancários de Cobrança

## Introdução

De acordo com a nova convenção da FEBRABAN [FB-376/2017](https://cmsportal.febraban.org.br/Arquivos/documentos/PDF/Conven%C3%A7%C3%A3o%20Nova%20plataforma%20de%20cobran%C3%A7a_%20Documento%20Registrado%20.pdf), todas as empressas que fazem emissão de títulos bancários deverão se adequar ao novo modelo de registro. Atualmente, as emissões de títulos bancários registrados são opcionais, isto é, a empresa emitir títulos não registrados ou títulos registrados vinculados a uma instituição bancária. Este modelo de emissão tem validade até 10/11/2018 conforme a nova plataforma de cobrança [1](https://cmsportal.febraban.org.br/Arquivos/documentos/PDF/L22_Nova_plataforma_cobranc%CC%A7a.pdf).

O motivo da mudança no modelo de emissão de títulos bancários é devido a necessidade de modernizar o processo de liquidação de títulos, aplicando novos mecanismos de segurança e controle nesse meio de pagamento.

A partir de Novembro de 2018 todas as empresas deverão adequar os seus sistemas de informação de acordo com o novo fluxo de processamento proposto pela convenção citado acima. O processo que antes poderia ser feito sem registro do título, com a adequação proposta pela nova convenção, a empresa emitente deverá registrar o título junto ao banco por meio de troca de arquivos, conhecidos como arquivos de remessa e retorno.

Os prazos para a emissão de títulos não registrados seguem o cronograma apresentado na Tabela 1.

<table border="1" cellpadding="2">

<caption>

**Tabela 1**

</caption>

<tr>

<th>

Data

</th>

<th>

Valor

</th>

</tr>

<tr>

<td>

A partir de 25 de agosto/2018

</td>

<th>

R\$ 400,00 ou mais

</th>

</tr>

<tr>

<td>

A partir de 13 de outubro/2018

</td>

<th>

R\$ 100,00 ou mais

</th>

</tr>

<tr>

<td>

A partir de 27 de outubro/2018

</td>

<th>

R\$ 0,01 ou mais

</th>

</tr>

<tr>

<td>

Em 10 de novembro/2018

</td>

<th>

Processo concluído

</th>

</tr>

</table>

  
**Devido a esta demanda este projeto visa abordar o desenvolvimento de um sistema capaz de:**

- Emitir arquivos de Remessa e Retorno conforme layout disponibilizado pela FEBRABAN [2](https://portal.febraban.org.br/pagina/3053/33/pt-br/layout-240), enviando os títulos recebidos a instituição bancária para seu devido registro.
- Disponibilizar o título em forma de boleto em formato pdf ao cliente.
- Efetuar baixas e cancelamentos por meio de arquivos de Remessa.
- Controlar recebimentos de títulos pagos por meio de processamento de arquivo de Retorno disponibilizado pela instituição bancária.

## Equipe

Professores/Orientadores  

- Alcione Benacchio
- Wellington Oliveira

Alunos  

- Alexandre Ferris
- Frederico Dellani Martinez

## Proposta

Este projeto tem como objetivo o desenvolvimento de um sistema web que permita emitir, receber e gerenciar títulos de cobrança bancários(boletos). Com uma interface simples que disponibilize os títulos em pdf, nos layouts padrão(fatura) e carnê(conjunto de boletos), e que permita a geração de arquivos de Remessa no layout CNAB240 definidos pela FEBRABAN e também disponibilize forma de recebimento de arquivos Retorno possibilitando baixas de títulos, confirmações de pagamentos e controle de títulos em atraso.

## Problema

A partir de novembro de 2018 a FEBRABAN finaliza seu calendário de implantação da nova plataforma de cobrança(Calendário de Implantação[3](https://portal.febraban.org.br/pagina/3150/1094/pt-br/servicos-novo-plataforma-boletos)). Com o objetivo de trazer mais segurança, controle e modernidade ao processo de liquidação de boletos serão aceitos apenas boletos com registro. Visando atingir as empresas que não possuem um fácil suporte a emissão de boletos e seus registros, iniciamos esse projeto com a pretensão de disponibilizar um sistema web que faça todo o processo de emissão de títulos e o cuidado durante seu ciclo de vida junto a instituição bancária pretendida pelo usuário.

## Objetivo

### Geral

Desenvolver uma plataforma Web capaz de auxiliar seu usuário a gerar e gerenciar seus títulos bancários registrados de forma fácil e prática.

### Especifico

- Desenvolver opções de geração de títulos para determinada carteira bancária (Para teste será utilizada uma carteira de cobrança rápida do banco SANTANDER)
- Dispor de geração de arquivos, de remessa e PDF para envio ao banco e download do título respectivamente
- Possibilitar processamento de arquivos de retorno para efetuar as baixas de pagamentos de títulos
- Disponibilizar relatórios de boletos gerados, pagos e em atraso
- Apresentar saldo total e bruto de títulos gerados e registrados na instituição bancária

## Público Alvo

Pessoas físicas ou jurídicas que necessitem emitir e receber seus títulos registrados, através de sua conta bancária de cobrança.

## Principais Funcionalidades

Este projeto deve apresentar as seguintes funcionalidades:

- Gerar boleto em diversos formatos, utilizando PDF;
- Gerar arquivos de remessa, utilizando o formato CNAB 240 disponibilizado por FEBRABAN;
- Efetuar a leitura de arquivos de retorno disponibilizado pela instituição bancária escolhida pelo usuário, utilizando o formato CNAB 240 disponibilizado por FEBRABAN;
- Gerir o usuário utilizador, seus dados e ações;
- API REST para integração dos sistemas de clientes;

## Metodologia de Desenvolvimento

Para o desenvolvimento da interface de usuário foram escolhidos VueJS, HTML5, CSS3 e SASS para garantir uma boa usabilidade e dinâmica de resposta rápida a qualquer interação do usuário. Para trabalhar a regra de negócio utiliza-se uma API desenvolvida em NodeJS, escolhido pela sua rapidez, fácil manutenção e reaproveitamento de código.

Como banco de dados para persistência das informações produzidas foi definido o uso do POSTGRESQL, escolhido pela sua aplicabilidade, escalabilidade e fácil acesso a sua documentação e comunidade. Para o serviço de geracao e processamento de arquivos foi escolhido Java com o framework Spring Boot, escolhidos pela sua confiabilidade e alta disponibilidade.

Conforme a lista de tecnologias abaixo:

[`NodeJS`](https://nodejs.org/)  
`- Versão: 8.11.4`

[`Vue.js`](https://vuejs.org/)  
`- Versão: 2.5.17`

[`Java EE`](http://www.oracle.com/technetwork/pt/java/javaee/overview/index.html)  
`- Versão: 1.8`

[`Spring Boot`](http://spring.io/projects/spring-boot)  
`- Versão: 1.5 Release`

[`Spring Tools Suite(Eclipse based)`](https://spring.io/tools)  
`- Versão: 3.9.5 Release`

[`POSTGRESQL`](https://www.postgresql.org/)  
`- Versão: 10.5`

[`Apache TomCat`](https://tomcat.apache.org/)  
`- Versão: 9.0.11`

[`Apache`](https://apache.org/)  
`- Versão: 2.2`

[`HTML`](https://www.google.com.br/search?q=html5)` `  
`- Versão: 5`

[`CSS`](https://www.google.com.br/search?q=css3)  
`- Versão: 3`

[`SASS`](https://sass-lang.com/)

[`JSON`](https://www.json.org/json-pt.html)

## Casos de Uso

<a href="Arquivo:UC_1_-_Gerenciar_Usuario_GT.png" class="wikilink" title="UC 1 - Gerenciar Usuário|180px">UC 1 - Gerenciar Usuário|180px</a> <a href="Arquivo:UC_2_-_Gerenciamento_de_Titulos_GT.png" class="wikilink" title="UC 2 - Gerenciamento de Títulos|180px">UC 2 - Gerenciamento de Títulos|180px</a> <a href="Arquivo:UC_3_-_Gerenciamento_de_Remessa_GT.png" class="wikilink" title="UC 3 - Gerenciamento de Remessa|180px">UC 3 - Gerenciamento de Remessa|180px</a> <a href="Arquivo:UC_4_-_Gerenciamento_de_Retorno_GT.png" class="wikilink" title="UC 4 - Gerenciamento de Retorno|180px">UC 4 - Gerenciamento de Retorno|180px</a>

## Desenvolvimento do Projeto

<table border="1" cellpadding="2">

<tr>

<th>

Descrição

</th>

<th>

Data Início

</th>

<th>

Data Fim

</th>

</tr>

<tr>

<td>

Wiki

</td>

<td>

</td>

<td>

20/09/2018

</td>

</tr>

<tr>

<td>

Implementação do front end

</td>

<td>

21/09/2018

</td>

<td>

07/10/2018

</td>

</tr>

<tr>

<td>

Implementação do back end

</td>

<td>

08/10/2018

</td>

<td>

01/11/2018

</td>

</tr>

<tr>

<td>

Validações e Testes

</td>

<td>

24/10/2018

</td>

<td>

01/11/2018

</td>

</tr>

</table>

## Requisitos

Neste documento apresentamos os requisitos não funcionais, funcionais e regras de negócio do sistema desenvolvido. O sistema web de geração de títulos será desenvolvido utilizando diversas tecnologias e linguagens como Java, Javascript, HTML, SCSS, Spring Boot, Vue.js e Node.js, como representado na Tabela1(RNFT 01).

<table border="1" cellpadding="2">

<caption>

**Tabela 1** – Requisitos não funcionais tecnológicos

</caption>

<tr>

<th>

Código

</th>

<th>

Requisitos Não Funcionais Tecnológicos

</th>

</tr>

<tr>

<th>

RNFT 01

</th>

<td>

O sistema web utilizará como linguagens Java e Javascript. Para layouts e telas, HTML e SCSS. Frameworks como Springboot, Vue.js e Node.js.

</td>

</tr>

<tr>

<th>

RNFT 02

</th>

<td>

O banco de dados será desenvolvido utilizando POSTGRESQL.

</td>

</tr>

<tr>

<th>

RNFT 03

</th>

<td>

Toda a interface deve ser fácil de utilizar e intuitiva.

</td>

</tr>

<tr>

<th>

RNFT 04

</th>

<td>

Os dados deverão ser armazenados externamente.

</td>

</tr>

<tr>

<th>

RNFT 05

</th>

<td>

O sistema fará uso de um microservico para o processamento de arquivos.

</td>

</tr>

</table>

*Na Tabela 2 observa-se os requisitos funcionais que estarão inseridos no contexto do sistema.*

<table border="1" cellpadding="2">

<caption>

**Tabela 2** – Requisitos funcionais.

</caption>

<tr>

<th colspan="2">

USUÁRIO

</th>

</tr>

<tr>

<th>

Código

</th>

<th align="left">

Requisito Funcional

</th>

</tr>

<tr>

<th>

RF 01

</th>

<td>

O sistema permitirá o cadastro de usuário e suas informações bancárias necessárias para geração de títulos.

</td>

</tr>

<tr>

<th>

RF 02

</th>

<td>

O sistema permitirá alterações de cadastro e informações cadastradas por ele.

</td>

</tr>

<tr>

<th>

RF 03

</th>

<td>

O cadastro inicial deve conter nome, senha, CPF, e-mail, telefones de contato e endereços.

</td>

</tr>

<tr>

<th>

RF 04

</th>

<td>

O complemento de cadastro, informações bancárias, será solicitada após a confirmação de cadastro. Elas devem ser: carteira, agência e conta.

</td>

</tr>

<tr>

<th colspan="2">

LOGIN

</th>

</tr>

<tr>

<th>

Código

</th>

<th align="left">

Requisito Funcional

</th>

</tr>

<tr>

<th>

RF 05

</th>

<td>

O sistema vai liberar o acesso à plataforma a partir de seu e-mail e senha.

</td>

</tr>

<tr>

<th colspan="2">

FUNCIONALIDADES

</th>

</tr>

<tr>

<th>

Código

</th>

<th align="left">

Requisito Funcional

</th>

</tr>

<tr>

<th>

RF 06

</th>

<td>

O usuário poderá emitir seus titulos bancários na plataforma.

</td>

</tr>

<tr>

<th>

RF 07

</th>

<td>

O usuário poderá gerar os boletos em formato PDF a partir dos títulos gerados na plataforma.

</td>

</tr>

<tr>

<th>

RF 08

</th>

<td>

O usuário poderá cancelar títulos emitidos

</td>

</tr>

<tr>

<th>

RF 09

</th>

<td>

O usuário poderá emitir arquivos de remessa.

</td>

</tr>

<tr>

<th>

RF 10

</th>

<td>

O usuário poderá efetuar download dos arquivos gerados.

</td>

</tr>

<tr>

<th>

RF 11

</th>

<td>

O sistema deverá efetuar a leitura de arquivos de remessa inseridos pelo usuário e fazer as baixas por pagamento de títulos.

</td>

</tr>

</table>
