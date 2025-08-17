## Introdução ao CSS

### Introdução

''Você não tem por que se intimidar com a perspectiva de usar as Folhas de Estilo em Cascata. Usar um computador pode ser algo assustador quando se vai experimentar pela primeira vez, mas decorrido algum tempo nem se pensa mais nas dificuldades iniciais. Tudo se resume, em se aprender por etapas e é isto que eu vou fazer nesta série de tutoriais. Uma etapa de cada vez.

Quer você seja usuário de um editor WYSIWYG e conhecedor do código por ele gerado ou mesmo não tenha sequer criado uma página Web, este tutorial vai orientá-lo na direção certa.

O tutorial pressupõe um pequeno ou nenhum conhecimento de produção de uma página Web. Ele trata o assunto realmente ' do seu início'''

**O que vai ser preciso?** ''Nada especial. Se você tem acesso a um editor de página Web, ótimo. Se não, você pode usar qualquer editor de texto - NotePad no PC ou SimpleText ou TextEdit em Mac. Se você é usuário do DreamWeaver ou GoLive, iremos usar o modo de 'código'.

Não se apavore! Um editor de imagens não será essencial, pois a princípio não irei me preocupar muito com criação de imagens.

Oh, você irá precisar de um navegador, mas isto eu não precisava dizer. De fato, eu recomendo que você tenha alguns diferentes navegadores. Se você só possui o Explorer, deveria instalar o Mozilla e alguns outros que você poderá obter consultando qualquer listagem Browsers Atuais.

Se você desejar fazer upload de suuas páginas para um servidor Web, vai precisar de um programa FTP, mas não se preocupe com isto agora, pois poderá fazer tudo ensinado no tutorial, no seu próprio computador.''

------------------------------------------------------------------------

**Etapa número 1 - Uma página básica** *Antes de fazer qualquer coisa iremos precisar de uma página Web. E a seguir você tem uma página, a mais básica possível.*

`''`

<html>

<head>

</head>

<body>

` Esta é a minha página Web`  

</body>

</html>

''

*Temos aqui três conjuntos de 'tags' - as tags, normalmente são aos pares, mas nem sempre é assim. Englobando toda a página temos o par de tags*'

<html>

...

</html>

**. A primeira**

<html>

*' é a 'tag de abertura' e a 'tag' de fechamento é a mesma com uma / (barra) entre o sinal de 'menor que' (\<) e html.*

*Dentro da tag*'

<html>

*' existem mais dois pares de tags.*

'''

<head>

...

</head>

*'*contém informações que não foram ainda colocadas no nosso exemplo, a mais importante destas informações é o título da página que aparece na barra de títulos do navegador. Você dá um título a sua página, escrevendo-o dentro da tag title, como mostrado a seguir...''

`''`

<html>

<head>

<title>

Minha Página

</title>

</head>

<body>

` Este é o conteúdo da minha página Web!`  

</body>

</html>

''

*O par de tags*'

<body>

...

</body>

*' engloba todo o conteúdo da sua página Web, texto, imagens, filmes Flash - e tudo mais. Você poderá digitar no seu editor de texto, na janela de código do seu editor WYSIWYG - ou mesmo copiar colar o código da página básica mostrado acima.*

------------------------------------------------------------------------

*Qualquer conteúdo deve ser colocado entre o par de tags*'

<body>

...

</body>

*' para que o navegador possa renderizá-lo.* ''Encher de textos a página, assim como ela está, não dá uma estrutura e nem estiliza os textos. Por não dar estrutura eu quero dizer que os textos simplesmente fluem da esquerda para a direita, de cima para baixo, que as palavras não tem outra ênfase particular que não seja a ordem natural em que são escritas. Faria muito mais sentido grupar palavras e sentenças em parágrafos, títulos, sub-títulos - bem, você deve saber, aquelas coisas básicas de estruturação de textos que se aprende na escola.

Browsers ignoram qualquer pulo de linha ou parágrafos que você insira em uma porção de texto. Eles ignoram também tabulações e até múltiplos espaços entre palavras que são interpretados como um espaço único.

É útil em qualquer porção de texto marcar títulos, sub-títulos, alguns parágrafos e talvez até uma assinatura final.

Em HTML, existem diferentes tags de marcação que se constituem no mecanismo apropriado para estruturar os textos.

Cria-se um parágrafo, colocando texto entre o par de tags '''

...

'''. Em HTML, um parágrafo é um bloco constituido de uma ou mais sentenças separado do próximo bloco por um espaço - tal como este paragráfo que você vê aqui.

Para títulos, existem seis níveis distintos de ênfase, indo desde o mais alto nível '''

<h1>

...

</h1>

**até o mais baixo**

<h6>

...

</h6>

*'. Eles são como mostrados a seguir...*

## Este é um titulo h1

#### Este é um titulo h2

##### Este é um titulo h3

###### Este é um titulo h4

###### Este é um titulo h5

###### Este é um titulo h6

*Como você pode notar diminui o tamanho quando cresce o número que indica o nível sendo que o **h4** equivale aproximadamente ao tamanho de texto chamado 'small' (pequeno). **h5 e h6** são 'smaller' (menor) ,mas em negrito.*

**Bold (negrito)** é uma variante mais destacada que o texto normal e marcada com o par de tags **<b>...</b>** contudo, trata-se de um estilo de apresentação para impressão e na Web é preferível usar-se strong <strong>...</strong>. Embora elas (tags bold e strong) se pareçam iguais quando renderizadas na tela de um monitor, o HTML deverá servir a outros dispositivos também. Softs leitores de tela usados por pessoas portadoras de necessidades especiais para visão, entenderão perfeitamente e lerão com a devida ênfase.

*Você deve saber que itálico é conseguido com a tag **<i>...</i>**. E aqui também, é melhor você não se utilizar de estilização visual, mas usar <em>...</em>. Este par de tags dá a funcionalidade do itálico ao texto independentemente do dispositivo em uso.*

*Sublinhado pode ser conseguido com o par de tags **<u>...</u>** , mas sublinhados na Web tem um significado especial. Usualmente indica um link. É melhor não usar sublinhado para enfatizar, pois esta prática poderá confundir o visitante do site.*

*Esta página básica provavelmente se parecerá um pouco diferente quando visualizada em diferentes navegadores e computadores. Cada navegador tem o seu próprio estilo padrão e a menos que você configure seu navegador ele usará os estilos padrão. Para sobrescrever os estilos padrão dos navegadores, nós criaremos nossos próprios estilos que serão agrupados em uma 'folha de estilos'.*

## Diferentes caminhos do css

### CSS interno

    <head>
       <style>
          div{
             background: yellow;
             width: 200px;
          }
       </style>
    </head>
    <body>
       <div>Essa é uma div.</div>
    </body>

Na tag style serão atribuídas características para a div que está dentro do body.

### CSS externo

    <link href="estilo.css" rel="stylesheet" type="text/css">

Isso vai direcionar à uma outra página onde estará o estilo do css que será atribuídos às tags da página HTML em questão.

### CSS inline

Exemplo:

    <div style="background: yellow; width: 200px;"></div>

Esse é um exemplo de css que será atribuído diretamente na tag em que está sendo colocada. Desse jeito, não será preciso conferir à essa tag um id ou class.

<a href="Categoria:CSS" class="wikilink" title="Categoria:CSS">Categoria:CSS</a> <a href="Categoria:Desenvolvimento_Web" class="wikilink" title="Categoria:Desenvolvimento Web">Categoria:Desenvolvimento Web</a>
