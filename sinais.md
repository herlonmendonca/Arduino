# #Arduino com sinais de Transito# 

**// dando um "nome" para as portas** 
int vermelha1 = 10;
int vermelha2 = 11;
int amarela1 = 9;
int amarela2 = 12;
int verde1 = 8;
int verde2 = 13;

void setup() {
  **// aqui setamos quais portas vamos usar**
  pinMode(vermelha1, OUTPUT);
  pinMode(amarelo1, OUTPUT);
  pinMode(verde1, OUTPUT);

  pinMode(vermelha2, OUTPUT);
  pinMode(amarelo2, OUTPUT);
  pinMode(verde2, OUTPUT);
}

void loop() {
   cruzamento();
}

void cruzamento() {
  **// primeiro sinal - amarelo**
  digitalWrite(vermelha1, LOW);
  digitalWrite(amarelo1, HIGH);
  digitalWrite(verde1, LOW);

  **// segundo sinal  vai ser amarelo tbm**
  digitalWrite(vermelha2, LOW);
  digitalWrite(amarelo2, HIGH);
  digitalWrite(verde2, LOW);

  **// seta tres segundos com sinal no amarelo**
  delay(3000);

  **// primeiro sinal apaga o amarelo e liga o vermelho**
  digitalWrite(amarelo1, LOW);
  digitalWrite(vermelha1, HIGH);
  // digitalWrite(verde1, LOW);

  // segundo sinal apaga o amarelo e liga o verde
  digitalWrite(amarelo2, LOW);
  // digitalWrite(vermelha2, LOW);
  digitalWrite(verde2, HIGH);

  **// aguarda 6s com o primeiro sinal fechado e o segundo aberto**
  delay(6000);  

  ****// primeiro sinal apaga o vermelho e liga o verde**
  digitalWrite(verde1, HIGH);**
  // digitalWrite(amarelo1, LOW);
  digitalWrite(vermelha1, LOW);

  **// segundo sinal 2 apaga o verde e liga o vermelho**
  digitalWrite(verde2, LOW);
  // digitalWrite(amarelo2, LOW);
  digitalWrite(vermelha2, HIGH);

  **// esperamos seis segundos com o sinal aberto**
  delay(6000);
}