# Laboratório: Ping no endereço de difusão

Objetivos  
Utilizar aplicativo Ping para verificar a conectividade em rede e a identificar os hosts de uma rede a partir do endereço de difusão ou *broadcast*.

Os principais aplicativos a serem utilizados são o **ifconfig** e **ping**.

Rever antes de iniciar: <a href="Laboratório:_Verificação_do_endereço_IP_e_conectividade_na_Internet" class="wikilink" title="Laboratório: Verificação do endereço IP e conectividade na Internet">Laboratório: Verificação do endereço IP e conectividade na Internet</a>.

Exercício 1  
Os exercícios devem ser realizados na **Máquina Virtual Ubuntu**, pois necessitam de parmissão de administrador (*root*).

1.  Executar o comando **ifconfig** e verificar o **endereço IP** da máquina, a **máscara de rede** e o **endereço de broadcast**.
2.  Executar o **ping** para diferentes hosts e verificar as respostas;

*Broadcast*  
Se desejarmos descobrir o endereço IP de vários *hosts* em uma rede local, poderemos utilizar o **ping** no endereço de ***broadcast***.

<!-- -->

  
Neste caso, deve-se executar o **ping** com a **opção -b**. No Ubunto esta opção está desabilitada por *default*. Para habilitar execute o comando:

`sudo echo "0" > /proc/sys/net/ipv4/icmp_echo_ignore_broadcasts`

Exercício 2  
**Ping** no endereço de ***broadcast***:

`ping -b 192.168.10.255`

1.  Executar o **ping** no endereço de ***broadcast*** da rede local;
2.  Verifique a quantidade de *hosts* diferentes que responderam ao ping;
3.  Explique porque aparece o termo **DUP!** após cada resposta do ping no endereço de *broadcast*?

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h39min de 12 de junho de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>
