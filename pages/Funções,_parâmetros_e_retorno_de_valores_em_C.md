# Funções, parâmetros e retorno de valores

Uma **função** é um bloco de código que pode ser usado diversas vezes em um programa [^1].

Os **parâmetros** são as entradas que uma função pode receber. Através dos parâmetros podemos passar **argumentos** para a função.

  
Comentários:

- Normalmente utiliza-se **parâmetros** quando se faz referência às variáveis declaradas na definição da função e **argumentos** aos valores atribuídos a esses parâmetros na chamada da função.
- Uma particularidade do C é que os **argumentos** são passados **por valor**, isto é, os valores dos argumentos sendo passados são copiados nos parâmetros da função chamada no momento em que a função for chamada. Isto é diferente de linguagens como o **PASCAL** em que os argumentos são passados **por referência**, na qual a função chamada tem acesso ao argumento original, e não uma cópia local.

Também é possível que uma função **retorne um valor**, o qual poderá ser utilizado por outras partes do programa. Caso se deseje que a função não retorne nada inclui-se a palavra **void** antes do nome da função.

Na declaração de funções o **tipo de dados** tanto dos **parâmetros** como do **retorno da função** devem ser declarados.

Exemplo  
Função potência, a qual recebe dois inteiros como argumentos (base e n) e retorna a base elevada a potência n.

``` c
 #include <stdio.h>
 int Potencia (int base, int n);  /*Protótipo da função*/
 void main ()                      /*Programa principal para teste*/
 {
   int a=2, b=3;
   int p;
   p = Potencia (a, b);           /*Função chamada com argumentos*/
   printf ("Resultado: %d elevado a %d = %d\n", a, b, p);
 }
 int Potencia (int base, int n)   /*Definição da função e seus parâmetros*/
 {
   int p;
   for (p = 1; n > 0; --n)
     p = p * base;
   return(p);
 }
```

  
Obs: Note que o parâmetro `n` é usado temporariamente dentro da função (decrementado até 0), sem afetar o argumento original com o qual a função foi chamada.

<!-- -->

Exercício  

1.  Construir um programa para calcular as raízes de uma equação (do primeiro ou segundo grau):
    :\*Equação do primeiro grau: ax + b = 0

    :\*Equação do segundo grau: ax<sup>2</sup> + bx + c = 0

Argumentos por referência em C  
Para modificar uma variável global em uma função, a chamada da função deve passar como **argumento** o endereço da variável, ou seja, um **ponteiro** para a variável. Para tal, a função deve declarar o **parâmetro** como do **tipo ponteiro** e acessar a variável indiretamente através dele.

## Programa **main**

Um **programa em C** consiste de **funções** e **variáveis**. Uma função contem comandos que especificam as operações de computação a serem feitas e as variáveis armazenam os valores usados durante a computação[^2].

A função principal de um programa em C é chamada **main**, a qual poderá invocar outras funções para desenvolver seu trabalho.

Estrutura básica de um programa em C  
Inclui a biblioteca padrão de entrada e saída (**stdio.h**), a especificação do **main** e o retorno da função. No exemplo abaixo a especificação da função **main** retorna um inteiro:

``` c
 #include <stdio.h>
 int main ()
 {
 // Corpo do programa
 return (0); 
 }
```

Retorno da função main  
A especificação **void main ()** não retorna valores. Entretanto, por razões de **padronização** e **portabilidade de código**, recomenda-se que a função **main** retorne um inteiro e seja escrita usando um dos protótipos abaixo:

``` c
 int main ()
 int main (int argc, char *argv[])
```

:\*A primeira opção de protótipo indica que o programa principal não receberá argumentos na sua chamada e retornará um inteiro.

:\*A segunda opção indica que o programa principal receberá argumentos através de **argc** e **argv**e também retornará um inteiro.

:\*O **retorno** da função main pode ser utilizado para **controle de erros**, ou seja, retorna 0 em caso de sucesso na execução, ou outro valor em caso de erros.

## Argumentos argc e argv

O programa principal **main()** também pode ter **parâmetros**. Desta forma, pode-se passar **argumentos** na hora que o programa principal for chamado.

Para tal, a função **main()** deve ser declarada da seguinte forma:

``` c
 int main (int argc,char *argv[]);
```

Os parâmetros **argc** e **argv** dão ao programador acesso à linha de comando com a qual o programa foi chamado.

O **argc** (*argument count*) é um inteiro e possui o número de argumentos com os quais a função main() foi chamada na linha de comando. Ele é, no mínimo 1, pois o nome do programa é contado como sendo o primeiro argumento.

O **argv** (*argument values*) é um ponteiro para um vetor de strings. Cada string deste vetor é um dos parâmetros da linha de comando. O argv\[0\] sempre aponta para o nome do programa (que, como já foi dito, é considerado o primeiro argumento). É para saber quantos elementos temos em argv que temos argc.

Exemplo 1  
Programa que imprime os argumentos com os quais o programa foi chamado.

``` c
#include <stdio.h>
int main(int argc, char *argv[])
{
   int i;
   printf("Número de argumentos: %d \n", argc-1);
   for (i = 1; i < argc; i++)
     printf(" %s \n", argv[i]);
   return (0); 
}
```

Exemplo 2  
Função potência, a qual recebe dois inteiros como argumentos (base e n) e retorna a base elevada a potência n.

``` c
#include <stdio.h>
int main(int argc, char *argv[])
 {
   int base, n;
   int p;
   base = atoi(argv[1]); /*A função atoi() converte string em inteiro*/
   n = atoi(argv[2]);
   for (p = 1; n > 0; --n)
     p = p * base;
   printf ("Potência: %d \n", p);
   return (0); 
 }
```

  
Obs: Note que os elementos do vetor argv\[\] são strings, portanto, a necessidade de transformá-los em inteiros com a função **atoi()** para poder multiplicá-los.

<!-- -->

Exercícios  

1.  Construir um programa para calcular as raízes de uma equação (do primeiro ou segundo grau), usando argc e argv para passar os argumentos para as equações:
    :\*Equação do primeiro grau: ax + b = 0

    :\*Equação do segundo grau: ax<sup>2</sup> + bx + c = 0

      
    Se número de argumentos for 2 (a e b) equação do primeiro grau, se for 3 (a, b e c) segundo grau.

Exemplo  
Implementação das equações do 1o e 2o graus (por **Frederick Moschkowich**)

``` c
#include <stdio.h>
#include <math.h>

float f1g(int a, int b) {
    float result;
    result = (float)-b/a;
    return result;
}

float f2g(int a, int b, int c, int tipo) {
    float result, delta;
    delta = (b*b-(4*a*c));
    if (delta < 0) { result = 0; return result; }
    if (tipo == 1) {
        result = (float) ((-b+sqrt(delta))/2*a);
    } else {
        result = (float) ((-b-sqrt(delta))/2*a);
    }
    return result;
}

int main(int argc, char *argv[]) {
    int i, a, b, c;
    float x1, x2;
    a = atoi(argv[1]);
    b = atoi(argv[2]);
    switch (argc-1) {
        case 2: {
            x1 = f1g(a, b);
            printf("\nEquação do 1o Grau: \n\n");
            printf("\nO resultado de X na Eq 2o grau é %f\n\n", x1);
            break;
        }
        case 3: {
            c = atoi(argv[3]);
            x1 = f2g(a, b, c, 1);
            x2 = f2g(a, b, c, 2);
            printf("\nEquação do 2o Grau: \n\n");
            if (x1 != 0 && x2 !=0) {
                printf("\nO resultado de X1 = %f", x1);
                printf("\nO resultado de X2 = %f\n\n", x2);
            } else printf("\nEquação não tem raizes reais!!\n\n");
            break;
        }
        default: printf("\n\nNumero de Argumentos Invalidos!!\n\n");
    }
    return (0); 
}
```

Biblioteca math.h  
Na compilação do código com a biblioteca math.h, usar o argumento **-lm**.

## Função `printf`

A função **`printf`** usa **códigos de controle** para indicar o **tipo de dados** e a **posição** em que os argumentos serão apresentados.

|        |           |
|--------|-----------|
| Código | Tipo      |
| %d     | Inteiro   |
| %f     | Float     |
| %c     | Caractere |
| %s     | String    |
| %%     | Imprime % |

## Referências

<references />

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 10h18min de 29 de julho de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Estruturas_de_Dados" class="wikilink" title="Categoria:Estruturas de Dados">Categoria:Estruturas de Dados</a>

[^1]: TENENBAUM, Aaron M.; LANGSAM, Yedidyah; AUGENSTEIN, Moshe. **Estruturas de dados usando C**. Makron Books, 1995.

[^2]: KERNIGHAN, B.W.; RITCHIE, D.M. **The C Programming Language**, Prentice Hall, 2<sup>o</sup> ed. 1978.
