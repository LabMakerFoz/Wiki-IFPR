# Cayenne

Página Wiki sobre a **plataforma de programação *low code* orientada ao hardware [Cayenne](https://cayenne.mydevices.com)**, a qual permite desenvolver aplicações **Web** para interagir com os dispositivos de hardware em projetos de **Internet das Coisas**.

Foi desenvolvida originalmente para o **Raspberry Pi**, mas agora também está habilitada para trabalhar com o **Arduíno**.

Os dispositivos de hardware se comunicam com a plataforma **Cayenne** através do protocolo **<a href="MQTT" class="wikilink" title="MQTT">MQTT</a>**.

Para uso com o **Arduíno** é necessário que o mesmo possua conexão com a Internet por meio de um ***shield* Ethernet ou Wifi** e a biblioteca **CayenneMQTTEthernet.h**. Outros modelos de microcontroladores, como o **Arduíno Yun** ou o **ESP32**, também podem ser utilizados.

Uma vez que o **Cayenne** esteja rodando no **Arduíno** ou **Raspberry Pi**, pode-se interagir com os dispositivos através da **Web**.

Na plataforma **Cayenne** estão disponíveis uma grande variedade de **sensores** e **dispositivos de hardware**, os quais podem ser incorporados ao projeto e monitorados e controlados remotamente. Também é possível ter acesso as **portas GPIO** do microcontrolador utilizado.

<a href="Arquivo:CayenneDevices.jpg" class="wikilink" title="300 px">300 px</a> <a href="Arquivo:CayenneGPIO.jpg" class="wikilink" title="300 px">300 px</a> [^1]

Com um sensor instalado pode-se fazer a leitura da corrente no aplicativo, ou da grandeza medida, por exemplo, temperatura. É possível adicionar qualquer tipo de dispositivo, como relés, motores, conversores ADC, etc.

## Programas para interação com Arduíno

A plataforma **GitHub** apresenta diversos *scketchs* para uso de sensores e atuadores conectados no **Arduíno**:

- <https://github.com/myDevicesIoT/Cayenne-MQTT-Arduino>

A **documentação** da plataforma **Cayenne** traz uma descrição detalhada para edição de *sketches* para rodar no Arduino:

- <https://developers.mydevices.com/cayenne/docs/sketch-files/>

------------------------------------------------------------------------

Vídeos  
- <https://www.youtube.com/watch?v=EDsCsPLqVGI>
- <https://www.youtube.com/watch?v=D0dHJ4Xr4yE>

## Referências

<references />

<a href="Categoria:_Computação_em_Nuvem" class="wikilink" title="Categoria: Computação em Nuvem">Categoria: Computação em Nuvem</a> <a href="Categoria:_IoT" class="wikilink" title="Categoria: IoT">Categoria: IoT</a>

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 09h38min de 10 de junho de 2020 (-03)

[^1]: <https://www.i-programmer.info/news/91-hardware/9725-cayenne-makes-iot-easy-really-easy.html>
