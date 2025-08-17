# Laboratório: Máscaras de Rede

Para este laboratório é importante revisar o papel da **máscara de rede** no **<a href="Classes_de_Endereçamento" class="wikilink" title=" Endereçamento CIDR"> Endereçamento CIDR</a>**, ou **endereçamento IP sem classes**.

## Objetivos

Experimentar a criação de **sub-redes** de diferentes tamanhos a partir da configuração do **endereço IP** e da **máscara de rede**.

## Máscara de rede e criação de sub-redes

Quando configuramos o TCP/IP num computador, devemos configurar o **endereço IP** e a **máscara de rede**.

A máscara de rede define que parte do endereço IP identifica a rede e que parte identifica o *host* dentro da rede.

### Exemplos de máscaras de rede

Suponha que um administrador de rede possua um **bloco de endereço** com **máscara de rede** **255.255.255.0**.

Máscara de rede /24 ou 255.255.255.0  
**Bloco total**: Pode endereçar 2<sup>8</sup> -2 endereços IP.

|                  |                     |                      |
|------------------|---------------------|----------------------|
| Endereço de rede | Endereços de *host* | Endereço *broadcast* |
| x.x.x.0          | x.x.x.1 - x.x.x.254 | x.x.x.255            |

#### Possibilidades de divisão em sub-redes

Máscara de rede /25 ou 255.255.255.128  
Pode representar 2 sub-redes cada uma com 2<sup>7</sup> -2 endereços IP.

|                  |                       |                      |
|------------------|-----------------------|----------------------|
| Endereço de rede | Endereços de *host*   | Endereço *broadcast* |
| x.x.x.0          | x.x.x.1 - x.x.x.126   | x.x.x.127            |
| x.x.x.128        | x.x.x.129 - x.x.x.254 | x.x.x.255            |

Máscara de rede /26 ou 255.255.255.192  
Pode representar 4 sub-redes cada uma com 2<sup>6</sup> -2 endereços IP.

|                  |                       |                      |
|------------------|-----------------------|----------------------|
| Endereço de rede | Endereços de *host*   | Endereço *broadcast* |
| x.x.x.0          | x.x.x.1 - x.x.x.62    | x.x.x.63             |
| x.x.x.64         | x.x.x.65 - x.x.x.126  | x.x.x.127            |
| x.x.x.128        | x.x.x.129 - x.x.x.190 | x.x.x.191            |
| x.x.x.192        | x.x.x.193 - x.x.x.254 | x.x.x.255            |

Máscara de rede /27 ou 255.255.255.224  
Pode representar 8 sub-redes cada uma com 2<sup>5</sup> -2 endereços IP.

|                  |                       |                      |
|------------------|-----------------------|----------------------|
| Endereço de rede | Endereços de *host*   | Endereço *broadcast* |
| x.x.x.0          | x.x.x.1 - x.x.x.30    | x.x.x.31             |
| x.x.x.32         | x.x.x.33 - x.x.x.62   | x.x.x.63             |
| x.x.x.64         | x.x.x.65 - x.x.x.94   | x.x.x.95             |
| x.x.x.96         | x.x.x.93 - x.x.x.126  | x.x.x.127            |
| x.x.x.128        | x.x.x.129 - x.x.x.158 | x.x.x.159            |
| x.x.x.160        | x.x.x.161 - x.x.x.190 | x.x.x.191            |
| x.x.x.192        | x.x.x.193 - x.x.x.222 | x.x.x.223            |
| x.x.x.224        | x.x.x.225 - x.x.x.254 | x.x.x.255            |

Máscara de rede /28 ou 255.255.255.240  
Pode representar 16 sub-redes cada uma com 2<sup>4</sup> -2 endereços IP.

|                  |                     |                      |
|------------------|---------------------|----------------------|
| Endereço de rede | Endereços de *host* | Endereço *broadcast* |
| x.x.x.0          | x.x.x.1 - x.x.x.14  | x.x.x.15             |
| x.x.x.16         | x.x.x.17 - x.x.x.30 | x.x.x.31             |
| x.x.x.32         | x.x.x.33 - x.x.x.46 | x.x.x.47             |
| x.x.x.48         | x.x.x.49 - x.x.x.62 | x.x.x.63             |
| x.x.x.64         | x.x.x.65 - x.x.x.78 | x.x.x.79             |
| x.x.x.80         | x.x.x.81 - x.x.x.94 | x.x.x.95             |
| ...              | ...                 | ...                  |

Máscara de rede /29 ou 255.255.255.248  
Pode representar 32 sub-redes cada uma com 2<sup>3</sup> -2 endereços IP.

|                  |                     |                      |
|------------------|---------------------|----------------------|
| Endereço de rede | Endereços de *host* | Endereço *broadcast* |
| x.x.x.0          | x.x.x.1 - x.x.x.6   | x.x.x.7              |
| x.x.x.8          | x.x.x.9 - x.x.x.14  | x.x.x.15             |
| x.x.x.16         | x.x.x.17 - x.x.x.22 | x.x.x.23             |
| x.x.x.24         | x.x.x.25 - x.x.x.30 | x.x.x.31             |
| x.x.x.32         | x.x.x.33 - x.x.x.38 | x.x.x.39             |
| x.x.x.40         | x.x.x.41 - x.x.x.46 | x.x.x.47             |
| x.x.x.48         | x.x.x.49 - x.x.x.54 | x.x.x.55             |
| x.x.x.56         | x.x.x.57 - x.x.x.62 | x.x.x.63             |
| ...              | ...                 | ...                  |

Máscara de rede /30 ou 255.255.255.252  
Pode representar 64 sub-redes cada uma com 2<sup>2</sup> -2 endereços IP.

|                  |                     |                      |
|------------------|---------------------|----------------------|
| Endereço de rede | Endereços de *host* | Endereço *broadcast* |
| x.x.x.0          | x.x.x.1 - x.x.x.2   | x.x.x.3              |
| x.x.x.4          | x.x.x.5 - x.x.x.6   | x.x.x.7              |
| x.x.x.8          | x.x.x.9 - x.x.x.10  | x.x.x.11             |
| x.x.x.12         | x.x.x.13 - x.x.x.14 | x.x.x.15             |
| x.x.x.16         | x.x.x.17 - x.x.x.18 | x.x.x.19             |
| x.x.x.20         | x.x.x.21 - x.x.x.22 | x.x.x.23             |
| x.x.x.24         | x.x.x.25 - x.x.x.26 | x.x.x.27             |
| x.x.x.28         | x.x.x.29 - x.x.x.30 | x.x.x.31             |
| x.x.x.32         | x.x.x.33 - x.x.x.34 | x.x.x.35             |
| x.x.x.36         | x.x.x.37 - x.x.x.38 | x.x.x.39             |
| ...              | ...                 | ...                  |

Máscara de rede /31 ou 255.255.255.254  
Esta máscara somente permite 2 endereços IP (endereço de rede e o *broadcast*), portanto, não é utilizada para endereçar sub-redes.

## Exercícios[^1]

Importante  
Vamos modificar a configuração do endereçamento IP das máquinas virtuais do laboratório, portanto, antes de alterar a configuração de sua máquina virtual, anote o endereço IP, a máscara de rede (*netmask*) e o roteador padrão (*gateway*) para, posteriormente, voltarmos a configuração original.

<!-- -->

Endereços IP a serem utilizados no laboratório  
Cada equipe utilizará um dos endereços IP da tabela abaixo.

|               |                |
|---------------|----------------|
| Computador 1  | 192.168.100.1  |
| Computador 2  | 192.168.100.2  |
| Computador 3  | 192.168.100.5  |
| Computador 4  | 192.168.100.6  |
| Computador 5  | 192.168.100.9  |
| Computador 6  | 192.168.100.10 |
| Computador 7  | 192.168.100.13 |
| Computador 8  | 192.168.100.14 |
| Computador 9  | 192.168.100.17 |
| Computador 10 | 192.168.100.18 |
| Computador 11 | 192.168.100.21 |
| Computador 12 | 192.168.100.22 |
| Computador 13 | 192.168.100.25 |
| Computador 14 | 192.168.100.26 |
| Computador 15 | 192.168.100.29 |
| Computador 16 | 192.168.100.30 |

### Exercício 1:

Configure a interface de rede de seu computador com **um dos endereços da tabela acima** e com **máscara de rede** igual a **255.255.255.252**.

Para configurar uma interface de rede no Ubuntu use o comando:

`sudo ifconfig eth0 192.168.100.x netmask 255.255.255.252 `

Ative na sua máquina virtual o **ping no endereço de *broadcast*** (ver <a href="Laboratório:_Ping_no_endereço_de_difusão" class="wikilink" title="Laboratório: Ping no endereço de difusão">Laboratório: Ping no endereço de difusão</a>) com o comando:

`sudo echo "0" > /proc/sys/net/ipv4/icmp_echo_ignore_broadcasts`

Responda:

1.  Qual o identificador de rede de seu computador?
2.  Qual o endereço de *broadcast* de sua rede?
3.  Qual o tamanho da sua rede?
4.  Quais outras máquinas pertencem a mesma rede de seu computador?
5.  Verifique com o comando **ping** as máquinas que você consegue acessar.
    - Teste o comando **ping no endereço de broadcast**:

`ping -b 192.168.100.X (onde X é o `*`broadcast`*`)`

### Exercício 2

Altere a **máscara de rede** para **255.255.255.248**.

`sudo ifconfig eth0 netmask 255.255.255.248 `

Responda:

1.  Qual o identificador de rede de seu computador?
2.  Qual o endereço de *broadcast* de sua rede?
3.  Qual o tamanho da sua rede?
4.  Quais outras máquinas pertencem a mesma rede de seu computador?
5.  Verifique com o comando **ping** as máquinas que você consegue acessar.

### Exercício 3

Altere a **máscara de rede** para **255.255.255.240**.

`sudo ifconfig eth0 netmask 255.255.255.240 `

Responda:

1.  Qual o identificador de rede de seu computador?
2.  Qual o endereço de *broadcast* de sua rede?
3.  Qual o tamanho da sua rede?
4.  Quais outras máquinas pertencem a mesma rede de seu computador?
5.  Verifique com o comando **ping** as máquinas que você consegue acessar.

### Exercício 4

Altere a **máscara de rede** para **255.255.255.224**.

`sudo ifconfig eth0 netmask 255.255.255.224 `

Responda:

1.  Qual o identificador de rede de seu computador?
2.  Qual o endereço de *broadcast* de sua rede?
3.  Qual o tamanho da sua rede?
4.  Quais outras máquinas pertencem a mesma rede de seu computador?
5.  Verifique com o comando **ping** as máquinas que você consegue acessar.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h35min de 11 de agosto de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: ROYER, J.C. Exercícios realizados pelo professor Júlio César Royer, IFPR.
