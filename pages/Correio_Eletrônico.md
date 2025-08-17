# Correio Eletrônico (e-mail) [^1]

A aplicação **Correio Eletrônico** (*e-mail*) existe desde o início da Internet e é hoje uma das aplicações mais importantes da rede. O *e-mail* permite uma comunicação assíncrona entre os usuários, na qual as pessoas enviam e recebem mensagens sob demanda.

Componentes da aplicação e-mail:

- **Agentes usuário**: Permitem que os usuários leiam, respondam, componham e transmitam suas mensagens. Há **leitores de email** dedicados, como o Mozilla Thunderbird e o Outlook da Microsoft. Entretanto, muitos usuários utilizam interfaces baseadas na Web, ou **Web email**, como o Gmail da Google, o Windows Live Mail (sucessor do Hotmail) da Microsoft e outros.
- **Servidores de email**: Formam o núcleo da infraestrutura do email, são responsáveis pelo **envio** e **recepção** das **mensagens dos usuários**.
- **Protocolo SMTP** (*Simple Mail Transfer Protocol*) (RFC 5321): É o protocolo utilizado pelo correio eletrônico. O SMTP, como outros protocolos de aplicação, tem dois lados, o lado cliente e o lado servidor. Quem envia a mensagem faz o papel do cliente e quem recebe de servidor, todavia, ambos os lados do SMTP devem ser implementados em cada servidor de email.
- Protocolo de Transporte: O SMTP usa o **serviço de transferência de dados confiável** do **TCP** para transferir uma mensagem desde o remetente até a caixa postal do destinatário.
- Porta: O lado servidor do SMTP usa a **porta 25** para aguardar solicitações de envio de mensagens de servidores cliente.

## Funcionamento do Servidor de Correio Eletrônico

Os servidores de Correio Eletrônico formam o núcleo da infraestrutura do email, são responsáveis pelo **envio** e **recepção** das **mensagens dos usuários**:

- Recepção de mensagens: Cada usuário possui uma **caixa postal** no seu servidor, na qual ficam armazenadas as mensagens recebidas e prontas para serem lidas e respondidas pelos usuários.
- Envio de mensagens: As mensagens enviadas pelos usuário vão para uma **fila de saída** e o servidor se encarrega de enviá-las direção ao servidor destino. Caso o servidor destino não esteja acessível no momento, o servidor de email tentará enviá-la mais tarde, persistindo nestas tentativas por alguns dias, quando então remove a mensagem e notifica o usuário que a tinha enviado.

<a href="Arquivo:CorreioEletronico.png" class="wikilink" title=" 700px"> 700px</a>

As mensagens trocadas pelo protocolo SMTP são mensagens em caracteres [**ASCII**](http://pt.wikipedia.org/wiki/ASCII). Para enviar uma mensagem, o cliente SMTP estabelece uma conexão TCP, na porta 25, com o servidor SMTP. Uma vez estabelecida à conexão TCP, cliente e servidores de email entram em uma fase de apresentação mútua (*handshaking*), trocando algumas informações (como o endereço de email do emissor e do destinatário), antes de enviarem a mensagem eletrônica em si.

### Leitura das mensagens pelos usuários

Para ler uma mensagem em sua caixa postal o destinatário da mensagem deve, a partir de seu **agente usuário**, acessar seu servidor. Para tal, o servidor de email requisita uma autenticação do usuário, através de uma identificação e uma senha:

- Caso o usuário utilize um **leitor de email**, as mensagens armazenadas na caixa postal do usuário serão transferidas do servidor para seu computador. Para realizar esta tarefa, o leitor de email normalmente utiliza o **protocolo POP3**, o qual abre uma **conexão TCP** na **porta 110** do servidor de email.
- Caso o usuário utilize um **Web email**, o usuário pode manipular suas mensagens diretamente no servidor, utilizando o navegador Web e o protocolo HTTP, sem haver a necessidade de transferência das mesmas para o computador local.

### Mensagens SMTP

A seguir é apresentado um exemplo de troca de mensagens SMTP em formato ASCII entre um cliente e um servidor de email.

São exatamente desta forma que as mensagens são enviadas pela conexão TCP entre o cliente e o servidor:

`C: MAIL FROM:<Paulo@escola.edu.br>`  
`S: 250 OK`  
`C: RCPT TO:<Maria@universidade.edu.br>`  
`S: 250 OK`  
`C: RCPT TO:<Tereza@universidade.edu.br>`  
`S: 550 No such user here`  
`C: RCPT TO:<Cristina@universidade.edu.br>`  
`S: 250 OK`  
`C: DATA`  
`S: 354 Start mail input; end with `<CRLF>`.`<CRLF>  
`C: Blah blah blah...`  
`C: ...etc. etc. etc.`  
`C: `<CRLF>`.`<CRLF>  
`S: 250 OK`

  
As palavras chave MAIL FROM e RCPT TO são usadas para identificar o emissor e receptor das mensagens, respectivamente.

A palavra chave DATA é usada para identificar o início do texto com a mensagem a ser enviada.

As respostas do servidor usam códigos para identificar sucesso (250 OK) ou problemas (550 *No such user here*).

No exemplo são trocadas mensagens entre Paulo no host escola.edu.br e Maria e Cristina no host universidade.edu.br. O usuário Tereza não tem caixa postal no servidor universidade.edu.br.

<!-- -->

Exercício  
Utilize o **telnet** na **porta 25** de um **servidor de email** e tente trocar mensagens SMTP. Por exemplo, tente acessar o servidor abaixo e trocar mensagens SMTP:

`telnet smtp.das.ufsc.br 25`

### Exercícios

1.  Verifique o cabeçalho de um email que você recebeu e analise cada uma das linhas.
2.  Qual a diferença entre MAIL FROM: da mensagem SMTP e o FROM do cabeçalho da mensagens do correio eletrônico?
3.  Pesquise sobre as vantagens de utilizar um **leitor de email**, ao invés de um **Web email**.
4.  Para uso de um leitor de email é preciso configurar o protocolo POP3. Veja como fazer isto para acessar os emails no seu servidor de email.
5.  Faça um teste com o leitor de email Thundersbird, instalando este programa na máquina virtual:

`sudo apt-get install thunderbird`

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h35min de 12 de junho de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: KUROSE, J.F; ROSS K. W. Redes de Computadores e a Internet: Uma abordagem *top-down*, São Paulo: Pearson, 2010.
