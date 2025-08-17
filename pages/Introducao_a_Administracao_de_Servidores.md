# Introdução a Administração de Servidores

O objetivo da **administração de servidores** é instalar e manter **serviços de rede** aos usuários de uma instituição de forma transparente [^1].

Exemplos de **serviços de rede** que podem ser providos aos usuários em uma rede institucional:

- controle de login na rede,
- permissões de acesso aos recursos da rede,
- correio eletrônico,
- navegação na Internet,
- hospedagem de páginas Web,
- Wiki
- armazenamento de dados em disco no servidor;
- impressoras de rede;
- acesso remoto ao servidor.

## Configuração típica de uma rede institucional

<a href="Arquivo:ServicosRede.png" class="wikilink" title="Arquivo:ServicosRede.png">Arquivo:ServicosRede.png</a> [^2]

Descrição dos principais elementos da rede:

- **Roteador** de acesso a Internet, provendo serviços como:
  - ***Firewall***: barreira de proteção para bloquear acesso a conteúdo malicioso;
  - ***Proxy/Cache***: intermediário para requisições entre clientes e servidores *Web*;
  - **DMZ** (*DeMilitarized Zone*): área de rede da organização acessada externamente, localizada entre a rede interna e a Internet;
  - **Rede Privativa**: área da rede interna a instituição, não acessada diretamente da Internet;
- **Servidor de serviços externos**, localizado na **DMZ**, oferecendo serviços como:
  - Servidor **DNS**, resolvedor nomes de nomes de domínio;
  - Servidor de **Email** para os usuários da organização;
  - Servidor **Wiki** da organização e dos usuários.
  - Servidor **WWW** para páginas da organização e dos usuários;
  - Servidor **FTP** e **SSH** para os usuários poderem alterar arquivos no servidor.
- **Switch gerenciável**, permitindo a configuração de VLANs;
- **Servidor de serviços internos**, localizado na **rede privativa**, oferecendo serviços como:
  - Servidor **DHCP** para prover IP dinâmico para os computadores da rede interna;
  - Servidor de **arquivos** e **impressão**;
  - Administração de **cotas de disco** para os usuários e grupos;
  - Servidor **Samba** para compartilhamento com máquinas Windows;
  - Servidor **FTP** e **SSH** para os usuários poderem alterar arquivos no servidor.
  - Serviço **LDAP**, fornecendo controle de *login* na rede;
- **Impressora de rede**;
- **Ponto de acesso sem fio**.

Do ponto de vista do **administrador**, para prover estes serviços de forma estável e segura são necessários uma série de procedimentos, apoiados em *softwares* e equipamentos específicos.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 18h21min de 5 de julho de 2015 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Administração_de_Servidores" class="wikilink" title="Categoria:Administração de Servidores">Categoria:Administração de Servidores</a>

[^1]: VALLE, O. T. Adminstração de Redes com Linux: Fundamentos e práticas, IFSC, Florianópolis, 2010.

[^2]:
