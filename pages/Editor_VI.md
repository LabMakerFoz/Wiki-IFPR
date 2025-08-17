# Editor vi

O **vi** (*Visual Editor*) é um dos editores de texto mais usados no mundo Linux/Unix e está disponível em todas as versões e distribuições. Cabe destacar que sistemas embarcados, como num roteador ou equipamento de rede, o editor **vi** pode ser a única opção disponível.

Uma versão aprimorada deste editor é o **vim** (*VI Improved*), no qual é possível abrir múltiplos arquivos, usar seleção visual, mapeamento de teclas, seleção vertical de texto, uso de expressões regulares, sintaxe colorida, repetições entre outras coisas.

Material de referência  
[Aurelio.net](http://aurelio.net/vim)

<!-- -->

Instalação do vim  

`sudo apt-get install vim`

<a href="Arquivo:EditorVI.png" class="wikilink" title="Arquivo:EditorVI.png">Arquivo:EditorVI.png</a>

## Exercício com editor vi

O texto abaixo faz parte do arquivo de configuração dos usuários em um Servidor Linux.

`root:x:0:0:root:/root:/bin/bash`  
`daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin`  
`bin:x:2:2:bin:/bin:/usr/sbin/nologin`  
`sys:x:3:3:sys:/dev:/usr/sbin/nologin`  
`www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin`  
`backup:x:34:34:backup:/var/backups:/usr/sbin/nologin`  
`joaop:x:1000:1000:João Pereira,,,:/home/joaop:/bin/bash`  
`paulos:x:1001:1000:Paulo Silva,,,:/home/paulos:/bin/bash`  
`pedrog:x:1002:1001:Pedro Gomes,,,:/home/pedrog:/bin/bash`  
`miguelb:x:1003:1001:Miguell Batista,,,:/home/miguelb:/bin/bash`  
`marial:x:1004:1000:Maria Lima,,,:/home/marial:/bin/bash`  
`mariom:x:1005:1002:Mario Matias,,,:/home/mariom:/bin/bash`

1.  Abra o **editor vi** em seguida copie e cole o texto no editor.
2.  Modifique o nome do usuário João Pereira para João Victor Pereira.
3.  Corrija o nome do usuário Miguel, removendo somente a letra l excedente.
4.  Apague a linha do usuário Maria Lima.
5.  Copie e cole a última linha no final do arquivo.
6.  Cadastre um novo usuário, chamado Eduardo Moreira, que deverá ser cadastrado com as ID 1006:1001, modificando a última linha inserida no final do arquivo.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h24min de 22 de junho de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Administração_de_Servidores" class="wikilink" title="Categoria:Administração de Servidores">Categoria:Administração de Servidores</a> <a href="Categoria:Introdução_a_Informática_e_as_Redes_de_Computadores" class="wikilink" title="Categoria:Introdução a Informática e as Redes de Computadores">Categoria:Introdução a Informática e as Redes de Computadores</a>
