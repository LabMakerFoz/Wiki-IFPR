# Caracteres e String em C

## Caracteres

Os **caracteres** em C são do tipo de dados **char** e são variáveis de um Byte.

Cada **caractere** é armazenado no Byte em [formato ASCII](http://pt.wikipedia.org/wiki/ASCII).

Se armazenarmos um dígito numérico como um char, o conteúdo do char será o código ASCII correspondente ao número, por exemplo:

`Dígito: 1 -> ASCII: 00110001`

Função para ler e imprimir um caractere digitado  

``` c
 #include <stdio.h>
 int main ()
 {
   char Ch;
   printf("Digite uma tecla\n");
   Ch = getchar();
   printf ("Voce pressionou a tecla %c\n",Ch);
   return (0); 
 }
```

Função que imprime código ASCII de um caractere  
Como um `char` armazena um inteiro, se utilizarmos **%d** na função `printf` ela irá imprimir o inteiro correspondente ao código ASCII do caractere.

``` c
 #include <stdio.h>
 int main ()
 {
    char Ch;
    printf("Digite uma tecla\n");
    Ch = getchar();
    printf ("O código ASCCI da tecla pressionada é %d\n",Ch);
    return (0); 
 }
```

## Strings

As **strings** em C são **vetores de caracteres** terminado com um caractere **nulo** (**\0**).

  
O caracter **nulo** (**\0**) corresponde ao código ASCII: `00000000`.

Como as strings são vetores de caracteres, podemos acessar cada caracter de uma string usando indexação de vetores, no qual o primeiro caractere é indexado por 0, o segundo por 1, e assim por diante.

Uma constante string é indicada por um conjunto de caracteres entre aspas. Por exemplo, a string "Brasil" tem 7 elementos, incluindo as letras da palavra e o caractere \0:

|     |     |     |     |     |     |     |
|-----|-----|-----|-----|-----|-----|-----|
| 0   | 1   | 2   | 3   | 4   | 5   | 6   |
| B   | r   | a   | s   | i   | l   | \0  |
|     |     |     |     |     |     |     |

Função que lê e imprime uma string digitada  

``` c
 #include <stdio.h>
 int main ()
 {
    char string[100];
    printf ("Digite uma string: ");
    gets (string); //Veja alerta e alternativa ao uso da função gets
    printf ("Voce digitou %s\n",string);
    return (0); 
 }
```

Função que percorre o vetor string e imprime cada caractere  

``` c
 #include <stdio.h>
 int main ()
 {
   char string[100];
   int i;
   printf ("Digite uma string: ");
   gets (string); //Veja alerta e alternativa ao uso da função gets
   for (i=0; string[i] != '\0'; i++)
     printf ("Caractere %d: %c\n", i, string[i]);
   return (0); 
 }
```

Exercício  
Construir uma função para copiar uma string (string1\[100\]) em outra (string2\[100\]).

Resolução:

``` c
 #include <stdio.h>
 int main ()
 {
   char string1[100], string2[100];
   int i;
   printf ("Digite uma string: ");
   gets (string1);
   for (i=0; string1[i] != '\0'; i++)
     string2[i]=string1[i];
   string2[i]='\0';
   printf ("String copiada: %s\n", string2);
   return (0); 
 }
```

## Funções da linguagem C para leitura de caracteres e strings

Estas funções fazem parte da biblioteca:

``` c
 #include <stdio.h>
```

### getchar()

Lê o próximo caractere da entrada (teclado) e retorna como um char.

``` c
 char Ch;
 Ch = getchar();
```

### gets()

Lê a entrada até "nova linha" (LF) e substitui por '\0' (NULL).

``` c
 char string[100];
 printf ("Digite uma string: ");
 gets (string); 
```

Alerta  
O **gets** não checa possibilidade de estouro do espaço reservado na declaração da string, por isto seu uso não é recomendado. Alguns compiladores apresentam *warning* ou não permitem seu uso. Uma alternativa para o **gets** é a função **fgets**, que checa o número de bytes lidos da entrada.

### fgets

Lê entrada até "nova linha" (LF). Quando a "nova linha" é lida o caractere '\n' (ASCII 10 LF) é acrescento na string, seguido pela terminação '\0' (NULL).

``` c
 fgets(string, sizeof(string), stdin);
```

Atenção  
Note que a string lida pelo **fgets** apresenta um caractere a mais, o '\n' (ASCII 10 LF), antes do '\0' (NULL).

<!-- -->

  
Exemplo de trecho de código para **limpar da string o caractere '\n**' (este código usa a função strlen da biblioteca string.h):

``` c
 #include <string.h>
 char string[100];
 int len;
 printf("Entre uma palavra: ");
 fgets(string, sizeof(string), stdin);
 len = strlen(string);
 if (string[len - 1] == '\n')
     string[len - 1] = '\0';
```

### scanf

Lê caracter a caracter da entrada.

``` c
 char Ch;
 scanf("%c", &Ch);
```

Atenção  
O **scanf** pode apresentar problemas na leitura de caracteres fornecido pelo usuário em sequência. Como **scanf** lê os caracteres no buffer de entrada (teclado), quando digitamos um caractere e teclamos Enter, o caractere '\n' vai para o buffer e é lido pelo próximo scanf.

Veja exemplo do problema:

``` c
 #include <stdio.h>
 int main()
 {
    char ch1, ch2;
    printf("Insira um caractere: ");
    scanf("%c",&ch1);
    printf("Insira outro caractere: ");
    scanf("%c",&ch2);
    printf("Você digitou: '%c' e '%c'", ch1, ch2);
    return(0);
 }
```

Soluções para limpar o *buffer* de entrada  
1\) Na função **scanf** insira um espaço entre a **aspa** e o símbolo **%c**.

``` c
 #include <stdio.h>
 int main()
 {
    char ch1, ch2;
    printf("Insira um caractere: ");
    scanf("%c",&ch1);
    printf("Insira outro caractere: ");
    scanf(" %c",&ch2);
    printf("Você digitou: '%c' e '%c'", ch1, ch2);
 }
```

  
2\) Limpar o *buffer* da entrada com a função **\_\_fpurge**.

### \_\_fpurge

A função \_\_fpurge limpa o *buffer* de entrada (stdin) e não retorna valor.

``` c
 #include <stdio.h>
 int main()
 {
    char ch1, ch2;
    printf("Insira um caractere: ");
    scanf("%c",&ch1);
    __fpurge(stdin);
    printf("Insira outro caractere: ");
    scanf("%c",&ch2);
    printf("Você digitou: '%c' e '%c'", ch1, ch2);
 }
```

Atenção  
A função **\_\_fpurge** não é padrão, portanto, um código com esta função pode não ser portável para outros sistemas. No Windows, usa-se a função **fflush**.

## Operações sobre Strings

Funções que implementam operações primitivas sobre strings, conforme apresentado em [^1].

Strlen  
Função para encontrar o tamanho de uma string.

``` c
 #include <stdio.h>
 int Strlen(char string[]);      /*Protótipo da função*/
 int main ()                    /*Programa principal para teste*/
 {
   char c[50]="Brasil2014";
   int len;
   len = Strlen(c);
   printf("Comprimento da string: %d\n", len);
   return (0); 
 }
 int Strlen(char string[])       /*Definição da função*/
 {
   int i;
   for (i=0; string[i] != '\0'; i++)
      ;
   return (i);
   //Note que ao percorrer a string, i varia de 0 a i-1 até encontrar '\0'.
   //Ao sair do for, i é incrementado uma última vez, fornecendo o tamanho da string corretamente.
 }
```

Strcat  
Esta função recebe duas strings como parâmetros e concatenada a segunda string na primeira.

``` c
#include <stdio.h>
void Strcat(char s1[], char s2[]);      //Protótipo da função
int main ()                             //Programa principal para teste
{
  char string1[20]="Brasil",string2[20]="2014";
  Strcat(string1, string2);
  printf("Strings concatenadas: %s\n", string1);
  return (0); 
}
void Strcat(char s1[], char s2[])        //Definição da função
{
  int i, j;
  for (i=0; s1[i] != '\0'; i++)
     ;
  for (j=0; s2[j] != '\0'; i++, j++)     //Veja nota abaixo
     s1[i]=s2[j];
} 
```

``` c
 //O segundo for poderia ser escrito da seguinte forma:
 for (j=0; s2[j] != '\0'; s1[i++]=s2[j++])
     ;
 //No caso, primeiro é realizada a operação s1[i]=s2[j]
 //e depois i e j são incrementados.
```

## Biblioteca \<string.h\>

A biblioteca **string.h** da linguagem C apresenta uma série de funções para manipular strings. Para utilizar estas funções deve-se incluir no início do programa a linha:

``` c
#include <string.h>
```

Função strlen()  
Recebe como argumento uma string e retorna um inteiro que é o comprimento do string.

``` c
#include <stdio.h>
#include <string.h>
int main ()
{
  char c[50];
  int len;
  printf("Entre seu nome: ");
  gets(c);
  len = strlen(c);
  printf("Seu nome tem %d caracteres.\n", len);
  return (0); 
}
```

Função strcat()  
Recebe como argumento duas strings e concatena a segunda string na primeira. Retorna ponteiro para a string concatenada.

``` c
#include <stdio.h>
#include <string.h>
int main ()
{
   char str[10] = "Brasil";
   strcat(str, "2014");
   printf("Copa do Mundo %s\n", str);
   return (0); 
}
```

Função strcmp()  
Recebe como argumento duas strings e as compara, retornando um inteiro:

- Se string1 = string2 -\> retorna 0;
- Se string1 \< string2 (vem antes no dicionário) -\> retorna inteiro negativo (\< 0);
- Se string1 \> string2 (vem depois no dicionário) -\> retorna inteiro positivo (\> 0).

``` c
#include <stdio.h>
#include <string.h>
int main()
{
  char palavra1[100], palavra2[100];
  int  resultado;
  printf("Entre com uma palavra: ");
  gets(palavra1);
  printf("Entre outra palavra: ");
  gets(palavra2);
  resultado = strcmp(palavra1, palavra2);
  if (resultado == 0)
    printf("Palavras iguais\n");
  else if (resultado < 0)
    printf("A primeira palavra vem antes no dicionário\n");
  else
    printf("A segunda palavra vem antes no dicionário\n");
  return (0); 
}
```

Função strcpy()  
Recebe como argumento duas strings e copia a segunda string na primeira. Retorna ponteiro para a string resultante.

``` c
#include <stdio.h>
#include <string.h>
int main ()
{
   char str1[10] = "Brasil";
   char str2[10];
   printf("str2 = %s\n", strcpy(str2, str1));
   return (0); 
}
```

## Exercícios sobre strings e caracteres

1.  Construa uma função que receba uma string e retorne a string escrita de trás para frente.
2.  Construa uma função para contar a ocorrência de um caractere em uma string.
3.  Construa uma função que receba as strings do nome completo de uma pessoa na linha de comando (argc e argv) e concatene as strings incluindo espaço entre os nomes.
4.  Construa uma função que receba uma string e converta seus caracteres para maiúsculo (Pesquise e use a função **strupr()** da biblioteca string.h).
5.  Construa uma função que receba uma string e converta seus caracteres para minúsculo (Pesquise e use a função **strlwr()** da biblioteca string.h).
6.  Modifique a função que recebe as strings do nome completo de uma pessoa, de forma que devolva na forma que os nomes aparecem nas referências bibliográficas da ABNT (ver abaixo).

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h33min de 20 de agosto de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Estruturas_de_Dados" class="wikilink" title="Categoria:Estruturas de Dados">Categoria:Estruturas de Dados</a>

[^1]: TENENBAUM, Aaron M.; LANGSAM, Yedidyah; AUGENSTEIN, Moshe. **Estruturas de dados usando C**. Makron Books, 1995.
