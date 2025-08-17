# Programando ESP8266 ou ESP32 com MicroPython

**[MicroPython](https://micropython.org/)** é uma implementação do **Python 3** voltada para **microcontroladores**. Foi desenvolvido para a placa **pyboard**, mas pode ser utilizado em outros microcontroladores como o **ESP8266**[^1] e **ESP32**[^2].

<a href="Arquivo:pyboard.jpg" class="wikilink" title="200px">200px</a>

Instalação do MicroPython  

Instalação no Ubuntu 20.04:

`sudo apt update`  
`sudo apt install python3 python3-pip python3-tk`  
`sudo apt install micropython`

Instalação da IDE [Thonny](https://thonny.org/)  

`sudo pip3 install thonny`

## MicroPython no ESP32 e ESP8266

Usar o **MicroPython** é uma excelente maneira de tirar o máximo proveito da placa **ESP32** e **ESP8266**.

### Instalação do firmware no ESP32 e ESP8266

Referência: [^3]

Download firmware  

- ESP32: <https://micropython.org/download/esp32/>
- ESP8266: <https://micropython.org/download/esp8266/>
    
  Escolher a última versão: v1.18 (2022-01-17) .bin (latest)

Instalar esptool  

`pip install esptool`

Verificar a porta USB que a placa está conectada  
Pode ser verificado com a **IDE do Arduíno**.

<!-- -->

Apagar o firmware anterior  

- ESP32:

`esptool.py --chip esp32 --port /dev/ttyUSB0 erase_flash`

  
Pressionar o botão **boot/flash** antes de executar o comando.

- ESP8266:

`esptool.py --chip esp8266 --port /dev/ttyUSB0 erase_flash`

Instalar novo firmware  

- ESP32:

`esptool.py --chip esp32 --port /dev/ttyUSB0 --baud 460800 write_flash -z 0x1000 esp32-20220117-v1.18.bin`

- ESP8266:

`esptool.py --chip esp8266 --port /dev/ttyUSB0 --baud 460800 write_flash -z 0x1000 esp8266-20220117-v1.18.bin`

## Programando ESP32 com Thonny

Setar no Thonny a placa ESP32 em uso:

`Ferramentas -> Opções -> Interpretador -> MicroPython (ESP32)`

Teste  
Acender/apagar led da placa

`>>> from machine import Pin`  
`>>> Pin(2, Pin.OUT).value(1)`

`>>> Pin(2, Pin.OUT).value(0)`

Blink  
Piscar led

``` python
from machine import Pin
from time import sleep
led = Pin(2, Pin.OUT)
while True:
  led.value(not led.value())
  sleep(0.5)
```

## Guia de programação MicroPython para ESP32

- Conceitos básicos: <https://randomnerdtutorials.com/micropython-programming-basics-esp32-esp8266/>
- Entradas e saídas digitais: <https://randomnerdtutorials.com/esp32-esp8266-digital-inputs-digital-outputs-micropython/>
- Interação com pinos GPIO: <https://randomnerdtutorials.com/micropython-gpios-esp32-esp8266/>

## MQTT ESP32 com MicroPython

Tutorial  
MicroPython with MQTT on ESP32/ESP8266: <https://randomnerdtutorials.com/micropython-mqtt-esp32-esp8266/>

Este tutorial mostra a interação entre dois **ESP32**.

Entretanto, pode-se utilizar apenas um **ESP32** e utilizar os clientes **mosquitto_pub** e **mosquitto_sub** para interagir com o ESP32.

<!-- -->

Procedimentos  

1.  Carregar a biblioteca **umqttsimple.py** e salvar no dispositivo:
      
    <https://raw.githubusercontent.com/RuiSantosdotme/ESP-MicroPython/master/code/MQTT/umqttsimple.py>
2.  Carregar **boot.py** e ajustar os parâmetros de configuração do Wifi e broker e em seguida salvar no dispositivo.
3.  Carregar **main.py** e executar.

ESP32  

- Publica: tópico: "hello"
- Subscreve: tópico: "notification"

Mosquitto Client  

- Publica: tópico: "notification"
- Subscreve: tópico: "hello"

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 09h12min de 10 de novembro de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Arduíno" class="wikilink" title="Categoria:Arduíno">Categoria:Arduíno</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>

[^1]: <https://docs.micropython.org/en/latest/esp8266/quickref.html>

[^2]: <https://docs.micropython.org/en/latest/esp32/quickref.html>

[^3]: <https://docs.micropython.org/en/latest/esp32/tutorial/intro.html#>
