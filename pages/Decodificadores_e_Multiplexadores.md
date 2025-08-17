# Decodificadores

O **decodificador** é um circuito combinacional que recebe como entrada um número binário e ativa apenas a saída correspondente ao número recebido, as demais saídas permanecem desativadas.

Veja um exemplo de um decodificador de 2 linhas de entrada para 1 de 4 linhas de saída. Para cada combinação de entrada (2<sup>2</sup> possibilidades), apenas uma saída é selecionada.

<a href="Arquivo:Decodificador2-4.png" class="wikilink" title=" 250px"> 250px</a>

Exercício de simulação  

- Simule o [Decodificador 1-de-4](http://www.falstad.com/circuit/e-decoder.html) e construa sua tabela verdade.

Exercício  

1.  Construa um decodificador com 3 linhas de entrada para 1 de 8 saídas.

Aplicação dos decodificadores  
Seleção de endereço de memórias

Uma aplicação importante dos decodificadores, interna a um chip de memória, é atuar como dispositivo para selecionar uma posição de **memória** para um dado ser armazenado no computador.

Cada posição de memória tem um **endereço**, fornecido por um **número binário**, o qual será a entrada do decodificador que indicará ao chip a posição selecionada da memória. Esta é a explicação do porque os tamanhos dos dispositivos de memória sempre são múltiplos de 2<sup>n</sup>.

<a href="Arquivo:DecodificadorMemoria.png" class="wikilink" title=" Decodificador de endereço de memória"> Decodificador de endereço de memória</a>

Exercícios  

1.  Para que um computador acesse uma memória RAM de 512 Mi (Mibi ou Mega) Bytes, quantas linhas de endereço ele precisa ter?
2.  Se o seu computador tem um limite de expansão da memória RAM de 4 Gi (Giga ou Gibi) Bytes, quantas linhas de endereço de memória ele possui?
3.  Pesquise sobre a capacidade de expansão de memória RAM dos computadores pessoais modernos.

## Tarefa: Exercícios de Simulação

Para este laboratório será utilizado o <a href="Simulador_de_Circuitos_Lógicos_-_Logisim" class="wikilink" title="Simulador de Circuitos Lógicos - Logisim">Simulador de Circuitos Lógicos - Logisim</a>  
Veja no *link* as instruções para *download* e instalação do programa.

### Decodificadores

1.  Construír com **portas lógicas** um circuito decodificador de 2 bits de entrada e 1 de 4 saídas.
2.  Construír com **portas lógicas** um circuito decodificador de 3 bits de entrada e 1 de 8 saídas.
3.  Construir e simular um decodificador de 2 bits de entrada e 1 de 4 saídas a partir do módulo **decodificador** disponível no Logisim.
    - Comparar a saída com o decodificador construído com portas lógicas.
4.  Modificar o circuito para que funcione como decodificador de 3 bits de entrada e 1 de 8 saídas.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h47min de 12 de junho de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Sistemas_Digitais" class="wikilink" title="Categoria:Sistemas Digitais">Categoria:Sistemas Digitais</a>
