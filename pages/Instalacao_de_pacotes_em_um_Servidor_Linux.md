# Instalação de pacotes no Ubuntu Server

## apt

**Sistema de gerenciamento de pacotes** que trabalha baixando pacotes de repositórios oficiais do **Ubuntu**.

A seguir estão descritas as principais utilizações do **apt-get** [^1]:

`sudo apt update`

Atualiza a lista de pacotes disponíveis em cada servidor. Deve ser executado regularmente, particularmente antes de fazer cada nova instalação de pacotes.

`sudo apt install apache2`

Exemplo de comando para instalação de pacote, no caso o **servidor Web apache**. O apt-get instala automaticamente todas as dependências do pacote, pedindo confirmação.

Atualização de pacote  
Para atualizar um pacote rode em sequência os comandos:

`sudo apt update`  
`sudo apt install apache2`

Para atualizar todos os pacotes do sistema de uma vez, execute:

`sudo apt update`  
`sudo apt upgrade`

Remoção de pacote  

`sudo apt remove apache2`

  
Este comando remove o pacote e preserva os arquivos de configuração, que podem ser aproveitados caso se queira reinstalar o pacote.

`sudo apt remove --purge apache2`

  
Remove o pacote e os arquivos de contiguração.

<!-- -->

Reinstalação de um pacote  

`sudo apt install --reinstall apache2`

Arquivos de configuração do apt-get  
O principal arquivo de configuração do **apt-get** é o arquivo:

`/etc/apt/sources.list`

  
Este arquivo apresenta a lista dos ***mirrors*** onde ficam hospedados os repositórios de pacotes do Ubuntu.

## dpkg

O **dpkg** complementa o **apt-get**, permitindo instalar pacotes **.deb** baixados manualmente [^2].

Instalação de pacote .deb  

`sudo dpkg -i pacote.deb`

  
ou, para instalar vários pacotes dentro de um diretório:

`sudo dpkg -i *.deb`  

O **dpkg** instala apenas o pacote indicado, não instala dependências. Para resolver isto, pode usar o comando:

`sudo apt -f install`

  
este comando resolve as dependências e corrige problemas que possam ter havido na instalação.

Se não conseguir resolver os problemas, pode-se experimentar o comando:

`sudo apt -f remove`

  
este comando remove os pacotes com problema.

## Gerenciador de downloads

Comando wget  
Permite gerenciar **downloads** via linha de comando, muito útil quando se precisa instalar um pacote no servidor via SSH.

Exemplo: Baixar VirtualBox para o Ubuntu 18.04 (Bionic Beaver), 64 bits, via terminal

`wget -c `[`http://download.virtualbox.org/virtualbox/5.2.10/virtualbox-5.2_5.2.10-122088~Ubuntu~bionic_amd64.deb`](http://download.virtualbox.org/virtualbox/5.2.10/virtualbox-5.2_5.2.10-122088~Ubuntu~bionic_amd64.deb)

  
O parâmetro -c faz com que ele continue o download caso seja interrompido.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 11h10min de 26 de julho de 2017 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Administração_de_Servidores" class="wikilink" title="Categoria:Administração de Servidores">Categoria:Administração de Servidores</a>

[^1]: MORIMOTO, C. E. Seridores Linux: Guia prático, Sul Editores, Porto Alegre, 2013.

[^2]:
