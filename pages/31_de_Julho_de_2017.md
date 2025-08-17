### Participantes:

Evandro Cantu  
Faahd Hassif Guerreiro Solano  
Julio Cesar Urnau de Almeida  
Sara Santana  

## 1ª Coleta de Dados

Em entrevista realizada no dia 31 de Julho de 2017, com o Dr Evandro Cantu, considerado um dos maiores escaladores da tríplice fronteira, foi discutido a interface e funcionalidades que o projeto deverá atingir ao final de seu desenvolvimento.  
Fora produzido um esboço das telas principais do sistema, cujo qual é anexo deste documento. Da coleta de dados foi consolidado a interface inicial do sistema que é expressada segmentadamente a seguir, vejamos:  

### Cabeçalho

Ao topo da página ficará localizado o ícone do sistema a esquerda, uma área para cadastro e login no sistema, logo abaixo estará localizado um menu dividido em Início, Setores, Blog e Contato, e contará ainda como uma barra da buscas no site. Esse conteúdo é padrão e será apresentando em todas as telas desenvolvidas no sistema. Ainda nesta área será realizado o controle de login do usuário, e apresentado outras funções de controle administrativas dependentes do privilégio do usuário que esteja logado.  

### Tela de Início

Mais abaixo será apresentando um mapa integrado a API do Google Maps onde é apresando a partir de determinado ZOOM IN sobre o mapa guias de referência de locais onde existem setores cadastrados. Anexo ao mapa existirá um campo de busca, por onde o usuário pode realizar busca de Setores ou Vias, e após a busca apresentar no mapa o setor escolhido, além disso o campo de busca apresentará resultados semelhantes para facilitar e agilizar a busca do usuário.  
Seguindo mais abaixo ficará localizado o campo Setores em Destaque que visá apresentar Setores relevantes a localidade do usuário e que apresentam um boa taxa de classificação. Organizados em blocos de 3 a 4 por linha, em até 3 linhas, onde cada bloco contem uma imagem do setor e informações como título e descrição, ainda todo o bloco ficará linkado para que com um clique em qualquer área do bloco leve o usuário até a página destina as informações do setor.  
O próximo tópico apresentando é o de História, que conterá uma breve introdução da origem da escalada e seu processo evolutivo, dicas sobre sua prática e orientações para despertar em usuários que estão tendo seu primeiro contato com a escala o desejo de praticar a modalidade.  
Ao final é apresentado um rodapé com informações relevantes ao site, sobre contato e termo de uso das informações.  
A ideia principal é trazer desde a chegada do usuário a página uma interface que ele possa rapidamente interagir e encontrar locais para poder praticar a modalidade. Em outras palavras, pode-se dizer que o sistema Escalador visa ser uma enciclopédia da prática de escalada com informações de fácil acesso e constantemente atualizadas.  

### Tela de Setores

Setores é pagina central de buscas e resultados, apresentando de maneira listada todos os setores relevantes a determinada busca pré-realizada ou determinada já nesta página, outra funcionalidade após a definição de uma cidade na busca é a capacidade de adicionar um Setor à cidade além disso estando com a cidade já selecionada será apresentando na tela até 6 (seis) blocos organizados em linhas com 3 blocos cada, onde é apresentando assim como na TELA DE INICIO uma imagem do setor e informações como título e descrição, e tudo estará linkado para após um clique em qualquer parte da área o usuário seja redirecionado para a página de informações do setor selecionado. Existirá um sistema de paginação que gerencia a quantidade de setores a serem apresentados além de guias de navegação de páginas.  

### Tela de Cadastro de Setor

Ao selecionar uma cidade na TELA DE SETORES e clicar sobre o botão ADICIONAR SETOR, o usuário é então redirecionado para essa página, onde de princípio apresenta uma mapa com foco na cidade definida anteriormente que exibe os pontos já cadastrado pela cidade e um guia que deve ser movida e posicionada sobre a localidade em que se deseja cadastrar o setor, feito isso é necessário que seja confirmado no botão que está abaixo do mapa com o nome de CONFIRMAR LOCAL.  
Após confirmado, surgirá na tela os seguintes campos a serem preenchidos:  
:- Nome:  
:- Local:  
:- Equipamento:  
Além disso existirá dois campos a voluntários que podem ser completados pelo usuário através do envio de foto (em formato JPEG ou PNG de tamanho máximo de 2mb ), sendo um deles o percurso para se chegar ao setor e imagens do setor. É importante que o usuário envie ao menos uma foto afim desta ser a foto de principal do setor, a qual será indexada em buscas.  
Nesta mesma página ainda será exibido as coordenadas latitudinais e longitudinais do setor.  
Ao finalizar todo o cadastro o usuário podem então salvar no sistema o setor clicando em SALVAR.  

### Tela Vias do Setor

Quando o usuário for redirecionado para está página encontrará as seguintes informações:  
:- Nome  
:- Local  
:- Latitude  
:- Longitude  
:- Fotos  
:- Classificação  
:- Checado por  
:- Uma tabela com vias  
Nesta tabela em que é exibida as vias cadastradas no setor será possível visualizar seu nome, sua dificuldade e um botão para edição. O nome da via *linkará* para a página de perfil da via, logo, ao clicar o usuário será então redirecionado para esta página.  

### Rodapé

Espaço dedicado para apresentação de informações de contato, suporte, informações básicas do serviço e termo de uso comum a todos os usuários.  
