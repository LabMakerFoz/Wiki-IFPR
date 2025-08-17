# 6LowPAN

Referências: [^1] (p. 125), [^2], [^3]

Adapta a **camada rede** da **Internet**, no caso o **IPv6**, para as limitações de **tamanho do quadro** impostas pelas redes **LLN** (*low-power and lossy networks*), em particular para enlaces **IEEE 802.15.4**.

<a href="Arquivo:6lowPAN.png" class="wikilink" title="150px">150px</a> [^4] (p. 126)

As redes **IEEE 802.15.4** definem quatro tipos de quadros: quadros *beacon*, quadros de comando MAC, quadros de reconhecimento e quadros de dados. Os **pacotes IPv6** devem ser carregados por **quadros de dados**.

O tamanho máximo do **quadro de dados** numa rede **IEEE 802.15.4** é **127 bytes**, com 25 bytes reservados para o cabeçalho e 21 bytes para o mecanismo de segurança da camada enlace. Sobram, portanto, 81 bytes para acomodar o **datagrama IPv6**. Obviamente isto não dá para acomodar um pacote de tamanho mínimo IPv6 de 1280 octetos, e também, a questão da fragmentação e remontagem de pacotes IPv6 usa octetos extra e deve ser prevista para a camada inferior. Para lidar com esta limitação de espaço foi desenvolvido o **6LowPAN**, o qual realiza três funções principais: compactação do cabeçalho IPv6, suporte para fragmentação e remontagem do IPv6 e roteamento no nível da camada 2 (para topologias *mesh*). Para isto, foram definidos três tipos de cabeçalhos, mostrados na figura.

<a href="Arquivo:6lowPAN-header-stack.png" class="wikilink" title="700px">700px</a> [^5] (p. 126)

## Compactação do cabeçalho IPv6

Como descreve [^6], o **6LoWPAN** remove alguns campos nos cabeçalhos **IPv6** e **UDP** por estes possuírem valores conhecidos ou por seus valores poderem ser inferidos a partir de campos no cabeçalho **IEEE802.15.4**. No cabeçalho IPv6, a versão é sempre 6, os campos *Traffic Class* e *Flow Label* não são usados e o comprimento *Lenght* é igual ao comprimento do campo IEEE802.15.4 menos tamanho do cabeçalho IPv6. Todos esses campos podem, portanto, serem removidos. O cabeçalho *Next-Header* tipicamente aponta para UDP (ou TCP), e assim campo de 8 bits pode ser substituído por um campo de 2 bits, como parte do campo HC1 do cabeçalho 6LoWPAN. Finalmente, os endereços IPv6 de 128 bits podem ser recuperados a partir de endereços MAC de 64 bits, como os campos de origem e destino do IEEE 802.15.4. Isso permite a remoção dos campos de endereço de destino e de origem IPv6. No final, apenas o campo de limite de saltos (*Hop Limit*) tem de estar presente no cabeçalho 6LoWPAN e, do mesmo modo para o UDP, o comprimento pode ser calculado a partir do campo de comprimento do IEEE 802.15.4. Nos casos mais comuns de utilização das redes de sensores, apenas um número limitado de portas é utilizado, de modo que quatro bits são suficientes para descrevê-las, em vez de 8 bits. Assim, o cabeçalho IPv6 e UDP pode ser compactado para 2 bytes.

<a href="Arquivo:Cabecalho-6LowPAN.png" class="wikilink" title="500px">500px</a> [^7] (p. 16)

## Roteamento nas redes 6LowPAN

Nas redes IEEE 802.15.4, diferentemente das redes cabeadas, pode não haver encaminhamento direto entre os nós da mesma camada de enlace, pois podem estar organizados numa topologia *mesh*. Para resolver esta questão pode utilizar um **protocolo *mesh*** (p.ex. Zigbee) que realiza a função de estabelecer os melhores caminhos entre os nós (*Mesh Header* na figura mais acima), ou usar um **protocolo de roteamento** como o **RPL** (*IPv6 Routing Protocol for Low-Power and Lossy Networks*) que leve em conta os endereços **IPv6** *link-local* dos nós para estabelecer o caminho. Esta forma de roteamento é chamada *route over* e usa mensagens especiais para definir o grafo de roteamento.

## Tecnologias

6LowPAN e ZigBee  
[^8]

## Referências

<references />

<a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a> <a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 15h21min de 14 de maio de 2020 (-03)

[^1]: Ammar Rayes & Samer Salam. <a href="Media:InternetOfThingsFromHypeToReality.pdf" class="wikilink" title="Internet of Things From Hype to Reality">Internet of Things From Hype to Reality</a>: The Road to Digitization, Springer, 2019.

[^2]: Miguel, Márcio Luiz Ferreira. [Arquitetura SDN para redes de sensores sem fio 6LOWPAN](https://www.ppgia.pucpr.br/pt/arquivos/doutorado/teses/2018/052_Tese_MarcioLuizFerreiraMiguel.pdf) /, Tese (doutorado) - Pontifícia Universidade Católica do Paraná, Curitiba, 2018.

[^3]: <https://www.rfc-editor.org/rfc/rfc4944.txt>

[^4]:

[^5]:

[^6]:

[^7]:

[^8]: <http://ipv6.br/post/zigbee-usa-agora-6lowpan-sua-proxima-lampada-tera-ipv6/>
