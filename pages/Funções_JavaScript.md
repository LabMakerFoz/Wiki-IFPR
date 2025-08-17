## Funçoes em JavaScript

*Vou tentar passar um pouco sobre funções em JavaScript. Elas são muito utilizadas e devem ser bem aproveitadas pelos seus aspectos positivos, não só em JavaScript, mas como em qualquer outra linguagem de programação, que são: O código fica bem organizado, você ganha tempo e espaço, o seu código é executado com melhor desempenho e você pode executar quantas vezes desejar a sua função.*

*Para a criaçãao de uma função em JavaScript, devemos fazer seguindo o modelo:*

`'''function nome-da-função {`  
`//`  
`é o parametro utilizado para a criação da função, portanto é`  
`uma palavra reservada para criação da função em JavaScript.`  
`ação da funçãojngyghnghjguh`  
`// Aqui se executa as funções que deseja.`  
`}'''`

*E para executar essa função posteriormente basta usar:*

nome-da-função();

*Muito simples. E muitas pessoas quando falamos: "Precisar usar função!" fica desesperada. Vamos para um exemplo bem simples para facilitar ainda mais o seu entendimento.*

`'''`  

<script>

`function exemplo() {`  
`// Criando a função chamada exemplo`  
`document.write("Estou testando minha primeira função em JavaScript!");`  
`// Escreve na tela a mensagem.`  
`}`  
` `  
`// Chamando a função teste`  
`exemplo()`  

</script>

`'''`  

*Agora que ja sabemos como criar uma função em JavaScript, vamos dar um exemplo mais interessante, onde o cliente clica em um botão e é executada uma função.*

`'''`  

<script>

`function clica() {`  
`document.getElementById("texto").innerHTML="Voce clicou no botao!";`  
`}`  

</script>

<input type=button onClick="clica();" value="Enviar">  

<div id="texto">

</div>

`'''`

*Vamos melhor o código acima? Imaginemos que você precisa, para todo botão enviar de seu website, mandar a mesma mensagem do exemplo anterior. Para isso, precisamos colocar a função em um arquivo separado de sua página (arquivo.js) e iremos chamá-lo nas páginas que necessitarmos, seja ela HTML e/ou PHP.*

*Crie o arquivo: funcao.js*

`'''function clica() {`  
`document.getElementById("texto").innerHTML="Voce clicou no botao!";`  
`}'''`

*Agora no arquivo exemplo.html*

`'''`  

<script language="JavaScript" src="funcao.js">

</script>

<input type=button onClick="clica();" value="Enviar">  

<div id="texto">

</div>

`'''`

''Existem também funções do javascript já predefinidas, são elas:

**atob(base64):** Converte um texto codificado em base64 para binário. Função inversa ao btoa(texto) **btoa(texto):** Converte um texto para base64. Função inversa ao atob(base64). **decodeURI(url):** Função inversa ao encodeURI **decodeURIComponent(url):** Função inversa ao encodeURIComponent **isFinite(valor):** Identifica se o numero é finito. **isNaN(valor):** Identifica se o valor não é um numero **encodeURI(url)**: como o escape ele faz substituições no texto para compatibilizar transferencia em links, mas não faz conversão para os caracteres !\*()' **encodeURIComponent(url)** como o escape ele faz substituições no texto para compatibilizar transferencia em links, mas não faz conversão para os caracteres !@#\$&\*()=:/;?+' **escape(url)**: Ajusta url para que possa ser passada em chamadas e links, convertendo os caracteres especiais para formato hexadecimal e espaço para o sinal de +, não faz mudança nos caracteres @\*/+ que ficam inalterados **eval(expressao)** Interpreta expressão de JavaScript, ex: **eval(“1+2”)**, resultado = 3 **parseInt(String)** ou **parseInt(String, base):** Converte a string num valor inteiro, ou converte uma string na base passada para inteiro. **Number(objeto):** Converte a string num valor ponto flutuante **parseFloat(String):** Converte a string num valor ponto flutuante **String(objeto):** Retorna a representação string do objeto **unescape(url):** Função inversa ao escape(url)''

## Tutorial JavaScript no YouTube.

[**JavaScript Tutorial**](http://www.youtube.com/watch?v=bmRH9l0Rn5Q)

<a href="Categoria:Javascript" class="wikilink" title="Categoria:Javascript">Categoria:Javascript</a>
