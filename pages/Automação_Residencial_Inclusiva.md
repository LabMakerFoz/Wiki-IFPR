\<span style="font-size:large"; style="color:red"\>**UM NOVO OLHAR NA AUTOMAÇÃO PARA DEFICIENTES FÍSICOS**</span>

# **Identificação**

**Linha de Pesquisa:** Este projeto tem como objetivo projetar, prototipar, implementar e ensinar soluções na linha de automação residencial na plataforma Arduino™, com enfoque em acessibilidade para pessoas com deficiência como, por exemplo, pessoas cegas ou surdas, através da criação de dispositivos de controle e monitoramento voltado as particularidades de cada necessidade de forma individual.

**Coordenador:**  
Evandro Cantú / Doutorado em Engenharia Elétrica / Siape: 0278185-9

**Colaborador Docente:**  
Humberto Martins Beneduzzi / Graduação em Sistemas de Informação / Siape: 1794416

**Colaboradores Discentes / Curso / Câmpus / Modalidade de Bolsa**  
Igor Amadeu Alves Leite / Curso Superior de Tecnologia em Análise e Desenvolvimento de Sistemas / Câmpus Foz do Iguaçu / PIBITI  
Igor Matheus Barbosa Quintana/ Curso Superior de Tecnologia em Análise e Desenvolvimento de Sistemas / Câmpus Foz do Iguaçu / PIBIS / Colaborador do projeto  
Matheus Marques Martines/ Curso Superior de Tecnologia em Análise e Desenvolvimento de Sistemas / Câmpus Foz do Iguaçu / PIBIS / Colaborador do projeto  
Frederick Moschkowick / Curso Superior de Tecnologia em Análise e Desenvolvimento de Sistemas / Câmpus Foz do Iguaçu / Colaborador do projeto  
  
  

# **Caracterização da Proposta**

## **Resumo do Projeto**

A área de automação residencial, também conhecida como domótica, tem se desenvolvido enormemente nos últimos anos. Diversos projetos estão sendo desenvolvidos nesta área, visando a automação e a gestão dos recursos habitacionais, simplificando a vida das pessoas e ampliando os recursos de comunicação e segurança. A chamada “Internet das coisas”, inglês: Internet of Things(IOT), que busca interligar os objetos e aparelhos do dia-a-dia, conectando-os as grandes bases de dados é uma grande tendência do mercado atual. Tais avanços visam dispor mais comodidade e segurança. Quando analisamos esses avanços não podemos omitir o princípio da sociedade inclusiva, onde todas as pessoas devem ter a suas necessidades atendidas, sejam elas deficientes, ou não.

A domótica e o foco na inclusão de pessoas com deficiência são as motivações desse trabalho, o qual buscará apresentar soluções de automação residencial em ambientes que necessitem de adaptações especiais, procurando atender os princípios de acessibilidade e viabilidade econômica. Será desenvolvido um protótipo com controladores capazes de comandar dispositivos domésticos como lâmpadas, aparelhos de condicionamento de ar, aparelhos de som, sensores de temperatura, incêndio, chuva, etc. O controle e monitoramento poderá ser feito através de interfaces móveis ou fixas, incluindo, por exemplo, computadores pessoais, dispositivos móveis ou outros dispositivos especiais a serem projetados para atender a demandas específicas.

A estrutura física da solução será desenvolvida sobre a plataforma Arduino™, projeto open-source hardware que permite a construção ágil de circuitos e que possui baixo custo. Para controlar o sistema remotamente será desenvolvido inicialmente um servidor web que fará o controle, monitoramento e posteriormente se comunicará via wireless, ou outra tecnologia de rede, com uma aplicação em um dispositivo móvel com sistema operacional Android™.

Nosso trabalho também consistirá no ensino dessas tecnologias para pessoas deficientes, com o objetivo de tornar construção e aplicação da automação de forma simples e possível para qualquer pessoa.

  
  

## **Contextualização**

A área de automação residencial vem se expandindo no Brasil e no mundo, cada vez mais podem ser vistas casas e apartamentos inteligentes que visam facilitar e automatizar diversas funcionalidades proporcionando comodidade e tornando interessante a possibilidade de não estar no local e controlar os itens a distância. Exemplo dessa tendência foi a aquisição pela Google da Nest\[1\], por U\$3,2 bilhões, empresa a qual tem como principal produto um termostato que aprende a rotina da casa e dos moradores e regula a temperatura de forma inteligente, e da DropCam\[2\] que faz câmeras Wi-Fi acessíveis remotamente. De acordo com um post no blog da Nest\[3\] as equipes começarão a trabalhar juntas no desenvolvimento de novos produtos.

Entretanto, muitas vezes, a automação residencial não considera a inclusão de pessoas deficientes, as quais necessitam de dispositivos especialmente desenvolvidos para terem suas necessidades atendidas. Assim, o foco desse projeto e desenvolver sistemas de automação residencial de forma que pessoas que possuem alguma deficiência tenham as suas necessidades especiais atendidas.

Segundo as Nações Unidas, inglês: United Nations, cerca de 15% da população mundial, ou cerca de 1 bilhão de pessoas, vivem com deficiência. Desse número cerca de 80% vivem em países em desenvolvimento. O Banco Mundial estima que 20% das pessoas mais pobres do mundo possuem algum tipo de deficiência, e tendem nas suas comunidades a serem considerados os mais desfavorecidos. Segundo a UNESCO 90% das crianças com deficiência em países em desenvolvimento não frequentam a escola\[4\]. No Brasil, segundo o Instituto Brasileiro de Geografia e Estatística(IBGE), 23% da população possuem pelo menos uma das deficiências investigadas: visual, auditiva, motora e mental, ou intelectual. Sendo que variam conforme a natureza. Em primeiro lugar está a deficiência visual que ocorre em 18,6% da população brasileira. Em segundo lugar a motora, ocorrendo em 7% da população, seguida da deficiência auditiva, em 5,10% e da deficiência mental ou intelectual, em 1,40%\[5\].

Diversas leis amparam as pessoas com deficiência, como a Lei n. 10.098, de 19 de dezembro de 2000, que estabelece normas gerais e critérios básicos para a promoção de acessibilidade das pessoas portadoras de deficiência ou com mobilidade reduzida\[6\]. Desse decreto podemos destacar o Art. 2o, paragrafo I:

`“Acessibilidade: possibilidade e condição de alcance para utilização, com segurança e autonomia, dos espaços, mobiliários e equipamentos urbanos, das edificações, dos transportes e dos sistemas e meios de comunicação, por pessoa portadora de deficiência ou com mobilidade reduzida;”`

A Associação Brasileira de Normas Técnicas (ABNT), criou a norma NBR 9050 que apresenta os parâmetros básicos a serem seguidos às condições de acessibilidade. Alguns exemplos que podemos citar são: alturas dos comandos das janelas, vãos das portas, tomadas, interruptores, rampas, dimensionamento de sanitários, entre outros. Apesar disso, o Brasil ainda é deficiente quanto às normas para projetos de automação, dentre os quais podemos citar a NBR 14565, que apresenta normativa referente a Procedimentos Básicos para Elaboração de Projetos de Cabeamento para Rede Interna Estruturada, mas que não abrange a automação em sua totalidade. Algumas empresas nacionais utilizam normas estrangeiras, como as elaboradas pelo Instituto Americano de Normas e Padrões.

Apesar do desenvolvimento de sistemas inteligentes ser uma tarefa que exige conhecimento técnico, também depende de mudanças de paradigmas e um maior comprometimento com as comunidades excluídas ou mais carentes, ampliando as oportunidades de acesso as novas tecnologias.

Alguns projetos já foram desenvolvidos na área de automação residencial para deficientes, no entanto, vários desses projetos possuem um custo elevado de aplicação e desenvolvimento, o que implica na maioria das vezes na separação das pessoas menos favorecidas impossibilitando o acesso a esses tipos de tecnologias.

  
  

## **Justificativa**

O aumento da autonomia oferecido por sistemas residências inteligentes contribui para a compensação de deficiências funcionais. A possibilidade de acionamento automático ou remoto de sistemas traz diversos benefícios como conforto, acessibilidade, segurança e bem-estar. Proporcionando autonomia e independência na realização de suas atividades diárias.

Um sistema de automação residencial integra dispositivos eletrônicos a controladores como um computador, telefone celular, tablet, entre outros, através de uma rede, permitindo o controle inteligente de cada ponto da residência, particularmente ou em conjunto com o restante do sistema. Incorporado ao conceito de automação residencial, segundo Pinheiro\[7\] existem três graus de integração destes sistemas:

- Sistemas Autônomos: são sistemas independentes e não há a interligação entre os dispositivos
- Sistemas Integrados: todos os sistemas estão integrados a um controlador (central de automação)
- Sistemas Complexos: princípio de funcionamento da casa inteligente, onde o sistema pode ser personalizado de acordo com a vontade do usuário.

<a href="https://commons.wikimedia.org/wiki/File:Possibilidades_oferecidas_pela_automa%C3%A7%C3%A3o_residencial.jpg" class="wikilink" title=" Possibilidades oferecidas pela automação residencial"> Possibilidades oferecidas pela automação residencial</a>

Apesar de podermos olhar para a automação residencial sob a ótica apenas do conforto, para o portador de necessidades especiais, morar em uma residência inteligente traz uma nova perspectiva de independência. Alguns exemplos que podemos citar é o acionamento de automático de lâmpadas através de sensores de presença, ou por controle remoto ou vocal, ou ainda o fechamento automático de janelas através de sensores como de chuva. Outro exemplo são as camas articuladas, que podem ser acionadas através de dispositivos móveis.

  
  

## **Construção da Maquete**

A maquete foi projetada para simular alguns sistemas básicos de uma residência, como iluminação, segurança, portão eletrônico, piscina e ar-condicionado. Foram implementados também os seguintes sensores: fogo, chuva, umidade, temperatura e vibração. Segue abaixo o link para o video que contém as fotos da construção da maquete passo-a-passo:

- <https://www.youtube.com/watch?v=8uFA90EVNao&feature=youtu.be>

  
  

## **Bibliografia**

1.  BARRETT B. **Google compra Nest, que deixa sua casa mais esperta, por US\$ 3,2 bilhões – eis o porquê.** Disponível em: \<<http://gizmodo.uol.com.br/google-compra-nest>\> Acesso em: 02 de setembro de 2014.
2.  GUSMÃO G. **Parte do Google, Nest compra fabricante de câmeras Dropcam por U\$ 555 milhões.** Disponível em: \<<http://info.abril.com.br/noticias/mercado/2014/06/parte-do-google-nest-compra-fabricante-de-cameras-dropcam-por-us-555-mi.shtml>\> Acesso em: 02 de setembro de 2014.
3.  **The Nest family is growing.** Disponível em: <https://nest.com/blog/2014/06/20/the-nest-family-is-growing/>\> Aceso em 02 de setembro de 2014.
4.  **Factsheet on Persons with Disabilities** - \<<http://www.un.org/disabilities/default.asp?id=18>\> Acesso em: 25 de outubro de 2014.
5.  Insituto Brasileiro de Geografia e Estatística. **Cartilha do Censo de 2010 - Pessoas com Deficiência** \<<http://www.pessoacomdeficiencia.gov.br/app/sites/default/files/publicacoes/cartilha-censo-2010-pessoas-com-deficienciareduzido.pdf>\> Acesso em: 24 de outubro de 2014
6.  **LEI No 10.098, DE 19 DE DEZEMBRO DE 2000.** Disponível em : \<<http://www.planalto.gov.br/ccivil_03/leis/l10098.htm>\> Acesso em: 03 de setembro de 2014.
7.  PINHEIRO, J. **Falando da Automação Predial.** Disponível em: \<<http://www.projetoderedes.com.br/artigos/artigo_falando_de_automacao_predial.php>\> Acesso em: 03 de setembro de 2014.
8.  **Depois da Automação Residencial vem a Domótica.** Disponível em \<<http://www.blog.ekolivre.com.br/?p=99>\> Acesso em: 03 de setembro de 2014.

------------------------------------------------------------------------

<a href="Categoria:LabMaker" class="wikilink" title="Categoria:LabMaker"><code>Categoria:LabMaker</code></a>`  `<a href="Categoria:Arduíno" class="wikilink" title="Categoria:Arduíno"><code>Categoria:Arduíno</code></a>
