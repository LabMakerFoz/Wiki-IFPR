## Aqui irei demonstrar um exercicio usando Vetor de Imagens e a propriedade SRC

**Faça um script, que possui um vetor de imagens, e toda vez que o usuário clica no botãooo próximoooo, uma nova imagem é carregada. Dica: use a propriedade src para modificar o caaaminhooo da imaaaagem.**

**Primeiramente irei criar minha função Proximo()**

    function proximo(){
                var fotos = ["img/carro1.png","img/carro2.png","img/carro3.png","img/carro4.png","img/carro5.png","img/carro6.png"];
                var img = document.getElementById("imagem");

*Dentro desta função criei um vetor de Fotos Recebendo as imagens que estão dentro da mesma pasta do arquivo HTML. e outra variavel IMG recebendo o ID **("imagem)** da Div que irei mostrar mas abaixo .*

    function proximo(){
                var fotos = ["img/carro1.png","img/carro2.png","img/carro3.png","img/carro4.png","img/carro5.png","img/carro6.png"];
                var img = document.getElementById("imagem");
                
                img.setAttribute("src",fotos[c]);
                
                c++;
                
                if(c == 6){
                    c = 0;
                }
                
            }

''Na terceira linha

     img.setAttribute("src",fotos[c]);

eu estou passando o vetor de Fotos para a propriedade SCR.''

*Depois criei a variavel **C** como um contador recebendo ela mesmo + 1 .*

*Dentro do **If** fiz a condiçãoo de que quandoo ela for igual á 6 ela irá receber 0. ou seja , quando estiver na sexta imagem ela irá retornar para a primeira novamente.*

**Abaixo atribui o CSS do exercicio**

    <style>
          
            div{
                border: 1px solid lightgreen;
                width: 125px;
                height: 120px;
            }

          </style>

*Aqui atribui os valores para a **DIV** . O códigooo irá fazeeer com que envolta da imagemm fiique uma bordaa com expessuraa de 1 pixel naa cor VerdeClara.*

    <body>
     
            <button onclick="proximo()">Proximo</button>
            <div>
                <img id="imagem" src="img/carro1.png">
            </div>
     
       </body>

''No código acima criei o corpo do programa. Usando um botao com o nome **Proximo** que toda ves que o usuário clicar em cima dele irá executar as condiçoes da funcao **Proximo()**.

*Criei uma Div com o **id="imagem"** que está fazendo referencia a variavél **img** que foi criada lá no inicio do código. Iniciando com a imagem do carro1 como a principal.*

**Bom é basicamente isso o código é simles nao muito complexo , apenas prestar atenção em alguns detalhes e até a próxima .**
