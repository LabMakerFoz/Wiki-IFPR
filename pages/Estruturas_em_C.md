# Estruturas em C

Uma **estrutura** em C é um uma **estrutura de dados** em forma de um **registro** com vários **campos**.

Criação de uma estrutura  
Para a criação de uma estrutura utiliza-se o comando **struct** e atribui-se um **nome para a estrutura**, o qual é depois utilizado para declarar variáveis deste tipo.

Exemplo[^1]:

``` c
 struct nametype{
   char first[10] ;
   char midinit ;
   char last[20] ;
 };

 struct nametyte name;
```

  
A primeira declaração cria uma **estrutura** de nome *nametype* com três **campos**, na qual o primeiro (*first*) e o terceiro (*last*) são strings e o segundo (*midinit*) é um caracter.

<!-- -->

  
A segunda declaração cria a variável *name* do tipo da estrutura *nametype*.

Uma alternativa ao uso de um nome de estrutura é utilizar a **definição de tipo** com o comando **typedef** do C e depois utilizar o novo tipo criado para declarar varáveis do **tipo da estrutura** criada. Por exemplo:

``` c
 typedef struct {
   char first[10] ;
   char midinit ;
   char last[20] ;
 } NAMETYPE;

 NAMETYTE name;
```

  
Observe que os nomes de estruturas são convencionalmente escritos com letras minúsculas, mas os especificadores de **typedef** são escritos com letras maiúsculas ao apresentar programas em C.

<!-- -->

Acesso aos campos da estrutura  
Cada **campo** da estrutura pode ser acessado especificando o **nome da variável** e no nome do **campo** correspondente.

Por exemplo:

``` c
 printf("%s", name.first);
```

  
pode ser usada para imprimir o primeiro nome na estrutura name, e a instrução:

``` c
 name.midinit = 'M';
```

  
atribui valor ao segundo campo da estrutura name.

<!-- -->

Programa exemplo  

``` c
 #include <stdio.h>
 #include <string.h>
 struct nametype{
   char first [10]; /*Tipo string*/
   char midinit;    /*Tipo char*/
   char last [10];  /*Tipo string*/
 };
 void main ()
 {
   struct nametype name;
   strcpy (name.first,"João");
   name.midinit = 'C';
   strcpy (name.last,"Silva");
   printf("Nome completo: %s %c. %s\n", name.first, name.midinit, name.last);
 }
```

### Exercícios

1.  Construa um programa para receber pelo teclado o nome, data de nascimento, telefone e email de uma pessoa e armazenar os valores em uma variável tipo estrutura, chamada ficha_pessoal. Em seguida imprimir as informações da pessoa.
2.  Modifique o programa anterior, fazendo com que o campo telefone da estrutura ficha_pessoal seja também uma estrutura, chamada telefones, com campos para telefones residencial, comercial e celular.
3.  Modifique o programa, atribuindo a definição da estrutura ficha_pessoal a uma variável tipo vetor, de forma a receber dados de 10 pessoas diferentes.

Ver: [**Curso C** -\> Tipo de dados definidos pelo usuário -\> Estruturas](http://www.mtm.ufsc.br/~azeredo/cursoC/c.html)

Exercício resolvido  
Por aluno Matheus Marques Martines

``` c
#include <stdio.h>
#include <string.h>

struct telefones {
   char res [15];
   char cel [15];
 };

struct dados {
   char nome [100];
   char nasc [12];
   struct telefones telefone;
   char email [200];
 };

 void main () {
   struct dados ficha_pessoal;

   printf("Digite o nome da pessoa: ");
   fgets(ficha_pessoal.nome,100,stdin);
   fflush(stdin);

   printf("Digite a data nascimento da pessoa da pessoa: ");
   fgets(ficha_pessoal.nasc,12,stdin);
   fflush(stdin);

   printf("Digite o telefone residencial da pessoa: ");
   fgets(ficha_pessoal.telefone.res,15,stdin);
   fflush(stdin);

   printf("Digite o telefone celular da pessoa: ");
   fgets(ficha_pessoal.telefone.cel,15,stdin);
   fflush(stdin);

   printf("Digite o email da pessoa: ");
   fgets(ficha_pessoal.email,200,stdin);
   fflush(stdin);

   printf("\n\n==================\nFICHA PESSOAL\n");
   printf("Nome: %s", ficha_pessoal.nome);
   printf("Data de Nascimento: %s", ficha_pessoal.nasc);
   printf("Telefones:\n");
   printf("\tResidencial: %s", ficha_pessoal.telefone.res);
   printf("\tCelular: %s", ficha_pessoal.telefone.cel);
   printf("Email: %s", ficha_pessoal.email);
}
```

## Estruturas e passagem de argumentos para funções

Uma **estrutura** pode ser passada como **argumento** para uma função. Para isto, na declaração da função, deve-se declarar o **parâmetro** como uma variável tipo estrutura.

Por exemplo, poderia definir uma função do tipo ImprimeFicha para receber um parâmetro do tipo estrutura[^2]:

``` c
 void ImprimeFicha (struct ficha_pessoal ficha)
 {
 ...
 }
```

Neste exemplo uma estrutura é passada como **argumento por valor** para a função, sendo copiado para o parâmetro da função chamada.

Se quisermos modificar a estrutura do programa principal, podemos utilizar **ponteiros**.

## Estruturas e ponteiros

Podemos ter um **ponteiro** para uma **estrutura**.

Veja um exemplo de declaração de uma estrutura do tipo ponteiro[^3]:

``` c
 struct ficha_pessoal *p;
```

Para acessar um campo de uma estrutura tipo ponteiro, devemos usar o comando:

``` c
 p->nome;
```

Assim, podemos utilizar um **ponteiro** para passar um **argumento por referência** para uma função.

Por exemplo, suponha que tivéssemos definida uma função PreencheFicha, usada para preencher uma variável tipo estrutura. Neste caso, poderíamos chamá-la passando como argumento um ponteiro:

``` c
 PreecheFicha(&ficha);
```

## Exercícios

1.  Construa funções as funções PreecheFicha e ImprimeFicha para o exercício 2 anterior.
2.  Use as funções PreecheFicha e ImprimeFicha no exercício 3 anterior, passando como argumento para acessar um campo do vetor um ponteiro:

` *(vetor + i)`

Exercício resolvido  
Por aluno: Frederick Moschkowich

``` c
#include <stdio.h>
#include <string.h>
// @author: Frederick Moschkowich
 struct telefones {
   char res [15];
   char com [15];
   char cel [15];
 };
struct dados {
   char nome [100];
   char nasc [12];
   struct telefones telefone;
   char email [200];
 };
void preencheFicha(struct dados *dadosp, int i) {
   printf("Digite o nome da %da. pessoa: ", i+1);
   fgets(dadosp->nome,100,stdin);
   fflush(stdin);

   printf("Digite a data nascimento da %da. pessoa da pessoa: ", i+1);
   fgets(dadosp->nasc,12,stdin);
   fflush(stdin);

   printf("Digite o telefone residencial da %da. pessoa: ", i+1);
   fgets(dadosp->telefone.res,15,stdin);
   fflush(stdin);

   printf("Digite o telefone comercial da %da. pessoa: ", i+1);
   fgets(dadosp->telefone.com,15,stdin);
   fflush(stdin);

   printf("Digite o telefone celular da %da. pessoa: ", i+1);
   fgets(dadosp->telefone.cel,15,stdin);
   fflush(stdin);

   printf("Digite o email da %da. pessoa: ", i+1);
   fgets(dadosp->email,200,stdin);
   fflush(stdin);
}
void imprimeFicha(struct dados *dadosp) {
   printf("\n\n==================\nFICHA PESSOAL\n");
   printf("Nome: %s", dadosp->nome);
   printf("Data de Nascimento: %s", dadosp->nasc);
   printf("Telefones:\n");
   printf("\tResidencial: %s", dadosp->telefone.res);
   printf("\tComercial: %s", dadosp->telefone.com);
   printf("\tCelular: %s", dadosp->telefone.cel);
   printf("Email: %s", dadosp->email);

}
void main () {
   struct dados ficha_pessoal[3];
   int i;
   for (i = 0; i < 3; i++) {
            preencheFicha(ficha_pessoal+i, i);
   }
    printf("\n\n==================\nFICHA PESSOAL\n");
    for (i = 0; i < 3; i++) {
          imprimeFicha(ficha_pessoal+i);
    }
 }
```

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h29min de 12 de junho de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Estruturas_de_Dados" class="wikilink" title="Categoria:Estruturas de Dados">Categoria:Estruturas de Dados</a>

[^1]: TENENBAUM, A. A.; LANGSAM, Y.; AUGENSTEIN, M.J. Estruturas de dados usando C, São Paulo: Makron Books, 1995.

[^2]: Curso C, UFMG. <http://www.mtm.ufsc.br/~azeredo/cursoC/c.html>

[^3]: Curso C, UFMG. <http://www.mtm.ufsc.br/~azeredo/cursoC/c.html>
