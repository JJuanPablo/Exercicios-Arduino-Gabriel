                                              `Exercicio 1`
int ledVermelho = 13;

void setup()
{
 pinMode(ledVermelho, OUTPUT); //Define o pino 13(LED) como saída
}
void loop()
{
 digitalWrite(ledVermelho, HIGH); //Liga o LED
 delay(1000); //Aguarda 1 segundo
 digitalWrite(ledVermelho, LOW); //Apaga o LED
 delay(1000); //Aguarda 1 segundo
}
--------------------------------------------------------------------------------------------------------------

                                            `Exercicio 2`


                                            
// Define o pino do LED vermelho
int ledVermelho = 9;

// Define o tempo de espera entre cada alteração de brilho (em milissegundos)
int esperaBrilho = 50;

// Valor do brilho do LED vermelho (0-255)
int brilhoLed = 0;

void setup() {
  // Define o pino do LED vermelho como saída
  pinMode(ledVermelho, OUTPUT);
}

void loop() {
  // Loop infinito para alterar progressivamente o brilho do LED vermelho

  // Aumenta gradualmente o brilho até o máximo (255)
  while (brilhoLed < 255) {
    // Define o brilho do LED vermelho
    analogWrite(ledVermelho, brilhoLed);

    // Espera o tempo definido
    delay(esperaBrilho);

    // Incrementa o brilho
    brilhoLed++;
  }

  // Diminui gradualmente o brilho até o mínimo (0)
  while (brilhoLed > 0) {
    // Define o brilho do LED vermelho
    analogWrite(ledVermelho, brilhoLed);

    // Espera o tempo definido
    delay(esperaBrilho);

    // Decrementa o brilho
    brilhoLed--;
  }
}
--------------------------------------------------------------------------------------------------------------
                                          `Exercicio 3`

                                          

// Define os pinos dos LEDs
int ledVermelho = 9;
int ledVerde = 10;
int ledAmarelo = 11;

void setup() {
  // Define os pinos dos LEDs como saída
  pinMode(ledVermelho, OUTPUT);
  pinMode(ledVerde, OUTPUT);
  pinMode(ledAmarelo, OUTPUT);

  // Inicia a comunicação serial
  Serial.begin(9600);
}

void loop() {
  // Verifica se há dados disponíveis na comunicação serial
  if (Serial.available()) {
    // Lê o caractere enviado
    String comandoAtivacao = Serial.readString();

    // Altera o estado dos LEDs de acordo com o caractere recebido
    if(comandoAtivacao == "R"){
        analogWrite(ledVermelho, 255);
        analogWrite(ledVerde, 0);
        analogWrite(ledAmarelo, 0);
      	return;
    }
    else if(comandoAtivacao == "G"){
        analogWrite(ledVermelho, 0);
        analogWrite(ledVerde, 255);
        analogWrite(ledAmarelo, 0);
      	return;
    }
    else if(comandoAtivacao == "Y"){
        analogWrite(ledVermelho, 0);
        analogWrite(ledVerde, 0);
        analogWrite(ledAmarelo, 255);
      	return;
    }
    else{
        analogWrite(ledVermelho, 0);
        analogWrite(ledVerde, 0);
        analogWrite(ledAmarelo, 0);
      	return;
    }
  }
}

--------------------------------------------------------------------------------------------------------------
                                          `Exercicio 4´


// Define o pino da chave tátil
int botao = 2;

void setup() {
  // Define o pino da chave tátil como entrada
  pinMode(botao, INPUT);

  // Inicia a comunicação serial
  Serial.begin(9600);
}

void loop() {
  // Lê o estado da chave tátil (0 ou 1)
  int estadoBotao = digitalRead(botao);

  // Imprime o estado da chave tátil no Serial Monitor
  Serial.println(estadoBotao);
}







                                          
