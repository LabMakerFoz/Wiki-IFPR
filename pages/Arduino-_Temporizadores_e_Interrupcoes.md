# Arduíno e ESP: Temporizadores e Interrupções

## Temporizadores

O **Arduíno** e o **ESP** possuem várias funções que permitem implementar **temporizadores** e realizar **medidas de tempo**.

Funções de pausa temporizada no programa  

`delay(ms)`

  
**Pausa** o programa por uma quantidade de tempo especificada como parâmetro em **milissegundos**. (onde 1000 milissegundos é 1 segundo).

`delayMicroseconds(us)`

  
Equivalente ao `delay()` com tempo especificado **microssegundos**.

<!-- -->

Funções para medidas de tempo  

`millis()`

  
Retorna o número de **milissegundos** decorridos desde que a placa Arduíno foi iniciada com o programa atual.

`micros()`

  
Equivalente ao `millis()` retornando o número de **microssegundos**.

### Laboratório 1: Blink sem pausar o programa em execução

Uma aplicação interessante da função `millis()` é poder realizar temporizações sem pausar o programa em execução.

- Programa **Blink** sem pausar programa [^1]:

``` c
/*
 * Blink sem delay();
 */
const int ledPin =  13;           // pino do led
int ledState = LOW;               // estado do led
unsigned long previousMillis = 0; // tempo anterior no qual o led foi chaveado
const long interval = 1000;       // intervalo para piscar led (milliseconds)
void setup() {
  pinMode(ledPin, OUTPUT);
}
void loop() {
  unsigned long currentMillis = millis();
  if (currentMillis - previousMillis >= interval) {
    previousMillis = currentMillis; // salva o tempo atual
    ledState = !ledState;           // chaveia o led    
    digitalWrite(ledPin, ledState); // atualiza estado do led
  }
}
```

- Carregar e testar o programa.

### Verificação do tempo de execução de um programa

A função `millis()` pode ser utilizada para verificar o tempo de execução de um programa ou de um trecho de código. Para tal, chamar a função no início e no fim do código no qual se deseja medir o tempo de execução.

## Interrupções

As **interrupções** permitem detectar mudanças em uma entrada sem a necessidade de checar constantemente seu estado. Quando uma interrupção é detectada uma **rotina de tratamento de interrupção** é chamada.

<a href="Arquivo:Interrupcao.png" class="wikilink" title="Arquivo:Interrupcao.png">Arquivo:Interrupcao.png</a>

A sintaxe das interrupções segue o comando:

`attachInterrupt(digitalPinToInterrupt(pin), ISR, mode)`

na qual:

- `digitalPinToInterrupt(pin)` informa o pino de interrupção;
- **ISR** é o nome da rotina de tratmento de interrupção;
- ***mode*** indica o modo de acionamento da interrupção externa.

No **Arduíno UNO** as **interrupções externas** são acionadas pelo pino 2 (interrupção 0) e/ou pino 3 (interrupção 1).

No **ESP8266** as **interrupções externas** são acionadas pino GPIO especificado pelo parâmetro `digitalPinToInterrupt(GPIO)`[^2].

No Arduíno e no ESP as **interrupções externas** podem ser acionadas de diferentes **modos**:

- CHANGE: Quando o valor do pino muda;
- RISING: Quando o valor do pino sobe de baixo para alto;
- FALLING: Quando o valor do pino desce de alto para baixo;

A cada mudança nos pinos de interrupção uma **rotina de tratamento de interrupção** será acionada.

### Laboratório 2: Piscar led por interrupção

- Programa **blink** acionado com chave e interrupção [^3]:

Conectar **chave *push button*** entre o pino 2 e o terra.

``` c
const byte ledPin = 13;
const byte interruptPin = 2;
volatile byte state = LOW;
void setup() {
  pinMode(ledPin, OUTPUT);
  pinMode(interruptPin, INPUT_PULLUP);
  attachInterrupt(digitalPinToInterrupt(interruptPin), blink, FALLING);
}
void loop() {
  digitalWrite(ledPin, state);
}
void blink() {
  state = !state;
}
```

- Carregar e testar o programa.

Detalhe da chave para o acionamento da interrupção  

- A função `pinMode(interruptPin, INPUT_PULLUP)` [^4] [^5] define a entrada como `INPUT_PULLUP`, isto é, uma entrada com resistor interno ***pull-up***, de forma que se estiver desconectado tem valor `HIGH`. Assim, quando levamos a `LOW` através de uma chave a entrada a interrupção é acionada na transição negativa do pino `FALLING`.
- Em caso de múltiplas transições no led, pode estar ocorrendo **trepidações na chave** (***bounce***).

### Laboratório 3: Blink/Button

Construa um programa para **acionar dois leds**, um piscando em uma **frequência constante** (**Blink**) e outro que pisque quando uma **chave for acionada** (**Button**).

A chave pode ser substituída, por exemplo, por um **sensor de movimento** do tipo **PIR**. Neste caso, quando um movimento for detectado, o programa é interrompido e uma **rotina de tratamento de interrupção** é chamada.

<a href="Arquivo:PIR-motion-sensor.jpg" class="wikilink" title="100px">100px</a>

## Medida do período de um sinal periódico

`pulseIn()`

A função `pulseIn()` permite ler um pulso em um pino. Por exemplo, se o valor do pino é HIGH, a função espera o pino ir de LOW para HIGH, inicia uma temporização, espera o pino ir novamente para LOW e pára a temporização. Retorna o comprimento do pulso em microssegundos (ou retorna 0 em caso de erro na leitura) [^6].

Esta função permite implementar, por exemplo, medidores de velocidade que emitem um pulso a cada volta, como o caso do **anemômetro** de uma **estação meteorológica**, ou do **velocímetro** de uma bicicleta.

### Exemplos de Aplicação

Veja os exemplos de aplicação no projeto da <a href="Estacao_Meteorologica" class="wikilink" title="Estação Meteorológica"><strong>Estação Meteorológica</strong></a> desenvolvida no IFPR:

- **Pluviômetro** -\> Emite um pulso cada 0.2794 mm de chuva dispara uma rotina de **interrupção** (`AttachInterrupt()`) para incrementar o total de mm de chuva.
- **Anemômetro** -\> A cada volta do anemômetro fecha um contato com a ajuda de um ímã. Para medir a velocidade do vento, **mede-se o tempo médio entre cada pulso** (`pulseIn()`) e realiza um cálculo onde se considera que, para uma velocidade do vento de 2.4 km/h, o interruptor fecha uma vez por segundo.

## RTC - *Real Time Clock*

Um **RTC** (*Real Time Clock*) é um módulo com relógio e bateria, muito útil para montar algum tipo de temporizador ou relógio acoplado ao Arduíno, para dispor de data e hora atualizada visando setar alarmes ou executar ações em horários predeterminados.

<a href="Arquivo:RTC.jpg" class="wikilink" title="200px">200px</a>

Um **RTC** é capaz de armazenar e fornecer informações completas de **data e hora**, nos formatos de 12 ou 24 horas, incluindo dia da semana, dia do mês e ano. O número de dias de cada mês, assim como anos bissextos são ajustados automaticamente.

Os módulos **RTC** geralmente de comunicam com o **Arduíno** através de **comunicação serial** baseada no **protocolo I<sup>2</sup>C**. Este protocolo utiliza duas linhas bidirecionais denominadas **Dados Seriais** (**SDA** - *Serial Data*) e **Relógio Serial** (**SCL** - *Serial Clock*). O **SDA** é responsável pela **troca de dados** e o **SCL** é responsável pela **sincronização** entre os dispositivos.

O **protocolo I<sup>2</sup>C** é um protocolo tipo **mestre/escravo**, onde um dispositivo mestre pode controlar, pelo mesmo barramento de comunicação, até 127 dispositivos escravos, cada um identificado por um **endereço** formado por um byte **hexadecimal**.

Na comunicação entre um **Arduíno** e um módulo **RTC**, normalmente, além da alimentação e terra, são utilizados duas **entradas** para as linhas de comunicação **SDA** e **SCL**. Além disto, cada módulo **RTC** normalmente tem uma **biblioteca** própria, com diversas funções para trabalhar e manipular os dados do relógio, incluindo conversões para diferentes tipos de apresentação da data e hora.

### Laboratório 4: Uso do módulo RTC DS3231 com Arduíno

Utilizar, se disponível, um módulo **RTC**, como o DS3231 e a respectiva biblioteca para uso com o Arduíno para dispor de dada e hora.

A referência [^7] apresenta um exemplo de código, com uso de biblioteca, para uso de um **RTC DS3231**.

## Protocolo I2C

A comunicação **I2C** é um protocolo de **comunicação serial** que permite que dispositivos diferentes se comuniquem e troquem dados através de um **barramento compartilhado**, permitindo que múltiplos dispositivos possam ser conectados no mesmo barramento.

No **I2C** um dispositivo é designado como **mestre** e os demais dispositivos são considerados **escravos**. O mestre envia uma solicitação de dados para o escravo desejado, e o escravo responde enviando os dados solicitados. Isso é possível graças ao uso de **endereços únicos** para cada dispositivo **escravo**, que permitem que o mestre saiba exatamente qual dispositivo deve ser acessado.

A **comunicação I2C** é realizada por meio de duas linhas de comunicação, o **SDA** (linha de dados) e o **SCL** (linha de sincronismo).

<a href="Arquivo:Barramento_I2C.png" class="wikilink" title="Arquivo:Barramento_I2C.png">Arquivo:Barramento_I2C.png</a>

No **Arduíno UNO** a comunicação I2C utiliza os pinos A4 (SDA) e A5 (SCL) e utiliza a biblioteca chamada **Wire.h** [^8].

No **ESP8266** a comunicação I2C utiliza por padrão pinos GPIO4 (SDA) e GPIO5 (SCL).

Uma vantagem importante da comunicação I2C é que podemos ter um dispositivo mestre se comunicando com vários dispositivos escravos (até 127), como diferentes tipos de sensores ou mesmo outros microcontoladores.

### Laboratório 5: Comunicação entre Arduínos utilizando I2C

Realizar a comunicação entre dois (ou mais) Arduínos utilizando a comunicação **I2C** e a biblioteca **Wire.h**.

Utilize os exemplos prontos da apresentados na **IDE do Arduíno**, no caminho **Arquivo/Exemplos/Wire**, como os exemplos `master_reader` e `master_writer` para uso como mestre, e `slave_sender` e `slave_receiver` para uso como escravo.

Se utilizar mais de um Arduíno como escravo, ajustar o endereço de forma que cada dispositivo tenha um endereço único no barramento.

Veja exemplo de comunicação entre dois Arduínos em [^9].

## Referências

<references />

------------------------------------------------------------------------

<a href="Usuário:Evandro.cantu" class="wikilink" title="Evandro.cantu">Evandro.cantu</a> (<a href="Usuário_Discussão:Evandro.cantu" class="wikilink" title="discussão">discussão</a>) 09h51min de 9 de novembro de 2021 (-03)

------------------------------------------------------------------------

<a href="Categoria:Arduíno" class="wikilink" title="Categoria:Arduíno">Categoria:Arduíno</a> <a href="Categoria:IoT" class="wikilink" title="Categoria:IoT">Categoria:IoT</a>

[^1]: <https://randomnerdtutorials.com/interrupts-timers-esp8266-arduino-ide-nodemcu/>

[^2]: <https://randomnerdtutorials.com/interrupts-timers-esp8266-arduino-ide-nodemcu/>

[^3]: <https://www.arduino.cc/reference/en/language/functions/external-interrupts/attachinterrupt/>

[^4]: <https://www.arduino.cc/reference/en/language/functions/digital-io/pinmode/>

[^5]: <https://www.arduino.cc/en/Tutorial/Foundations/DigitalPins>

[^6]: <https://www.arduino.cc/reference/en/language/functions/advanced-io/pulsein/>

[^7]: <https://portal.vidadesilicio.com.br/real-time-clock-rtc-ds3231/>

[^8]: <https://www.arduino.cc/reference/en/language/functions/communication/wire/>

[^9]: <https://portal.vidadesilicio.com.br/i2c-comunicacao-entre-arduinos/>
