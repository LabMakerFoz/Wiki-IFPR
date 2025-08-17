# Transferência de Arquivos (FTP) [^1]

O protocolo FTP (*file transfer protocol*) (RFC 959) é o protocolo que suporta a aplicação de transferência de arquivos entre computadores.

Numa sessão FTP um usuário pode transferir arquivos de um computador remoto para um computador local e vice-versa (*download* e *upload*, respectivamente). Uma maneira típica de realizar um FTP é utilizar um terminal de texto do Linux, iniciando a aplicação com o comando **ftp** e executando os comandos apropriados. O primeiro comando do usuário (**open**) deve fornecer endereço do computador remoto, estabelecendo com isto uma **conexão TCP entre o processo FTP cliente e servidor**. Depois o usuário deve fornecer sua identificação e sua senha. Outros comandos possíveis são: mudar de diretório (**cd**), solicitar arquivos (**get**), enviar arquivos (**put**), etc.

O **protocolo FTP usa duas conexões paralelas TCP** para transferir arquivos: uma para controle da conexão e outra para a transferência de dados. O controle de conexão é usado para trocar informações como a identificação do usuário e senha e para transferir os comandos FTP. A conexão de dados é usada para transferir os arquivos propriamente ditos. Cada uma destas duas conexões TCP usa uma porta específica: a **conexão de controle** de conexão usa a **porta 21** e a **conexão de dados** usa a **porta 20**.

<a href="Arquivo:FTP.png" class="wikilink" title="Arquivo:FTP.png">Arquivo:FTP.png</a>

As **mensagens de controle FTP** são codificadas em **formato ASCII**, com caracteres maiúsculos, como nos exemplos abaixo.

`USER NAME (USER)`  
`PASSWORD (PASS)`  
`CHANGE WORKING DIRECTORY (CWD)`  
`LOGOUT (QUIT)`  
`RETRIEVE (RETR)`  
`STORE (STOR)`

As respostas são sempre de três dígitos, com uma mensagem opcional seguindo o número, como nos exemplos abaixo..

`331 User name OK, password required`  
`125 Data conection already open; transfer starting`  
`425 Cant open data conection`  
`452 Error writing file.`

## Laboratório: FTP

Objetivo  
Instalar e testar um servidor FTP

<!-- -->

Instalação do servidor FTP  
Instalar o servidor FTP na máquina virtual.

`sudo apt-get install vsftpd`

Teste e conexão com o servidor FTP  
A conexão com o servidor FTP deve ser feita a partir de um terminal da máquina hospedeira.

Procedimentos:

1.  Prepare um arquivo para ser transferido para o servidor.
2.  Inicie a aplicação FTP com o comando:

`ftp `

Principais comandos para uso com a aplicação FTP:

`help -> Lista comandos disponíveis `  
`open `<endereço_IP_do_servidor>` -> Conecta com o servidor`  
`ls -> Lista conteúdo do diretório o servidor remoto`  
`pwd -> Mostra o diretório corrente no servidor remoto`  
`cd -> Muda de diretório no servidor remoto`  
`get `<arquivo>` -> Faz o download de um arquivo do servidor remoto para a máquina local`  
`put `<arquivo>` -> Faz o upload de um arquivo da máquina local para o servidor remoto`  
`exit -> Sai do aplicativo`

Exercícios:

1.  Liste o conteúdo do diretório corrente do servidor remoto.
2.  Transfira um arquivo (*upload*) para o servidor remoto.
3.  Verifique se o arquivo foi transferido.
4.  Navegue até o diretório /var/www do servidor remoto.
5.  Faça um *download* do arquivo index.html que está armazenado no servidor remoto.
6.  Faça modificações no arquivo index.html em sua máquina local.
7.  Faça um *upload* do arquivo index.html modificado para o servidor remoto.
8.  Teste a nova página Web base no servidor.

#### Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h42min de 12 de junho de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: KUROSE, J.F; ROSS K. W. Redes de Computadores e a Internet: Uma abordagem *top-down*, São Paulo: Pearson, 2010.
