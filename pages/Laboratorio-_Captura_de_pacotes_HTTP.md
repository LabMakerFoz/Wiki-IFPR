# Laboratório: Captura de pacotes HTTP

Fonte: [^1].

Requisitos de software  
Este laboratório utiliza a ferramenta de captura de pacotes **Wireshark**.

- Para utilizar o **Wireshark** é necessário que o administrador atribua permissão para os usuários normais poderem executá-lo.
- Outra opção é utilizar uma **máquina virtual** com a placa de rede configurada em modo ***bridge*** e com permissão de administrador e instalar os aplicativos e utilizar o **Wireshark**.

Veja no link **<a href="wireshark" class="wikilink" title="wireshark">wireshark</a>** as instruções para download e instalação do **Wireshark**, bem como as instruções para uso do ferramenta.

## Objetivos

O objetivo deste laboratório é estudar o funcionamento da **<a href="Aplicação_Web" class="wikilink" title="Aplicação Web">Aplicação Web</a>** e explorar o funcionamento do **<a href="Protocolo_HTTP" class="wikilink" title="Protocolo HTTP">Protocolo HTTP</a>**, incluindo as **mensagens de pedido e resposta** e a **memória *cache* do navegador** .

## Pedido e Resposta HTTP

Vamos iniciar a nossa exploração do HTTP baixando um arquivo em HTML simples.

Procedimentos  

1.  Verifique com **ifconfig** a configuração de sua interface de rede;
2.  Inicie o navegador **Firefox** e não abra nenhuma página Web;
3.  Inicie o Wireshark, em seguida selecione a **placa de rede** e nas **opções de captura** selecione o **filtro http**, de tal forma que apenas as mensagens HTTP capturadas serão exibidas na janela de listagem de pacotes. ;
4.  Inicie a captura de pacotes
5.  Digite no navegador a URL para acessar o seu servidor Web com a página padrão ou uma página HTML simples;
6.  Pare a captura de pacotes.

Análise dos pacotes capturados  

1.  Verifique a mensagem GET (enviada pelo seu navegador para o servidor) e a mensagem de resposta do servidor para o seu navegador;
2.  Verifique os detalhes da mensagem GET;
3.  Verifique o encapsulamento dos protocolos, com a mensagem HTTP sendo transportada em um segmento TCP, que é carregado em um datagrama IP, que por sua vez é levado em um quadro Ethernet.

Perguntas  

1.  O seu navegador executa HTTP 1.0 ou 1.1?
2.  Qual a versão de HTTP do servidor?
3.  Quais idiomas o seu navegador indica que pode aceitar ao servidor?
4.  Qual o endereço IP do seu computador e do servidor?
5.  Qual o número da porta TCP utilizada no seu computador e pelo servidor?
6.  Qual o endereço MAC do seu computador?
7.  Qual o código de *status* retornado do servidor para o seu navegador?
8.  Quando o arquivo em HTML que você baixou foi modificado no servidor pela última vez?
9.  Quantos bytes de conteúdo são baixados pelo seu navegador?

## Pedido HTTP GET Condicional e Resposta

A maioria dos navegadores web tem uma **memória *cache*** que permite armazenar as últimas páginas acessadas. Desta forma o navegador realiza um **GET condicional** quando busca um objeto HTTP a fim de verificar se o objeto em *cache* é o mesmo que está sendo provido pelo servidor.

Procedimentos  

1.  Inicie o navegador web;
2.  Limpe o ***cache*** do seu navegador:
      
    Firefox: Preferências -\> Privacidade e Segurança -\> Cookies e Dados de Sites;
3.  Inicie o Wireshark e selelcione o filtro **http**, de tal forma que apenas as mensagens HTTP capturadas serão exibidas na janela de listagem de pacotes. ;
4.  Digite a uma URL no navegador;
5.  Visualize os pacotes capturados;
6.  Pressione o botão “atualizar” no navegador;
7.  Pare a captura de pacotes.

Perguntas  

1.  Inspecione o conteúdo da primeira mensagem HTTP GET do seu navegador para o servidor. Você vê uma linha *If-Modified-Since*?
2.  Inspecione o conteúdo da resposta do servidor. O servidor retornou explicitamente o conteúdo do arquivo? Como você pode dizer isso?
3.  Agora inspecione o conteúdo da segunda mensagem HTTP GET do seu navegador para o servidor. Você vê uma linha *If-Modified-Since*? Caso a resposta seja afirmativa, qual informação segue o cabeçalho *If-Modified-Since*?
4.  Qual é o código de status e a frase retornada do servidor na resposta à segunda mensagem HTTP GET? É diferente do código de retorno da primeira mensagem?
5.  O servidor retornou explicitamente o conteúdo do arquivo? Explique.
6.  Qual o tamanho da primeira e segunda mensagem de retorno do servidor?

#### Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 17h40min de 26 de abril de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: <http://wiki.sj.ifsc.edu.br/wiki/index.php/RED29004-2015-1>
