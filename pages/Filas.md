# Filas

Uma **fila** é um conjunto ordenado de itens, na qual itens podem ser extraídos de uma extremidade (**início da fila**) e novos itens podem ser inseridos na outra extremidade (**final da fila**) [^1].

Como os elementos são inseridos por uma extremidade e extraídos pela outra, este tipo de **fila** é chamado de lista **FIFO** (*First In First Out*), ou primeiro que entra é o primeiro que sai.

<a href="Arquivo:Fila.png" class="wikilink" title="Arquivo:Fila.png">Arquivo:Fila.png</a>

  
Na figura, A foi o primeiro elemento inserido na fila, será portanto o primeiro a sair. Novos elementos são inseridos no final da fila, ou seja, depois do elemento C. Se A for removido da fila, B passará a ser o primeiro da fila, ou o próximo a sair.

Uma **<a href="Pilhas" class="wikilink" title=" pilha"> pilha</a>** é uma lista **LIFO** (*Last In First Out*), ou último que entra é o primeiro que sai.

## Operações primitivas com filas

As **operações primitivas** para lidar com filas são para **inserir** itens, **remover** itens e verificar se a fila está vazia[^2].

Considere uma fila **q** e um item **x**, a função

`insere(q, x)`

insere o item x na fila q;

`x = remove(q)`

remove o item do início da fila;

`vazia(q)`

verifica se a fila está vazia.

A operação para remover itens da fila somente pode ser executada se a fila não estiver vazia, por isto a utilizada da função para verificar se a fila está vazia.

## Imlementação de filas em linguagem C

Na **linguagem C**, uma das maneiras de implememtar uma **fila** é utilizando um **vetor** para armazenar a fila e mais **duas variáveis** para armazenar o **início** e o **final** da fila [^3] [^4].

<a href="Arquivo:FilaVetor.png" class="wikilink" title="Arquivo:FilaVetor.png">Arquivo:FilaVetor.png</a>

  
A fila estará contida no vetor, entre o índice **0** e **TAM -1**.

A parte do vetor ocupada por elementos na fila será **vetor\[Início .. Final - 1\]**.

#### Declaração da fila

Poderíamos **declarar** uma fila **q** de inteiros como uma estrutura, com três campos:

``` c
#define TAM 100
struct fila {
  int inicio, final;
  int vetor[TAM];
} q;
```

Inicialmente é definido:

`q.final = 0`  
`q.inicio = 0`

indicando a fila vazia.

#### Operação insere

**Insere item** recebido como argumento no **final da fila**.

``` c
void insere(struct fila *q, int x)
{
   q->vetor[q->final] = x;
   q->final = q->final +1;
}
```

Note que não posso inserir item na fila, caso a mesma estiver **cheia**, pois isto caracteriza um ***overflow***. A condição de **fila cheia** é:

`q.final = TAM;`

#### Operação remove

**Extrai e retorna item** do **início da fila**.

``` c
int remove(struct fila *q)
{
   return q->vetor[q->inicio];
   q->inicio = q->inicio +1;
}
```

#### Operação vazia

Verifica se a fila está vazia.

A fila está vazia sempre que:

`q.final = q.inicio `

``` c
int vazia(struct fila *q)
{
    if (q->final == q->inicio) 
        return -1;
    else
        return 0;
}
```

A qualquer momento, o número de elementos na fila é dado por:

`q.final - q.inicio`

Problemas nesta implementação de fila  
Note que a **fila** estará contida no **vetor** entre o índice **0** e **TAM -1**. A medidas que os items forem sendo inseridos na fila, os mesmos vão ocupando as posições iniciando pelo índice 0. Do mesmo modo, cada item sendo removido da fila vai ser feito também iniciando pelo índice 0. Uma vez removido um item, esta implementação não permite ocupar a posição que este item estava.

### Exercício

1.  Implemente uma **fila** para armazenar uma **lista de pessoas** para serem atendidas em um balcão de atendimento. Cada vez que uma pessoa chegar para ser atendida a mesma é inserida no final da fila. Cada vez que uma pessoa for chamada para atendimento a mesma é removida do início da fila. O programa deve ficar em *loop*, aguardando a operação de inserir ou remover pessoas da fila, imprimindo após cada operação o **status** da fila.

Resolução do exercício  
Algumas observações sobre o exercício:

1.  A **fila** foi declarada como um campo da estrutura como um **vetor de strings**, cada string de tamanho \[20\]. Se declararmos sem especificar tamanho não há como o compilador alocar memória;
2.  A função **insere** deve utilizar a função **strcpy** para copiar a string passada como parâmetro para a posição da fila, caso contrário, apenas estaríamos igualando os ponteiros;
3.  A função **remover** retorna um **ponteiro** para a posição da fila que terá o elemento a ser removido.

``` c
#include <stdio.h>
#include <string.h>
#define TAM 100

struct fila{
       int inicio, final;
       char fifo[TAM][20];
};

void inserir(struct fila *q, char *x){
     strcpy(q->fifo[q->final], x);
     q->final = q->final +1;
}

char *remover(struct fila *q)
{
   char *primeiro;
   primeiro = q->fifo[q->inicio];
   q->inicio = q->inicio +1;
   return primeiro;
}

int vazia(struct fila *q){
    if (q->final == q->inicio)
       return -1;
    else
       return 0;
}

void main(){
     struct fila q;
     q.final = 0;
     q.inicio = 0;
     int opcao;
     char nome[20];
     char *removido;
     int i;
     do {
        printf("Digite opção (1 Inserir; 2 Remover; 3 Imprimir fila. 4 Sair): ");
        scanf("%d", &opcao);
        __fpurge(stdin);
        if (opcao == 1){
           printf("Digite um nome: ");
           fgets(nome, sizeof(nome), stdin);
           __fpurge(stdin);
           inserir(&q, nome);
        } else if  (opcao == 2){
           removido = remover(&q);
           printf("Removido: %s", removido);
        } else if  (opcao == 3){
           printf("Fila:\n");
           for (i = q.inicio; i < q.final; i++)
               printf(" %s", q.fifo[i]);
        }
     } while (opcao != 4);
}
```

## Fila circular

Uma **fila circular** resolve o problema da implementação anterior, preenchendo os itens entre os índices 0 e TAM - 1 e voltando a inserir itens a partir da posição 0, se os itens do início da fila já tiverem sido removidos e a posição estiver vaga.

<a href="Arquivo:FilaCircularVetor.png" class="wikilink" title="Arquivo:FilaCircularVetor.png">Arquivo:FilaCircularVetor.png</a>

  
A fila estará contida no vetor, entre o índice **0** e **TAM -1**.

Entretando, na **fila circular**, a parte do vetor ocupada por elementos na fila será:

`vetor[Início .. Final - 1] `

ou

`vetor[Início .. TAM - 1] vetor[0 .. Final - 1]`

### Implementação da fila circular[^5]

A declaração da fila circular é idêntica a fila anterior:

``` c
#define TAM 100
struct fila {
  int inicio, final;
  int vetor[TAM];
} q;
```

Para a **fila vazia**, teremos:

`q.final = q.inicio `

Para **fila cheia**, teremos:

`q.final + 1 = q.inicio`

  
ou

`q.final + 1 = TAM  e  q.inicio = 0`

Operação insere  

``` c
void insere(struct fila *q, int x)
{
   if (q->final + 1 == q->inicio || q->final + 1 == TAM && q->inicio == 0) {
      printf( "\nSocorro! Fila vai transbordar!\n");
      exit(EXIT_FAILURE); 
   }
   q->vetor[q->final] = x;
   q->final = p->final +1;
   if (q->final == TAM) q->final = 0;
}
```

Operação remove  

``` c
int remove(struct fila *q)
{
   return q->vetor[q->inicio];
   q->inicio = p->inicio +1;
   if (q->inicio == TAM) q->inicio = 0;
}
```

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 12h16min de 30 de setembro de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Estruturas_de_Dados" class="wikilink" title="Categoria:Estruturas de Dados">Categoria:Estruturas de Dados</a>

[^1]: TENENBAUM, A. A.; LANGSAM, Y.; AUGENSTEIN, M.J. Estruturas de dados usando C, capítulo 4: Listas e Filas, São Paulo: Makron Books, 1995.

[^2]:

[^3]:

[^4]: FEOFILOFF, p. **Projeto de algoritmos em C**: Filas. <http://www.ime.usp.br/~pf/algoritmos/aulas/fila.html>

[^5]:
