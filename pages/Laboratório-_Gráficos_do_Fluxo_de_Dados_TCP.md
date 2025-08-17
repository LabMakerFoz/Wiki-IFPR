# Laboratório: Gráficos do Fluxo de Dados TCP

Para este laboratório será utilizado a ferramenta <a href="wireshark" class="wikilink" title="wireshark">wireshark</a>.  

O **laboratório** deve ser realizado em uma **máquina virtual**, em virtude da necessidade de conta de **administrador** para utilizar o **wireshark**.

## Fluxo de Dados Confiável TCP

O TCP é um protocolo **orientado a conexão** e com **transferência garantida**.

Uma vez aberta a conexão TCP os dois lados podem **trocar dados em ambos os sentidos**, ou ***full-duplex***.

Para implementar a **transferência garantida** o TCP utiliza **números de sequência** (**Seq**), **números de reconhecimento** (**Ack**) e **temporizações**.

Em uma mesma conexão é possível trocar qualquer quantidade de dados, por isto se diz que o TCP permite um **fluxo de dados confiável**.

Como o **fluxo de dados confiável** entre emissor e receptor pode em **volume grande de dados**, como por exemplo quando fazemos um *download* de um arquivo grande, o TCP integra mais dois serviços:

- **controle de fluxo**, evitando que o emissor envie dados mais rápido que o receptor possa processar;
- **controle de congestionamento** que ajuda a prevenir congestionamentos na rede. O controle de congestionamento envolve várias etapas, como:
  - **partida lenta** na qual o TCP inicia a transmissão de um segmento e vai aumentando o número de segmentos enviados de forma exponencial;
  - **prevenção de congestionamento**, quando a partir de um limiar o aumento no número de segmentos transmitidos começa a ser de forma linear;
  - **AIMD**, que reduz o número de segmentos enviados quando detecta congestionamento.

Objetivo do laboratório  
Analisar o comportamento da do **fluxo de dados confiável** do TCP em uma transferência com grande volume de dados.

## Wireshark: Gráficos para análise do fluxo de dados TCP

O wireshark possui ferramentas gráficas para análise do fluxo de dados TCP:

*Wireshark -\> Statistics -\> TCP Stream Graph*  

- ***Round Trip Time Graph***: Mostra a evolução do **RTT** (Tempo de Ida e Volta) para os Ack ao longo do tempo;
- ***Throughput Graph***: Mostra a evolução da **vazão** usando os números de sequência.
- ***Time-Sequence Graph***: Mostra a evolução dos **números de sequência** (bytes trocados) ao longo do tempo;
- ***Window Scaling Graph***: Mostra a evolução da **janela do receptor** ao longo do tempo.

Consulte sobre estes gráficos em [^1].  

### Atividade prática

Procedimentos  

1.  Inicie o **navegador** e prepare o ***download*** de um arquivo grande, por exemplo, o arquivo ISO do Ubunbu: <http://www.ubuntu.com/download/desktop>;
2.  Inicie o **Wireshark** e selecione o filtro **tcp**, de tal forma que apenas segmentos TCP capturados serão exibidos na janela de listagem de pacotes;
3.  Inicie a **captura de pacotes**
4.  Inicie o ***download*** do arquivo, e mantenha a captura por alguns minutos;
5.  Pare a captura de pacotes;
6.  Analise os pacotes capturados e identifique a abertura de conexão e o início da transferência do arquivo;
7.  Selecione o primeiro pacote com **dados vindo do servidor ao cliente**. Isto é importante por os gráficos ilustram somente a transmissão de dados em um sentido. Como se está fazendo um *download* o sentido maior do fluxo de dados é portanto do servidor ao cliente.
8.  Gere os diferentes gráficos disponíveis em ***Wireshark -\> Statistics -\> TCP Stream Graph***.
9.  Para o gráfico ***Window Scaling Graph***, é mais interessante analisar a **janela do receptor** (ver: [^2]) do lado cliente, que está recebendo os dados, para tal, selecione um Ack do cliente antes de gerar o gráfico.
10. **Analise os gráficos**. Sobre o gráfico **Time-Sequence Graph (tcptrace)**, consulte [^3]
11. Gere **cópia dos gráficos** (PrtScr) para análise posterior e documentação

### Tarefa

1.  **Pesquise** sobre as informações que os gráficos permitem avaliar.
2.  Faça um **relatório** detalhando as o procedimento realizado para **análise do fluxo de dados TCP** e inclua os **gráficos** obtidos.
3.  Faça uma **análise crítica** dos dados obtidos com os aspectos teóricos do funcionamento do TCP.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 16h50min de 29 de abril de 2015 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: Tampkins, R. Statistics TCP Stream Graph. <http://pt.slideshare.net/LoveMyTool/ostu-wireshark-tcp-stream-graphs-by-ray-tompkins-presentation>

[^2]: GREER, C. The TCP Window. <http://www.lovemytool.com/blog/2010/07/practical-tcp-series-the-tcp-window-by-chris-greer.html>

[^3]: Rogers, K. Understanding the tcptrace Time-Sequence Graph in Wireshark. <http://packetbomb.com/understanding-the-tcptrace-time-sequence-graph-in-wireshark/>
