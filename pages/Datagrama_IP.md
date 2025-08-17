# Datagrama IP

Referências: [^1], [^2].

Um **datagrama IP** é o **pacote de dados** na rede Internet, definido na RFC791.

O formato do datagrama apresenta um **cabeçalho**, que contém os **endereços IP** da **fonte** (*Source Address*) e do **destino** (*Destination Address*), além de outros campos, e uma área de dados.

`   0                   1                   2                   3   `  
`   0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 `  
`  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+`  
`  |Version|  IHL  |Type of Service|          Total Length         |`  
`  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+`  
`  |         Identification        |Flags|      Fragment Offset    |`  
`  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+`  
`  |  Time to Live |    Protocol   |         Header Checksum       |`  
`  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+`  
`  |                       Source Address                          |`  
`  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+`  
`  |                    Destination Address                        |`  
`  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+`  
`  |                    Options                    |    Padding    |`  
`  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+`

Campos do Datagrama IP:

- **Versão** (*Version*) indica a versão do protocolo, no caso a versão 4, também conhecida como IPv4.
- **IHL** (*Internet Header Length*) indica o comprimento do cabeçalho, em função dos campos opcionais, tipicamente o cabeçalho contém as 5 primeiras linhas, totalizando 20 bytes.
- **Tipo de serviço** (*Type of Service*) permite diferenciar datagramas de diferentes tipos de serviço, sendo utilizado para implementar mecanismos de QoS (Qualidade de Serviço).
- **Tamanho total** (*Total Length*) indica o comprimento total do datagrama em bytes.
- **Identificação** (*Identification*), ***flags**'' e***Fragment Offset**'' são usados em caso de fragmentação do datagrama IP.
- **Tempo de sobrevida**, **TTL** (*Time to Live*), indica o tempo de vida do datagrama, após o qual o mesmo é descartado. \*:Na prática é medido em número de saltos (*hops*), sendo decrementado de uma unidade em cada roteador.
- **Protocolo** (*Protocol*) indica o protocolo da camada superior que está sendo transportado, como por exemplo TCP ou UDP. Para cada protocolo há um número padronizado pela RFC1700, como por exemplo:

`Assigned Internet Protocol Numbers`  
`Decimal    Keyword     Protocol `  
`    1     ICMP        Internet Control Message       `  
`    2     IGMP        Internet Group Management    `  
`    4     IPv4        IP in IP (encasulation)               `  
`    6     TCP         Transmission Control           `  
`   17     UDP         User Datagram                  `

- ***Header Checksum*** é utilizado para detecção de erros no cabeçalho.
- **Opções** (*Options*) é raramente usado.
- **Dados** sucedem o cabeçalho, podendo ser, por exemplo, segmentos TCP ou UDP, mensagens do protocolo ICMP, mensagens de roteamento, etc.

O **comprimento total** do datagrama teoricamente poderia ser de 64K bytes (em função dos 16 bits do campo Tamanho (2<sup>16</sup>=65535), todavia, na prática, nunca é maior que 1.500 bytes. Isto é feito para evitar a fragmentação do datagrama na rede física, já que o mesmo é encapsulado em um **quadro** da camada enlace. No caso das redes locais Ethernet, a mais utilizada, o tamanho do quadro é de 1.500 bytes. O tamanho máximo dos pacotes que podem ser transportados pela camada enlace é chamado de **MTU** (*Maximum Transfer Unit*).

<a href="Arquivo:MTU.png" class="wikilink" title="Arquivo:MTU.png">Arquivo:MTU.png</a>

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h36min de 12 de junho de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: KUROSE, J.F; ROSS K. W. Redes de Computadores e a Internet: Uma abordagem *top-down*, São Paulo: Pearson, 2010.

[^2]: <http://www.rfc-editor.org/info/rfc791>
