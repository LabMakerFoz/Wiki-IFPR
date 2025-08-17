# Sistema de Gerência de Estabelecimentos

## Equipe

Professor orientador  

- Estevan Brandt Braz Costa
- Alcione Benacchio

Alunos  

- João Paulo Mazega Pagani
- Lucas Gomes Guerra

## Objetivo

Desenvolver um sistema WEB que vai funcionar na rede local para gerir o controle de entrada, saída de clientes, assim como a consumação, com ferramentas para gerenciar o estoque e o caixa.

## Problema

Nem todo estabelecimento possuí uma forma de controlar a entrada e saída de clientes integrada com o sistema. Ou se possuí o sistema costuma ser uma solução dekstop, o que por muitas vezes acaba "engessando" o sistema, tornando muito complicado a adição de novos módulos, assim como ser dependente de determinado sistema operacional e versão.

## Solução

O controle de entrada e saída dos clientes será efetuado através de um cartão com um código de barras que será lido pelo leitor específico ou o número digitado manualmente, dependendo da complexidade da implementação, é desejável que a câmera de um celular possa verificar esse código de barras, porém há problemas através do browser, como acesso a câmera do celular, biblioteca javascript para reconhecer os padrões da imagem. O sistema visa ser amplo e podendo ser usado em diversas situações diferentes, a parte de controle de usuário, pode ou não ser usada, tudo depende do usuário do sistema. A justificativa para o sistema ser desenvolvido para web é, para que o sistema seja executado em vários dispositivos, sem se preocupar com muito com sua portabilidade, dando a possibilidade de que seja executado em qualquer sistema que possua um navegador. Também facilitando a adição de novos módulos e funcionalidades ao sistema, por exemplo, se por algum motivo seja necessário o desenvolvimento de um aplicativo para o celular, isso pode ser mais facilmente executado, devido a proximidade da aplicação com o servidor criar um serviço Rest se torna menos penoso.

## Público Alvo

O projeto pretende atingir o seguinte público:

- Casas noturnas;
- Bares e restaurantes, que necessitam controlar a entrada e saída de clientes, assim como o consumo.

## Principais Funcionalidades

- Possibilidade de troca do tema, de acordo com o estabelecimento.
  - O sistema poderá trocar cores e formas de botões e imagens de acordo com o tema

escolhido pelo hotel, podendo assim criar um sistema mais personalizado.

- Controle de entrada, saída de clientes.
  - sistema terá uma forma de controlar a entrada e saída de clientes a fim de gerar

relatórios de ocupação por hora ou dia.

- Controle de consumo de clientes.
  - O sistema proverá o controle do consumo do cliente através de uma mesa. Todos os

pedidos serão ligados a mesa que terá a lista dos itens e o valor total da conta.

- Controle de estoque
  - sistema terá um cadastro de produtos que diretamente o jogará no estoque,

assim como uma atualização da quantidade que pode ser manual, quando o dono do estabelecimento lança uma entrada, ou automática, através da venda de produtos.

- Controle gerencial, lucro, quantidade de vendas.
  - Através de relatórios, o sistema irá informar dados importantes para o

gerenciamento e manutenção do estabelecimento, como por exemplo: lucro diário ou mensal, produtos vendidos no dia ou mensal, quantidade total de ocupação, entre outros.

## Tecnologias a serem Utilizadas

- [Java](https://academy.oracle.com/pt-br/solutions-java.html)
  - Versão:

<!-- -->

- [JSF](https://www.oracle.com/technetwork/java/javaee/javaserverfaces-139869.html)
  - Versão:

<!-- -->

- [PrimeFace](https://www.primefaces.org/)
  - Versão:

<!-- -->

- [Hibernate](https://hibernate.org/)
  - Versão:

<!-- -->

- [Eclipse](https://www.eclipse.org/)
  - Versão:

<!-- -->

- [PostgreSQL](https://www.postgresql.org/)
  - Versão:

<!-- -->

- [Apache TomCat](https://tomcat.apache.org/)
  - Versão:

<!-- -->

- [Apache Maven](https://maven.apache.org/)
  - Versão:

## Requisitos

- Funcionais

<!-- -->

- Tecnológicos

<!-- -->

- Regras de Negócio

## Layout

- Em breve, finalizando conteúdo.

## Caso de Uso

- Em breve, finalizando conteúdo.

## Diagrama de Classe

<a href="Imagem:classDiagram.png" class="wikilink" title=" 800px |Diagrama de Classes"> 800px |Diagrama de Classes</a>

## Diagrama Entidade Relacional

<a href="Imagem:diagramadobancodedados.png" class="wikilink" title=" 800px | Diagrama relacional do banco de dados"> 800px | Diagrama relacional do banco de dados</a>

## Código Desenvolvido

- Em breve, finalizando conteúdo.

## Referências

<references />

------------------------------------------------------------------------

<a href="Categoria:Projeto_Integrador_II" class="wikilink" title="Categoria:Projeto Integrador II">Categoria:Projeto Integrador II</a>
