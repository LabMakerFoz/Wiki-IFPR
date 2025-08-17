# Comutação de pacotes x Comutação de circuitos

Nas redes de computadores se utiliza a **comutação de pacotes** como tecnologia de comunicação no núcleo da rede, em contraste com as redes telefônicas tradicionais que usam a **comutação de circuitos**.

Comutação de circuitos  
Foi por muito tempo a forma de comutação utilizada no sistema telefônico. Quando dois usuários desejavam se comunicar a rede estabelecia um **circuito dedicado fim-a-fim** entre os dois aparelhos telefônicos. O circuito estabelecido ficava **reservado** durante toda a duração da conversação.

<a href="Arquivo:ComutacaoCircuitos.jpg" class="wikilink" title="Arquivo:ComutacaoCircuitos.jpg">Arquivo:ComutacaoCircuitos.jpg</a> [^1]

  
A comutação de circuitos, entretanto, é ineficiente para ser aplicada nas redes de computadores devido as características do tráfego nestas redes, o qual é caracterizado por um fluxo esporádico de dados, com curtos intervalos de atividade espaçados no tempo, diferente do fluxo contínuo do tráfego telefônico.

<!-- -->

Comutação de pacotes  
Não há estabelecimento de circuito fim a fim entre os dois sistemas terminais que desejam se comunicar. Por exemplo, quando um computador deseja enviar uma informação a outro computador da rede, ele encapsula a informação em um **pacotes de dados**, inclui em um **cabeçalho** o endereço do destinatário e envia pela rede. O pacote será então encaminhado de roteador em roteador em função do endereço do destino. Na comutação de pacotes **não há reserva de recursos** da rede, mas sim compartilhamento de recursos na forma de uma **multiplexação estatística**.

<a href="Arquivo:ComutacaoPacotes.jpg" class="wikilink" title="Arquivo:ComutacaoPacotes.jpg">Arquivo:ComutacaoPacotes.jpg</a> [^2]

Os defensores da comutação de pacotes argumentam que a comutação de circuitos é ineficiente, pois reserva o circuito mesmo durante os períodos de silêncio na comunicação. Por exemplo, durante uma conversa telefônica, os silêncios da conversação, ou as esperas para chamar uma outra pessoa, não podem ser utilizados para outras conexões. Além disto, os tempos necessários para o estabelecimento de circuitos fim-a-fim são grandes, além de ser uma tarefa complicada e requerer esquemas complexos de sinalização ao longo de todo o caminho da comunicação.

Por outro lado, os opositores da comutação de pacotes argumentam que a mesma não seria apropriada para aplicações tempo real, como por exemplo conversas telefônicas, devido os atrasos variáveis em filas de espera, difíceis de serem previstos. Todavia, com o desenvolvimento de técnicas específicas e o aumento da velocidade dos enlaces, observa-se uma tendência em direção à migração dos serviços telefônicos também para a tecnologia de comutação de pacotes.

### Exercícios

1.  Qual a vantagem de uma rede de **comutação de pacotes** em relação a **comutação de circuitos** para comunicação de dados?
2.  Qual a técnica de comutação utilizada no sistema de **telefonia fixa** da maioria operadoras de telecomunicações no Brasil?
3.  Qual a técnica de comutação utilizada numa **chamada de voz** utilizando o aplicativo **WhatsApp**. Avalie a qualidade desta comunicação em relação a telefonia fixa.

### Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 15h36min de 20 de fevereiro de 2015 (BRST)

------------------------------------------------------------------------

<a href="Categoria:Redes_de_Computadores" class="wikilink" title="Categoria:Redes de Computadores">Categoria:Redes de Computadores</a>

[^1]: <http://www.teleco.com.br/tutoriais/tutorialvoipconv/pagina_3.asp>

[^2]:
