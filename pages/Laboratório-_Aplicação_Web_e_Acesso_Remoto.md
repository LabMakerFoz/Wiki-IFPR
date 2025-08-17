# Laboratório: Aplicação Web e Acesso Remoto

Requisitos de Software/Hardware  
Este laboratório deve ser realizado em uma **Máquina Virtual** **Linux Ubuntu** na qual os alunos possuam permissão de administrador para poder instalar pacotes.

- A Máquina Virtual deve ser instalada configurando a **placa de rede** em **modo *bridge***, visando mantê-la na mesma rede local dos demais computadores do laboratório;
- No exemplo será utilizado o **usuário redes** e o **IP 192.168.X.Y** para ilustrar o acesso a Máquina Virtual.

## Parte 1 - Laboratório sobre Aplicação Web

Objetivos  

Testar o funcionamento da **aplicação Web** e do **protocolo HTTP** e instalar um Servidor Web **apache**.

Fundamentação  
A **aplicação Web** é uma aplicação que permite a um **navegador** (cliente) acessar páginas de hipertextos armazenadas em em **servidor Web**.

<a href="Arquivo:AplicacaoWeb.png" class="wikilink" title="Arquivo:AplicacaoWeb.png">Arquivo:AplicacaoWeb.png</a>

- Os navegadores e o servidor Web se comunicam através de mensagens do **protocolo HTTP**, utilizando como camada de transporte o **protocolo TCP**.
- Para que o **navegador** possa acessar uma página em um **servidor Web** o mesmo deve estar ativo, aguardando por pedidos de **conexão TCP** na **porta 80**.
- Uma vez aberta a conexão TCP entre o navegador e o servidor Web, o servidor será capaz de aceitar **requisições HTTP** vinda do navegador e servi-lo com **respostas HTTP**, incluindo dados, normalmente na forma de **páginas HTML**.

### Navegadores Web

A parte cliente da aplicação Web é implementada pelos **navegadores Web**.

São exemplos de navegadores o Mozilla **Firefox**, o Google **Chrome**, o **Safari** padrão da Macintosh, o **IExplorer** padrão do Windows e outros.

Outro navegador interessante é o **lynx** que permite navegar na Web usando um **terminal de textos**.

Instalação do **lynx**  
Obs: Instalar o lynx na máquina virtual.

`sudo apt-get install lynx`

Testar o **lynx**  
Por exemplo, lendo as notícias de um jornal *online*

`lynx www.folha.com.br`

### Servidores Web

Os **servidores Web** permitem armazenar as páginas Web e disponibilizá-las na Internet.

Um servidor Web bem conhecido é o **apache**, disponível como padrão nas versões do **Linux** e um dos mais utilizados na Internet.

Instalação do **apache**  
Obs: Instalar o lynx na máquina virtual.

`sudo apt-get install apache2`

Testar se o servidor Web está operando normalmente  

1.  Em um **navegador** coloque no endereço da URL o **endereço IP** da máquina onde o apache foi instalado;
2.  Se tudo está funcionando, você verá a resposta padrão do apache.

Armazenamento das páginas HTML no servidor apache  

As **páginas HTML** a serem disponibilizadas pelo servidor **apache** ficam armazenadas do diretório:

`/var/www/html`

Verificação da página padrão da instalação  

`cd /var/www/html`  
`ls`  
`cat index.html`

Para que o servidor mostre uma página diferente deste padrão de instalação deve ser criada uma nova página **index.html**.

Exercício  
Construa uma **página HTML** simples e hospede no **servidor Web**. Para tal, substitua o arquivo **index.html** pela nova página construída.

Salve a página index.html original com outro nome, por exemplo, index.html.old.

## Parte 2 - Acesso Remoto ao Servidor Web

A aplicação de **acesso remoto** é uma aplicação cliente/servidor, na qual um programa cliente, através de um terminal, poderá fazer um **login remoto** no servidor.

O programa do lado cliente é diferente do programa do lado servidor, pois no servidor a aplicação de acesso remoto deve estar ativa e aguardando conexões por parte dos clientes.

Duas aplicações de acesso remoto bem conhecidas nos sistemas Linux são o **SSH** e o **telnet**, entretanto, dicilmente vamos encontrar servidores telnet ativos na Internet, pois no telnet as senhas trafegam em formato ASCII, sem criptografia, o que facilita o ataque de hackers visando obter a senha dos usuários.

### Acesso remoto com SSH

O **SSH** (*Secure Shell*) possibilita acesso remoto seguro, através do uso de criptografia na conexão entre o cliente e o servidor.

O cliente e o servidor SSH se comunicam utilizando como camada de transporte o **protocolo TCP** e o servidor fica aguardando por pedidos de conexão na **porta 22**.

Instalação do servidor SSH  
Obs: Instalar na Máquina Virtual.

Para instalar o **servidor SSH**, digite:

`sudo apt-get install openssh-server `

Para verificar se o serviço de acesso remoto com SSH está ativo, digite:

`ps -aux|grep ssh`

  
Se o serviço estiver ativo, o processo **sshd** deve estar na lista dos processos rodando.

<!-- -->

Testar o acesso remoto ao servidor SSH  

Em outra máquina, que pode ser a máquina hospedeira da máquina virtual, fazer acesso remoto ao servidor, por exemplo:

`ssh redes@192.168.40.X`

  
onde X é o último byte do endereço IP do servidor.

Execute comandos de arquivo e navegue na estrutura de diretórios do servidor, usando comandos como:

`ls`  
`cd`

#### Cópia remota com servidor SSH (scp — *secure copy*)

Com o acesso remoto via SSH ao servidor, é possível ao cliente copiar arquivos do cliente para o servidor, e vice-versa:

- **Cópia** de arquivos do **cliente** para o **servidor**, por exemplo:

`scp arquivo.html redes@192.168.40.X:index.html`

  
No exemplo acima o arquivo **index.html** para o diretório **home** do usuário que possui conta no servidor.

Posteriormente o arquivo deve ser copiado, com comando de **sudo**, para o diretório **/var/www/html** para poder ser acessado pela Internet.

- **Cópia** de arquivos do **servidor** para o **cliente**, por exemplo:

`scp redes@192.168.40.X:/var/www/html/index.html .`

  
No exemplo acima o arquivo **index.html** será copiado diretamente do diretório **/var/www/htm**l. O "." indica que o arquivo será copiado no diretório corrente do terminal do cliente.

<!-- -->

Exercícios  

1.  Use o **SSH** para copiar arquivos com **páginas HTML** do cliente para o **servidor Web**;
2.  Instale a página para o servidor como **index.html** no diretório **/var/www/html**.
3.  Verifique as **permissões** dos arquivos .html, pois estes arquivos devem ter acesso para leitura e execução por todos para poderem ser acessados via Web.
4.  Convide os colegas a visitarem sua página disponibilizada no seu servidor Web.
5.  Acesse sua página Web com o navegador **lynx**.

### Acesso remoto com telnet

Devido a ausência de criptografia na comunicação entre o servidor e o cliente, o **telnet** não é utilizado para acesso remoto.

Por padrão, o **telnet** utiliza na camada de transporte o **protocolo TCP** e a **porta 23**, mas dificilmente encontraremos um servidor disponível para conexão.

Entretando, é possível utilizar o **telnet** para **abrir conexões TCP** em outras portas normalmente abertas a conexões, como por exemplo, a porta 80 de um Servidor Web ou a porta 25 de um Servidor de Email.

Exercício  

- Abra uma **conexão TCP**, usando **telnet**, na **porta 80** do seu **servidor Web**, por exemplo:

`telnet 192.168.40.X 80`

- Envie **via teclado uma mensagem ASCII** de **requisição HTTP** ao seu servidor Web pedindo uma página HTML, por exemplo:

`GET /index.html HTTP/1.0`

  
Obs: Note que foi incluído no **pedido HTTP** a versão do protocolo como HTTP/1.0. Isto é necessaŕio porque com o **telnet na porta 80** não é possível implementar "conexões TCP persistentes", que os navegadores com a versão HTTP/1.1 conseguem implementar.

Análise:

- Verifique a **resposta HTTP** do servidor Web.
- Envie novamente uma mensagem de pedido HTTP e troque a versão do protocolo para HTTP/1.1 e veja a resposta.
- Envie outra mensagem de requisição HTTP e solicite outro arquivo, como teste.html, e veja a resposta.

### Tarefa

Faça um relatório detalhando os passos para instalação do **servidor Web** usando como referência o roteiro de laboratório disponivilizado.

Documente o servidor incluindo impressão de telas da configuração de rede do servidor (ifconfig), de testes conectividade com outras máquinas (ping).

Instale no servidor, como página Web, o ambiente desenvolvido para a disciplina de Inglês.

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h37min de 12 de junho de 2014 (BRT)

Revisâo: --<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 16h03min de 8 de outubro de 2018 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>
