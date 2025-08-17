# App Inventor: Plano Inclinado

Vamos utilizar o [**App Inventor**](http://ai2.appinventor.mit.edu) vamos desenvolver uma **aplicação voltada a física**, no caso a simulação de um **plano inclinado**.

## Plano Inclinado

Quando colocamos um **corpo** sobre um **plano inclinado**, **sem atrito**, o corpo deslizará para baixo no plano pela ação da **gravidade**.

No **plano inclinado** a **força gravitacional** atua com duas componentes:

- **Força perpendicular ao plano** (m g cos Θ): esta componente tem intensidade igual, porém sentido oposto à força normal N exercida pelo plano sobre o objeto. Não há movimento perpendicular ao plano;
- **Força paralela ao plano** (m g sen Θ), responsável por fazer o objeto deslizar para baixo no plano inclinado.

<a href="Arquivo:PlanoInclinado.png" class="wikilink" title="Arquivo:PlanoInclinado.png">Arquivo:PlanoInclinado.png</a>[^1]

Aceleração do corpo no plano inclinado  
O **corpo** vai deslizar para baixo no **plano inclinado** com **aceleração**:

`a = g sen Θ`

O **movimento do corpo**, portando, segue as características do **MRUV**:

`s = s0 + v0 t + a t`<sup>`2`</sup>` / 2`

  
ou, considerando s0 = 0, v0 = 0 e a = g sen Θ:

`s = g sen Θ t`<sup>`2`</sup>` / 2`

## Simulação de um plano inclinado na tela do dispositivo móvel

Vamos construir uma **aplicação** para o dispositivo móvel que simule um **plano inclinado**. Para tal, vamos utilizar o **sensor de orientação** do dispositivo móvel, o qual oferece informações sobre a **orientação tridimensional** da tela do dispositivo.

### Sensor de Orientação do AppInventor

O **Sensor de Orientação** oferece informações sobre a **orientação tridimensional** do dispositivo móvel através de três parâmetros:

Rolagem  
Ângulo de **inclinação lateral** do dispositivo:

- **0 grau** com o dispositivo **nivelado**;
- Aumenta para **90 graus** a medida que o **lado direito** é levantado;
- Diminui para **-90 graus** a medida que o **lado esquerdo** é levantado.

<!-- -->

Altura  
Ângulo de **inclinação longitudinal** do dispositivo:

- **0 grau** com o dispositivo **nivelado**;
- Aumenta para **90 graus** a medida que a **base** do dispositivo é levantada;
- Diminui para **-90 graus** a medida que o **topo** do dispositivo é levantado.

<!-- -->

Azimute  
Ângulo orientação em relação ao **norte magnético da terra**:

- **0 grau** quando o dispositivo aponta para o **norte**;
- **90 graus** quando o dispositivo aponta para o **leste**;
- **180 graus** quando o dispositivo aponta para o **sul**;
- **270 graus** quando o dispositivo aponta para o **oeste**.

### Exercício

Construa com o **AppInventor** um aplicativo utilizando o **Sensor de Orientação** e a guia **Desenho e Animação**, utilizando uma **Pintura** de fundo de tela e uma **Bola** que funcione da seguinte forma:

- **Quando a tela for tocada**, mover a **Bola** para a **coordenada** da tela que foi tocada;
- **Quando o celular for movimentado**, utilizar os **ângulos** relativos a **Rolagem** e **Altura** para que a **Bola** se movimente na tela de acordo com as **relações matemáticas** da física relativas a um **Plano Inclinado**.

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 20h22min de 6 de novembro de 2023 (UTC)

------------------------------------------------------------------------

<a href="Categoria:App_Inventor" class="wikilink" title="Categoria:App Inventor">Categoria:App Inventor</a> <a href="Categoria:LabMaker" class="wikilink" title="Categoria:LabMaker">Categoria:LabMaker</a> <a href="Categoria:Informática_Aplicada_ao_Ensino_de_Física" class="wikilink" title="Categoria:Informática Aplicada ao Ensino de Física">Categoria:Informática Aplicada ao Ensino de Física</a>

[^1]: <https://pt.wikipedia.org/wiki/Plano_inclinado>
