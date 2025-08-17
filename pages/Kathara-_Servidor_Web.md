# Kathará

## Laboratório: Servidor Web

<a href="Aplicação_Web" class="wikilink" title="Aplicação Web">Aplicação Web</a>  
Conceitos sobre a aplicação Web.

<!-- -->

Laboratório  
Verificação do funcionamento da interação entre um **cliente** e um **servidor Web** (Referência: [^1]):

<a href="Arquivo:Kathara-ServidorWeb.png" class="wikilink" title="Arquivo:Kathara-ServidorWeb.png">Arquivo:Kathara-ServidorWeb.png</a>

Hierarquia de arquivos e diretórios para os scripts do laboratório  

`lab.conf`  
`client.startup`  
`server.startup`  
`client/`  
`server/`

Conteúdo dos arquivos:

`lab.conf`  
`  client[0]=A`  
`  server[0]=A`

`server.startup`  
`  ifconfig eth0 10.0.0.1/24 up`  
`  /etc/init.d/apache2 start`

`client.startup`  
`  ifconfig eth0 10.0.0.2/24 up`

Diretório do servidor:

`server/var/www/html/index.html`

  
O arquivo index.html contem a **página HTML** a ser disponibilizada.

Iniciar rede do laboratório:

`kathara lstart`

## Procedimentos práticos

Teste do servidor Web  

O servidor Web **apache** implementa o lado servidor da **aplicação Web** e atende requisições de **clientes Web**, ou **navegadores**, através do **protocolo HTTP**.

No **servidor**, verificar se o **apache** está rodando:

`/etc/init.d/apache2 status`

No **cliente**, acessar o servidor apache usando o navegador modo texto **links**:

`links 10.0.0.1`

Verificar no servidor a **página HTML** armazenada:

`cat /var/www/html/index.html`

Verificar o **arquivo de log** no servidor Web:

`tail -f /var/log/apache2/access.log`

### Análise da troca de pacotes entre cliente e servidor Web

Preparar o servidor Web para capturar pacotes com **tcpdump** e armazenar a saída em arquivo:

`tcpdump -w /hosthome/capturaWeb.ncap`

Análise com Wireshark  
Utilizar o **Wireshark** na máquina hospedeira e analisar os pacotes capturados:

- Abertura de conexão <a href="Protocolo_TCP" class="wikilink" title="TCP"><strong>TCP</strong></a>;
- Pedido/Resposta <a href="Protocolo_HTTP" class="wikilink" title="HTTP"><strong>HTTP</strong></a>;
- Encerramento de conexão <a href="Protocolo_TCP" class="wikilink" title="TCP"><strong>TCP</strong></a>.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 16h32min de 25 de fevereiro de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: <https://github.com/KatharaFramework/Kathara-Labs/tree/main/main-labs/application-level/web-server>
