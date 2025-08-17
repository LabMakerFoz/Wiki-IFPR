# Agendamento de Tarefas

O **agendamento de tarefas** permite agendar a execução de qualquer programa numa certa periodicidade ou em uma data e hora exata. O agendamento é útil para tarefas de manutenção como realização de backup, análise de segurança, atualizações, etc [^1].

No Ubuntu o agendamento é realizado através do programa **cron** e programado em uma tabela chamada **crontab** e **scripts shell** comuns.

A configuração da **crontab** tem duas partes:

- **global**, controlada pelo administrador;
- **usuário**, controlada pelo usuário.

## Crontab

Inicialização do serviço:

`service cron start`

Configuração da crontab por usuário  
Utiliza-se o comando **crontab** junto com um parâmetro:

`crontab -e #edita a crontab do usuário`  
`crontab -l #exibe o conteúdo atual da crontab`  
`crontab -r #remove a crontab do usuário`

  
As tabelas **crontab** dos usuários ficam armazenadas no diretório protegido:

`/var/spool/cron/crontab`

Configuração da crontab global  
A tabela **crontab** global somente pode ser editada pelo administrador e fica no arquivo:

`/etc/crontab`

### Formato da crontab

Cada **tarefa** a ser agendada deve ser escrita em uma linha da crontab.

Cada linha tem 6 campos, separados por espaço ou tabulação:

**`m h dom mon dow command`**

Onde:

- (**m**) minuto
- (**h**) hora
- (**dom**) dia do mês
- (**mon**) mês
- (**dow**) dia da semana

Para cada tarefa o agendamento define valores específicos ou pode-se usar '\*' nestes campos para definir 'qualquer'.

A especificação dos campos numéricos pode ser, por exemplo:

- valor absoluto: 0,20,40
- qualquer valor: \*
- por intervalo: 10-20
- periodicidade: valor absoluto/período : \*/5

Exemplos  

- Executar o comando ls -l e salvar o conteúdo no arquivo arq.txt nos minutos 0 e 10, toda hora, todo dia:

`0,10 * * * * ls -l >> arq.txt`

- Executar o script backup.sh todo domingo as 3 horas da manhã:

`0 3 * * 1 backup.sh`

- Executar o script backup.sh com periodicidade de 5 em 5 dias as 19h45:

`45 19 */5 * * backup.sh`

#### Exercícios

1.  Realizar agendamento para, a cada 3 minutos, executar o comando ls -l no diretório home e salvar em um arquivo com a indicação da hora.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 20h13min de 11 de novembro de 2015 (BRST)

------------------------------------------------------------------------

<a href="Categoria:Administração_de_Servidores" class="wikilink" title="Categoria:Administração de Servidores">Categoria:Administração de Servidores</a>

[^1]: VALLE, O. T. Adminstração de Redes com Linux: Fundamentos e práticas, IFSC, Florianópolis, 2010.
