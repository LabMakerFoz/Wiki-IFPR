# Laboratório: Classes de Endereçamento

## Objetivos

Experimentar a criação de **redes** de tamanhos correspondentes as **classes A, B e C** a partir da configuração do **endereço IP** e da **máscara de rede**.

## Máscara de rede

Cada **endereço IP** engloba duas partes:

- **Identificador da rede**: identifica a rede onde se encontram todos os computadores da mesma rede local.
- **Identificador do *host***: identifica um dispositivo em uma rede local, como um computador ou roteador.

A **máscara de rede** define que parte do **endereço IP** que **identifica a rede** e que parte **identifica o *host*** dentro da rede.

## Classes de endereçamento

Quando o protocolo IP foi criado o **tamanho de uma rede** era definido por sua **classe de endereçamento**, especificada através das seguintes **máscaras de rede**:

- **Classe A**: máscara de rede /8 ou 255.0.0.0 -\> 2<sup>24</sup> *hosts*
- **Classe B**: máscara de rede /16 ou 255.255.0.0 -\> 2<sup>16</sup> *hosts*
- **Classe C**: máscara de rede /24 ou 255.255.255.0 -\> 2<sup>8</sup> *hosts*

## Laboratório

Neste laboratório utilizaremos **máquinas virtuais** utilizando o ambiente **VirtualBox**.

Para utilizar as máquinas virtuais, inicialmente abra **VirtualBox** e verifique se a configuração de **Rede** do VirtualBox está **conectado a placa em modo Bridge**. Em seguida inicialize a **máquina virtual** chamada **Redes**.

Importante  
Vamos modificar a configuração do endereçamento IP das **máquinas virtuais** do laboratório, portanto, antes de alterar a configuração de sua máquina virtual, anote o endereço IP, a máscara de rede (*netmask*) e o roteador padrão (*gateway*) para, posteriormente, voltarmos a configuração original.

`#Verificação da configuração IP`  
`ifconfig`

Endereços IP a serem utilizados no laboratório  
Cada equipe utilizará um dos endereços IP da tabela abaixo.

<table>
<caption>Numeração das Alas, Filas e Computadores do Laboratório 1</caption>
<tbody>
<tr>
<td><p>Lab</p></td>
<td colspan="5"><p>Ala 1</p></td>
<td></td>
<td colspan="3"><p>Ala 2</p></td>
</tr>
<tr>
<td><p>Fila 1</p></td>
<td><p>10.1.1.1</p></td>
<td><p>10.1.1.2</p></td>
<td><p>10.1.1.3</p></td>
<td><p>10.1.1.4</p></td>
<td><p>10.1.1.5</p></td>
<td></td>
<td><p>10.2.1.1</p></td>
<td><p>10.2.1.2</p></td>
<td><p>10.2.1.3</p></td>
</tr>
<tr>
<td><p>Fila 2</p></td>
<td><p>10.1.2.1</p></td>
<td><p>10.1.2.2</p></td>
<td><p>10.1.2.3</p></td>
<td><p>10.1.2.4</p></td>
<td><p>10.1.2.5</p></td>
<td></td>
<td><p>10.2.2.1</p></td>
<td><p>10.2.2.2</p></td>
<td><p>10.2.2.3</p></td>
</tr>
<tr>
<td><p>Fila 3</p></td>
<td><p>10.1.3.1</p></td>
<td><p>10.1.3.2</p></td>
<td><p>10.1.3.3</p></td>
<td><p>10.1.3.4</p></td>
<td><p>10.1.3.5</p></td>
<td></td>
<td><p>10.2.3.1</p></td>
<td><p>10.2.3.2</p></td>
<td><p>10.2.3.3</p></td>
</tr>
<tr>
<td><p>Fila 4</p></td>
<td><p>10.1.4.1</p></td>
<td><p>10.1.4.2</p></td>
<td><p>10.1.4.3</p></td>
<td><p>10.1.4.4</p></td>
<td><p>10.1.4.5</p></td>
<td></td>
<td><p>10.2.4.1</p></td>
<td><p>10.2.4.2</p></td>
<td><p>10.2.4.3</p></td>
</tr>
<tr>
<td><p>Fila 5</p></td>
<td><p>10.1.5.1</p></td>
<td><p>10.1.5.2</p></td>
<td><p>10.1.5.3</p></td>
<td><p>10.1.5.4</p></td>
<td><p>10.1.5.5</p></td>
<td></td>
<td><p>10.2.5.1</p></td>
<td><p>10.2.5.2</p></td>
<td><p>10.2.5.3</p></td>
</tr>
<tr>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

### Exercício 1:

Configure a interface de rede de seu computador com o respectivo **endereço IP**, conforme a tabela acima, e com **máscara de rede** igual a **255.255.255.0**.

Para configurar uma interface de rede no Ubuntu use o comando:

`sudo ifconfig eth0 10.x.y.z netmask 255.255.255.0 `

Verifique a nova configuração do endereçamento IP de sua máquina:

`ifconfig`

Verifique a tabela de roteamento de sua máquina:

`route -n`

Verifique com quais máquinas do laboratório seu computador consegue se comunicar:

`ping 10.x.y.z `

Responda:

1.  Qual o identificador de rede de seu computador?
2.  Qual o endereço de *broadcast* de sua rede?
3.  Qual o tamanho da sua rede?
4.  Quais outras máquinas pertencem a mesma rede de seu computador?
5.  Explique porque somente estas máquinas conseguem se comunicar com a sua.

Endereço de *broadcast*  
Ative na sua máquina virtual o **ping no endereço de *broadcast***:

**<a href="Laboratório:_Ping_no_endereço_de_difusão" class="wikilink" title="Laboratório: Ping no endereço de difusão">Laboratório: Ping no endereço de difusão</a>**, com o comando:

`sudo echo "0" > /proc/sys/net/ipv4/icmp_echo_ignore_broadcasts`

  
Para testar o *ping no endereço de*broadcast**'' deve-se utilizar a opção**-b''':

`ping -b 10.x.y.z (onde X é o `*`broadcast`*`)`

Exercícios:

1.  Teste o comando **ping no endereço de broadcast** e verifique quais máquinas consegue acessar;
2.  Explique porque aparece a mensagem DUP em algumas respostas do ping.

### Exercício 2:

Configure a interface de rede de seu computador com **um dos endereços da tabela acima** e com **máscara de rede** igual a **255.255.0.0**.

Para configurar uma interface de rede no Ubuntu use o comando:

`sudo ifconfig eth0 10.x.y.z netmask 255.255.0.0 `

Verifique a nova configuração do endereçamento IP de sua máquina:

`ifconfig`

Verifique a tabela de roteamento de sua máquina:

`route -n`

Verifique com quais máquinas do laboratório seu computador consegue se comunicar:

`ping 10.x.y.z `

Responda novamente:

1.  Qual o identificador de rede de seu computador?
2.  Qual o endereço de *broadcast* de sua rede?
3.  Qual o tamanho da sua rede?
4.  Teste novamente o ping no endereço de broadcasr;
5.  Quais outras máquinas se comunicam com a sua em relação ao exercício anterior?

### Exercício 3:

Configure a interface de rede de seu computador com **um dos endereços da tabela acima** e com **máscara de rede** igual a **255.0.0.0**.

Para configurar uma interface de rede no Ubuntu use o comando:

`sudo ifconfig eth0 10.x.y.z netmask 255.0.0.0 `

Verifique a nova configuração do endereçamento IP de sua máquina:

`ifconfig`

Verifique a tabela de roteamento de sua máquina:

`route -n`

Verifique com quais máquinas do laboratório seu computador consegue se comunicar:

`ping 10.x.y.z `

Responda novamente:

1.  Qual o identificador de rede de seu computador?
2.  Qual o endereço de *broadcast* de sua rede?
3.  Qual o tamanho da sua rede?
4.  Teste novamente o ping no endereço de broadcasr;
5.  Quais outras máquinas se comunicam com a sua em relação ao exercício anterior?

### Tarefa

Monte um arquivo **.txt** descrevendo os procedimentos realizados, juntamente com os comandos realizados em cada parte do exercício. Para cada exercício, responda as questões solicitadas.

Entregar a tarefa por email.

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 20h12min de 2 de julho de 2015 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>
