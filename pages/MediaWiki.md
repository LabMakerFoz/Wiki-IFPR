Este aplicativo é um pacote de software livre, licenciado sob a GNU GPL, escrito em PHP *"PHP: Hypertext Preprocessor"*,que faz o uso de banco de dados MySQL, teve seu uso originado no Wikipédia, mas que hoje é utilizado por diversos outros projetos.

Por isso, acaba sendo o aplicativo mais conhecido pelo seu poder e flexibilidade, já que oferce funcionalidades a realização de trabalhos de forma colaborativa.

Como pré-requisitos a sua instalação, o computador precisa ter intalado o Servidor Web Apache, Banco de dados MySQL, e o PHP, que é o componente que executa scripts, conectado ao banco de dados MySQL.

Devido a sua exposição a internet, é preciso, como qualquer software de servidor, que se tome medidas de atualizações quanto a segurança. Isso se faz necessário, já que o software é livre, e devido essa vulnerabilidade, não existe qualquer garantia.

Na sequência, segue os passos para instalação do MediaWiki em um sistema operacional Linux Ubuntu:

Transferir o MediaWiki da fonte:

`wget `[`https://releases.wikimedia.org/mediawiki/1.27/mediawiki-1.27.0.tar.gz`](https://releases.wikimedia.org/mediawiki/1.27/mediawiki-1.27.0.tar.gz)`.`

É conveniente checar a última atualização, através do site www.mediawiki.org/wiki/Download/pt-br

Depois se faz necessário a ação de extrair o pacote:

`tar xvzf mediawiki-1.27.0. tar.gz`

Feito isso, movemos o diretório MediaWiki para raiz do documento:

`sudo mv mediawiki-1.27.0.tar.gz /var/www/html`

Após os comandos digitados para instalação do MediaWiki, precisamos configurá-lo pelo browser. Na página inicial digitar:

`localhost/mediawiki`

Depois disso, será apresentada uma tela que servirá de orientação para configuração do MediaWiki.

1\. Selecionar **Configurar o Wiki**. 2. Selecione o **idioma** desejado. 3. Configurações do MySQL, escolher o tipo de **banco de dados**, o **host**, e um **usuário e senha**.

Concluídas as etapas anteriores, o arquivo **LocalSettings.php** irá ser baixado automaticamente. Para efetivar a instalação, será necessário mover o arquivo para o servidor.
