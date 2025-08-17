# CIDR (*Classless Interdomain Routing*)

O **CIDR**, ou **endereçamento IP sem classes**, otimiza a distribuição dos endereços IP de 32 bits, permitindo **máscaras de rede** de qualquer tamanho.

O endereçamento CIDR usa a **notação / (barra)** para indicar a quantidade de bits que **identifica a rede** (que pode ser qualquar valor entre 0 e 32 bits) e, por consequência, a quantidade de bits que **identificam hosts** dentro da rede.

Conversão de binário para decimal  
O valor em decimal do endereço IP é obtido somando os correspondentes valores decimais das casas que têm o bit 1.

|  |  |  |  |  |  |  |  |  |
|----|----|----|----|----|----|----|----|----|
| Valores posicionais | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
| Potências de 2 | 2<sup>7</sup> | 2<sup>6</sup> | 2<sup>5</sup> | 2<sup>4</sup> | 2<sup>3</sup> | 2<sup>2</sup> | 2<sup>1</sup> | 2<sup>0</sup> |
|  | MSB |  |  |  |  |  |  | LSB |
|  |  |  |  |  |  |  |  |  |

  
MSB: Bit mais significativo (*Most Significant Bit*)

LSB: Bit menos significativo (*Less Significant Bit*)

**Exemplo**:

`10000000 = 128`  
`11000000 = 128 + 64 = 192`  
`11100000 = 128 + 64 + 32 = 224`  
`11110000 = 128 + 64 + 32 + 16 = 240`  
`11111000 = 128 + 64 + 32 + 16 + 8 = 248`  
`11111100 = 128 + 64 + 32 + 16 + 8 + 4 = 252`  
`11111110 = 128 + 64 + 32 + 16 + 8 + 4 + 2 = 254`  
`11111111 = 128 + 64 + 32 + 16 + 8 + 4 + 2 + 1 = 255`

## Máscaras de rede possíveis no CIDR

No CIDR não temos mais somente as máscaras:

`255.0.0.0 (classe A)`  
`255.255.0.0 (classe B)`  
`255.255.255.0 (classe C)`

No último Byte da máscara de rede, podemos ter qualquer número de bits MSB em 1.

Disso podemos concluir que os valores possíveis para o último byte da máscara de rede são:

`128, 192, 224, 240, 248 e 252`

  
Não há sentido em atribuir uma máscara de rede 254, pois não haverão endereços IP disponíveis para máquinas.

<!-- -->

Tamanho de uma rede  
A quantidade de bits que **identificam os hosts** dentro de uma rede define o **tamanho da rede**.

## Endereços IP especiais em uma rede

Dos bits que **identificam hosts** em uma rede existem dois endereços IP especiais:

Endereço da rede  
Possui bits "**tudo zero**" nos bits correspondentes ao **identificador de host**.

O **endereço da rede** é utilizado em **tabelas de roteamento** visando identificar a rede destino de um datagrama encaminhado a um *host*.

<!-- -->

Endereço de *broadcast*  
Possui bits "**tudo um**" nos bits correspondentes ao **identificador de host**.

O endereço de broadcast é considerado um endereço de difusão limitado a rede do *host* origem do datagrama (não encaminhado). É equivalente ao endereço de 255.255.255.255.

### Exemplos endereçamento CIDR

Dado os **endereços IP** e as **máscaras de rede**, determinar:

:\*A **máscara de rede** na notação decimal;

:\*O endereço IP da rede, ou **identificador de rede**;

:\*A **quantidade de hosts** possíveis para esta rede;

:\*O **endereço de *broadcast*** da rede.

Exemplo 1  
Dado o IP **200.17.101.9/24**:

Resolução:

  
Máscara de rede em binário:

`11111111.1111111.1111111.00000000`

  
  
Máscara de rede em decimal:

`255.255.255.0`

  
  
Endereços IP e número de *hosts* possíveis:

`200.17.101.`**`0`**`   -> Idenfificador da rede`  
`200.17.101.`**`1`**`   -+`  
`200.17.101.`**`2`**`    | `  
`200.17.101.`**`3`**`    | Endereços para `*`hosts`*` e roteadores `  
`...             | dentro da rede (2`<sup>`8`</sup>` - 2 = 254)`  
`200.17.101.`**`253`**`  |`  
`200.17.101.`**`254`**` -+`  
`200.17.101.`**`255`**` -> `*`Broadcat`*` dentro da rede`

Exemplo 2  
Dado o IP: **200.130.2.73/26**:

Resolução:

  
Máscara de rede em binário:

`11111111.1111111.1111111.11000000`

  
  
Máscara de rede em decimal:

`255.255.255.192`

  
  
Convertendo 73 em binário (Byte onde a máscara /26 divide):

**`01`**`001001 (os dois primeiros bits fazem parte do identificador da rede)`

  
  
Número de hosts:

2<sup>6</sup> = 64 hosts, sendo 2 reservados, "000000" para o endereço da rede e "111111" para o endereço de *broadcast*.

Endereços IP:

`200.130.2.(01`**`000000`**`) = 200.130.2.64  -> Identificador da rede`  
`200.130.2.(01`**`000001`**`) = 200.130.2.65  -+`  
`200.130.2.(01`**`000010`**`) = 200.130.2.66   | Endereços para hosts e roteadores`  
`...                                   | dentro da rede (2`<sup>`6`</sup>` - 2 = 62)`  
`200.130.2.(01`**`111110`**`) = 200.130.2.126 -+`  
`200.130.2.(01`**`111111`**`) = 200.130.2.127 -> `*`Broadcat`*` dentro da rede`

Exemplo 3  
Estrutura do endereçamento IP da rede dos Labs. Informática:

`Binário                              Decimal`  
`11111111.11111111.111111 00.00000000 255.255.252.0 Máscara /22`

`11000000.10101000.001010 00.00000000 192.168.40.0 Rede`  
`11000000.10101000.001010 00.00000001 192.168.40.1 ----+`  
`11000000.10101000.001010 00.00000010 192.168.40.2     |`  
`...                                                   |`  
`11000000.10101000.001010 00.11111111 192.168.40.255   |`  
`11000000.10101000.001010 01.00000000 192.168.41.0     |`  
`11000000.10101000.001010 01.00000001 192.168.41.1     |`  
`...                                                   |`  
`11000000.10101000.001010 01.11111111 192.168.41.255   | Hosts 1022`  
`11000000.10101000.001010 10.00000000 192.168.42.0     |`  
`11000000.10101000.001010 10.00000001 192.168.42.1     |`  
`...                                                   |`  
`11000000.10101000.001010 10.11111111 192.168.42.255   |`  
`11000000.10101000.001010 11.00000000 192.168.43.0     |`  
`11000000.10101000.001010 11.00000001 192.168.43.1     |`  
`...                                                   |`  
`11000000.10101000.001010 11.11111110 192.168.43.254 --+`  
`11000000.10101000.001010 11.11111111 192.168.43.252 Broadcast`

### Exercícios CIDR

Dado os **endereços IP** e as **máscaras de rede**, determinar:

:\*A **máscara de rede** na notação decimal;

:\*O endereço IP da rede, ou **identificador de rede**;

:\*A **quantidade de hosts** possíveis para esta rede;

:\*O **endereço de *broadcast*** da rede.

1.  200.100.50.33/24
2.  200.100.50.201/26
3.  200.100.208.45/20
4.  200.100.215.0/20
5.  200.163.1.2/11

## Divisão em sub-redes

O **CIDR** permite a uma instituição solicitar um **bloco de endereços** IP de qualquer tamanho [^1],

De posse de um bloco de endereços, a organização pode dividir seu bloco em **sub-redes**, criando suas próprias redes internas.

### Exemplo

Suponha que uma organização tenha recebido o **bloco de endereços** **200.23.34.0/23**.

1.  Qual o **tamanho do bloco**?
2.  Suponha se deseja **dividir o bloco /23 em 8 blocos menores**, um para cada sub-rede, como fica a divisão?
3.  Para cada **sub-rede**, determine o a **máscara de rede**, **identificador da sub-rede**, o ***broadcast* da sub-rede**, os **endereços IP** possíveis para a sub-rede.

Resolução  

Tamanho do bloco:

- A **máscara de rede /23** indica que os 23 primeiros bits do endereço identificam a rede, sobrando, portando, *'9 bits para identificar*hosts**'' dentro desta rede (**2<sup>9</sup>=512''').

Divisão do bloco em 8 sub-redes:

- Como preciso de 8 sub-redes, vou utilizar **3 bits (2<sup>3</sup>=8)** mais a esquerda dos identificadores de host do bloco total para identificar cada sub-rede[^2];
- Para cada **sub-rede**, restam **6 bits (2<sup>6</sup>=64) para os hosts** dentro de cada sub-rede.

<a href="Arquivo:CIDR2.png" class="wikilink" title="Arquivo:CIDR2.png">Arquivo:CIDR2.png</a>

Bloco completo de endereços IP:

`Organização     11001000.00010111.0010001`**`0.00000000`**`   200.23.34.0/23`

  
Os bits em negrito identificam os endereços disponíveis para a organização.

Divisão dos endereços IP para as sub-redes:

`Sub-rede 0  11001000.00010111.0010001`**`0.00`**`000000   200.23.34.0/26   -> ID sub-rede 0`  
`            11001000.00010111.0010001`**`0.00`**`000001   200.23.34.1/26   -+`  
`            11001000.00010111.0010001`**`0.00`**`000010   200.23.34.2/26    | Endereços IP`  
`            ...                                                     | da sub-rede 0`  
`            11001000.00010111.0010001`**`0.00`**`111110   200.23.34.62/26  -+ `  
`            11001000.00010111.0010001`**`0.00`**`111111   200.23.34.63/26  -> `*`Broadcast`*` sub-rede 0`

`Sub-rede 1  11001000.00010111.0010001`**`0.01`**`000000   200.23.34.64/26   -> ID sub-rede 1`  
`            11001000.00010111.0010001`**`0.01`**`000001   200.23.34.65/26   -+`  
`            11001000.00010111.0010001`**`0.01`**`000010   200.23.34.66/26    | Endereços IP`  
`            ...                                                      | da sub-rede 1`  
`            11001000.00010111.0010001`**`0.01`**`111110   200.23.34.126/26  -+ `  
`            11001000.00010111.0010001`**`0.01`**`111111   200.23.34.127/26  -> `*`Broadcast`*` sub-rede 1`

`Sub-rede 2  11001000.00010111.0010001`**`0.10`**`000000   200.23.34.128/26   -> ID sub-rede 2`  
`            11001000.00010111.0010001`**`0.10`**`000001   200.23.34.129/26   -+`  
`            11001000.00010111.0010001`**`0.10`**`000010   200.23.34.130/26    | Endereços IP`  
`            ...                                                      | da sub-rede 2`  
`            11001000.00010111.0010001`**`0.10`**`111110   200.23.34.190/26  -+ `  
`            11001000.00010111.0010001`**`0.10`**`111111   200.23.34.191/26  -> `*`Broadcast`*` sub-rede 2`

`Sub-rede 3  11001000.00010111.0010001`**`0.11`**`000000   200.23.34.192/26   -> ID sub-rede 3`  
`            11001000.00010111.0010001`**`0.11`**`000001   200.23.34.193/26   -+`  
`            11001000.00010111.0010001`**`0.11`**`000010   200.23.34.194/26    | Endereços IP`  
`            ...                                                      | da sub-rede 3`  
`            11001000.00010111.0010001`**`0.11`**`111110   200.23.34.254/26  -+ `  
`            11001000.00010111.0010001`**`0.11`**`111111   200.23.34.255/26  -> `*`Broadcast`*` sub-rede 3`

`Sub-rede 4  11001000.00010111.0010001`**`1.00`**`000000   200.23.35.0/26   -> ID sub-rede 4`  
`            11001000.00010111.0010001`**`1.00`**`000001   200.23.35.1/26   -+`  
`            11001000.00010111.0010001`**`1.00`**`000010   200.23.35.2/26    | Endereços IP`  
`            ...                                                     | da sub-rede 4`  
`            11001000.00010111.0010001`**`1.00`**`111110   200.23.35.62/26  -+ `  
`            11001000.00010111.0010001`**`1.00`**`111111   200.23.35.63/26  -> `*`Broadcast`*` sub-rede 4`

`Sub-rede 5  11001000.00010111.0010001`**`1.01`**`000000   200.23.35.64/26   -> ID sub-rede 5`  
`            ...`

`Sub-rede 6  11001000.00010111.0010001`**`1.10`**`000000   200.23.35.128/26   -> ID sub-rede 6`  
`            ...`

`Sub-rede 7  11001000.00010111.0010001`**`1.11`**`000000   200.23.35.192/26   -> ID sub-rede 7`  
`            ...   `

  
Os **3 bits em negrito** ilustram a divisão em **8 sub-redes** do bloco maior.

Note que todas as sub-redes tem máscara de rede **/26**.

### Exercícios Sub-Redes

1.  Um administrador dispõe do bloco de endereços IP 192.168.0.0/24 e precisa alocar endereços para montar a rede mostrada na figura conforme segue:
    - Sub-rede 1: 32 IPs;
    - Sub-rede 2: 16 IPs;
    - Sub-rede 3: 8 IPs.

      
    Faça uma alocação de endereços IP para cada sub-rede (sub-rede 1, 2 e 3) e responda:

    - Qual o endereço identificador de rede de cada sub-rede?
    - Qual a máscara de rede de cada sub-rede?
    - Qual o endereço de *broadcast* de cada sub-rede?

      
    <a href="Arquivo:RedesCIDR1.png" class="wikilink" title="Arquivo:RedesCIDR1.png">Arquivo:RedesCIDR1.png</a>

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h42min de 12 de junho de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: KUROSE, J.F; ROSS K. W. Redes de Computadores e a Internet: Uma abordagem *top-down*, São Paulo: Pearson, 2010.

[^2]: COMER, D. E. Interligação em Redes com TCP/IP, vol. 1, 5<sup>a</sup> ed., Rio de Janeiro: Elsevier/Campus, 2006.
