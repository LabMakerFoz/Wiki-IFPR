# Instalação do Ubuntu Server no Virtual Box

Esta seção mostra os passos para **instalar** um **Servidor Linux** em uma **máquina virtual** do **VirtualBox**.

## Download do Ubuntu Server

Download  
O *download* do **Ubuntu Server 22.04** pode ser obtido diretamente do site do Ubuntu:

[`https://ubuntu.com/download/server`](https://ubuntu.com/download/server)

Salvar o arquivo **ISO** em um **pendrive** (ou CD-ROM).

O processo de instalação do **Ubuntu server** é similar a versão *desktop*, contudo, tudo é realizado via **terminal de comandos**.

## Passos para criação da Máquina Virtual no VirtualBox

1.  Abrir o VirtualBox e na guia **Máquina** escolhar **Novo**;
2.  Definir o **nome**, o **tipo** e a **versão** do sistema operacional e selecionar o local da **Imagem ISO**;
3.  Escolher o **tamanho da memória** (RAM) e do **disco rígido** virtual no padrão sugerido;
4.  Na **configuração** da máquina virtual no **VirtualBox**, estabelacer a configuração de rede do **Servidor Linux** como **Placa em modo Bridge**, para que o servidor fica na mesma rede local dos demais computadores do laboratório;

### Instalação do sistema operacional **Ubuntu Server**

Passos para instalação do  
<https://tutorials.ubuntu.com/tutorial/tutorial-install-ubuntu-server>

## Configurações para Servidor com IP fixo

Instalar pacotes para acesso a ferramentas de rede:

`sudo apt update`  
`sudo apt install net-tools`

### Netplan

O Ubuntu utiliza o utilitário de configuração de rede em linha de comandos **Netplan**, o qual opera por meio do emprego de **arquivos YAML** para descrição das interfaces de rede. Esta ferramenta substitui o tradicional arquivo /etc/network/interfaces.

Mudar para o diretório:

`/etc/netplan`

Fazer uma cópia backup do arquivo original

`sudo cp 00-installer-config.yaml 00-installer-config.yaml.original`

Editar o arquivo

`sudo nano 00-installer-config.yaml`

Configure o arquivo como segue:

`network:`  
`   ethernets:`  
`      enp0s3:`  
`         dhcp4: no`  
`         addresses:`  
`          - 192.168.71.2XX/23`  
`         routes:`  
`          - to: default`  
`            via: 192.168.70.1`  
`         nameservers:`  
`            addresses: [8.8.8.8]`  
`   version: 2`

Teste a sintaxe do arquivo:

`sudo netplan try --state /etc/netplan`

Aplicar a configuração:

`sudo netplan apply`

## Instalação de outros aplicativos

Instalação do servidor Web apache  

`sudo apt install apache2`

- Testar funcionamento do servidor a partir de um navegador na máquina hospedeira.

Instalação no navegador lynx  

`sudo apt install lynx`

- Testar navegador **lynx**.

Instalar aplicativos de rede  

`sudo apt install traceroute`  
`sudo apt install tcpdump`  
`sudo apt install wireshark`

- Verificar configuração completa de rede utilizando os aplicativos **ifconfig**, **ping**, **traceroute**, **route**.
- Verifique e anote os seguintes parâmetros:
  - Endereço IP
  - Máscara de rede
  - Endereço de *broadcast*
  - Roteador padrão
  - Roteador de borda da rede do Campus

## Resolvendo problemas com monitor e teclado

Teclado ABNT Brasil  
Caso tenha instalado versão em inglês do teclado, o mesmo pode ser ajustado com o comando:

`setxkbmap -model abnt2 -layout br`

Monitor invertido  
Caso o monitor (principalmente de notebooks) fique invertido, o mesmo pode ser ajustado com o comando:

`xrandr -o normal`

## Aplicativos Gráficos

Executar aplicativos gráficos via SSH  
É possível executar aplicativos gráficos via SSH fazendo alguns ajustes no servidor:

`vim /etc/ssh/sshd_config `

  
Altere as linhas no arquivo sshd_config:

`Protocol 2`  
`PermitRootLogin without-password`  
`X11Forwarding yes`

  
Reinicie o outserviço:

`/etc/init.d/ssh restart `

  
Conecte-se ao servidor via SSH usando:

`ssh -X -C user@server`

  
Chame o aplicativo normalmente.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 11h10min de 26 de julho de 2017 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Administração_de_Servidores" class="wikilink" title="Categoria:Administração de Servidores">Categoria:Administração de Servidores</a>
