# Cópias de Segurança ou *Backups*

A **cópia de segurança** dos dados, ou ***backup***, consiste em manter uma ou mais cópias dos dados para fins de recuperação em caso de acidente ou erro que ocasione e perda ou danificação dos dados [^1].

Também é importante manter as cópias de segurança em **local seguro**. Para dados importantes, com necessidade extrema de recuperabilidade, várias cópias devem ser providenciadas e armazenadas em locais diferentes, em prédios ou cidades distinta.

Com o avanço da Internet e dos sistemas de **armazenamento em nuvem**, cópias de segurança podem ser providenciadas para serem armazenadas por meio da rede, permitindo um espalhamento físico dos dados.

## Tipos de *backup*

O tipo de backup a ser utilizado varia de acordo com a necessidade da organização, e depende de quantidade de informação a ser guardada e da frequência com que a informação é atualizada.

Existe basicamente três tipos de backups [^2]:

- Backup total;
- Backup incremental;
- Backup diferencial.

### Backup total

Um **backup total** consiste em **salvar todos os dados**, incluindo todos os arquivos de todos os discos rígidos, onde haja informações a serem recuperadas.

A vantagem deste método é dispor de uma **cópia total dos dados**, facilitando sua recuperação caso seja necessário. Entretanto, caso haja grande quantidade de informações a serem guardadas, o backup total pode ser muito demorado e ainda ser necessário várias conjuntos de dispositivos para armazenar as informações.

Como os backup devem ser realizados regularmente, mantendo-se as informações de cada período considerado, o uso de backup total leva a manter dados redundantes, uma vez que toda a informação é copiada em cada backup.

### Backup incremental

Um **backup incremental** somente **salva os dados que foram alterados** desde o último backup total ou incremental. No backup incremental deve-se manter uma base de dados com um **backup total** (não importa a quanto tempo tenha sido criada) e todos os **backups incrementais** realizados.

A vantagem do backup incremental é o uso eficiente do tempo e do espaço a ser utilizado pelos dados, já que o processo de cópia envolve somente a cópia dos dados que foram modificados desde o último backup.

A desvantagem é que as restaurações totais ou parciais são demoradas, já que pode-se ter que pesquisar em várias bases de dados para se localizar os dados necessários.

### Backup diferencial

Um **backup diferencial** **salva os dados que foram alterados** desde o último backup total. É necessário uma base de dados com o backup total e da base de dados mais recente do backup diferencial para realizar uma recuperação completa do sistema.

O **backup diferencial** tem a vantagem de permitir uma recuperação rápida, mas a desvantagem de ser demorado caso tenha passado muito tempo desde o último backup total.

<a href="Arquivo:BackUp.png" class="wikilink" title="Arquivo:BackUp.png">Arquivo:BackUp.png</a>

## Armazenamento

Existem vários tipos de **dispositivos de armazenamento** que podem ser utilizados para guardar a cópia de segurança dos dados, como **unidades de fita**, **discos rígidos** e **serviços em nuvem**.

As **unidades de fita** ainda são utilizadas para backups [^3], entretanto, exigem organização e cuidado para seu armazenamento para não comprometer os dados.

Os **discos rígidos** são uma ótima unidade de armazenamento em termos de custo e capacidade de armazenar informações. Unidades removíveis são práticas de serem substituídas e podem ser uma boa solução para empresas de pequeno porte.

Os **serviços em nuvem** são soluções modernas para o armazenamento de cópias de segurança.

## Políticas de backup

Uma **política de backup** tem por objetivo formalizar os procedimentos técnicos para a realização da cópia de segurança dos dados. A definição da política deve levar em conta o tamanho da instituição, a quantidade de dados a serem guardados, a frequência em que as cópias devem ser realizadas e o tipo de equipamento que a organização dispõe.

Pontos a serem definidos em uma política de backup [^4]:

- Frequência em que a cópia de segurança deve ser realizada;
- Quanto tempo demora a cópia;
- Quanto tempo a recuperação dos dados pode levar;
- Por quanto tempo será mantida a cópia de segurança.

## Backup em Servidores Linux

Num **servidor Linux** os principais **diretórios** que precisam de **cópias de segurança** são [^5]:

- **/var/www**: É o diretórios onde ficam as **páginas Web** de um **servidor Web**.
- **/var/lib/mysql**: É o diretório padrão das **bases de dados MySQL** e possui arquivos que são utilizados por servidores Web e outros aplicativos.
- **/home**: É o diretório onde ficam os **arquivos pessoais** dos usuários.
- **/etc**: É o diretório onde ficam os principais **arquivos de configuração** do sistema. É bom manter cópias dos mesmos para evitar reconfigurar totalmente o sistema após uma reinstalação.
- **/var/log**: É o diretório onde ficam os **arquivos de log** do sistema, com o registro de todas as ações sobre a operação do sistema.

Também é importante registrar como estão **montadas as partições** fora da estrutura principal de diretórios do Linux, para reconfigurar o sistema caso seja necessário.

## Utilitários para backup

Amanda  
O **Amanda** é um sistema dedicado para realização de backup de maneira mais profissional, baseado em software livre e gratuito. É voltado para backup em **unidades de fita**, o que nem sempre é uma opção barata e fácil para pequenas empresas. Entretanto, também é possível utilizar este sistema para programar backup em **disco rígido**.

<!-- -->

tar  
O utilitário **tar** foi desenvolvido originalmente para a função de backup, gerando um único arquivo que depois poderia ser armazenado em fita, disco rígido ou outra unidade. Por ser um utilitário padrão no Linux e fácil utilizar em pequenas organizações, o **tar** é a opção que vamos em nosso servidor.

<!-- -->

gzip  
O utilitário **gzip** é utilizado para compactar arquivos, geralmente utilizado em conjunto com o **tar**. Os arquivos compactados com o gzip usam a extensão **tar.gz**.

Exemplo de comando para **compactar** o diretório /dados e **criar um arquivo tar.gz** [^6]:

`tar -zcvf arquivo.tar.gz dados/`

:\*onde a opção **z** indica para compactar com gzip, **c** para criar cópia dados, **v** para exibir informações e **f** para usar como destino um arquivo.

Para descompactar o arquivo posteriormente, troca-se a opção **c** por **x** para extrair os dados:

`tar -zxvf arquivo.tar.gz`

:\*Como não foi indicada um diretório destino, este comando descompacta no diretório corrente.

Estes comandos são úteis para realizar **cópias de segurança** de um ou mais diretórios do sistema, gerando um arquivo compactado que poderia ser armazenado em um **disco rígido externo** ou gravado em **DVD**.

### Scripts de backup

Tão importante quanto fazer as cópias de segurança e organizá-la e datá-las para facilitar a recuperação posterior dos dados.

Suponha que seja preciso fazer backups diários de um diretório de dados diariamente. As invés de renomear cada arquivo gerado pelo backup, um pequeno script poderia facilitar o processo [^7]:

`#!/bin/bash`  
`` DATA=`date +%Y%b%d` ``  
`cd /mnt/backup`  
`tar -zcvf Backup-"$DATA".tar.gz dados/`

:\*No exemplo os arquivos de backup são armazenados no diretório **/mnt/backup**, que pode ser um diretório montado em um disco rígido exclusivo para as cópias de segurança.

### Agendamento de backup

Para que script seja executado diariamente de forma automática, o mesmo pode ser incluído no **agendamento de tarefas** com a **crontab global**, por exemplo [^8]:

`30 6 * * * root /usr/local/bin/script-backup`

:\*onde **30 6** indica minuto e hora, root indica que o script será executado com permissão de administrdor e **/usr/local/bin/** é o local onde está armazenado o script.

## Backup em Servidor Remoto

Uma boa opção para realizar **cópias de segurança** é salvar os backups em um **servidor remoto**. Usar servidores em locais diferentes elimina a possibilidade de desastres e destruir o servidor principal e o servidor com o backup.

Para transferir dados entre os servidores pode-se utilizar a aplicação **SSH** e o comando de cópia remota **scp**.

Para que o backup seja feito de forma automática, é necessário utilizar **chaves de autenticação** para permitir que o **script de backup** transfira os arquivos sem necessidade de interferência do usuário [^9].

Uso de Chaves de Autenticação  
Veja como gerar **chaves de autenticação** em **<a href="Servidor_SSH" class="wikilink" title="Servidor SSH">Servidor SSH</a>**.

## Backup Incremental com rsync

O utilitário **rsync** permite **sincronizar** o conteúdo de dois diretórios, transferindo apenas as modificações. Ele não trabalha apenas comparando arquivo por arquivo, mas também comparando o conteúdo de cada um. Se apenas uma parte do arquivo foi modificada, o **rsync** transferirá apenas ela, sem copiar novamente todo o arquivo [^10].

Com o **rsync** é possível programar **backup incrementais** de grandes quantidades de dados, mantendo-se cópias atualizadas em discos rígidos externos ou em servidores remotos.

Instalação do rsync  
Utilizar o instalador de pacotes:

`sudo apt-get install rsync`

### Backup local com rsync

Informar os diretórios de origem e de destino, para onde os arquivos serão copiados:

`rsync -av /dados/ /mnt/backup/`

:\*No exemplo o diretório **/dados/** será salvo dentro diretório **/mnt/backup/**.

:\*A opção **-a** mantem as permissões dos arquivos e a opção **v** mostra o progresso da cópia na tela.

:\*O parâmetro **--delete** pode ser acrescentado para que o **rsync** delete no destino arquivos que tenham sido deletados no diretório origem.

A primeira cópia é mais demorada, uma vez que são copiados todos os arquivos, mas, a partir da segunda cópia a operação será mais rápida, transferindo apenas as mudanças.

Para recuperar os dados, basta inverter a ordem do comando:

`rsync -av /mnt/backup/dados/ /dados/`

### Backup remoto com rsync

O **rsync** também pode ser utilizado remotamente com a ajuda do **SSH**.

Para tal, caso o **rsync** seja executado por um **script de backup**, o servidor **SSH** que será utilizado para armazenar o backup deve ser acessível via uma **[chave pública de autenticação](http://wiki.foz.ifpr.edu.br/wiki/index.php/Servidor_Remoto_SSH#Gera.C3.A7.C3.A3o_de_chaves_de_autentica.C3.A7.C3.A3o_p.C3.BAblica)**, como visto no caso do **tar**.

A utilização do **rsync** remotamente poderia ser realizada com um comando do tipo [^11]:

`sudo rsync -av --rsh "ssh -l bkuser" /dados/ bkuser@endereçoServidor:/backup/`

:\*O parâmetro **--rsh "ssh -l bkuser"** orienta o **rsync** a utilizar o SSH e o **-l bkuser** indica que o servidor remoto será acessado pelo usuário bkuser.

:\*O parâmetro **-av** faz com que o **rsync** atualize os arquivos e grave novos arquivo no destino, sem remover arquivos que tenham sido deletados no diretório origem.

:\*O parâmetro **--delete** pode ser acrescentado para que o **rsync** delete no destino arquivos que tenham sido deletados no diretório origem.

:\*O parâmetro **-z** pode ser acrescentado para que o **rsync** faça compressão dos dados.

Para recuperar o backup basta inverter a ordem dos arquivos de origem e destino.

### Backup incremental com rsync

O **rsync** também pode ser utilizado para realizar **backups incrementais**, guardando um histórico dos arquivos durante um período de tempo.

O script de **backup incremental**, apresentado por [^12], combina o **rsync** com o comando **cp -al**:

cp -al  
O comando **cp** é utilizado para copiar arquivos.

- O parâmetro **-a** faz a cópia exata de um diretório, mantendo as permissões.
- O parâmetro **-l** faz que com o **cp** gere um **hard link**, ao invés de copiar os arquivos.

<!-- -->

hard links  
Os **hard links** são **atalhos** para arquivos que apontam diretamente para o **inode** do arquivo dentro do sistema de arquivos e são vistos pelo sistema operacional exatamente como os arquivos reais. Funciona como se fossem dois arquivos compartilhando para a mesma área de memória.

- Caso o arquivo seja modificado o **hard link** apontará para o arquivo modificado.
- Caso o arquivo original seja apagado, o **hard link** continuará existindo, apontando para o **inode** do arquivo (que continuará existindo).
- O arquivo somente será removido de fato quanto todos o **hard link** for removido.

<!-- -->

soft links  
**Soft links**, ou **links simbólicos**, são atalhos gerados com o comando **ln -s**.

- Diferentemente do **hard link**, no **soft link** caso o arquivo seja removido o link ficará quebrado.

#### Script para backup incremental

Exemplo apresentado em [^13]:

`rm -rf backup-6`  
`mv backup-5 backup-6`  
`mv backup-4 backup-5`  
`mv backup-3 backup-4`  
`mv backup-2 backup-3`  
`mv backup-1 backup-2`  
`cp -al backup-0 backup-1`  
`rsync -av --delete /dados/ backup-0`

Se executado diariamente o script cria um conjunto com um histórico de 7 diretórios, numerados de 0 a 6, usados para armazenar os backups:

- O diretório backup-0 tem o **backup completo** dos dados;
- A cada execução do script os diretórios de backups são **rotacionados** e o backup completo é atualizado no backup-0;
- Os diretórios de backup são na verdade **hard links** para os arquivos do backup-0, ocupando em disco o espaço que seria equivalente a um único backup.

O **script** funciona para aquivos que foram criados e deletados. Ao remover arquivos do diretório original não são removidos os **hard links** criados com o **cp -al**, assim, os backups anteriores mantem os arquivos deletados. Entretanto, caso o arquivo seja modificado, não há como recuperar ar versões anteriores do mesmo.

## Tarefa

Backup total  
Utilizar um **servidor remoto**, acessado via **SSH**, para ser utilizado para armazenar arquivos de **backup total**:

1.  Utilizar como **servidor remoto** o Ubuntu Server instalado no IFPR (192.168.71.201)
2.  O servidor remoto possui um **grupo especial** chamado **backup** e uma **conta especial** para ser acessada pelo **script de backup**, chamada **bkuser** (senha: 1234).
3.  O **diretório home** do usuário **bkuser** é um diretório especial para guardar os **arquivos de backup**, portanto, poderia ser montado em uma partição exclusiva para backup.
4.  Gerar a **chave de autenticação pública** no cliente (ssh-keygen) que vai rodar o script de backup e copiá-la para o servidor remoto (ssh-copy-id), que vai armazenar os backups .
5.  Criar na máquina cliente um **script de backup** que identifique o **proprietário do backup**, a **identificação da data** e salve diariamente os diretórios **/home** e **/dados** e que depois transfira os mesmos para o **servidor remoto**.
6.  Agendar a tarefa usando o agendamento de tarefas.

Avaliação da Tarefa  
Montar **arquivo TXT** com os seguintes itens:

- **Script** de backup;
- **ls -l** dos diretórios que terão os dados copiados;
- Impressão do **verbose** (saída do comando tar) realizado durante a execução do script.
- Comando **scp** realizado para transferir o **arquivo de backup** para o servidor remoto (pode fazer parte do script);
- **ls -l** do diretório do **servidor remoto** onde foi armazenado o **arquivo de backup**;
- Mostrar o agendamento na tabela **crontab**.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 16h49min de 12 de abril de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Administração_de_Servidores" class="wikilink" title="Categoria:Administração de Servidores">Categoria:Administração de Servidores</a>

[^1]: VALLE, O. T. Adminstração de Redes com Linux: Fundamentos e práticas, IFSC, Florianópolis, 2010.

[^2]:

[^3]:

[^4]:

[^5]: MORIMOTO, C. E. Seridores Linux: Guia prático, Sul Editores, Porto Alegre, 2013.

[^6]:

[^7]:

[^8]:

[^9]:

[^10]:

[^11]:

[^12]:

[^13]:
