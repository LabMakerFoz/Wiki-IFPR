# Qualygame

## Equipe

Professore orientadores  

- Estevan Brandt Braz Costa
- Alcione Benacchio

Aluno  

- Victor Hartur de Carvalho Blosquievis

Ano  

- 2017

## Objetivo

Desenvolver uma gamificação e uma ferramenta para ser usada em empresas de desenvolvimento de software, aumentando o engajamento na produção de artefatos de qualidade e por consequência contribuindo no aumento da qualidade do produto final. A ferramenta visa também facilitar o feedback entre Programadores/Engenheiros de Software e Gerente de Qualidade.

## Problema

O MPS-BR ou Melhoria de Processos do Software Brasileiro, é um modelo de qualidade de processo criado em 2003 pela Softex (Associação para Promoção da Excelência do Software Brasileiro) para melhorar a capacidade de desenvolvimento de software nas empresas brasileiras. Para a definição do MPS-BR levou em consideração normas e modelos internacionalmente reconhecidos como CMMI (Capability Maturity Model Integration), e nas normas ISO/IEC 12207 e ISO/IEC 15504 e na realidade do mercado brasileiro de software.

Os níveis de maturidade no modelo MPS-BR estabelecem patamares de evolução dos processos. O nível de maturidade em que se encontra uma organização permite prever o seu desempenho futuro ao executar um ou mais processos. O modelo define sete níveis de maturidade:

- A (Em Otimização);
- B (Gerenciado Quantitativamente);
- C (Definido);
- D (Largamente Definido);
- E (Parcialmente Definido);
- F (Gerenciado);
- G (Parcialmente Gerenciado).

Sendo o nível G o primeiro a ser implementado e o nível A o nível máximo que a empresa poderá atingir.[^1]

O objetivo da ferramenta é aumentar o engajamento na produção de alguns artefatos que são requeridos em um determinado nível do MPS-BR, pois, observou-se que por ser um trabalho repetitivo e maçante gera um certo descontentamento e negligência na produção desses artefatos.

## Proposta

A proposta é desenvolver uma gamificação (Estrutura) que, por meio de recompensas virtuais e reais estimule os colaboradores a produzir os artefatos de qualidade. Por consequência da maior produção de artefatos, existe a possibilidade de que os colaboradores tenham maior ciencia a respeito de erros/bugs no produto final e dessa forma procurem soluções no momento oportuno, aumentando a qualidade do produto final. Também será desenvolvida uma ferramenta que irá implementar a gamificação para auxiliar na obtenção de dados e oferecer feedback sobre o progresso dos jogadores.

#### Project Canvas

<http://app.projectcanvas.online/#/board/IScYajFwysxQCBF1QyyGFOFJtWIh1hl5xxpQZJ7fM8=/public>

### Protótipos de baixa fidelidade

<a href="Arquivo:Pbf-qualygame.pdf" class="wikilink" title="Arquivo:Pbf-qualygame.pdf">Arquivo:Pbf-qualygame.pdf</a>

## Público Alvo

Empresas de desenvolvimento de software que implementam algum processo de qualidade envolvendo produção de artefatos (Arquivos, Checklists...), em especial empresas que implementam o MPS-BR.

Será utilizado como modelo uma empresa que funciona como fábrica de software certificada com MPS-BR nível F, localizada em Foz do Iguaçu, Paraná, Brasil, com aproximadamente 30 colaboradores sendo aproximadamente 15 da área operacional da fabrica, responsáveis pela produção da maior parte dos artefatos de qualidade.

## Principais Funcionalidades

- Monitoramento e gerenciamento de commits
- Gerenciamento de usuários
- Gerenciamento de projetos e ciclos
- Feedback de progresso dos jogadores
- Ranking de jogadores
- Badges/Medalhas (Recompensas virtuais)

## Cronologia

<a href="Cronologia" class="wikilink" title="Cronologia">Cronologia</a>

## Gamificação

A gamificação foi estruturada da seguinte maneira:

### Mecânicas

Foram selecionadas algumas mecânicas de gamificação de acordo com os seguintes critérios:

- Perfil de jogador indicado (Levando em conta os perfis presentes na fabrica usada como base)
- Relação com o problema (O quanto a mecanica auxilia na resolução do problema)
- Dificuldade de implementação

As mecânicas selecionadas foram as seguintes [^2]:

- Tutorials
- Progress
- Flow
- Consequences
- Social Status
- Social Discovery
- Level
- Learning
- Light Touch
- Points
- Physical Rewards
- Leaderboards
- Badges

### Ações Relevantes

As ações relevantes são ações executadas no sistema que oferecem pontuação para os jogadores. Após estudos foram elicitadas as seguintes açõess relevantes:

- Commit
- Artefato avaliado sem erros
- Ciclo completo
- Projeto completo
- Não conformidade
- Reporte de Bug
- Commit incorreto

Depois de testes foi estipulado uma pontuação para cada ação relevante, a relação de ação e pontuação final foi a seguinte:

| Ação relevante                                           | Pontuação |
|----------------------------------------------------------|-----------|
| Commit                                                   | 50        |
| Artefato avaliado sem erros                              | 100       |
| Sprint completa com todos artefatos                      | 400       |
| Sprint completa com todos artefatos sem erros            | 500       |
| Projeto completo com todos artefatos                     | 600       |
| Projeto completo com todos artefatos sem erros           | 800       |
| Não conformidade\|\|-25                                  |           |
| Finalizar sprint faltando artefatos\|\|-100 Por artefato |           |
| Bug reportado por cliente e validado\|\|-200 Por Bug     |           |
| Envio incorreto (Com tag mas faltando artefatos)\|\|-500 |           |

### Níveis

Após os testes com a pontuação chegou-se a conclusão que o melhor seria fazer a evolução com valores fixos de pontuação e não progressivos. A relação de níveis e pontuações se encontra na tabela a baixo:

| Nível   | Pontuação |
|---------|-----------|
| Nível 1 | 0-99      |
| Nível 2 | 100-499   |
| Nível 3 | 500-999   |
| Nível 4 | 1000-1499 |
| ...     | ...       |

A partir do nível 4 o jogador sobe 1 nível a cada 500 pontos.

Caso o jogador tenha sua pontuação reduzida a baixo do mínimo necessário para o nível ele tem seu nível rebaixado. Ex:

Jogador nível 5 tem 1500 pontos e perdeu 100 pontos, sua pontuação é rebaixada para 1400 e ele retorna para o nível 4.

### Medalhas

Foram criadas algumas medalhas que serão usadas como recompensa virtual, a relação de medalhas está na tabela a seguir:

| Medalha                          | Icone |
|----------------------------------|-------|
| Primeiro Envio                   | \*    |
| 10 Envios                        | \*    |
| 25 Envios                        | \*    |
| 50 Envios                        | \*    |
| 5 envios consecutivos sem NCs\*  | \*    |
| 10 envios consecutivos sem NCs\* | \*    |
| 20 envios consecutivos sem NCs\* | \*    |
| Nível 5                          | \*    |
| Nível 10                         | \*    |
| Nível 20                         | \*    |
| Nível 50                         | \*    |

style="caption-side:bottom; color:#494949;text-align:left;"\|*\*Não Conformidade*

O Jogador nunca perderá suas medalhas, uma vez obtida ela é vinculada ao seu perfil por tempo indeterminado.

<a href="Testes_de_pontuação" class="wikilink" title="Testes de pontuação">Testes de pontuação</a>

## Ferramenta

A arquitetura da ferramenta será composta pelo framework **Angular 2**[^3] em sua versão 4.3.2, também será utilizada a plataforma **Firebase**[^4] para persistencia de dados em banco de dados tempo real e autenticação de usuários.

Como o framework Angular 2 é baseado em webcomponents serão utlizados alguns sets de componentes, são eles:

- Angular Material 2 [^5]na versão 2.0.0-beta.8
- Teradata Covalent [^6] na versão 1.0.0-beta.6
- Ngx-Charts [^7] na versão 6.0.2

Para a integração entre o framework Angular 2 e a plataforma Firebase será utilizado o plugin oficial **angularfire2**[^8] desenvolvido pela própria Firebase na versão 4.0.0-rc.1 e a biblioteca **firebase**[^9] também desenvolvido pela empresa detentora da plataforma na versão 4.2.0, para desenvolvimento será utilizado um servidor **node.js**[^10] na versão 8.1.0, o assistente **angular-cli**[^11] na versão 1.2.6, a linguagem **typescript**[^12] na versão 2.4.1 e o editor de texto **Visual Studio Code**[^13] em sua versão 1.14.2.

Todas as ferramentas utilizadas são grátis ou *opensource* e estão em desenvolvimento, ou seja, estão recebendo atualizações constantes, portanto algumas versões poderão ser alteradas até o fim do projeto.

Os requisitos serão elicitados em 3 níveis, Agregadores, de Usuário e Sub-Função onde:

- **Agregadores** são requisitos que englobam requisitos de usuários.
- **De Usuário** são requisitos que formam uma função completa ou um processo elementar do sistema.
- **Sub-Funções** são requisitos que compoem requisitos de usuário ou seja, não são funções completas apenas partes de outras funções.

O cronograma de desenvolvimento da ferramenta pode ser acompanhado pelo quadro na ferramenta Trello: <a href="https://trello.com/b/RNKJvhqU_Quadro_de_tarefas" class="wikilink" title="https://trello.com/b/RNKJvhqU Quadro de tarefas">https://trello.com/b/RNKJvhqU Quadro de tarefas</a>

## Referências

<references />

------------------------------------------------------------------------

<a href="Categoria:Projeto_Integrador_II" class="wikilink" title="Categoria:Projeto Integrador II">Categoria:Projeto Integrador II</a>

[^1]: Blog da Qualidade, *O que é o MPS-BR?*, (<a href="http://www.blogdaqualidade.com.br/o-que-e-o-mps-br/_blogdaqualidade.com.br" class="wikilink" title="http://www.blogdaqualidade.com.br/o-que-e-o-mps-br/ blogdaqualidade.com.br">http://www.blogdaqualidade.com.br/o-que-e-o-mps-br/ blogdaqualidade.com.br</a>)

[^2]: Gamified.uk,*52 Gamification Mechanics and Elements*, <a href="https://www.gamified.uk/user-types/gamification-mechanics-elements/_gamified.uk" class="wikilink" title="https://www.gamified.uk/user-types/gamification-mechanics-elements/ gamified.uk">https://www.gamified.uk/user-types/gamification-mechanics-elements/ gamified.uk</a>

[^3]: Angular 2, *Angular 2*, <a href="https://angular.io/_angular.io" class="wikilink" title="https://angular.io/ angular.io">https://angular.io/ angular.io</a>

[^4]: Firebase, *Firebase*, <a href="https://firebase.google.com/?hl=pt-br_firebase.google.com" class="wikilink" title="https://firebase.google.com/?hl=pt-br firebase.google.com">https://firebase.google.com/?hl=pt-br firebase.google.com</a>

[^5]: Angular Material 2, *Angular Material*, <a href="https://material.angular.io/_material.angular.io" class="wikilink" title="https://material.angular.io/ material.angular.io">https://material.angular.io/ material.angular.io</a>

[^6]: Teradata Covalent, *Teradata Covalent*, <a href="https://teradata.github.io/covalent/#/_teradata.github.io/covalent" class="wikilink" title="https://teradata.github.io/covalent/#/ teradata.github.io/covalent">https://teradata.github.io/covalent/#/ teradata.github.io/covalent</a>

[^7]: Ngx-Charts, *Ngx-Charts*, <a href="https://github.com/swimlane/ngx-charts_github.com/swimlane/ngx-charts" class="wikilink" title="https://github.com/swimlane/ngx-charts github.com/swimlane/ngx-charts">https://github.com/swimlane/ngx-charts github.com/swimlane/ngx-charts</a>

[^8]: Angular Fire 2, *Angular Fire 2*, <a href="https://github.com/angular/angularfire2_github.com/angular/angularfire2" class="wikilink" title="https://github.com/angular/angularfire2 github.com/angular/angularfire2">https://github.com/angular/angularfire2 github.com/angular/angularfire2</a>

[^9]: Firebase, *Firebase JS SDK*, <a href="https://github.com/firebase/firebase-js-sdk_github.com/firebase/firebase-js-sdk" class="wikilink" title="https://github.com/firebase/firebase-js-sdk github.com/firebase/firebase-js-sdk">https://github.com/firebase/firebase-js-sdk github.com/firebase/firebase-js-sdk</a>

[^10]: Node.Js, *Node.Js*, <a href="https://nodejs.org/en/_Node.Js" class="wikilink" title="https://nodejs.org/en/ Node.Js">https://nodejs.org/en/ Node.Js</a>

[^11]: Angular CLI, *Angular CLI*, <a href="https://cli.angular.io/_cli.angular.io" class="wikilink" title="https://cli.angular.io/ cli.angular.io">https://cli.angular.io/ cli.angular.io</a>

[^12]: Typescript, *Typescript*, <a href="http://typescriptlang.org/_typescriptlang.org" class="wikilink" title="http://typescriptlang.org/ typescriptlang.org">http://typescriptlang.org/ typescriptlang.org</a>

[^13]: Visual Studio Code, *VSCode*, <a href="https://code.visualstudio.com/_code.visualstudio.com" class="wikilink" title="https://code.visualstudio.com/ code.visualstudio.com">https://code.visualstudio.com/ code.visualstudio.com</a>
