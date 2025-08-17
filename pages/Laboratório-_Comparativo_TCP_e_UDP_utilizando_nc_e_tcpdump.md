# Laboratório: Comparativo TCP e UDP utilizando nc e tcpdump

Neste laboratório serão utilizadas as ferramentas nc (netcat) e <a href="tcpdump" class="wikilink" title="tcpdump">tcpdump</a>.  

## tcpdump

O **tcpdump** é um programa que permite **capturar e analisar o tráfego de rede**, e é executado a partir de um **terminal**.

Veja no *link* as instruções para *download* e instalação do **<a href="tcpdump" class="wikilink" title="tcpdump">tcpdump</a>**, bem como as instruções para seu uso.

O **tcpdump** necessita de conta de **administrador** para poder ser executado. Caso você esteja utilizando **máquina virtual**, certifique-se que a mesma esteja na mesma **rede local** das demais máquinas do laboratório. Se não estiver, modificar a configuração da máquina virtual para trabalhar em modo ***bridge***.

## nc (NetCat)

Permite criar **comunicações** e **portas de escuta** **TCP** e **UDP** .

Parâmetros comuns para uso com nc  

- **-l** especifica porta para escuta TCP ou de recepção UDP;
- **-n** não converte endereços IP e porta, mantendo o formato numérico;
- **-u** usa comunicação UDP (por default usa TCP).

As **páginas de manual** do **nc** trazem informações detalhadas do uso deste comando:

`man nc`

Teste do netcat  
Comunicação entre um cliente e um servidor

- Verificar o **endereço IP** que está sendo utilizado pelas máquinas que serão utilizadas para comunicação com o comando **ifconfig**.
- Teste a conectividade entre as máquinas que serão utilizadas através do comando **ping**.
- No computador **servidor** execute o **netcat** para criar uma **porta de escuta TCP** em uma **porta** especificada, por exemplo, 5555:

`nc -l 5555`

- No computador **cliente** execute o **netcat** para abrir uma **conexão TCP** com o servidor especificado no **endereço IP** (X é o número do computador do colega de laboratório que vai aceitar a conexão) e **porta** especificada:

`nc 192.168.10.X 5555 `

- Com estes dois comandos, abre-se uma **conexão TCP**, *full-duplex* entre as máquinas, na qual tudo o que for teclado em um *host* será enviado ao outro host.
- Teste a comunicação enviando várias frases de um computador ao outro.
- Depois de testada a conexão, encerrar a mesma com CTRL-C.

## Comparativo entre uma comunicação TCP e UDP

Para este exercício será utilizado um terminal no seu computador e outro em um computador de um colega ou na máquina virtual.

### Conexão TCP

#### Abertura de conexão, troca de pacotes e encerramento de conexão TCP

Procedimentos:

- A primeira comunicação será feita usando o **protocolo TCP** repetindo os comandos testados anteriormente com o **netcat** e capturando pacotes com o **tcpdump**.
- Preparar, em um **terminal**, um comando **tcpdump** para capturar pacotes na porta 5555.

`sudo tcpdump -nSX -i eth0 port 5555`

- Repetir os comandos testados anteriormente com o **netcat**:

:\*Servidor:

`nc -l 5555`

:\*Cliente:

`nc 192.168.10.X 5555 `

- Com estes dois comandos, abre-se uma **conexão TCP**, *full-duplex* entre as máquinas, na qual tudo o que for teclado em um *host* será enviado ao outro host.
- Teste a comunicação enviando várias frases de um computador ao outro.
- Depois de testada a conexão, encerrar a mesma com CTRL-C.

Análise dos pacotes capturados numa conexão TCP  

Procedimentos:

\#\*Verifique as **portas origem e destino** escolhidas pelo cliente e servidor;

\#\*Analise a sequência de abertura de conexão TCP, verificando os ***flags*** setados em cada pacote;

\#\*Verifique os **números de sequência** iniciais escolhidos pelo cliente e servidor;

\#\*Verifique o **tamanho Máximo de Segmento** (**MMS**) escolhidos pelo cliente e servidor na conexão;

1.  Verifique a evolução dos **números de sequência e reconhecimento** durante as trocas de pacotes realizadas, e compare com a quantidade de bytes de cada mensagem;
2.  Verifique o **encerramento de conexão TCP** quando um dos host derruba a conexão com CTRL-C.

#### Teste de uma recusa de conexão TCP

- Utilizar o comando **netcat** criar no computador **servidor** um **soquete de escuta TCP** em uma **porta** especificada, por exemplo, 5555:

`nc -l 5555`

- Preparar, em **outro terminal**, um comando **tcpdump** para capturar pacotes na porta 5555.
- No computador **cliente** execute o **netcat** para abrir uma **conexão TCP** com o servidor especificado no **endereço IP** (X é o número do computador do colega de laboratório que vai aceitar a conexão) e uma **porta inexistente**, por exemplo 6666:

`nc 192.168.10.X 6666 `

Análise dos pacotes capturados na recusa de conexão TCP  

\#\*Verifique as **portas origem e destino** escolhidas pelo cliente e servidor;

\#\*Analise a tentativa de abertura e recusa de conexão TCP, verificando os ***flags*** setados em cada pacote.

### Comunicação UDP

Procedimentos:

- Verificar o **endereço IP** que está sendo utilizado pela máquina remota que será utilizada para comunicação com o comando **ifconfig**.
- Esta transferência será feita usando o **protocolo UDP**. No computador **servidor** execute o **netcat** com o parâmetro **-u**, o qual criará um **soquete de escuta UDP** em uma **porta** especificada, por exemplo, 5555:

`nc -u -l 5555`

- Preparar, em **outro terminal**, um comando **tcpdump** para capturar pacotes na porta 5555. Inclua no filtro a possibilidade de captura de **pacotes ICMP** visando analisar o que ocorre quando o servidor não está mais escutando na porta especificada.

`sudo tcpdump -nSX -i eth0 port 5555 or icmp`

- No computador **cliente** execute o **netcat** para **enviar um datagrama UDP** para o servidor especificado no **endereço** (X é o número do computador do colega de laboratório que vai aceitar a conexão) e **porta** especificada:

`nc -u 192.168.10.X 5555 `

- Com estes comandos tudo o que for teclado em um host será enviado ao outro host pelo **protocolo UDP**.
- Teste a comunicação enviando várias frases entre um computador e outro.
- Depois de testada a comunicação, encerrar a mesma em um dos lados com CTRL-C.
- Tentar enviar novamente enviar mensagens no lado onde a conexão não foi encerrada e verificar o que acontece.

Análise dos pacotes capturados na comunicação UDP  

1.  Verifique a ausência de conexão no UDP;
2.  Verifique o tamanho dos pacotes UDP a cada troca de mensagens realizada;
3.  Verifique o que acontece quando um dos lados da comunicação usando UDP encerra com CTRL-C e o outro lado tenta enviar novos pacotes.

### Transferência de arquivos com NetCat

Baixe o <a href="Mídia:arquivo.txt" class="wikilink" title="arquivo.txt">arquivo.txt</a> para transferência com TCP  

- Escolha um arquivo para transferência;
- Verificar o **endereço IP** que está sendo utilizado pela máquina remota que será utilizada para comunicação com o comando **ifconfig**.
- A transferência será feita usando o **protocolo TCP**. No computador **receptor** execute o **netcat** que criará um **soquete de escuta TCP** em uma **porta** especificada, por exemplo, 5555:

`nc -l 5555 > arquivo.txt`

- No computador **transmissor** execute o **netcat** para **criar uma conexão TCP** com o receptor especificado no **endereço** (X é o número do computador do colega de laboratório que vai aceitar a conexão) e **porta** especificada:

`time nc 192.168.10.X 5555 < arquivo.txt`

- O comando enviará o arquivo usando **conexão TCP**, ao fim da transmissão a conexão é encerrada.
- O comando **time** no antes do **nc** permite visualizar o tempo da transmissão.
- Preparar, em **outro terminal**, um comando **tcpdump** para capturar pacotes na porta 5555.
- Relançar a **conexão TCP** com **netcat** e capturar os pacotes com o **tcpdump**.

Análise da transferência TCP e dos pacotes capturados  

1.  Verifique se o tamanho dos arquivos é o mesmo;
2.  Verifique o tempo da transferência do arquivo;
3.  Nos pacotes capturados, identifique a abertura e encerramento de conexão;
4.  Verifique os números de sequência e reconhecimento TCP nas trocas de pacotes realizadas;
5.  Verifique o tamanho original do arquivo e o número de pacotes com que o mesmo foi fragmentado.
6.  Verifique se o número de pacotes trocados é compatível com o MSS estabelecido para a conexão TCP.

Transferência de arquivos com UDP  
O protocolo UDP não é adequado para transferência de arquivos, justamente por não dar garantias de que os dados chegarão corretamente.

O UDP é útil quando quando a aplicação tolera perder alguns dados, como no caso da voz digitalizada de uma comunicação telefônica. Também pode ser útil para mensagens curtas, como na troca de mensagens dos protocolos de roteamento entre roteadores, ou consultas DNS.

Uma aplicação que for utilizar UDP para transferir arquivos deve gerenciar a montagem de cada pacote UDP a ser enviado. Se o arquivo tiver que ser fragmentado, o papel fica a cargo da aplicação, a qual também deverá poder lidar com possíveis perdas de dados.

### Tarefa

Faça um relatório detalhando as **diferenças entre os protocolos TCP e UDP** usando como referência os experimentos realizados com o **NetCat** e a captura de pacotes com o **tcpdump**.

Ilustre o relatório com **diagramas de troca de mensagens** e arquivos com as **capturas** realizadas.

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 15h25min de 16 de abril de 2015 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>
