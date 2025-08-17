# Administração de Usuários e Grupos

Um **usuário** Linux é uma entidade que possui um **login**, uma **senha** e um **número de identificação**. Estas informações permitem ao Linux **controlar o acesso** do usuário ao sistema e definir, a partir de suas **permissões de acesso**, o que ele pode fazer [^1].

Um **grupo** é um **conjunto de usuários**, e também possui **nome** e um **número de identificação**.

Os grupos devem ser formados a partir de usuários afins, como por exemplo em uma escola, o grupo professores, o grupo técnicos e o grupo alunos. A criação dos grupos deve refletir a estrutura organizacional da instituição. Os grupos compartilham recursos e permissões, como por exemplo, acesso a determinados arquivos, impressoras, etc.

Cada usuário deve pertencer a pelo menos um grupo, que é seu grupo primário. Outros grupos podem ser associados e serão seus grupos secundários.

### Criação de contas de usuários e grupos

Criar um grupo  

`groupadd nome_grupo`

Remover um grupo  

`groupdel nome_grupo`

Criar um usuário e incluí-lo em um grupo primário  

`adduser --ingroup grupo_primario nome_login`

Se não utilizar o parâmetro **--ingroup**, o Linux cria um grupo com o mesmo nome do usuário.

`adduser nome_login`

Para adicionar um usuário a um **grupo secundário**, usa-se o comando:

`adduser usuário grupo_secundário`

Para alterar a senha do usuário, usa-se o comando:

`passwd login`

Remover um usuário  

`userdel login`

Parâmetro adicional:

- **--remove-home** apaga o diretório /home do usuário e todo seu conteúdo.

### Arquivos de cadastro e definição das contas dos usuários do sistema

As contas de **usuários**, **grupos** e **senhas** ficam armazenadas nos arquivos:

`/etc/passwd`  
`/etc/group`  
`/etc/shadow`

Arquivo /etc/passwd  
Neste arquivo estão cadastrados **todos os usuários** do sistema. Contas com **UID** (identificação de usuário) e **GID** (identificação de grupo) menor que 500 são contas do sistema. O primeiro usuário e grupo cadastrado tem o número 1000. Este arquivo deve ter **permissão de leitura** por **todos os usuários**.

Exemplo de linha do arquivo **/etc/passwd**, com cada campo separado por ":"

`login:x:1000:1000:Nome Completo,,,:/home/login:/bin/bash`

Descrição dos campos:

- login: Login do usuário;
- x:Este campo continha a senha do usuário. Nos sistemas modernos as senhas são criptografadas e ficam armazenadas no arquivo /etc/shadow;
- 1000: UID
- 1000: GID
- Nome completo e outras informações separadas por vírgula;
- /home/login: Diretório home do usuário;
- /bin/bash: Shell do usuário.

Arquivo /etc/group  
Contem a relação dos **grupos** do sistema. Cada linha do arquivo contem o nome do grupo, a senha, o GID (identificação de grupo) e a lista de usuários do grupo.

<!-- -->

Arquivo /etc/shadow  
Contém as **senhas criptografadas** dos usuários . Este arquivo é de uso exclusivo do administrador, somente ele consegue visualizar, editar ou copiar este arquivo.

<!-- -->

Arquivo /etc/login.defs  
Contem diretivas e padrões utilizados na criação das contas de usuários, incluindo número de caracteres para senhas, número de dias para que as senhas expirem, UID e GIU mínimo e máximo, criação ou não de diretório /home, etc.

<!-- -->

Arquivo /etc/default/useradd  
Também contem diretivas para criação das contas de usuários, incluindo a definição do grupo primário, o local do diretório /home, o shell padrão do usuário, etc.

### Pesquisa nas bases de dados passwd e group

O comando **getent** auxilia a pesquisar em **arquivos de texto**, chamados **bases de dados** do sistema, entre eles o **passwd** e o **group** [^2].

  
Exemplos de uso:

`getent passwd`

`root:x:0:0:root:/root:/bin/bash`  
`daemon:x:1:1:daemon:/usr/sbin:/bin/sh`  
`bin:x:2:2:bin:/bin:/bin/sh`  
`sys:x:3:3:sys:/dev:/bin/sh`  
`sync:x:4:65534:sync:/bin:/bin/sync`  
`games:x:5:60:games:/usr/games:/bin/sh`  
`man:x:6:12:man:/var/cache/man:/bin/sh`  
`lp:x:7:7:lp:/var/spool/lpd:/bin/sh`  
`mail:x:8:8:mail:/var/mail:/bin/sh`

`getent passwd man`

`man:x:6:12:man:/var/cache/man:/bin/sh`

## Tarefa

Criar contas de **usuário** e **grupo** para no mínimo 6 alunos e 4 professores da turma:

- **Grupos primários**: Alunos e Professores
- **Grupos secundários**: Arduino, PHP, Mobile, Java
  - Verificar com a turma os grupos de interesse para formar os grupos secundários.

  
Cada usuário **deve** pertencer a **um grupo primário** e **pode** pertencer a **um ou mais grupos secundários**.

Requisitos para as contas de usuário e grupo:

- Estabelecer **regramento** para os nomes de login
  - Por exemplo: nome: João Paulo de Souza -\> login: jsouza
- Cadastrar cada usuário incluindo as seguintes informações: Nome Completo, Telefone, email.
- Cadastrar **senhas** (1234) e solicitar para os usuários fazerem a troca e testar a conta através **ssh**.

Exemplo:

`groupadd alunos`  
`groupadd professores`  
`groupadd arduino`  
`adduser --ingroup alunos jsouza`  
`adduser jsouza arduino`

  
No exemploServidor SSH foram criados três **grupos** alunos, arofessores e arduino; em seguida foi criado o **usuário** jsouza no **grupo primário** alunos; depois o usuário jsouza foi incluído no **grupo secundário** arduino.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 09h22min de 15 de março de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Administração_de_Servidores" class="wikilink" title="Categoria:Administração de Servidores">Categoria:Administração de Servidores</a>

[^1]: VALLE, O. T. Adminstração de Redes com Linux: Fundamentos e práticas, IFSC, Florianópolis, 2010.

[^2]: <https://en.wikipedia.org/wiki/Getent>
