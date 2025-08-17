## O que é Shell Script?

É um arquivo executável, que se transforma em uma ferramenta de automação interpretado pelo shell de comandos das derivações de sistemas operacionais Linux/Unix. É uma arquivo com comandos e intruções que facilita muito as tarefas dos profissionais de TI, pois proporciona ao usuário executar ou automatizar várias tarefas para serem executadas pelo sistema. Resumindo, acaba sendo uma linguagem de programação de alto nível que é interpretada pela shell.

## Iniciando a linguagem de programação Shell Script

No terminal do linux, devemos escolher um editor para criar o shell script. Como exemplo, usando o editor nano, digitamos:

`nano.nomedoscript.sh`

Alguns scripts usados nas atividades:

`delqtd.sh`  
`mediawikibkp.sh`  
`moodlebkp.sh`  
`moodlehtmlbkp.sh`  
`mysqlbkp.sh`  
`my_wiki.sql`

### Linha inicial do script

`#!/bin/bash`

Esta linha, após ser digitada em um editor, invoca o bash (ou /sh no caso do shell), que interpreta e executa as instruções contidas no script.

# SHELL SCRIPT sem variável

- shell script pasta mediawiki (sem variável)

A pasta mediawiki possui toda a base de dados gerada. Em nosso exemplo, ela está localizada no endereço: /var/www/html. A seguir segue o exemplo de shell script para acessar a pasta, compactar ela e fazer a cópia para a pasta Backup. O nome "backupwwwwiki.tar.gz" foi atribuído por escolha pessoal.

`#!/bin/bash`  
`cd /var/www/html`  
`tar -zcvf backupwwwwiki.tar.gz mediawiki/`  
`cp backupwwwwiki.tar.gz /home/usuario/Backup`  
`exit`

- shell script base de dados my_wiki do banco de dados MySQL (sem variável)

No exemplo a seguir, foi escolhida uma base de dados do MySQL (my_wiki.sql),gerou o dump dessa base de dados, compactou e copiou para a pasta Backup do ususário.

`#!/bin/bash`  
`mysqldump -u root -psenha my_wiki > my_wiki.sql`  
`cd /home/usuario`  
`tar -zcvf backupmysqlwiki.tar.gz my_wiki.sql`  
`cp backupmysqlwiki.tar.gz /home/usuario/Backup`  
`exit`

- shell script base de dados moodle do banco de dados MySQL (sem variável)

Neste outro exemplo, foi escolhida outra base de dados do MySQL (moodle), também foi gerada o dump dessa base de dados, foi compactada e copiada para a pasta Backup do usuário.

`#!/bin/bash`  
`mysqldump -u root -psenha moodle > moodle.sql`  
`cd /home/usuario`  
`tar -zcvf backupwwwmoodle.tar.gz moodle.sql`  
`cp backupwwwmoodle.tar.gz /home/usuario/Backup`  
`exit`

# SHELL SCRIPT com variável

Devido a programação trabalhar com muitos valores, eles acabam variando muito em determinadas situações. Em nosso exemplo, utilizamos da variável para ser alterada quando for necessário, sem que se desvie do objetivo final do script criado.

## backup web mediawiki

- shell script pasta mediawiki (com variável)

Seguindo a mesma descrição dos scripts criando sem variável, segue o script com variável da pasta "mediawiki". Este script vai gerar um arquivo compactado, que terá um nome, seguido de um número, que representa a hora, dia e mês em que foi criado.

`#!/bin/bash`  
`data=$(date +%s)`  
`$DIR=/var/www/html`  
`cd $DIR`  
`DIR_ORIG="/var/www/html/mediawiki/"`  
`DIR_DEST="/home/usuario/Backup"`  
`BKP_NAME="backupwwwwiki-${data}.tar.gz"`  
`tar -zcvf ${BKP_NAME} ${DIR_ORIG}`  
`cp ${BKP_NAME} ${DIR_DEST}`  
`exit`

- shell script pasta my_wiki (com variável)

Abaixo segue o script com variável da pasta de base de dados my_wiki do banco de dados do MySQL. Em relação ao script sem variável da mesma pasta citada acima, observa-se o uso das variáveis como diferencial. Este script vai gerar um arquivo compactado, que terá um nome seguido de um número, que representa a hora, dia e mês em que foi criado.

## backup banco de dados mediawiki

`#!/bin/bash`  
`data=$(date +%s)`  
`mysqldump -u root -psenha my_wiki > /home/usuario/my_wiki.sql`  
`$diretorio =/home/usuario/`  
`cd  $diretorio`  
`DIR_ORIG="/home/usuario/my_wiki.sql"`  
`BKP_NAME="backupmysqlwiki-${data}.tar.gz"`  
`DIR_DEST="/home/usuario/Backup/"`  
`tar -zcvf ${BKP_NAME} ${DIR_ORIG}`  
`cp ${BKP_NAME} ${DIR_DEST}`  
`exit`

- shell script pasta moodle (com variável)

Abaixo segue o script com variável da pasta de base de dados moodle do banco de dados do MySQL. Em relação ao script sem variável ,da pasta moodle que foi citada acima, observa-se o uso das variáveis como diferencial. Este script vai gerar um arquivo compactado, que terá um nome seguido de um número, que representa a hora, dia e mês em que foi criado.

`#!/bin/bash`  
`data=$(date +%s)`  
`mysqldump -u root -psenha moodle > /home/usuario/moodle.sql`  
`$diretorio =/home/usuario/`  
`cd  $diretorio`  
`DIR_ORIG="/home/usuario/moodle.sql"`  
`BKP_NAME="backupwwwmoodle-${data}.tar.gz"`  
`DIR_DEST="/home/usuario/Backup/"`  
`tar -zcvf ${BKP_NAME} ${DIR_ORIG}`  
`cp ${BKP_NAME} ${DIR_DEST}`  
`exit`

# SHELL SCRIPT para deletar arquivos

Como visto nos scripts acima, foram gerados backups de determinados arquivos. Chega um momento que eles precisam ser eliminados quando se esgotar o prazo de guarda que foi determinado como política de armazenamento, ou até mesmo para que o espaço reservado para backups não seja totalmente preenchido. Uma maneira de resolver essa situação, é criar um script, determinando algum critério para eliminação dos arquivos. Abaixo, alguns exemplos utilizados nessa ação. Lembrando que os scripts são gerados manualmente. Se for necessário automatizar sua execução, utilizar a ferramenta **cron** para agendar o script.

O script abaixo, no momento em que for executado, determina que sejam eliminados os arquivos **modificados** a mais de 5 dias que estão dentro da pasta /home/marco/Backup/.

`#!/bin/bash`  
`find /home/marco/Backup/ -mtime +5 -exec rm {} \;`  
`exit`

------------------------------------------------------------------------

Neste caso, o difencial é em relação a data de criação. Serão eliminados os arquivos que estiverem na pasta /home/marco/Backup que foram **criados** a mais de 5 dias.

`#!/bin/bash`  
`find /home/marco/Backup/ -ctime +5 -exec rm {} \;`  
`exit`

------------------------------------------------------------------------

Agora o que muda neste exemplo, é que os arquivos serão deletados pela contagem em minutos, o script determina que sejam deletados os arquivos **modificados** a mais de 60 minutos.

`#!/bin/bash`  
`find /home/marco/Backup/ -mmin +60 -exec rm {} \;`  
`exit`

------------------------------------------------------------------------

Esse outro exemplo, o script determina que sejam eliminados os arquivos da pasta /home/marco/Backup/ que foram **criados** a mais de 60 minutos.

`#!/bin/bash`  
`find /home/marco/Backup/ -cmin +60 -exec rm {} \;`  
`exit`

------------------------------------------------------------------------

O próximo script, determina que sejam eliminados arquivos pela quantidade existente na pasta de destino. Supondo que a pasta deva ter no máximo 20 arquivos, o script abaixo vai listar os arquivos na pasta /home/marco/Backup, vai manter os 20 arquivos mais recentes e eliminar o restante.

`#!bin/bash`  
`ls -td1 /home/marco/Backup/* | sed -e '1,20d' | xargs -d '\n' rm -rif`  
`exit`

## Referências

El blog de emijrp. Cómo migrar un MediaWiki de un servidor a otro. Disponível em:\<<http://emijrp.blogspot.com.br/2011/05/como-migrar-un-mediawiki-de-un-servidor.html>\>. Acesso em: 21 de outubro de 2016.

Portal Viva o Linux. Backup automático em Shell Script. Disponível em:\<<https://www.vivaolinux.com.br/artigo/Backup-automatico-em-Shell-Script>\>. Acesso em: 27 de julho de 2016.

Portal InfoWester. Compactação e descompactação de arquivos com Tar e gzip. Disponível em:\<<http://www.infowester.com/lintargzip.php>\>. Acesso em: 01 de agosto de 2016.

Portal Stack Overflow. Create timestamp variable in bash script. Disponível em:\<<http://stackoverflow.com/questions/17066250/create-timestamp-variable-in-bash-script>\>. Acesso em: 23 de agosto de 2016.

--<a href="Usuário:Marco_Aurélio" class="wikilink" title="Marco Aurélio">Marco Aurélio</a> (<a href="Usuário_Discussão:Marco_Aurélio" class="wikilink" title="discussão">discussão</a>) 20h13min de 21 de novembro de 2016 (BRST)

------------------------------------------------------------------------

<a href="Categoria:Estágio_Manutenção_de_Servidores" class="wikilink" title="Categoria:Estágio Manutenção de Servidores">Categoria:Estágio Manutenção de Servidores</a>
