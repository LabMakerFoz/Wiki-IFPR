# Kathará

O **[Kathará](https://www.kathara.org/)** é um ambiente para **emulação** de **redes de computadores** virtuais, baseado no uso de contêineres **[Docker](https://www.docker.com/)**.

A página **[Wiki do Kathará](https://github.com/KatharaFramework/Kathara/wiki)** apresenta vários exemplos ilustrativos, alguns dos quais descritos na sequência.

## Instalação do Kathara

O **Kathara** depende do **<a href="Docker" class="wikilink" title="Docker">Docker</a>** para rodar, portanto, instalar o Docker primeiro.

Instalação no **Ubuntu**[^1]:

- Adicionar a chave pública para obter o Kathará:

`sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 21805A48E6CBBA6B991ABE76646193862B759810`

- Adicionar o repositório do Kathará:

`sudo add-apt-repository ppa:katharaframework/kathara`

- Atualizar o acesso aos repositórios:

`sudo apt update`

- Instalar o Kathará:

`sudo apt install kathara`

## Introdução ao Kathará

Referência: [^2].

O **Kathará** é um ambiente para **emulação** de **redes de computadores** através da criação de **contêineres** **Docker** em uma máquina hospedeira.

Cada contêiner pode ser configurado como um **dispositivo de rede** específico e pode desempenhar diferentes papeis, como ***host**'',**roteador**,***switch**'' etc.

### Dispositivos de rede

Cada **dispositivo de rede** emulado possui um as seguintes características:

- **console**,
- **memória**,
- **sistema de arquivos**,
- **interfaces de rede**.

Através das **interfaces de rede** os dispositivos são conectados a um **domínio de colisão virtual** e podem se comunicar com outros dispositivos.

### Comandos

O **Kathará** apresenta três tipos de **comandos**, utilizados em um terminal:

- **v-commands**: permitem criar e configurar um dispositivo via terminal.
- **l-commands**: permite criar um ambiente com vários dispositivos conectados em rede através de um script.
- **global-commands**: comandos de gerenciamento global.

Comando para **checar** se ambiente Kathará está operando corretamente:

`kathara check`

Ver demais comandos em:

`man kathara`

### Dicas para copiar/colar comandos no terminal

- Selecionar comando desejado na Wiki;
- Clicar no terminal a rodinha do mouse para colar.

### Compartilhamento de arquivos

O Kathará permite o **compartilhamento de arquivos** entre dispositivos e o hospedeiro.

Há duas maneiras de compartilhar arquivos entre dispositivos e o hospedeiro:

- O diretório **/shared** em um dispositivo aponta para o diretório /shared de todos os dispositivos do laboratório (habilitado por *default*).
- O diretório **/hosthome** em um dispositivo aponta para o diretório /home no hospedeiro (desabilitado por *default*).

Para modificar os compartilhamentos utilizar o comando:

`kathara settings`

:\*Habilitar o compartilhamento do diretório **/hosthome**.

## Rede com dispositivos criados manualmente

Exemplo de **rede básica** com dispositivos criados manualmente via terminal a partir de comandos **v-commands** [^3]:

<a href="Arquivo:Netkit-lab1.png" class="wikilink" title="Arquivo:Netkit-lab1.png">Arquivo:Netkit-lab1.png</a>

### Procedimentos práticos

- Comandos para **iniciar os dispositivos** pc1 e pc2, ambos com a interface eth0 conectada ao domínio de colisão A:

`kathara vstart --name pc1 --eth 0:A`  
`kathara vstart --name pc2 --eth 0:A`

  
  
Cada comando ativará a console do respectivo dispositivo.

- **Configuração das interfaces de rede** dos dispositivos com **ifconfig**:

  
  
Acessar a console de cada dispositivo para configurar as interfaces de rede:

`ifconfig eth0 192.168.0.1/24 up`

:\*pc2:

`ifconfig eth0 192.168.0.2/24 up`

  
  
Verificar as configurações em cada dispositivo:

`ifconfig`

- **Teste de conectividade** com **ping**:

:\*pc1 -\> pc2:

`ping 192.168.0.2`

- **Captura de pacotes** com **tcpdump**:

:\*pc2:

`tcpdump icmp`

  
  
Captura pacotes **icmp** (ping) na interface eth0 (default).

- Visualizar a captura de forma gráfica com **wireshark** no hospedeiro:

:\*Ativar o compartilhamento do /hosthome com o comando:

`kathara settings`

:\*Capturar no pc2 pacote e gravar saída em arquivo:

`tcpdump icmp -w /hosthome/cap1.ncap`

:\*Abrir arquivo no hospedeiro com wireshark.

- **Limpar todos os dispositivos e domínios de colisão**:

`kathara wipe`

## Rede criada com arquivos de configuração

O Kathará permite a construção de **estruturas de rede** com diferentes tipos de **dispositivos**, como ***hosts***, **roteadores** e outros, os quais são configurados por meio de **arquivos de configuração** e **diretórios**.

Exemplo de **rede básica** construída com comandos **Kathará l-commands** [^4]:

<a href="Arquivo:Netkit-lab1.png" class="wikilink" title="Arquivo:Netkit-lab1.png">Arquivo:Netkit-lab1.png</a>

Hierarquia de **arquivos** e **diretórios** para configuração do laboratório  

`lab.conf      #Configura a estrutura de rede`  
`pc1.startup   #Configura dispositivo pc1`  
`pc2.startup   #Configura dispositivo pc2`  
`pc1/          #Diretório com arquivos de configuração para pc1`  
`pc2/          #Diretório com arquivos de configuração para pc2`

Conteúdo dos arquivos  

`lab.conf      `  
`  pc1[0]=A`  
`  pc2[0]=A`

  
Configura rede simples com domínio de colisão A

`pc1.startup   `  
`  ifconfig eth0 192.168.0.1/24 up`

  
Configura pc1 e seu endereço IP

`pc2.startup   `  
`  ifconfig eth0 192.168.0.2/24 up`

  
Configura pc2 e seu endereço IP

`pc1/          `  
`pc2/`

  
Diretórios que permitem passar arquivos de configuração para a estrutura de diretórios dos dispositivos.

<!-- -->

Comando para iniciar e parar rede do laboratório  

`kathara lstart`

  
Inicia rede

`kathara lclean`

  
Pára rede

`kathara wipe`

  
Limpar todos os dispositivos e domínios de colisão

## Arquivos Kathara com exemplos prontos

[Exemplos prontos](https://drive.google.com/drive/folders/1u7MdyU2C48c-DuyVy_dYRYpPsn9o3W21?usp=drive_link)

## Outros exemplos de laboratórios

- **<a href="Kathara:_Protocolo_ARP" class="wikilink" title="Protocolo ARP">Protocolo ARP</a>**
- **<a href="Kathara:_Servidor_Web" class="wikilink" title="Servidor Web">Servidor Web</a>**
- **<a href="Kathara:_Roteamento" class="wikilink" title="Roteamento Estático e Dinâmico">Roteamento Estático e Dinâmico</a>**

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 17h07min de 25 de janeiro de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: <https://github.com/KatharaFramework/Kathara/wiki/Linux>

[^2]: <https://github.com/KatharaFramework/Kathara-Labs/blob/master/001-kathara-introduction.pdf>

[^3]: <https://github.com/KatharaFramework/Kathara-Labs/blob/master/Basic%20Topics/Two%20hosts/003-kathara-lab_two-hosts.pdf>

[^4]: <https://github.com/KatharaFramework/Kathara-Labs/blob/master/Basic%20Topics/Static%20routing/004-kathara-lab_static-routing.pdf>
