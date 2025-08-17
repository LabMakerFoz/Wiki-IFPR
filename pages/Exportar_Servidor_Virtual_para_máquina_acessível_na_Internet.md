# Exportar Servidor Virtual para máquina acessível na Internet

Os **Servidores Virtuais Ubuntu** serão exportados para uma **máquina virtual** rodando em um **servidor hospedeiro** acessível da rede interna do Campus e pela Internet, com as seguintes características:

- **Endereço IP público** do Servidor: **200.17.101.X** (A definir)
- **Endereço IP privado** do Servidor: **192.168.40.10**

<a href="Arquivo:ServidoresVirtuais.png" class="wikilink" title="Arquivo:ServidoresVirtuais.png">Arquivo:ServidoresVirtuais.png</a>

Acesso aos Servidores Virtuais  

- **Laboratórios de Informática**:
  - Acesso direto via **SSH** utilizando o **IP privado** do **Servidor Virtual**.
- **Internet**:
  - Acesso via **SSH** ao **Servidor Hospedeiro** utilizando o **IP público** e uma **conta** de usuário.
  - Uma vez acessado o servidor hospedeiro os **Servidores Virtuais** poderão ser acessados via **IP privado** da rede interna.
  - Contas de **usuário** e **senha**: Cada **aluno** da turma terá uma conta no servidor, identificada pelo **primeiro nome** (alessandre, cesar, christian, etc).

### Endereços IP dos servidores de cada equipe:

- 192.168.40.10: Servidor Principal
- 192.168.40.11: Victor & Luis
- 192.168.40.12: Kaio & William
- 192.168.40.13: Maickel & Leo
- 192.168.40.14: Joabe & Tiago
- 192.168.40.15: VitorMatheus & Pablo
- 192.168.40.16: Pedro & Roger
- 192.168.40.17: Guilherme & Henrique
- 192.168.40.18: Cesar & Ederson
- 192.168.40.19: Gustavo & Rodrigo
- 192.168.40.20: Lucas & Christian
- 192.168.40.21: Alessandre
- 192.168.40.22: Evandro

IP Alias utilizados nos Servidores Web  

- 192.168.40.23:
- 192.168.40.24: Gustavo & Rodrigo
- 192.168.40.25: VitorMatheus & Pablo
- 192.168.40.26: Lucas & Christian
- 192.168.40.27: Joabe & Tiago
- 192.168.40.28:
- 192.168.40.29:
- 192.168.40.30: Evandro

## Roteiro para exportar servidor Ubuntu para máquina virtual

Configuração de IP estático para o Servidor Virtual  
Utilizar o IP fornecido para o respectivo servidor.

`sudo vim /etc/network/interfaces`

`# The loopback network interface`  
`auto lo`  
`iface lo inet loopback`

`# The primary network interface`  
`auto enp0s3`  
`iface enp0s3 inet static`  
`      address 192.168.40.XX`  
`      netmask 255.255.252.0`  
`      gateway 192.168.40.1`  

Configurações do Virtual Box  
Devem ser realizadas com o Servidor Virtual **desligado**:

1.  Na guia **Geral** escrever o **Nome** do servidor com o seguinte padrão: **TADS-XX**, onde XX é o último byte do endereço IP do respectivo **Servidor Virtual**;
2.  Na guia **Sistema**, deixar selecionado somente **Disco Rígido** na ordem de boot;
3.  Na guia **Monitor**, deixar Memória de Vídeo com 12MB;
4.  Na guia **Áudio**, desabilite o áudio;
5.  Na guia **Rede**, habilitar **Placa em Modo Bridge**;
6.  Na guia **USB**, desabilite o USB.

Exportar Servidor Virtual  
A partir da guia **Arquivo** exportar o Servidor Virtual:

- A exportação vai gerar um arquivo no diretório **home** com o nome **TADS-XX.ova**.

<!-- -->

Enviar o Servidor Virtual ao Servidor Hospedeiro via SCP  
Utilize o comando:

`scp TADS-XX.ova ifpr@192.168.40.10:.`  
`senha: 2017@foz`

Importar o Servidor Virtual  
Conectar-se via **SSH** ao **Servidor Hospedeiro** e executar o seguinte comando (substituir XX pelo último byte do endereço IP do Servidor Virtual):

` VBoxManage import TADS-XX.ova --vsys 0 --vmname “TADS-XX” --unit 10 --disk /vms/TADS-XX/TADS-XX.vdi --unit 9 --ignore`

Ativar o Servidor Virtual acessando o VirtualBox em modo gráfico via SSH  
Acessar novamente o **Servidor Hospedeiro** com o comando:

`ssh -X -C ifpr@192.168.40.10`

  
com isto o X11 vai exportar qualquer aplicativo gráfico que for executado.

Chamar o **VirtualBox** e ativar o **Servidor Virtual**:

`virtualbox`

Depois de instalados os **Servidores Virtuais** serão programados para serem ativados automaticamente no boot do **Servidor Hospedeiro**.

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 09h35min de 17 de agosto de 2017 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Administração_de_Servidores" class="wikilink" title="Categoria:Administração de Servidores">Categoria:Administração de Servidores</a>
