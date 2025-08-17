# DNS

O **DNS** (*Domain Name Service*), ou **serviço de nomes de domínio**, é um sistema que permite traduzir o nome de um domínio (como por exemplo www.ifpr.edu.br) em um endereço IP (como 200.17.98.70). Isto facilita na medida em que não precisamos mais memorizar endereços IP, mas sim nomes de domínio, muito mais fáceis de serem lembrados e ao mesmo tempo identificados com o proprietário do domínio. [^1].

No Brasil os nomes de domínio são registrados pelo **[Registro.br](http://registro.br)**.

Para resolver os nomes, o DNS realiza uma busca em um **banco de dados distribuído**, armazenado em sistemas cooperativos independentes, chamados **servidores de nomes** ou **servidor DNS**, que fazem a tradução do nome de domínio em endereço IP.

Uma solicitação de tradução de um nome a um **servidor DNS** pode usar um ou mais servidores para obter o endereço desejado. Por exemplo, um servidor de nomes consultado por um cliente verifica se o nome solicitado pertence a seu sub-domínio. Se for o caso, traduz o nome ao endereço de acordo com sua base de dados e devolve ao solicitante. Se não puder resolver o nome o servidor de nomes contacta um **servidor DNS de mais alto nível** para que possa resolver o nome e devolver a resposta ao cliente.

## Hierarquia de servidores de nome

Os servidores de nome estão organizados em uma hierarquia de servidores:

Servidor de nomes raiz  
Há na Internet em torno de 14 **servidores de nomes raiz**. São responsáveis por indicar os domínios de alto nível existentes na Internet.

<a href="Arquivo:MapaDNS.png" class="wikilink" title="Arquivo:MapaDNS.png">Arquivo:MapaDNS.png</a>

Servidor de nomes de domínio de alto nível (*Top Level Domains* - TLD)  
São responsáveis por **domínios de alto nível**, como **.com**, **.edu**, **.gov**, etc e por todos os domínios de alto nível de países, como **.br**, **.ar**, **.py**, etc.

<!-- -->

Servidor de nomes com autoridade  
Toda organização que tiver servidores que precisam ter acesso público na Internet devem fornecer registros destes servidores para a Internet através de um **servidor de nomes com autoridade**. A organização pode implementar seu servidor de nomes com autoridade ou abrigar seus registros em um **servidor de nomes com autoridade de algum provedor**.

### Servidor de nomes local e memória *cache*

Visando a melhoria da performance do sistema DNS, toda organização necessita ter um **servidor de nomes local**, o qual deve fazer parte da **configuração de rede** de cada host da instituição. Para as máquinas da instituição, o endereço do servidor DNS local é geralmente fornecido pelo servidor DHCP, juntamente com a configuração do endereço IP da estação. Toda pesquisa no serviço DNS sempre inicia no **servidor de nomes local**.

O **servidor de nomes local** precisa saber como contactar pelo menos um **servidor de nomes raiz**. Todos os nomes recentemente usados são armazenados na *'memória*cache***local do servidor de nomes, bem como a informação de como foram obtidos. Como a informação em memória pode estar desatualizada, o servidor de nomes marca como **não autoritativa** (*non authoritative''), podendo o cliente contactar o**servidor de nomes com autoridade''' para ver se o nome ainda é válido.

## Resolução de nomes

O processo mais utilizado de **resolução de nomes** envolve consulta a um ou mais **servidores de nomes** de forma **interativa**.

A figura a seguir ilustra o processo de interação entre vários servidores DNS:

<a href="Arquivo:DNS.png" class="wikilink" title="Arquivo:DNS.png">Arquivo:DNS.png</a>

1.  O **cliente DNS** consulta um nome de domínio no **servidor DNS local**;
2.  Se o **servidor DNS local** não conseguir resolver o nome ou não tiver o registro em *cache*, consulta um **servidor DNS raiz**;
3.  O **servidor DNS raiz** informa um **servidor DNS de alto nível** capaz de resolver o nome;
4.  O **servidor DNS local** consulta o **servidor DNS de alto nível**;
5.  Se o **servidor DNS de alto nível** não conseguir resolver o nome ou não tiver o registro em *cache*, informa um **servidor DNS com autoridade** para resolver o nome;
6.  O **servidor DNS local** consulta o **servidor DNS com autoridade**;
7.  O **servidor DNS com autoridade** devolve a consulta solicitada ao **servidor DNS local**;
8.  O **servidor DNS local** devolve a consulta ao **cliente DNS**.

## Paradigma cliente-servidor do DNS

O **DNS** está situado no nível da **camada aplicação** da **arquitetura Internet** e usa o mesmo paradigma **cliente-servidor** dos demais **protocolos de aplicação**, como o HTTP, FTP e SMTP. Entretanto, o DNS é um serviço auxiliar utilizado pelas demais aplicações usuários, as quais, antes iniciar uma comunicação na Internet, precisam obter o endereço IP do seu correspondente.

### Protocolo de transporte usado pelo DNS

As **mensagens DNS** entre um **cliente** e um **servidor** são encaminhadas como mensagens de aplicação utilizando o **protocolo UDP** e a **porta 53**.

No funcionamento do DNS existe também comunicação entre um **servidor DNS primário** e um **servidor DNS secundário**, quando o primeiro transfere uma cópia da sua zona para o servidor secundário. Neste caso a comunicação utiliza **protocolo TCP** e a **parta** 53.

### Mensagem DNS

Toda comunicação do **DNS** é realizada por meio de uma **mensagem** cujos campos são mostrados na figura.

`   +---------------------+`  
`   |        Header       |`  
`   +---------------------+`  
`   |       Question      | the question for the name server`  
`   +---------------------+`  
`   |        Answer       | RRs answering the question`  
`   +---------------------+`  
`   |      Authority      | RRs pointing toward an authority`  
`   +---------------------+`  
`   |      Additional     | RRs holding additional information`  
`   +---------------------+`

O cabeçalho (*Header*) é sempre presente e especifica a quantidade campos presentes na sequência da mensagem e também se a mensagem é uma solicitação ou resposta. O campo questão (*Question*) contém a solicitação ao servidor de nomes. O campo resposta (*Answer*) contém a resposta, chamada de RR (*resource record*). O campo autoridade (*Authority*) contém RRs que apontam para um servidor de nomes com autoridade para responder a solicitação. O campo adicional (*Additional*) contém RRs outras informações relacionadas a solicitação.

tcpdump ou Wireshark  
Com os aplicativos **tcpdump** ou **Wireshark** podemos visualizar as mensagens DNS, incluindo filtros para capturar pacotes **UDP** na **porta 53**.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 11h45min de 29 de setembro de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: KUROSE, J.F; ROSS K. W. Redes de Computadores e a Internet: Uma abordagem *top-down*, São Paulo: Pearson, 2010.
