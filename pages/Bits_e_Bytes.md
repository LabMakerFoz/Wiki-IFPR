# Conceitos sobre Informática

## Conceitos fundamentais

bit  
É a menor unidade de informação manipulada pelo computador, podendo assumir dois valores, **0** ou **1**.

O termo bit é a contração de *binary digit*.

<!-- -->

Palavra binária  
**n bits** formam uma palavra binária, a qual pode representar 2<sup>n</sup> valores diferentes.

<!-- -->

Byte  
É o termo clássico utilizado para uma **palavra binária de 8 bits**, o qual pode representar 2<sup>8</sup> = 256 combinações diferentes.

Exemplo de binário de 8 bits:

|     |     |     |     |     |     |     |     |
|-----|-----|-----|-----|-----|-----|-----|-----|
| 1   | 0   | 1   | 1   | 1   | 1   | 0   | 0   |
|     |     |     |     |     |     |     |     |

## Sistemas Numéricos

### Sistema Decimal

  
Base: 10

Digitos: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9

Exemplo:

  
5374<sub>10</sub>

  
= 5 x 10<sup>3</sup> + 3 x 10<sup>2</sup> + 7 x 10<sup>1</sup> + 4 x 10<sup>0</sup>

= 5 x 1000 + 3 x 100 + 7 x 10 + 4 x 1

= 5374

`5 3 7 4`  
`| | | +-> Unidade (Peso    1)`  
`| | +---> Dezena  (Peso   10)`  
`| +-----> Centena (Peso  100)`  
`+-------> Milhar  (Peso 1000)`

### Sistema Binário

  
Base: 2

Digitos: 0, 1

Exemplo:

  
1100<sub>2</sub>

  
= 1 x 2<sup>3</sup> + 1 x 2<sup>2</sup> + 0 x 2<sup>1</sup> + 0 x 2<sup>0</sup>

= 8 + 4 + 0 + 0

= 12

`1 1 0 0`  
`| | | +-> (Peso 1)`  
`| | +---> (Peso 2)`  
`| +-----> (Peso 4)`  
`+-------> (Peso 8)`

Exemplos de números binários  

| Decimais | Binários |
|----------|----------|
| 0        | 0        |
| 1        | 1        |
| 2        | 10       |
| 2        | 11       |
| 4        | 100      |
| 5        | 101      |
| 6        | 110      |
| 7        | 111      |
| 8        | 1000     |
| 9        | 1001     |
| 10       | 1010     |
| 11       | 1011     |
| 12       | 1100     |
| 13       | 1101     |
| 14       | 1110     |
| 15       | 1111     |
|          |          |

Exemplo de 1 Byte em binário  

|  |  |  |  |  |  |  |  |  |
|----|----|----|----|----|----|----|----|----|
| Binário | 1 | 0 | 1 | 1 | 1 | 1 | 0 | 0 |
| Potências de 2 | 2<sup>7</sup> | 2<sup>6</sup> | 2<sup>5</sup> | 2<sup>4</sup> | 2<sup>3</sup> | 2<sup>2</sup> | 2<sup>1</sup> | 2<sup>0</sup> |
| Valores posicionais | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
|  |  |  |  |  |  |  |  |  |

`10111100`<sub>`2`</sub>` = 128 + 32 + 16 + 8 + 4 = 188`<sub>`10`</sub>

## Código ASCII

O [**código ASCII**](http://pt.wikipedia.org/wiki/ASCII) é um código alfanumérico, utilizado como padrão para a troca de informações entre a CPU de um computador e dispositivos como teclado, monitores e impressoras, por exemplo.

No código ASCII cada caractere é codificado em 7 bits, existindo, portanto, 2<sup>7</sup> = 128 representações codificadas.

[Conversor de texto ASCII em binário](http://nickciske.com/tools/binary.php)

Editores TXT  
Editores de texto TXT, como o **Bloco de Notas** (Windows) ou **Gedit** (Linux) produzem arquivos de **texto sem formatação**, formados exclusivamente com **caracteres ASCII**.

## Códigos digitais e relação com extensões de arquivos

Toda **informação digital**, seja ela **texto**, **imagem**, **som** ou **vídeos**, são armazenadas nos computadores utilizando **códigos digitais** específicos.

### Exemplos

Editores de Texto  
São capazes de produzir textos com formatação sofisticada, incluindo diferentes tipos de fonte, tamanhos de fonte, títulos, sub-títulos, numeração de páginas, etc.

O código digital gerado possui uma codificação específica e somente pode ser lido pelos respectivos editores.

| Editor                     | Extensão de arquivo |
|----------------------------|---------------------|
| Word (Windows)             | .**doc**            |
| LibreOffice Writer (Linux) | .**odt**            |
|                            |                     |

Planilhas de Cálculo  
Permitem produzir planilhas de cálculo, incluindo fórmulas e funções matemáticas. Gráficos também podem ser gerados diretamente a partir dos dados tabelados.

| Planilha                 | Extensão de arquivo |
|--------------------------|---------------------|
| Excell (Windows)         | .**xls**            |
| LibreOffice Calc (Linux) | .**ods**            |
|                          |                     |

Imagens e figuras  

| Tipos de codificação |
|----------------------|
| .**jpeg**            |
| .**png**             |
| .**gif**             |
|                      |

Som  

| Características  | Tipos de codificação |
|------------------|----------------------|
| Som qualidade CD | .**wav**             |
| Som compactado   | .**mp3**             |
|                  |                      |

Vídeo  

| Aplicativo                        | Tipos de codificação |
|-----------------------------------|----------------------|
| Windows Media Player              | .**avi**             |
| Windows Media Player (Compactado) | .**wmv**             |
|                                   |                      |

------------------------------------------------------------------------

--<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 11h13min de 31 de julho de 2014 (BRT)

------------------------------------------------------------------------

<a href="Categoria:Sistemas_Digitais" class="wikilink" title="Categoria:Sistemas Digitais">Categoria:Sistemas Digitais</a>
