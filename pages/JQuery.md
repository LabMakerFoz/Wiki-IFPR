jQuery é uma biblioteca JavaScript cross-browser desenvolvida para simplificar os scripts client side que interagem com o HTML.1 Ela foi lançada em janeiro de 2006 no BarCamp de Nova York por John Resig. Usada por cerca de 55% dos 10 mil sites mais visitados do mundo, jQuery é a mais popular das bibliotecas JavaScript.2 3

jQuery é uma biblioteca de código aberto e possui licença dual, fazendo uso da Licença MIT ou da GNU General Public License versão 2.4 A sintaxe do jQuery foi desenvolvida para tornar mais simples a navegação do documento HTML, a seleção de elementos DOM, criar animações, manipular eventos e desenvolver aplicações AJAX. A biblioteca também oferece a possibilidade de criação de plugins sobre ela. Fazendo uso de tais facilidades, os desenvolvedores podem criar camadas de abstração para interações de mais baixo nível, simplificando o desenvolvimento de aplicações web dinâmicas de grande complexidade.

## Usando JQuery

Um dado importante de se saber sobre o JQuery, é que para pegar um elemento por id, classe ou tag é usado o cifrão (\$).

### Primeiro passo

Colocar o código javascript abaixo no início do arquivo html, dentro da tag \<head\>

``` javascript
<script>
$(document).ready(function(){
   
});
</script>
```

Dentro deste bloco de código colocamos o código JQuery que deseja-se executar. Por exemplo, para testarmos se o JQuery está funcionando podemos fazer o seguinte teste:

``` javascript
<script>
$(document).ready(function(){
   alert('JQuery funcionando');
});
</script>
```

##### Por exemplo:

Quando o cifrão está pegando um elemento por id, é preciso usar a cerquilha antes da palavra.

``` javascript
$("#idDoElemento").css("color", "red");
```

Quando o cifrão está pegando um elemento pela classe, é preciso usar um ponto antes da palavra.

``` javascript
$(".classeDoElemento").css("color", "red");
```

Quando o cifrão está pegando um elemento por sua tag, só é necessário colocar o nome da tag.

``` javascript
$("div").css("color", "red");
```

### Exemplo Basico

``` javascript
$(document).ready(function(){alert("Olá Mundo JQUERY!");});
```

{{#ev:youtube\|dQVLctAytQ0}}

### Hide e Show

Vai mostrar(show) ou esconder(hide) um elemento.

##### Exemplo:

``` javascript
$('document').ready(function(){
    $('#clickme').bind("click", function(){
        if($("#clickme").is(":checked")){ //se o checkbox estiver marcado
            $("#super").hide(); //ele esconde o elemento com o id #super                        
        }else{ //se não estiver marcado
            $("#super").show(); //ele mostra o elemento com o id #super
        }

    });
});
```

### Pegando o valor de um input

Permite que você use o valor que há em um elemento nele mesmo, ou em outras tags.

##### Exemplo:

``` javascript
$('document').ready(function(){
    $("#largura").bind("change", function(){
    var largura = ($("#largura").val());//pega o valor do elemento que mostra as larguras que podem ser dadas à um elemento
    $("#praia").width(largura);//dá a largura escolhida ao elemento com o id #praia
    }); 
});
```

### Mudando atributo e a classe

- Attr - permite a mudança de algum atributo da tag.
- toggleClass - permite a mudança do nome de uma classe, mudando assim, seus atributos.

##### Exemplo:

``` javascript
$('document').ready(function(){
    $("#luz").bind("dblclick",function(){
        if($("#luz").attr("src")=="on.png"){
            $("#luz").attr("src","off.png"); //muda o atributo src da tag img com o id #luz
        }else{
            $("#luz").attr("src","on.png");
        }
        $("html").toggleClass("apaga"); //muda a classe para a de nome .apaga
    });
});
```

### Mudando o CSS

O objeto do JQuery usado pra isso é o .css(); e funciona da seguinte forma .css(“propriedade”, “atributo”); ex: .css(“color”, red);. Darei um exemplo de uso:

    <ul>
    <li>Item 1<li>
    <li>Item 2<li>
    <li>Item 3<li>
    </ul>

    $("li").css("color", "red");
    $("p").css("background-color","yellow");

Mudando mais de um atributo

## Funções do JQuery

### Append

É uma função que cria um html para ser adicionado ao código, quantas vezes seja necessário, a partir da interação com um elemento já existente.

``` javascript
$('document').ready(function(){
    $("#add").click(function(){ //ao clicar no elemento de id #add
        $("#item").append("<br>Item Compra: <input type='text'>"); //ele adiciona no elemento de id #item o html colocado entre parênteses
    });

});
```

### Before

É uma função que cria um html para ser adicionado ao código anterior ao desejado, quantas vezes seja necessário, a partir da interação com um elemento já existente.

``` javascript
$('document').ready(function(){
    $("#addEndereco").click(function(){ // evento: clique no elemento de id #addEndereco
        $("#addEndereco").before("<br>Endereço: <input type='text' id='endereco'><br>"); //será adicionado antes do elemento de id #addEndereco o código apresentado entre parênteses  
    });
});
```

### After

É uma função que cria um html para ser adicionado ao código Posterior ao desejado, quantas vezes seja necessário, a partir da interação com um elemento já existente.

``` javascript
$( ".container" ).after( $( "h2" ) );
```

Resultado:

    <div class="container">
      <div class="inner">1</div>
      <div class="inner">2</div>
    </div>
    <h2>Funcionou!</h2>

### Wrap

Coloca determinado elemento em torno do elemento referenciado.

``` javascript
$("button").click(function(){
  $("p").wrap("<div></div>");
});
```

### Animate

Torna um elemento animado a partir de uma interação com ele.

Exemplo:

``` javascript
$('document').ready(function(){
    function aumentar(){
        $(this).animate({'font-size': "250px"}, 500); //aumenta o tamanho da fonte
    }
    function diminuir(){
        $(this).animate({'font-size': "30px"}, 500); //diminui o tamanho da fonte
    }
    $('#titulo font').bind('mouseover', aumentar); //coloca em ação a função aumentar()
    $('#titulo font').bind('mouseout', diminuir); //coloca em ação a função diminuir()  
});
```

### Children

Pega um elemento dentro de outro elemento. É como se o elemento maior (ou seja, o elemento que não está envolvido por nenhum outro) fosse o pai e os que estão dentro dele são os filhos. Essa função pega o elemento "filho" que pertence a uma tag.

Exemplo:

``` javascript
$('document').ready(function(){
   $("#pai").click(function(){ //aqui mostra tag pai
      $(this).children().css({"border":"2px solid #58ACFA","color":"#0174DF"}); //e aqui ele atribui um estilo ao filho da tag apontada quando foi aberta a função
   });
});
```

O pai também pode ser pegado na interação com seu filho.

Exemplo:

    $('document').ready(function(){
       $("#filho").click(function(){ //aqui mostra tag filho
          $(this).parent(); //pega a tag pai
       });
    });

### Key

Possui várias funcionalidades relacionadas com a teclas pressionadas no teclado.

#### KeyDown

Mostra que a tecla está pressionada.

    $(document).ready(function(){
        $("input").keydown(function(event){
            $("#status").html('tecla pressionada.');
        });

        
    });

#### KeyUp

Mostra quando a tecla foi solta.

    $(document).ready(function(){
        $("input").keyup(function(){
            $("#status").html('tecla solta.');
        });
        
    });

#### KeyPress

Mostra quando foi pressionada uma tecla. Se for usado um contador, é possível mostrar quantas teclas foram pressionadas.

    var c = 0;
    $(document).ready(function(){
        $("input").keypress(function(event){ //essa é a função que mostra quando uma tecla foi pressionada
            c = c+1; //aqui ele incrementa o número de vezes que foram pressionadas as teclas

        });
        
    });

#### KeyCode

Pega o código da última tecla pressionada.

    $(document).ready(function(){
        $("input").keydown(function(event){ //essa função usa o KeyDown
            var cod = event.keyCode; //aqui pega o código da tecla pressionada
            $("#cod").html("Código da tecla: " + cod); //mostra na tela
        });
        
    });

### Clone

Clona o elemento desejado.

Exemplo:

    $(document).ready(function(){
        var id = 1; //variável criada para incrementar o id, pois ele n pode ser igual
        $("img").click(function(){
            var clone = $("#1").clone(true); //"clona" a imagem com o id = 1
            $("body").append(clone); //coloca o "clone" dentro da tag body
            id = id + 1; //muda o id, senao o clone teria id = 1
            $(clone).attr("id", id); //atribui a id da tag o número incrementado da variável
        });
    });

### Closest

Pega o elemento mais perto em relação à tags, ou seja, a tag pai ou filho mais perto do elemento selecionado

Exemplo:

    $(document).mouseover(function(event) { // 
              $(event.target).closest("td").toggleClass("hilight"); //pega o elemento mais perto ta td onde está o mouse, no caso, uma tr
        });
        $(document).mouseout(function(event) {
              $(event.target).closest("td").toggleClass("hilight"); //faz o mesmo, retirando a formatação da classe
        });
    });

### Filter

Filtra um tipo de elemento requerido, para então, mudar/mexer somente em elementos desse tipo.

Exemplo:

    $(document).ready(function(){
        $("#colorir").click(function(){
            $("div").filter(function(index){ //index começa no 0
                if(index %2 != 0){ //pega o mod do index, ou seja, o resto do numero divido por 2
                    $(this).css("background", "lightblue"); //muda o fundo das divs pares
                }
            });
        });
    });

### Wrap

Essa função, quando chamada, vai envolver um objeto qualquer.

Exemplo:

    $('document').ready(function(){
        $("strong").bind("click", wrapar); //ao clique na tag <strong>
            function wrapar(){
                    $("strong").wrap("<div><div><p><em><b></b></em></p></div></div>"); //o elemento será envolvido pelo que está sendo apresentado dentro dos parênteses
            });
    });

### InsetBefore e Insert After

Essa função, quando chamada, insere algo a um objeto selecionado.

Exemplo:

    $(document).ready(function(){
          $("button").click(function(){
            $("<span>OlÃ¡ Mundo!!!</span>").insertBefore("p"); //insere texto antes da tag <p>
            $("<div>OlÃ¡ Mundo!!!</div>").insertAfter("p"); //insere texto depois da tag <p>
      });
    });

<a href="Categoria:Jquery" class="wikilink" title="Categoria:Jquery">Categoria:Jquery</a> <a href="Categoria:Desenvolvimento_Web" class="wikilink" title="Categoria:Desenvolvimento Web">Categoria:Desenvolvimento Web</a>
