# Cotas em disco

O sistema de **cotas em disco** permite o controle do espaço de armazenamento em disco pelos usuários e grupos.

No Linux a implementação de cotas em disco é realizada por **partições**, na qual todos os arquivos pertencentes a determinado usuário/grupo são contabilizados em sua cota, independente do diretório onde está inserido [^1].

Para uma melhor eficiência na administração das quotas de disco o ideal é que os diretórios para os quais se deseja atribuir quotas sejam montados em partições separadas do restante do sistema.

Num sistema Linux os locais onde é importante implementar cotas são diretório **/home**, que contém os arquivos pessoais dos usuários, o diretório **/var/www** que num servidor Web armazena as páginas Web dos usuários e **diretório de dados** compartilhados utilizados por usuários e grupos.

Por exemplo, se se deseja atribuir quotas para os diretórios /home, para o diretório /var/www e para um diretório compartilhado /dados, o ideal é montá-los em dispositivos separados:

`#`<file system>` `<mount point>  
` /dev/hda7     /home`  
` /dev/had9     /var/www`  
` /dev/hda4     /dados`

  
Onde os diretórios /home. /var/www e /dados foram montados em dispositivos físicos separados.

## Instalação e configuração do sistema de quotas

Instalação  
Para **instalação de cotas de disco** no Ubuntu usa-se o comando:

`sudo apt-get install quota`

### Atribuição de cotas de disco as partições

Em seguida deve-se informar ao sistema de arquivo em quais partições deseja-se implementar quotas de disco. Para isto, deve-se editar o arquivo **/etc/fstab** e inserir no final da quarta coluna, separado por vírgula, as diretivas **usrquota** e/ou **grpquota**, para inserir cotas para usuários, grupos ou ambas [^2].

Exemplo 1  
Montagem em partição única do diretório **/** (Máquina Virtual no **Multipass**):

`# /etc/fstab: static file system information.`  
`# `<file system>`         `<mount point>` `<type>` `<options>`  `<dump>` `<pass>  
`LABEL=cloudimg-rootfs   /             ext4   defaults,usrquota,grpquota        0 1`  
`LABEL=UEFI              /boot/efi     vfat   umask=0077      0 1`

Exemplo 2  
Montagem em partição única do diretório **/** (Máquina Virtual no **VirtualBox**):

`# /etc/fstab: static file system information.`  
`#`  
`# `<file system>`                       `<mount point>` `<type>` `<options>`  `<dump>` `<pass>  
`UUID=aac578da-2bbe-43e7-be09-6cd1c0e1ac2c /         ext4 errors=remount-ro,usrquota,grpquota 0 1`  
`UUID=A31B-8BC5                            /boot/efi vfat umask=0077        0 1`  
`/swapfile                                 none      swap sw                0 0`

Caso as **cotas de disco** forem aplicadas a **partição / (raiz)**, o sistema deve ser reiniciado.

### Inicialização do sistema de cotas

O sistema é iniciado com o comando:

`quotacheck -augvmf`

  
Ests comando cria em cada diretório para os quais foram aplicados cotas de disco os arquivos **aquota.user** e **aquota.group**. Estes arquivos contém uma relação entre usuários/grupos e o espaço de disco utilizados pelos mesmos [^3].

<!-- -->

Ativação do sistema de cotas  
Para ativar o sistema de cotas usa-se o comando:

`quotaon -augv`

  
Para desativá-lo:

`quotaoff -augv`

### Manipulação de cotas

O espaço a ser atribuído a cada usuário ou grupo deve ser editado através dos comandos:

`edquota usuário`

  
ou

`edquota -g grupo`

  
O arquivo manipulado pelo editor de cotas apresenta o seguinte formato:

`Quotas de disco para user `<usuário>` (uid 1002):`  
` Sistema de arquivos    blocos   permitido físico inodes permitido físico`  
` /dev/hda7              32       0         0      9      0         0`

  
Onde:

- Primeira linha tem as informações do usuário e seu UID.
- Na sequência seguem linhas com informações sobre os dispositivos com cotas habilitadas:
  - **blocos**: informa o espaço em disco em uso pelo usuário em blocos de 1KBytes;
  - **permitido** (*soft*): cota em disco do usuário;
  - **físico** (*hard*): limite máximo a ser utilizado pelo usuário temporariamente (*grace period*);
  - **inode**: quantidade de arquivos e diretórios em nome do usuário;
  - **permitido** (*soft*): quantidade permitida de arquivos e diretórios em nomo do usuário;
  - **físico**: (*hard*) limite máximo de arquivos e diretórios a ser utilizado pelo usuário temporariamente.

Cotas permitido e físico 0 (zero) significa que não há limites especificados.

<!-- -->

inode  
Um [**inodes**](https://www.vivaolinux.com.br/artigo/Voce-sabe-o-que-e-INODE) é uma estrutura responsável por conter informações básicas sobre seus arquivos e pastas, como permissões de acesso, identificação dos donos dos arquivos, data e hora do último acesso e alterações, tamanho e o mais importante, os famosos ponteiros para o arquivo em si.

Para alterar o **tempo de uso temporário** do limite físico (*grace period*), usa-se o comando:

`edquota -t`

Para atribuir cotas de disco a vários usuários, pode-se utilizar um **usuário** como **padrão** e replicar a mesma cota para os demais usuários com o comando:

`edquota -p padrão usuário`

### Verificação de cotas

Para se verificar a cota de algum usuário ou rupo (-g) usa-se o comando:

`quota usuário`

  
ou

`quota -g grupo`

Para visualizar um relatório completo das cotas, usa-se o comando **repquota** seguido pelo diretório onde a cota foi aplicada.

`repquota /`

  
No comando acima, assume-se que as cotas foram aplicadas ao diretório raiz.

## Tarefa

Criar **cotas em disco** para usuários e grupos para controle do espaço de armazenamento dos diretórios /home e /dados. O ideal seria que estes diretórios tivessem sido montados em partições separadas. Como não foi montado desta forma, vamos aplicar o sistema de quotas a **partição / (raiz)** do sistema.

- Atribuir quota de 1MB por usuário e 5MB por grupo.
- Atribuir 500 inodes por usuário e 500 inodes por grupo.
- Testar o funcionamento do sistema de quotas.

Gerar arquivos txt com os testes do funcionamento das cotas.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 18h25min de 29 de março de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Administração_de_Servidores" class="wikilink" title="Categoria:Administração de Servidores">Categoria:Administração de Servidores</a>

[^1]: VALLE, O. T. Adminstração de Redes com Linux: Fundamentos e práticas, IFSC, Florianópolis, 2010.

[^2]:

[^3]:
