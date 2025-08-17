# Comandos Básicos Linux

Origem do Linux  
O sistema operacional **Linux** foi desenvolvido pelo programador finlandês Linus Torvalds insperado no sistema **Minix** [^1]. Este último, por sua vez, é um sistema baseado no **Unix**, construído para fins didáticos por Andrew S. Tanenbaum, visando explicar o funcionamento e o projeto de um sistema operacional [^2].

<!-- -->

Linux Ubuntu  
O **Ubuntu** é um **sistema operacional** de código aberto, baseado no **Debian**. O **Ubuntu** lança uma nova versão do sistema a cada seis meses, nos meses de **abril** (**04**) e **outubro** (**10**). A cada dois anos é lançada uma versão chamada **Longo Tempo de Suporte** (**LTS**), na qual o suporte é três anos para desktops. Por exemplo, a versão 16.04 é a última versão LTS lançada. Depois desta, foram lançadas as versões 16.10, 17.04 e 17.10. A próxima versão será a LTS 18.04.

Nos labotórios do Campus Foz do Iguaçu do IFPR o Ubuntu é o sistema operacional escolhido.

## Comandos Básicos Linux

O Ubuntu possui uma **interface gráfica** chamada **Gnome**. Entretanto, para facilitar a instalação de aplicativos e outras tarefas, muitas vezes é necessário executar **comandos de linha** em um **terminal**.

Um **terminal** é o local onde você digita os comandos para dizer ao computador o que ele deve fazer.

Site para treinar comandos básicos  
[Terminal Linux](http://cb.vu/).

<!-- -->

Sites com comandos básicos para revisar  

- <http://www.infowester.com/comandoslinux.php>
- <https://www.vivaolinux.com.br/dica/Comandos-basicos-para-iniciantes>

### Comandos Básicos de Arquivos e Diretórios

Um bom usuário Linux deve dominar um conjunto de **comandos de linha**, pois muitas das ações no sistema serão facilitadas se realizadas via **terminal de comandos**.

Principais comandos a disposição do usuário para o dia a dia no sistema  

**`cd`**` - muda diretório`  
**`pwd`**` - mostra diretório atual`  
**`ls`**` - lista conteúdo do diretório atual`  
**`ls -l`**` - para ver permissões de acesso`  
**`ls -a`**` - para ver arquivos ocultos`  
**`cat`**` - lista conteúdo de um arquivo`  
**`cp`**` - cópia de arquivos`  
**`cp -r`**` - cópia recursiva para diretórios`  
**`mv`**` - mover arquivos e diretórios`  
**`rm`**` - remover arquivos e diretórios`  
**`mkdir`**` - criar diretórios`  
**`rmdir`**` - remover diretórios`  
**`man`**` - ajuda sobre comandos`

### Exercícios

1.  Na interface gráfica do Ubuntu, abrir o **Gerenciador de Arquivos** e navegar pela árvore de diretórios do sistema.
2.  Abra um **terminal** de comandos e utilize os comandos **pwd** e **cd** para navegar pela árvore de diretórios do sistema e o comando **ls -l** para listar o conteúdo dos diretórios.

## Estrutura de arquivos e diretórios do Linux

O **diretório raiz** (**/**) do Linux apresenta a seguinte lista de diretórios:

`$ ls /`  
`bin    dev   lib     proc  sbin  tmp  `  
`boot   etc   media   root  opt   usr  `  
`cdrom  home  mnt`

Descrição e função dos diretórios:

- **/home**: Diretório ***home* dos usuários**.
- **/root**: Diretório ***home* do superusuário**.
- **/bin**: Arquivos **binários executáveis** de comandos essenciais, como o cp, mv e grep.
- **/boot**: Arquivos relacionados ao ***boot**'' e ao***kernel**''.
- **/dev**: Arquivos associados a **ponteiros para dispositivos físicos**, como os discos rígidos, placas de som e vídeo etc.
- **/etc**: **Arquivos de configuração** dos sistemas e aplicativos instalados na máquina.
- **/lib**: **Bibliotecas** do sistema.
- **/mnt**: Diretório de **montagem** dos dispositivos de armazenamento .
- **/media**: Diretório de montagem dos **sistemas de arquivos temporários**, como *pendriver*.
- **/cdrom**: Diretório de montagem do **CD-ROM**.
- **/opt**: Arquivos de **programas de terceiros**, que não acompanham a distribuição.
- **/proc**: Diretório de informações de **processos e hardware** do sistema.
- **/sbin**: Arquivos **binários executáveis** do superusuário.
- **/tmp**: **Arquivos temporários**.
- **/usr**: Onde ficam a maioria dos **aplicativos** instalados no sistema.
- **/var**: **Arquivos de dados variáveis**, como *spool* de impressão, os arquivos de *cache* e arquivos de log.

## Edição de textos

A edição de pequenos arquivos a partir de um terminal pode ser realizada com o comando

`cat > nome_arquivo`

após a edição pode utilizar os comandos

`CTRL-D para salvar`  
`CTLR-C para sair sem salvar`

Para continuar a edição de um documento existente pode-se usar o comando

`cat >> nome_arquivo`

### Editor vi

O **vi** (*Visual Editor*) é um dos editores de texto mais usados no mundo Linux/Unix e está disponível em todas as versões e distribuições. Cabe destacar que sistemas embarcados, como num roteador ou equipamento de rede, o editor **vi** pode ser a única opção disponível.

Uma versão aprimorada deste editor é o **vim** (*VI Improved*), no qual é possível abrir múltiplos arquivos, usar seleção visual, mapeamento de teclas, seleção vertical de texto, uso de expressões regulares, sintaxe colorida, repetições entre outras coisas.

Instalação do vim  

`sudo apt-get install vim`

<a href="Arquivo:EditorVI.png" class="wikilink" title="Arquivo:EditorVI.png">Arquivo:EditorVI.png</a>

### Editor nano

O editor **nano** é um editor de textos simples, que pode ser utilizado a partir de um ternimal de comandos.

`nano nome_arquivo`

Os comandos para para copiar, recortar, colar, salvar e outros sempre começão com a tecla CTRL, que deve ser mantida pressionada:

- CTRL-x - Sai do editor.
- CTRL-k - 'recorta' o texto.
- CTRL-U - 'cola' o texto.
- CTRL S - Salva o arquivo e continua trabalhando.
- CTRL-w - faz uma busca no texto.
- CTRL-a- leva o cursor para o início da linha.
- CTRL-e - leva o cursor para o fim da linha.
- CTRL-g - mostra a ajuda do Nano.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 09h13min de 23 de fevereiro de 2018 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Administração_de_Servidores" class="wikilink" title="Categoria:Administração de Servidores">Categoria:Administração de Servidores</a>

[^1]: <https://pt.wikipedia.org/wiki/Linux>

[^2]: <https://pt.wikipedia.org/wiki/MINIX>
