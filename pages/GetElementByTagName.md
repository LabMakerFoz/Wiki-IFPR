## Usando getElementByTagName

**getElementsBytagName**

''Se você notarem, no exemplo acima na função de remover o item eu usei o método getElementsByTagName.

Diferentemente do getElementById, com getElementsByTagName você não resernva um único elemento, mas todos os elementos que você quiser, exemplo, no exemplo acima eu reservei todas as uls, mas resolvi usar apenas à primeira.''

''Você pode se perguntar, mas se há apenas um elemento porque devo dizer qual eu quero, veja, isso é um padrão da linguagem e embora em principio pareça estranho, é bem útil se você pensar que seu código pode crescer e aoo invés de você ter uma ul, pode ter 300.

Dessa forma você tem que dizer ual elemento você quer 0, 1, 2, etc ou percorrer com um for por todos os elementos.''

''Vou usar o exemplo acima, mas vou mudar um pouco, digamos que esta é a lista do que você comprou, ou melhor, digamos que é a lista final do supermercado, precisamos obter o valor final desta lista, vamos lá.

O HTML é o mesmo anterior, então nem vou exibí-lo agora.''

**JS**

    function SomarValor(){
        valores = document.getElementsByTagName('ul')[0].getElementsByTagName('li');
        total = 0;
        for(var i=0;i<valores.length;i++){
            total+=parseFloat(valores[i].innerHTML)
        }
        document.getElementById('total').innerHTML = total
    }

''Neste exemplo, eu pego todos os lis que estão dentro da primeira ul, percorro através de um for, somo seus valores e exibo o resultado na mesma div total.

Veja essa linha de código''

    document.getElementsByTagName('ul')[0].getElementsByTagName('li');

*Nesta linha eu uso duas vezes o getElementsByTagName, isso significa que eu quero pegar todos os elementos do segundo getElementsByTagName que estão dentro do primeiro getElementsByTagName, neste caso, quero pegar todos os lis que estão dentro daquela ul.*

<a href="Categoria:Javascript" class="wikilink" title="Categoria:Javascript">Categoria:Javascript</a>
