# Laboratório: NetKit DNS

O **servidor DNS** vem instalado no ambiente do **[Netkit2](http://wiki.sj.ifsc.edu.br/wiki/index.php/Netkit2)**, correspondendo ao aplicativo **bind** disponível para distribuições Linux.

## Ambiente para testes do serviço DNS

Vamos montar no Netkit2 um ambiente para testes do serviço DNS, conforme a figura a seguir [^1]:

<a href="Arquivo:ServidorDNS.png" class="wikilink" title="Arquivo:ServidorDNS.png">Arquivo:ServidorDNS.png</a>

Todas as máquinas estarão na mesma **rede local**. A máquina 192.168.100.101 funcionará como **servidor DNS secundário** para os demais servidores. No **servidor DNS secundário** serão criadas **zonas escravas** que receberão cópias das zonas dos outros **servidores DNS primários**, de forma que o mesmo também poderá resolver nomes vinculados ao domínio demais servidores.

## Configuração do servidor DNS secundário

O servidor DNS secundário será configurado com uma zona tipo **master** e outras zonas tipo **slave**, as quais receberão cópias das zonas dos outros **servidores DNS primários** para também poder resolver nomes destes sub-domínios.

Cache  
Criação de diretório para armazenar a cópia das zonas servidores primários.

`mkdir /var/cache/bind/slaves`  
`chown bind:bind /var/cache/bind/slaves`

  
Deve-se dar permissão ao usuário bind para editar no diretório que será usado para guardar as cópias das zonas dos demais servidores.

<!-- -->

/etc/bind/named.conf.local  

`zone "redes1.edu.br" {`  
`        type master;`  
`        file "/etc/bind/db.redes1";`  
`};`  
  
`zone "100.168.192.in-addr.arpa" IN {`  
`        type master;`  
`        file "/etc/bind/db.100.168.192";`  
`};`  
` `  
`zone "redes2.edu.br" IN {`  
`        type slave;`  
`        file "/var/cache/bind/slaves/db.redes2";`  
`        masters { 192.168.100.102; };`  
`};`  
` `  
`zone "redes3.edu.br" IN {`  
`        type slave;`  
`        file "/var/cache/bind/slaves/db.redes3";`  
`        masters { 192.168.100.103; };`  
`};`  
` `  
`zone "redes4.edu.br" IN {`  
`        type slave;`  
`        file "/var/cache/bind/slaves/db.redes4";`  
`        masters { 192.168.100.104; };`  
`};`

  
Nas zonas tipo **slave** é indicado o local e o nome do arquivo com a cópia da zona e o endereço IP do servidor **master** correspondente.

<!-- -->

/etc/bind/db.redes1  

`$TTL    86400`  
`@       IN      SOA     ns.redes1.edu.br. admin.redes1.edu.br. (`  
`                     2014040900         ; Serial`  
`                         604800         ; Refresh`  
`                          86400         ; Retry`  
`                        2419200         ; Expire`  
`                          86400 )       ; Negative Cache TTL`  
`;`  
`@       IN      NS      ns.redes1.edu.br.`  
`@       IN      MX      10      mail.redes1.edu.br.`  
`ns      A       192.168.100.101`  
`www     A       192.168.100.101`  
`ftp     A       192.168.100.101`  
`mail    A       192.168.100.101`

/etc/bind/db.2.168.192  
Zona reversa

`$TTL    86400`  
`@       IN      SOA     ns.redes1.edu.br. admin.redes1.edu.br.  (`  
`                     2014040900         ; Serial`  
`                         604800         ; Refresh`  
`                          86400         ; Retry`  
`                        2419200         ; Expire`  
`                          86400 )       ; Negative Cache TTL`  
`;`  
`          IN      NS      ns.redes1.edu.br.`  
`101       IN      PTR     ns.redes1.edu.br.`  
`102       IN      PTR     ns.redes2.edu.br.`  
`103       IN      PTR     ns.redes3.edu.br.`  
`104       IN      PTR     ns.redes4.edu.br.`

## Configurações dos demais servidores DNS primários

/etc/bind/named.conf.local  
Exemplo para máquina 192.168.100.102 (domínio redes2.edu.br):

`zone "redes2.edu.br" {`  
`   type master;`  
`   file "/etc/bind/db.redes2";`  
`   allow-transfer {`  
`     192.168.100.101;`  
`   };`  
`};`

- O arquivo **/etc/bind/db.redes2** contem a configuração deste domínio;
- A linha **allow-transfer** indica qual **servidor DNS secundários** terá permissão para realizar a transferência de zona.

Cada servidor DNS deve responder pelo nome do próprio domínio, **www**, **ftp**, **ns** e **mail**, todos apontando para o mesmo **endereço IP**.

/etc/bind/db.redes2  
Configuração do domínio.

`$TTL    86400`  
`@   IN    SOA   ns.redes2.edu.br. admin.redes2.edu.br. (`  
`                              2014040902; serial`  
`                              3H ; refresh`  
`                              60 ; retry`  
`                              1W ; expire`  
`                              3W ; minimum`  
`                             )`  
`@       IN  NS     ns.redes2.edu.br. ; este é o servidor master deste domínio`  
`@       IN  MX     10 mail.redes2.edu.br.`  
`ns   A 192.168.100.102`  
`mail A 192.168.100.102`  
`www  A 192.168.100.102`  
`ftp  A 192.168.100.102`  
`ns   A 192.168.100.102`

### Configuração do DNS na máquina local

No Ubuntu a configuração do DNS era realizada no arquivo **/etc/resolv.conf**. Entretanto, este arquivo não é mais editável. No lugar dele foi implementado conjunto de scripts que contam com a ajuda do **DHCP Client** e alteram o DNS em conexões com IP dinâmico .

Para alterar manualmente a configuração do DNS deve-se editar arquivo **/etc/resolvconf/resolv.conf.d/head** e incluir os servidores DNS que queremos que nossa máquina utilize para resolver nomes.

No caso do nosso servidor primário, pode-se incluir o **servidor DNS secundário** para resolver nomes fora do domíno, por exemplo:

`vim /etc/resolvconf/resolv.conf.d/head`  
`nameserver 192.168.100.101`

Faça update da configuração:

` resolvconf -u`

Para visualizar se as alterações foram feitas:

`cat /etc/resolv.conf`

## Verificação a configuração e testando o DNS

Utilitário para testar o arquivo que contém o conteúdo de uma zona:

`named-checkzone nome_do_dominio arquivo_da_zona  `

`named-checkzone redes2.edu.br /etc/bind/db.redes2`

Utilitário para testar a configuração do BIND:

`named-checkconf -z`

Restart do serviço:

`service bind9 restart`

Verificando se está tudo certo:

`tail -n 200 /var/log/syslog`

### Sequência de testes

Comandos para testar o funcionamento do DNS:

`dig ns.redesN.edu.br`

`ping www.redesN.edu.br`  
`ping ns.redesN.edu.br`  
`ping ftp.redesN.edu.br`  
`ping mail.redesN.edu.br`

Teste do DNS reverso:

`dig -x 192.168.100.10X`

## Experimento Desafio

Modifique a arquitetura da rede de testes, alojando os **servidores DNS primários** e o **servidor DNS secundário** em **redes locais** distintas, separadas por **roteadores**. Em cada **rede local** inclua outras estações, algumas com IP fixo e outras com DHCP. Em seguida teste se o **serviço DNS** funciona.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 19h40min de 9 de dezembro de 2015 (BRST)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: VALLE, O. T. Gerência de Redes, Diário Aula, 2014. <http://wiki.sj.ifsc.edu.br/wiki/index.php/GER20706-2014-1>
