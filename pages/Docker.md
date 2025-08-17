# Docker

**[Docker](https://www.docker.com/)** é um **Contêiner**, que é uma unidade padronizada de software que permite aos desenvolvedores isolar suas aplicações do meio no qual vai rodar.

A imagem de um contêiner Docker é leve, roda de forma independente e possui todas os requisitos necessários para rodar as aplicações, como códigos, ferramentas de sistema, bibliotecas e configurações.

<a href="Arquivo:container-what-is-container.png" class="wikilink" title="400px">400px</a> <https://www.docker.com/resources/what-container>

## Docker - Conceitos Básicos

Conceitos Básicos [^1]:

- ***Image***: Uma imagem define o sistema operacional base, pacotes, ambiente, configuração, bibliotecas e tudo aquilo que for necessário para rodar uma aplicação.
- ***Container***: É uma instância criada de uma imagem rodando com comando apropriado. De uma imagem muitas instâncias podem ser criadas.
- ***Dockerhub***: É um repositório de onde podemos baixar (ou subir) imagem.
- ***Dockerfile***: É um documento de texto que contém um conjunto de comandos de linha que um usuário pode utilizar para montar ou modificar uma imagem.

## Instalação e teste

### Instalação do Docker

Sobre Ubuntu 20.04:

- <https://docs.docker.com/install/linux/docker-ce/ubuntu/>
- <https://docs.docker.com/install/linux/linux-postinstall/>

Verificar ***status*** da instalação:

`sudo systemctl status docker`

### Hello World

`sudo docker run hello-world `

  
Quando manda rodar uma aplicação ou sistema o **Docker** verifica se há **imagem** está disponível localmente, se não, faz o ***download*** e em seguida **executa**.

**Ajuda** com comandos Docker:

`docker help`

## Imagens Docker

Listar imagens  
Imagens do Docker já baixadas na máquina hospedeira.

`docker images`

Remover imagens  
Remove imagens baixadas na máquina hospedeira.

`docker rmi imagem`

## Instalação de Linux no Docker

### Linux Alpine rodando em um contêiner

O **[Alpine Linux](https://alpinelinux.org/)** é uma distribuição **Linux** minimalista, simples e segura (**Alpine**: *Small, Simple, Secure*), ideal para dispositivos embarcados com hardware reduzido.

Várias aplicações que rodam no **Docker** utilizam o **Alpine** como sistema operacional base.

Rodar um Linux Alpine em um contêiner  

`docker run -it --name alpine1 alpine ash`

- O parâmetro --name é o nome do contêiner e **alpine** é a imagem a ser utilizada.
- A opção -i roda em modo interativo e a opção -t abre um terminal.

Colocar contêiner em **segundo plano**:

`CTRL-p CTRL-q`

**Listar** contêineres ativos:

`docker ps (-a todos os contêineres, ativos e inativos)`

**Atachar** ao terminal do contêiner:

`docker attach alpine1`

**Parar**/**reiniciar** e **Parar**/**remover** contêiner:

`docker stop alpine1`  
`docker start alpine1`

`docker stop alpine1`  
`docker rm alpine1`

### Linux Ubuntu rodando em um contêiner

**Rodar** um **Linux Ubuntu** em um contêiner:

`docker run -it --name ubuntu1 ubuntu bash`

- O parâmetro --name é o nome do contêiner e **ubuntu** é a imagem a ser utilizada.
- A opção -i roda em modo interativo e a opção -t abre um terminal.

Sai do terminal e colocar o contêiner em **segundo plano**:

`CTRL-p CTRL-q`

**Listar** contêineres ativos:

`docker ps (-a todos os contêineres, ativos e inativos)`

**Atachar** ao terminal do contêiner:

`docker attach ubuntu1`

Para rodar uma segunda **instância** do Ubuntu, pode executar:

`docker run -it --name ubuntu2 ubuntu bash`

**Parar**/**reiniciar** e **Parar**/**remover** uma instância rodando em um contêiner:

`docker stop ubuntu1`  
`docker start ubuntu1`

`docker stop ubuntu1`  
`docker rm ubuntu1`

## Servidor Web Apache em um contêiner Doccker

O **Servidor Web Apache** pode ser instalado em um contêiner **Docker** [^2]sem necessitar nenhuma instalação de software no computador hospedeiro a partir da execução do seguinte comando:

`docker run -dit --name web-server -p 8080:80 -v /home/$USER/Documentos/WebServer:/usr/local/apache2/htdocs/ httpd`

Onde:

- **docker run**: Executa o contêiner.
- **-dit**
  - -d (detached): Roda o contêiner em segundo plano;
  - -i (interactive): Roda o contêiner em modo interativo;
  - -t (tty): Roda o contêiner com um pseudo terminal TTY.
- **-name web-server**: Cria um nome para o contêiner.
- **-p 8080:80**: Redireciona a porta 80 do contêiner para a porta 8080 do seu computador. Se a porta 80 do hospedeiro estiver livre, não há necessidade de redirecionar.
- **-v /home/\$USER/Documentos/WebServer:/usr/local/apache2/htdocs/**: Redireciona o volume (diretório) /home/\$USER/Documentos/WebServer do seu computador para o diretório /usr/local/apache2/htdocs/ do contêiner. Desse modo, basta você colocar o seu código HTML nesse diretório e ele aparecerá automaticamente dentro do seu contêiner e vice versa, sem perder o seu código quando o contêiner for desligado.
- **httpd**: Nome da imagem que será utizada.

Teste do Servidor Web  

Incluir o arquivo **index.html** no diretório:

`cd`  
`cd Documentos/WebServer`  
`vim index.html`  
`:Editar o arquivo com o conteúdo a ser mostrado.`

Abrir o navegador com o endereço:

`localhost:8080`

### Configurações personalizadas para o Apache

Para personalizar as configurações do Servidor Web Apache rodando no Docker [^3], primeiro deve-se obter a configuração atual do contêiner:

`docker run --rm httpd cat /usr/local/apache2/conf/httpd.conf > my-httpd.conf`

Depois de ajustada a configuração, a mesma pode ser copiada para o contêiner utilizando um arquivo **Dockerfile** com o conteúdo:

`FROM httpd`  
`COPY ./my-httpd.conf /usr/local/apache2/conf/httpd.conf`

## Configuração de rede

O Docker usa diferentes *drivers* para conectividade em rede <https://docs.docker.com/network/>:

- ***bridge***: Configuração *default*, cria contêiner dentro da sub-rede (172.17.0.0/16): <https://docs.docker.com/network/bridge/>
  - Tutorial: <https://docs.docker.com/network/network-tutorial-standalone/>
- ***host***: Usa a configuração de rede do host diretamente: <https://docs.docker.com/network/host/>
  - Tutorial: <https://docs.docker.com/network/network-tutorial-host/>
- ***macvlan***: Atribui um MAC address ao contêiner e faz ele aparecer como uma rede física: <https://docs.docker.com/network/macvlan/>
  - Tutorial: <https://docs.docker.com/network/network-tutorial-macvlan/>
- ***none***: Desabilita rede.

### Teste de rede *bridge* com [Alpine Linux](https://alpinelinux.org/)

Referência: [^4]

Lançar duas máquinas **alpine** no **Docker**:

`docker run -it --name alpine1 alpine ash`  
`docker run -it --name alpine2 alpine ash`

Verificar os contêineres iniciados:

`docker container ls`

Inspecionar a configuração de rede dos contêineres:

`docker network inspect bridge `

  
Próximo ao topo está a sub-rede da *bridge* (172.17.0.0/16) e o *gateway* (172.17.0.1) entre o *host* do Docker e a *bridge*.

Cada alpine tem seu endereçamento IP pertencente a esta *bridge*.

Acessar o terminal de cada alpine:

`docker attach alpine1`

Verificar endereçamento IP:

`ip addr show`

Testar conectividade:

`ping 172.17.0.1 (host Docker)`  
`ping 172.17.0.2 (alpine2)`  
`ping google.com`

Parar e remover máquinas alpine:

`docker container stop alpine1 alpine2`  
`docker container rm alpine1 alpine2`

## Referências

<references />

<a href="Categoria:_Computação_em_Nuvem" class="wikilink" title="Categoria: Computação em Nuvem">Categoria: Computação em Nuvem</a> <a href="Categoria:_IoT" class="wikilink" title="Categoria: IoT">Categoria: IoT</a>

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 13h48min de 3 de abril de 2020 (-03)

[^1]: [Abdallah Jarwan. MQTT Application using Docker, Medium, Jun 30, 2019.](https://medium.com/@abdallahjarwan/mqtt-application-using-docker-6e61d7a3642d)

[^2]: <https://hub.docker.com/_/httpd>

[^3]:

[^4]: <https://docs.docker.com/network/network-tutorial-standalone/>
