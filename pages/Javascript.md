## Introdução a JavaScript 2

**Iniciando o Tutorial...**

**Para quem é direcionado este Tutorial de JavaScript?..** *Para quem não sabe nada de JavaScript ainda, mas já sabe básico de HTML...*

**O que é JavaScript?** *É uma linguagem utilizada principalmente para auxílio de desenvolvimento de páginas para a Internet...*

**JavaScript é a mesma coisa que Java?** *Não, JavaScript é mais simples que Java. Aprender JavaScript é o melhor começo se você quer aprender Java, C, C++, PHP, pois a sintaxe (forma de escrever a linguagem) é semelhante.*

**O que posso fazer com o JavaScript?** *Você pode tornar suas páginas mais "inteligentes", com recursos adicionais como: botões que muudam ao passar o mouse em cima, exibir o horário atual, verificar se o preenchimento de um formulário está correto, e muito mais! O JavaScript pode lhe salvar nas horas em que você menos espera, pois as possibilidades de utilização são infinitas. Só não garanto que vá resolver o problema da fome no mundo ;).*

**02 - Onde coloco o código JavaScript?** ''O Código JavaScript fica Entre o

<script>

e o

</script>

. Ficaremos com a seguinte estrutura:''

`''`

<html>

<body>

<script>

`alert("Minha primeira mensagem!")`  

</script>

</body>

</html>

''

**Entendendo o código:** *alert("Minha primeira mensagem!")* Exibe uma janela com a frase **Minha primeira mensagem!** com apenas um botão de OK. Teste você mesmo, crie um arquivo com extensão .html e execute.

================================================================================================================

**03 - Exemplo básico, manipulação de variável** **Fazer aparecer na tela o resultado de um cálculo.**

`''`

<html>

<body>

<script>

`a = 2`  
`b = 9`  
`c= a + b`  
`alert(c)`  

</script>

</body>

</html>

''

**Entendendo o código:** a = 2 Faz com que a variável **a** receba o número 2.

b = 9 Faz com que a variável **b** receba o número 9.

c = a + b Faz com que a variável **c** receba o resultado de **a + b**.

**alert(c)** Faz com que uma janela exiba o conteúdo da variável **c**. Note que não usamos aspas na frente e atrás do c porque estamos consultando o valor de uma variável. Se colocássemos aspas, ele iria mostrar apenas a letra c, literalmente.

================================================================================================================

**04 - Expressões condicionais if** **Implementar o uso de expressões condicionais**

`''`

<html>

<body>

<script>

`bananas = 6`  
`if (bananas == 6)`  
`{`  
`   alert("É verdade. Temos meia dúzia de bananas")`  
`}`  

</script>

</body>

</html>

'' O**if** é a mais básica das expressões condicionais no JavaScript. Com ele, você pode decidir se quer executar uma ação ou não.

**Entendendo o código:** bananas = 6 Faz com que a variável "bananas" receba o número 6.

`'`**`'if`**` (bananas == 6)`  
`{`  
`    alert("É verdade. Temos meia dúzia de bananas")`  
`}''`

**Esta é a expressão condicional. Se ela for verdadeira (no caso, se bananas for igual a seis), entraremos no bloco de código. A seguir, temos a estrutura de um bloco de código.**

*Você pode fazer experimentos, trocando o "bananas = 6" por "bananas = 10" ou qualquer outro valor que não seja 6. Já que a condicional não vai ser verdadeira, ele simplesmente não entra no bloco do código que faz o alert("É verdade. Temos meia dúzia de bananas").*

================================================================================================================

**05 - Expressões seletoras switch** *Usar o switch para condições de comparações simples, ao invés de utilizar o if*

`''`

<html>

<body>

<script>

`farol = "amarelo"`  
`switch (farol) {`  
`case "vermelho":`  
`alert("Pare")`  
`break`  
`case "amarelo":`  
`alert("Atencao")`  
`break`  
`case "verde":`  
`alert("Prossiga")`  
`break`  
`default:`  
`alert("Cor ilegal")`  
`}`  

</script>

</body>

</html>

''

*Atenção, não esqueça do break! Sempre inclua um default. Se todas as condições anteriores forem falsas, o switch entrará no default. Ele é muito importante. O sistema de telefonia dos Estados Unidos já foi uma vez paralisada por várias horas por causa da falta de um default!*

==================================================================================

**06 - Expressões de loops for** **Usa-se o for quando se quer que um trecho de código se repita n vezes.**

`''`

<html>

<body>

<script>

`a = 2`  
`for (i = 0; i < 2; i++)`  
`{`  
`a = i`  
`}`  
`alert(a)`  

</script>

</body>

</html>

''

*A novidade é a linha de código acima mostrada em vermelho. Vamos analizá-la.*

**for (i = 0; i \< 2; i++)** Utilizamos uma variável temporária chamada i. Inicializamos ela com valor igual a zero.

**for (i = 0; i \< 2; i++)** O bloco do meio funciona como um if. Se o valor de i for menor que 2, ele entra no loop.

**for (i = 0; i \< 2; i++)** A última parte diz o que fazer com a variável i. Neste caso a cada repetição, estamos incrementando o valor de i. Se não fizéssemos isto, a condição anterior (i \< 2) sempre seria verdadeira, e entraríamos em um loop infinito, pois o valor de i sempre seria menor que dois. ================================================================================================================ **07 - Expressões de loops while** **Usa-se o while quando se quer que um trecho de código se repita n vezes, com condicional bem simples.**

`''`

<html>

<body>

<script>

`numero = 0`  
`while (numero < 10)`  
`{`  
`numero++`  
`}`  
`alert(numero)`  

</script>

</body>

</html>

''

Enquanto a condição for verdadeira, o bloco será executado. Note que dentro do bloco estamos executando um código que fará a condição ser falsa depois de algumas repetições. Se não fizéssemos a condição ficar falsa, ele entraria no que chamamos de loop infinito, o que não é nada bom.

================================================================================================================

**08- Expressões de loops do while** **Usa-se o do while quando se quer que um trecho de código se repita n vezes, mas executa o bloco de código antes da verificação da condição.**

`''`

<html>

<body>

<script>

`numero = 0`  
`do`  
`{`  
`numero++`  
`}`  
`while (numero < 10)`  
`alert(numero)`  

</script>

</body>

</html>

''

*A diferença de ter um **do** na frente é que o código será executado antes da condição ser verificada. Execute exemplo e verifique se o resultado é diferente do while normal..*

<a href="Categoria:Javascript" class="wikilink" title="Categoria:Javascript">Categoria:Javascript</a>
