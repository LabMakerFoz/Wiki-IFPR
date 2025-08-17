# Laboratório: Captura de pacotes ICMP

Para este laboratório será utilizado a ferramenta de captura de pacotes **wireshark**.

## Objetivos

O objetivo deste laboratório é estudar o funcionamento do **<a href="Protocolo_ICMP" class="wikilink" title="Protocolo ICMP">Protocolo ICMP</a>** utilizando captura de pacotes com **wireshark**.

## Wireshark

O **Wireshark** é um programa que permite capturar e analisar o tráfego de rede.

Em uma **rede local**, com os computadores conectados através de ***hubs***o **wireshark** permite capturar todo o tráfego circulando, já que o*hub'' se comporta como um barramento. Com o uso de***switches**'' o tráfego da rede local é segmentado entre as duas entidades que estão se comunicando, não sendo possível capturar o tráfego de terceiros.

Em uma **rede local sem fio (wifi)** o **wireshark** permite capturar todo o tráfego circulando.

Outro programa similar ao wireshark é o **tcpdump**, o qual é utilizado diretamente em uma janela de textos e é útil para verificar o tráfego de rede em roteadores e outros dispositivos remotos.

### Tela do Wiresark

<a href="Arquivo:Wireshark.png" class="wikilink" title=" 600px"> 600px</a>

### Captura de pacotes em modo promíscuo

Execute o comando **ifconfig** e verifique qual o nome da **interface** de rede conectada a internet, na qual serão capturados pacotes.

A captura de pacotes em modo promíscuo, captura qualquer pacote circulando na rede local. Para tal, selecione a **interface** na qual o **wireshark** deve realizar a captura:

- Selecione a guia ***Capture/Interfaces***;
- Selecione a interface de rede apropriada.

Verifique a quantidade e o tipo dos pacotes sendo capturados. Procure identificar pacotes de protocolos conhecidos.

Para facilitar a análise dos pacotes, é importante utilizar **filtros** para protocolos específicos.

## Ping

Procedimentos para captura de **mensagens ICMP** trocadas pelo comando **ping**:

- Prepare o **wireshark** para capturar pacotes utilizando o filtro **icmp**;
- Execute o comando **ping** em um host remoto e realize uma **captura de pacotes** procurando identificar as **mensagens ICMP** trocadas.
- Analise o formato dos pacotes **ICMP *Echo Request/Echo Replay***.
- Consulte as páginas **man** do **ping** e modifique o **tamanho** dos pacotes enviados pelo ping (*default* 56 Bytes). Analise os pacotes capturados e verifique a mudança no **tamanho total** no cabeçalho do **datagrama IP**.
- Modifique o **ttl** dos pacotes enviados pelo **ping** e analise os pacotes capturados verificando este campo no no cabeçalho do **datagrama IP**. Gere pacotes *Echo Request* que encerrem seu tempo de vida antes de atingir o destino e analise a **mensagens ICMP** de resposta a esta ocorrência.
- Utilize a opção -p *pattern* para preencher com dados **hexadecimais** os pacotes enviados pelo **ping**. Analise o conteúdos dos pacotes enviados a partir da captura de pacotes.

## Traceroute

Procedimentos para captura de **mensagens ICMP** e **UDP** trocadas pelo comando **traceroute**::

- Prepare o **wireshark** para capturar pacotes utilizando o filtro **icmp** ou **udp**;
- Execute o comando **traceroute** em um host remoto e realize uma captura de pacotes procurando identificar o funcionamento do traceroute a partir da análise dos **datagramas IP** enviados (**ttl**=1, 2, 3, ...) e das **mensagens ICMP** informando que o tempo de vida expirou. Note que o traceroute envia os datagramas ordinários usando o **protocolo UDP**.
- Produza um texto com uma descrição detalhada do funcionamento do traceroute.

## Tarefa

Faça uma pesquisa sobre o **protocolo ICMP**:

- Descrevendo o papel do ICMP no funcionamento da Internet.
- Descreva em particular o funcionamento dos comandos **ping** e **traceroute**.
- Acrescente telas com a execução dos comandos **ping** e **traceroute** e a sequência de mensagens ICMP trocadas durante a execução dos mesmos e capturada pelo **wireshark**.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 11h40min de 28 de maio de 2015 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>
