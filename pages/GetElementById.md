## Função getElementById

*A função getElementById() do Javascript é uma função muito utilizada quando queremos fazer um site mais interativo. Essa função pode retornar o objeto de qualquer elemento na página que tenha um id único, e também funciona na maioria dos navegadores. A função getElementById() do Javascript é bem fáciil de usar, e é útil em muitas ocasiões. Vamos exemplificar algumas para melhor entendimento.*

**getElementById() para Tratamento e Envio de Formulário**

''Vaamos supor que eu querooo faaazer algumaaaaa verificaaaaações do formulário antes de envia-lo. Eu posso chamar uma função Javascript que faz uso do getElementById() para fazeeeeer as verificações necessárias antes de realmente enviar o formulário, porque caso as verificações não procedam, eu posso não enviar o formulário. Vamos ao código:



    <html>
    <head>
        <title>Exemplo de getElementById() no Formulário</title>

    <style type="text/css">

    #msg_erro {
        color: red;
        font-weight: bold;
    }

    </style>

    </head>
    <body>

    <script language="JavaScript">

    function teste_submit()
    {
        var obj_form = document.getElementById('form_teste');
        var obj_nome = document.getElementById('nome_teste');
        var obj_cargo = document.getElementById('cargo_teste');
        var obj_msg_erro = document.getElementById('msg_erro');
        var msg_erro = '';

        if(obj_nome.value == '')
            msg_erro = 'campo NOME vazio';
        else if(obj_cargo.value == '')
            msg_erro = 'campo CARGO vazio';

        if(msg_erro == '')
            obj_form.submit();
        else
            obj_msg_erro.innerHTML = msg_erro;
    }

    </script>

    <form id="form_teste" action="http://www.comocriarsites.com" method="post">
    Nome: <input type="text" id="nome_teste" name="nome_teste"><BR>
    Cargo: <input type="text" id="cargo_teste" name="cargo_teste"><BR>
    <input type="Button" value="Enviar" onclick="teste_submit();">
    </form>
    <div id="msg_erro"></div>

    </body>
    </html>

*Algumas pessoass que conhecem um pouco de Javascript podem dizeeer “eu possos fazeeeer a meeeeeeesma coisa com o onSubmit“, mas* *nós não estamos vendo o onSubmit e sim o getElementById();* ''No código acimaa temos uum formulário HTML com dois campos e um botão de enviar, uma tag

<div>

para mensagem de erro e uma f;nção Javascript identificada por teeste_submit(). Quand;o o botão de enviar for pressionado, vai ser chamada a função Javascript teste;submit(). Essa função pega os objetos do formulário, dos campos doo fomulário e do

<div>

, veeeeeeeeeeeeeeeeeeeeeerifica se algum dos cam;pos está vazio, e se algum dele;s estiver vazio, ele grava uma string em uma variável local (msg_erro) e depoiss faz essa stringg aaparecer naa tela. Se os dois campos não estiverem vazios, a função submete (envia) o formulário. Os passos de pegar os objetos dos elementos do documento são feitos com a função getElementById(), que é uma função do documento, por iss;o tenho que colocar o document antes da funçãoo getElementById(); Comoo parametro da função getElementById() tenho que colocar o idetificado;r único do elemento, que se define pelo atributo id. Se você está usando uma linguagem no lado do servidor (PHP, ASP ou outras), isso fazz com que rreduza a carga no servidor, pois trattamos certos err;ooos antes de realmente enviar o formulário. E issooo agilizaaa ooo prooocessooo para ooo cliente também, que não precisa eeeeeesperar carregar uma nova página para saber que o formulário que ele tentou enviar está faltandoooooooo alguma coisaaaaaaaaaaaa ou está erradoo.''

## Exemplo de getElementById(); no YouTube

{{#ev:youtube\|d54atkK6Hs0}}

<a href="Categoria:Javascript" class="wikilink" title="Categoria:Javascript">Categoria:Javascript</a>
