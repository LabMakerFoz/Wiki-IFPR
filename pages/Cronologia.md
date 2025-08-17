## 24/07/2017

### Aula Inicial e concepção da idéia

Neste dia os professores orientadores apresentaram a proposta do formato de trabalho da disciplina, e também foi levantada a idéia inicial. Inicialmente a idéia era criar uma ferramenta gamificada porém ainda não tinha um proposito.

## 27/07/2017

### Aprofundamento do formato de trabalho da disciplina e aprimoramento da idéia

Neste dia os professores orientadores aprofundaram a explicação sobre como a disciplina irá descorrer e também foi feito um aprimoramento na idéia. Idéia: Desenvolver uma ferramenta que auxilie na produção de artefatos de qualidade no contexto de uma fabrica de software. Motivação: Foi observado que o processo de controle de qualidade no contexto de uma fabrica de software certificada com MPS-BR Nível F é muito repetitivo e burocrático, a partir disso surgiu a idéia de desenvolver uma gamificação e uma ferramenta que implementasse a estrutura desenvolvida para aumentar o engajamento na produção e também a qualidade dos artefatos produzidos. Será utilizado como base um caso real de uma fábrica de software certificada para o desenvolvimento da gamificação e da ferramenta, a fim de produzir uma ferramenta mais adequada às necessidades reais.

## 31/07/2017

### Apresentação da idéia inicial

Neste dia foi apresentado aos professores e demais alunos da disciplina a idéia inicial, o projeto foi aceito pelos orientadores que fizeram algumas colocações:

- Concentrar esforços na ferramenta e não na gamificação uma vez que o objetivo da disciplina é o desenvolvimento da ferramenta
- Definir requisitos
- Definir arquitetura tomando os devidos cuidados para utilizar ferramentas que possibilitem o desenvolvimento total da solução.

## 01/08/2017

### Definição das mecanicas utilizadas

Neste dia foram definidas as mecânicas que serão utilizadas na gamificação, as mecanicas foram escolhidas levando em consideração os seguintes aspectos:

- Perfil de jogador indicado (Levando em conta os perfis presentes na fabrica usada como base)
- Relação com o problema (O quanto a mecanica auxilia na resolução do problema)
- Dificuldade de implementação

As mecânicas selecionadas podem ser encontradas na página principal seção Gamificação: <a href="http://wiki.foz.ifpr.edu.br/wiki/index.php/Ferramenta_Gamificada#Mec.C3.A2nicas_Página_principal" class="wikilink" title="http://wiki.foz.ifpr.edu.br/wiki/index.php/Ferramenta_Gamificada#Mec.C3.A2nicas Página principal">http://wiki.foz.ifpr.edu.br/wiki/index.php/Ferramenta_Gamificada#Mec.C3.A2nicas Página principal</a>

## 02/08/2017

### Definição da arquitetura, testes de arquitetura e inicio da elicitação de requisitos

Neste dia foi definido que a arquitetura da ferramenta será composta pelo framework Angular 2 em sua versão 4.3.2, também será utilizada a plataforma Firebase para persistencia de dados em banco de dados tempo real e autenticação de usuários, possívelmente a ferramenta também utilizará outras funcionalidades do firebase porém ainda não foram definidas. Como o framework Angular 2 é baseado em webcomponents serão utlizados alguns sets de componentes, são eles: Angular Material 2 na versão 2.0.0-beta.8 e Teradata Covalent na versão 1.0.0-beta.6, para a integração entre o framework Angular 2 e a plataforma Firebase será utilizado o plugin oficial angularfire2 desenvolvido pela própria Firebase na versão 4.0.0-rc.1 e a biblioteca firebase também desenvolvido pela empresa detentora da plataforma na versão 4.2.0, para desenvolvimento será utilizado um servidor node.js na versão 8.1.0, o assistente angular-cli na versão 1.2.6, a linguagem typescript na versão 2.4.1 e o editor de texto Visual Studio Code em sua versão 1.14.2, lembrando que todas as ferramentas utilizadas estão em desenvolvimento e recebendo atualizações constantes, portanto algumas versões poderão ser alteradas até o fim do projeto. Foram executados alguns testes na arquitetura ( autenticação e a persistência de um objeto ), e até o momento não há nenhum problema quanto a mesma. Neste dia também inicou-se a elicitação dos requisitos da ferramenta, foi definido que os requisitos serão elicitados em 3 níveis, Agregadores, de Usuário e Sub-Função onde: Sub-Funções são requisitos que compoem requisitos de usuário ou seja, não são funções completas apenas partes de outras funções. De Usuário são requisitos que formam uma função completa ou um processo elementar do sistema. Agregadores são requisitos que englobam requisitos de usuários.

o Documento inicial de requisitos pode ser encontrado aqui: <a href="https://docs.google.com/document/d/1TkPZzTe7ai1gNGYiwGTm86e4hSaXv0WVSROwN6eveww/edit?usp=sharing_Documento_inicial_de_requisitos" class="wikilink" title="https://docs.google.com/document/d/1TkPZzTe7ai1gNGYiwGTm86e4hSaXv0WVSROwN6eveww/edit?usp=sharing Documento inicial de requisitos">https://docs.google.com/document/d/1TkPZzTe7ai1gNGYiwGTm86e4hSaXv0WVSROwN6eveww/edit?usp=sharing Documento inicial de requisitos</a>

## 03/08/2017

### Definição das pontuações, testes de pontuações, níveis e medalhas

Neste dia foi definida a primeira versão das pontuações, níveis e medalhas da gamificação. Com os testes foi possível observar um pouco sobre o 'flow' que é a proporção entre a dificuldade e a progressão, após alguns ajustes o sistema pareceu ter ficado nivelado. O esquema de ações e pontos pode ser encontrado na página principal seção Gamificação. <a href="http://wiki.foz.ifpr.edu.br/wiki/index.php/Ferramenta_Gamificada#A.C3.A7.C3.B5es_Relevantes_Página_principal" class="wikilink" title="http://wiki.foz.ifpr.edu.br/wiki/index.php/Ferramenta_Gamificada#A.C3.A7.C3.B5es_Relevantes Página principal">http://wiki.foz.ifpr.edu.br/wiki/index.php/Ferramenta_Gamificada#A.C3.A7.C3.B5es_Relevantes Página principal</a>

## 07/08/2017

### Validação da pontuação e especificação de requisitos

Neste dia foi validado junto à Gerente de Produção da fabrica modelo as pontuações definidas para cada ação, também foram apresentados e validados os cenários de exemplo. Também foram especificados os seguintes requisitos agregadores: Manter Usuário, Manter Time e Manter Commit.

## 08/08/2017

### Estudos

Nesse dia não foi possível trabalhar na documentação, entretanto foi feito um estudo a respeito do banco de dados não relacional que é o paradigma que será utilizado na ferramenta. Foram utilizados os seguintes materiais para estudo:

- Documentação oficial Firebase[^1]
- Documentação oficial Firebase[^2]
- Blog Ta Safo[^3]
- Nomadev[^4]

## 09/08/2017

### Conclusão da especificação de requisitos

Neste dia foi finalizada a primeira versão das especificações dos requisitos do sistema. Também foi iniciado o estudo da estrutura básica do banco de dados.

## 10/08/2017

### Estudos e testes banco de dados

Neste dia foram efetuados alguns testes e estudos práticos a respeito da estrutura básica do banco de dados.

## 14/08/2017

### Estudos e testes banco de dados e script cli

No dia de hoje foram feitos mais estudos quanto a estrutura do banco de dados. Também foi desenvolvido um teste de script cli, que faria a comunicação com o firebase para inserir os commits por meio dos git/svn hooks. O próximo passo é integrar as ferramentas para que a partir do commit o script seja executado com os devidos argumentos.

## 15/08/2017

### Estudos e testes script cli

Neste dia foram realizados estudos que validaram a idéia de inserir o registro do commit na base de dados por meio de git hooks (No caso da ferramenta Git). Para a ferramenta svn serão necessários mais estudos que serão feitos conforme a necessidade.

## 17/08/2017

### Especificação de casos de uso

Neste dia foi dado inicio a produção do documento de especificação de casos de uso. Foram feitas correções na documentação, produção dos diagramas de caso de uso e a especificação do caso de uso "Inserir commit".

## 21/08/2017

### Conclusão casos de uso e desenvolvimento do modelo de dados

Neste dia foi concluída a especificação de casos de uso da funcionalidade principal do software que será a de monitorar e inserir commits automáticamente. Também foi desenvolvido o modelo de dados do que se espera que seja o banco de dados final. Nesse dia também foi liberado o acesso ao ambiente Wiki.

## 22-23/08/2017

### Atualização Wiki

Esses dias foram usados para atualização do ambiente Wiki com as informações do projeto.

## 23-24/08/2017

### Project Canvas

Sob orientação do professor Jésus foi elaborado nesses dias o Canvas do projeto que está disponível na página principal seção proposta <a href="http://wiki.foz.ifpr.edu.br/wiki/index.php/Ferramenta_Gamificada#Proposta_Página_principal" class="wikilink" title="http://wiki.foz.ifpr.edu.br/wiki/index.php/Ferramenta_Gamificada#Proposta Página principal">http://wiki.foz.ifpr.edu.br/wiki/index.php/Ferramenta_Gamificada#Proposta Página principal</a>.

## 24/08/2017

### Protótipos de baixa fidelidade

Nesse dia foram desenvolvidos os protótipos de baixa fidelidade das telas do sistema. Os protótipos estão disponíveis na Página principal seção Proposta <a href="http://wiki.foz.ifpr.edu.br/wiki/index.php/Ferramenta_Gamificada#Proposta_Página_principal" class="wikilink" title="http://wiki.foz.ifpr.edu.br/wiki/index.php/Ferramenta_Gamificada#Proposta Página principal">http://wiki.foz.ifpr.edu.br/wiki/index.php/Ferramenta_Gamificada#Proposta Página principal</a>.

## 25/08/2017

### Inicio implementação

Neste dia foi iniciada a fase de implementação do sistema. Foi desenvolvida a funcionalidade de autenticação de usuários e o inicio da dashboard de usuário jogador.

## 26/08/2017

### Dashboard de usuário (Jogador)

Neste dia foi desenvolvida mais uma parte da dashboard de usuário jogador, estão sendo utilizados dados fictícios para desenvolvimento da tela, em um momento posterior será implementado o serviço que integra com a base de dados.

Neste dia foi verificada a falta de um componente de barra de progresso portanto será desenvolvido um componente específico para a ferramenta.

## 27-30/08/2017

### Dashboard de usuário (Jogador) e barra de progresso

Nesses dias foi desenvolvido o dashboard de usuário jogador e o componente de barra de progresso, foi feita a integração com o firebase da maioria dos dados do perfil do usuário, foi dado inicio ao desenvolvimento do componente que exibe os ultimos commits do usuário.

## 31/08/2017

### Dashboard de jogador e uso de Enums

Nesse dia foi desenvolvido mais uma parte do dashboard de jogador (Quadro de ultimos commits). Também foi descoberta uma maneira de utilizar enums para os dados de código (Status, profile...)

Nesse dia também foi desenvolvido o inicio do quadro de ultimas pontuações

## 11/09/2017

### Dashboard de jogador

Nesse dia foi dado continuídade no desenvolvimento do dashboard de jogador, finalizando a funcionalidade de alguns cards (Ultimos commits, Ultimas pontuações, Resumo do time) e iniciando o panorama de níveis. Após o termino da funcionalidade do panorama de níveis será iniciado o desenvolvimento das demais funcionalidades da dashboard de jogador. Neste dia foi adicionada uma nova dependencia no projeto: Ngx-charts para desenho de gráficos.

Também neste dia foi adicionada a funcionalidade de pesquisa de jogadores, e o popup de perfil de jogador (visitante) que graças a tecnologia dos webcomponents foi reaproveitado não precisando ser desenvolvido novamente. Também foi componentizado o ranking rapido de jogadores.

## 13/09/2017

### Dashboard de jogador

Nesse dia foi desenvolvido mais uma parte da dashboard de jogador, completando a funcionalidade de listagem de badges (medalhas), também foi componentizada esse item, foi também removido o componente de barra de progresso do projeto sendo utilizado o mesmo componente mas como um componente externo.

O componente de barra de progresso desenvolvido está disponível em: <https://www.npmjs.com/package/rt-progress-bar> e será mantido também pelo desenvolvedor deste projeto.

## 14/09/2017

### Dashboard de jogador

Nesse dia foi finalizado o trabalho de componentização do componente de medalhas e construída a lógica de busca e exibição de medalhas. Foi desenvolvida a logica de plotagem do ranking rapido e da posição atual do jogador no perfil (visitante). Também foram feitas correções e adaptações para suportar jogadores em diversas posições no ranking e jogadore sem time.

## 18/09/2017

### Dashboard de gerente

Nesse dia foi dado inicio ao desenvolvimento do dashboard de gerente. Ficou completa a tela de listagem de commits, faltando apenas desenvolver as ações e os pop-ups que possibilitarão o gerente revisar e analisar commits.

## 21/09/2017

### Dashboard de gerente

Neste dia foi iniciado o desenvolvimento do popup de analise de commits. Por precisar de uma funcionalidade que não estava disponível na versão utilizada foi feita a atualização do set de componentes Angular Material 2 para a versão 2.0.0-beta.10, também foi atualizado o set Covalent Teradata para a versão 1.0.0-beta.7

## 25/09/2017

### Dashboard de gerente e client cli

Neste dia foi finalizada a funcionalidade básica do dashboard de gerente e iniciado o desenvolvimento do script cli que insere os commits automaticamente.

## 30/09/2017

### Script cli

Neste dia foi desenvolvida a primeira versão do script cli que fará a inserção dos commits no servidor git. É necessário agora implementar as validações do script e implementar o sistema de atribuição de pontuações

## 02/10/2017

### Script cli

Neste dia foram implementadas melhorias no script. Está inserindo commits, artefatos e pontuações, tanto positivas quanto negativas. Também foram implementadas as atribuições de pontuação na tela do manager (CommitedArtifacts) e adicionado mais um atributo na pontuation para encontrar a pontuação referente ao artefato.

## 04/10/2017

### Correções nas pontuações e barra de progresso de níveis

Neste dia foram feitas correções no sistema de atribuição de pontuação e na barra de progesso de níveis.

## Referências

<references />

------------------------------------------------------------------------

<a href="Categoria:Projeto_Integrador_II" class="wikilink" title="Categoria:Projeto Integrador II">Categoria:Projeto Integrador II</a>

[^1]: Documentação oficial Firebase, *Indexing data*, <a href="https://firebase.google.com/docs/database/security/indexing-data_Firebase" class="wikilink" title="https://firebase.google.com/docs/database/security/indexing-data Firebase">https://firebase.google.com/docs/database/security/indexing-data Firebase</a>

[^2]: Documentação oficial firebase, *Structure data*, <a href="https://firebase.google.com/docs/database/web/structure-data_Firebase" class="wikilink" title="https://firebase.google.com/docs/database/web/structure-data Firebase">https://firebase.google.com/docs/database/web/structure-data Firebase</a>

[^3]: Blog Ta Safo, *MongoDb normalizar ou desnormalizar? Eis a questão*, <a href="https://tasafo.org/2013/09/05/mongodb-normalizar-ou-desnormalizar-eis-a-questao/_Ta_Safo" class="wikilink" title="https://tasafo.org/2013/09/05/mongodb-normalizar-ou-desnormalizar-eis-a-questao/ Ta Safo">https://tasafo.org/2013/09/05/mongodb-normalizar-ou-desnormalizar-eis-a-questao/ Ta Safo</a>

[^4]: Nomadev, *Como mudar seu jeito relacional de pensar?*, <a href="http://nomadev.com.br/mongodb-como-mudar-seu-jeito-relacional-de-pensar/_Nomadev" class="wikilink" title="http://nomadev.com.br/mongodb-como-mudar-seu-jeito-relacional-de-pensar/ Nomadev">http://nomadev.com.br/mongodb-como-mudar-seu-jeito-relacional-de-pensar/ Nomadev</a>
