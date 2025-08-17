# Laboratório: Captura de pacotes TCP

Requisitos de software  
Este laboratório utiliza a ferramenta de captura de pacotes **Wireshark**.

- Para utilizar o **Wireshark** é necessário que o administrador atribua permissão para os usuários normais poderem executá-lo.
- Outra opção é utilizar uma **máquina virtual** com a placa de rede configurada em modo ***bridge*** e com permissão de administrador e instalar os aplicativos e utilizar o **Wireshark**.

Veja no link **<a href="wireshark" class="wikilink" title="wireshark">wireshark</a>** as instruções para download e instalação do **Wireshark**, bem como as instruções para uso do ferramenta.

## Objetivos

O objetivo deste laboratório é estudar o funcionamento da **Aplicação Web** e explorar o funcionamento do **protocolo TCP**, incluindo as a análise das portas TCP utilizadas pelo cliente e pelo servidor e dos pacotes de abertura e encerramento da conexão TCP.

## Captura de pacotes de abertura e encerramento de conexão

Exercícios  

1.  Verificar o **endereço IP** e a **interface de rede** que está sendo utilizada pela máquina onde o **wireshark** será executado, com o comando **ifconfig**.
2.  Escolher um **servidor Web** para acessar a partir do navegador.
3.  Faça um **ping** no servidor Web para descobrir seu endereço IP.
4.  Preparar o **wireshark** para capturar pacotes TCP.
5.  Acessar o servidor Web e analisar a **captura de pacotes** realizadas, procurando identificar as seguintes informações:
    - No pacote IP, identifique o **endereço IP** do cliente e do servidor;
    - No pacote TCP identifique a **porta origem e destino** escolhidas pelo cliente e pelo servidor;

      
    <a href="Arquivo:PortasTCP.png" class="wikilink" title="Arquivo:PortasTCP.png">Arquivo:PortasTCP.png</a>

    - Analise a sequência de **abertura de conexão TCP**, verificando os ***flags*** setados em cada pacote;

      
    <a href="Arquivo:AberturaConexao.png" class="wikilink" title="Arquivo:AberturaConexao.png">Arquivo:AberturaConexao.png</a>

    - **Números de sequência** iniciais escolhidos pelo cliente e servidor;
    - O **Tamanho Máximo de Segmento** (**MMS**) negociado na conexão;

      
    <a href="Arquivo:MTU.png" class="wikilink" title="Arquivo:MTU.png">Arquivo:MTU.png</a>

    - Analise a evolução dos **números de sequência e reconhecimento** ao longo da transferência da página Web e sua relação com a quantidade de Bytes trocados em cada pacote;
    - Analise a sequência de **encerramento de conexão TCP**, verificando os ***flags*** setados em cada pacote;

      
    <a href="Arquivo:EncerramentoConexao.png" class="wikilink" title="Arquivo:EncerramentoConexao.png">Arquivo:EncerramentoConexao.png</a>

### Tarefa

Construir um **diagrama de troca de mensagens**, ilustrando os pacotes trocados entre o cliente e o servidor, incluindo os valores reais utilizados como **endereços IP**, **números de porta**, ***flags***, **números de sequência e reconhecimento** e quantidade de **bytes** trocados.

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 17h12min de 20 de março de 2015 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>
