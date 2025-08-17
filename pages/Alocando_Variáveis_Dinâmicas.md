# Alocando Variáveis Dinâmicas

Um <a href="Ponteiros_em_C" class="wikilink" title=" ponteiro"> <strong>ponteiro</strong></a> é uma variável que contem o **endereço** de uma variável.

Se **x** é uma variável qualquer, **&x** é um ponteiro para x. Se **p** é um ponteiro, **\*p** é o objeto para o qual p aponta[^1].

Através dos **ponteiros**, podemos **alocar e liberar dinamicamente espaço para variáveis** em C.

Em C, um ponteiro para uma variável inteiro pode ser declarado como:

`int *p`

assim que a variável p for declarada como ponteiro, podemos alocar dinamicamente um objeto deste tipo e atribuir seu endereço a p.

Função malloc  
A função **malloc(*size*)** aloca dinamicamente espaço na memória, de tamanho *size*, e retorna um ponteiro para este espaço.

Por exemplo:

`int *p`  
`p = (int *) malloc(sizeof (int));`

aloca dinamicamente para p espaço relativo a um tipo inteiro.

Função free  
A função **free(var)** é usada em C para liberar o espaço alocado dinamicamente para uma variável.

Por exemplo:

`free(p);`

invalida quaisquer referências futuras a \*p.

Ponteiro para NULL  
Em C, é possível atribuir a um ponteiro p o valor NULL, o que indica que o mesmo não aponta para nada. Neste caso, uma referência a \*p será uma operação inválida.

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h13min de 7 de novembro de 2014 (BRST)

------------------------------------------------------------------------

<a href="Categoria:Estruturas_de_Dados" class="wikilink" title="Categoria:Estruturas de Dados">Categoria:Estruturas de Dados</a>

[^1]: TENENBAUM, Aaron M.; LANGSAM, Yedidyah; AUGENSTEIN, Moshe. **Estruturas de dados usando C**. Makron Books, 1995.
