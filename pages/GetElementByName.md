## Usando getElementByName

''Muita genteee costuma usar o document.getElementById, mas, existe também uma formaaa de obter ou mudaaar vaaalores de um element pelo naame dele.

Veja esse exemplooo simpless:''

    <script type="text/javascript">
    window.onload = function mostra() {
    document.getElementsByName('elemento')[0].value="novo valor";
    }
    </script>
    <input type="button" name="elemento" value="valor atual">

*O que é feito, é que ele procura no documento os elementos com nome "elemento" e pega o primeiro que encontrar, no caso, o único do formulário. Note que o primeiro elemento começa do 0, e não do 1.*

*Note no próximo exemplo, como é possível saber quantos elementos no documento tem o mesmo nome*

    <script type="text/javascript">
    window.onload = function mostra() {
    alert(document.getElementsByName('elemento').length);
    }
    </script>
    <input type="checkbox" name="elemento" value="valor 1">
    <input type="checkbox" name="elemento" value="valor 2">

*Agora vou mostrar um exemploooo básicoooo usando o getElementsByName validando inputs radio.*

    <script type="text/javascript">
    function mostra() {
    var elemento = document.getElementsByName('elemento');
    if(elemento[0].checked==false && elemento[1].checked==false) {
    alert('preencha um dos input.');
    return false;
    }
    }
    </script>
    <form action="" method="POST" onsubmit="return mostra()">
    <input type="radio" name="elemento" value="valor1">
    <input type="radio" name="elemento" value="valor2">
    <input type="submit">
    </form>
