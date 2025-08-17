# Software Alternativo para Lego Mindstorms

Uma alternativa de software para programas os módulos Lego NXT é a linguagem **Enchanting**, a qual é uma adaptação da linguagem **Scratch**. Para funcionar, o Enchanting necessita que o *firmware* original do NXT seja substituído pelo sistema **LeJOS** (*Lego Java Operating System*).

## Enchanting

[Site do Enchanting](https://launchpad.net/enchanting)  
Enchanting cards: <a href="Mídia:EnchantingCards.pdf" class="wikilink" title=" Enchanting Cards"> Enchanting Cards</a>

### Instalação do Enchanting no Ubuntu

Baixar o arquivo .deb do Enchanting: [Download Enchanting](http://enchanting.robotclub.ab.ca/tiki-index.php#Download_Enchanting).

Abrir um terminal e ir para o diretório onde está o arquivo.

Executar os comandos:

`sudo dpkg --install enchanting_0.2.4.3_all.deb `  
`sudo apt-get --fix-broken install`

### Instalação do Lejos no Ubuntu 13.10

Guia escrito pelo **Prof. Fernando Nakayama de Queiroz** para utilização dos alunos do IFPR Câmpus Foz do Iguaçu

Comandos Iniciais

`sudo apt-get update`  
`sudo apt-get install libusb-dev libbluetooth-dev ant`

Obtendo o Lejos <http://sourceforge.net/projects/lejos/files/lejos-NXJ/>

Versão utilizada: 0.9.1beta Extraindo os arquivos

`tar -zxvf lejos_NXJ_0_9_1beta-3.tar.gz`

Tornando o programa executável:

`cd /diretório_de_instalação/bin`

`chmod +x nxj*`

Compilando o driver USB

`cd /diretório_de_instalação/build`

`ant`

Configurando as variáveis de ambiente

`sudo nano /etc/environment`

Edite o arquivo da seguinte forma:

`PATH="/diretório_de_instalação/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games"`

Criar as regras para o lego em:

`sudo nano /etc/udev/rules.d/70-lego.rules`

O conteúdo do arquivo deve ser o seguinte:

`BUS=="usb", SYSFS{idVendor}=="03eb", GROUP="lego", MODE="0660"`  
`BUS=="usb", SYSFS{idVendor}=="0694", GROUP="lego", MODE="0660"`

Criar grupo lego:

`sudo groupadd lego`

Adicionar seu usuário ao grupo lego:

`sudo gpasswd -a username lego`

### Fazendo o upload do Lejos para o NXT

Dentro do diretório aonde foi instalado (descompactado e feito o build com o comando ant), existe um diretório /bin dentro deste diretório estarão todos os executáveis para o programa. Inicialmente seria interessante utilizar o nxjbrowse para identificar possíveis erros de instalação.

`./nxjbrowse`

se a instalação foi feita corretamente você deve ver os dispositivos conectados.

Depois é necessário fazer o flash do novo firmware no NXT, que é realizado em dois passos  

1.  Colocar o NXT em modo de atualização. Para tal é necessário pressionar um botao no equipamento, situado na parte de trás escondido no canto superior esquerdo. <a href="Arquivo:nxt.png" class="wikilink" title="thumb">thumb</a>
2.  Executar no modo console o comando:

`./nxjflash`

Depois de dado o comando o percentual de instalação será mostrado. Se tudo correr bem o NXT já irá reiniciar com o novo sistema operacional.

------------------------------------------------------------------------

<a href="Categoria:Robótica" class="wikilink" title="Categoria:Robótica">Categoria:Robótica</a>
