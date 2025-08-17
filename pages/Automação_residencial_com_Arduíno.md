## Automação residencial com Arduíno

  
Ano: 2013

Alunos: Amir L. K. Annahas e Stephani C. S. da Silva

Curso Integrado em Informática

Orientador: Prof. Humberto Martins Benbeduzzi

Colaboradora: Profª. Danieli C. Cassuli

<!-- -->

Objetivo  
Tem como objetivo permitir que as luzes internas da residência possam ser controladas através de um sistema com interface Web, de modo que o usuário possa utilizar qualquer computador, tablet ou smartphone para controlar a iluminação de cada cômodo da casa. A luz externa acende-se automaticamente no início da noite, acionada por um sensor de luminosidade.

<!-- -->

Acionamento automático de ventilação com base na temperatura ambiente  

Montagem de um termômetro com leitura da temperatura a partir de um sensor, e exibição da temperatura em uma barra de leds coloridos. No momento em que a temperatura atingir um determinado valor pré-definido, aciona-se automaticamente a ventilação.

Sistema Montado  

<a href="Arquivo:SistemaArduinoAutomacao.jpg" class="wikilink" title="Arquivo:SistemaArduinoAutomacao.jpg">Arquivo:SistemaArduinoAutomacao.jpg</a>

### Código Fonte

#### Arduino

    //iluminacao interna

    int ledQuarto1 = 9;
    int ledQuarto2 = 10;
    int ledBanho = 11;
    int ledCozinha = 12;
    int ledSala = 13;
    boolean ledQuarto1On, ledQuarto2On, ledBanhoOn, ledCozinhaOn, ledSalaOn;
    int op;

    //iluminacao externa

    const int LDR = 1;
    const int Led = 8;
    const int valorMinimoLuz = 20;
    int ValorLido = 0;

    //Temperatura sensor LM35

    const int pinoSensor = 0;//pino Anlogico de Entrada 0
    int valorSensor = 0;
    float valorCelsius = 0;
    int tempMinima = 10; //temp barra led: temp minima + 2x intervalo
    int intervalo = 3;

    //

    void setup(){
      // iluminacao interna
      Serial.begin(57600);
      while(!Serial){
      }

      pinMode(ledQuarto1, OUTPUT);
      pinMode(ledQuarto2, OUTPUT);
      pinMode(ledBanho, OUTPUT);
      pinMode(ledCozinha, OUTPUT);
      pinMode(ledSala, OUTPUT);

      ledQuarto1On = ledQuarto2On = ledBanhoOn = ledCozinhaOn = ledSalaOn = false;

      //iluminacao externa

      pinMode(Led, OUTPUT);

      //termometro

      for (int i=2; i<8; i++){ //pinos 2 a 7
        pinMode(i,OUTPUT);    //define como saida
      }

    }

    //



    void loop(){
      luzesInterno();
      luzesExterno();
      termometro();
      delay(100);
    }

    //

    void termometro(){
      valorSensor = analogRead(pinoSensor);
      //Serial.print("Valor do Sensor = ");
      //Serial.println(valorSensor);
      valorCelsius = valorSensor * 0.488;

      //Serial.print("Temperatura em graus Celsius: ");
      //Serial.println(valorCelsius);   
      //Serial.print("Temperatura sensor: ");
      //Serial.println(valorSensor);   

      for (int i=2; i<8; i++){
        if (valorCelsius > ((i*intervalo)+tempMinima)){
          digitalWrite(i, HIGH);
        } 
        else {
          digitalWrite(i, LOW); 
        }
      }  
    }

    //

    void luzesExterno(){

      ValorLido = analogRead(LDR);
      if (ValorLido < valorMinimoLuz){
        digitalWrite(Led, HIGH);
      }
      else{
        digitalWrite(Led, LOW);
      }

    }

    //

    void luzesInterno(){
      if (Serial.available() > 0) {
        op = Serial.read();
        op = op - 48; //recebe em ascii, com -48 iguala. ex: 48 enviado no php é o caractere 0


        if (op == 2){
          ledQuarto1On = acender(ledQuarto1, ledQuarto1On);
        }
        else if (op == 3){
          ledQuarto2On = acender(ledQuarto2, ledQuarto2On);
        }
        else if (op == 4){
          ledBanhoOn = acender(ledBanho, ledBanhoOn);
        }
        else if (op == 5){
          ledCozinhaOn = acender(ledCozinha, ledCozinhaOn);
        }
        else if (op == 6){
          ledSalaOn = acender(ledSala, ledSalaOn);
        } 
        else if (op == 7){ // a partir daqui sao as confirmações para ver se tal lampada está acesa
          Serial.print(ledQuarto1On);
        } 
        else if (op == 8){ 
          Serial.print(ledQuarto2On);
        } 
        else if (op == 9){ 
          Serial.print(ledBanhoOn);
        } 
        else if (op == 0){ 
          Serial.print(ledCozinhaOn);
        } 
        else if (op == 1){ 
          Serial.print(ledSalaOn);
        }

      }
    }

    boolean acender(int l, boolean lOn){
      if (lOn){
        digitalWrite(l, LOW);
        return false;
      }
      else {
        digitalWrite(l, HIGH);
        return true;
      }

    }

    //

#### PHP

##### index

    <?php
        function lerArduino($op){
            $ler = fopen('/dev/ttyACM0', 'r');
            $port = fopen('/dev/ttyACM0', 'w+');
            
            fwrite($port, $op);
            while(true){
            
                $ex = fread($ler, 1);
                if (strlen($ex)>0){
                    break;
                }
            }
            
            fclose($ler);
            fclose($port);
            return $ex;
        }
        
    ?>

    <html>
    <head>
        <title>Planta Arduino</title>
        <link rel="stylesheet" href="estilo.css" type="text/css"/>
    </head>
    <body>
        <div id="site">
            <a href="GerenciadorCasa.php?acao=quarto1">
                <div id="quarto1">
                    <img 
                        <?php 
                            $lido  = lerArduino('7');
                            if ($lido  == '0'){
                                echo 'src="lampada2.png"';
                            }else if ($lido  == '1'){
                                echo 'src="lampada1.png"';
                            }else{
                                echo 'src="erro.png"';
                            }
                        ?>
                    />
                    Dormitorio 1
                </div> 
            </a>
            <a href="GerenciadorCasa.php?acao=banho">
                <div id="banho">
                    <img 
                        <?php 
                            $lido  = lerArduino('9');
                            if ($lido  == '0'){
                                echo 'src="lampada2.png"';
                            }else if ($lido  == '1'){
                                echo 'src="lampada1.png"';
                            }else{
                                echo 'src="erro.png"';
                            }
                        ?>
                    />
                    Banho
                </div> 
            </a>
            <a href="GerenciadorCasa.php?acao=quarto2">
                <div id="quarto2">
                    <img 
                        <?php 
                            $lido  = lerArduino('8');
                            if ($lido  == '0'){
                                echo 'src="lampada2.png"';
                            }else if ($lido  == '1'){
                                echo 'src="lampada1.png"';
                            }else{
                                echo 'src="erro.png"';
                            }
                        ?>
                    />
                    Dormitorio 2
                </div>
            </a>
        <br>
            <a href="GerenciadorCasa.php?acao=cozinha">
                <div id="cozinha">
                    <img 
                        <?php 
                            $lido  = lerArduino('0');
                            if ($lido  == '0'){
                                echo 'src="lampada2.png"';
                            }else if ($lido  == '1'){
                                echo 'src="lampada1.png"';
                            }else{
                                echo 'src="erro.png"';
                            }
                        ?>
                    />
                    Cozinha
                </div>
            </a>
            <a href="GerenciadorCasa.php?acao=sala">
                <div class="sala" id="sala">
                    <img 
                        <?php 
                            $lido  = lerArduino('1');
                            if ($lido  == '0'){
                                echo 'src="lampada2.png"';
                            }else if ($lido  == '1'){
                                echo 'src="lampada1.png"';
                            }else{
                                echo 'src="erro.png"';
                            }
                        ?>
                    />
                    Sala de Estar
                </div>
            </a>
        </div>
    </body>

    </html>

##### GerenciadorCasa

    <?php
    $gCasa= new GerenciadorCasa;

    class GerenciadorCasa{
    private $port;

        function __construct() {
            
            // Conecta na porta
            $this->setPort(fopen('/dev/ttyACM0', 'w+'));

            $acao = $_GET['acao'];

            
            if(isset($acao)){
                $this->processarAcao($acao);
            }else{
                echo("<script type='text/javascript'> alert('Nenhuma acao a ser processada.'); </script>");
            }
        }


        public function processarAcao($acao){
            if($acao == "quarto1"){
                $this->quartoUno();
            }else if($acao == "quarto2"){
                $this->quartoDuo();
            }else if($acao == "banho"){
                $this->banho();
            }else if($acao == "cozinha"){
                $this->cozinha();
            }else if($acao == "sala"){
                $this->sala();
            }else{
                $this->padrao();
            }
            fclose($port);//desconecta com o arduino
            echo('<script>location.href="index.php";</script>');//fecha a janela
        }
        
        public function getPort(){
            return $this->port;
        }
        
        public function setPort($porta){
            $this->port = $porta;
        }

        public function quartoUno(){
            fwrite($this->getPort(), '2');
        }
        
        public function quartoDuo(){
            fwrite($this->getPort(), '3');
        }
        
        public function banho(){
            fwrite($this->getPort(), '4');
        }
        
        public function cozinha(){
            fwrite($this->getPort(), '5');
        }
        
        public function sala(){
            fwrite($this->getPort(), '6');
        }

    }
    ?>

------------------------------------------------------------------------

<a href="Categoria:Arduíno" class="wikilink" title="Categoria:Arduíno">Categoria:Arduíno</a>
