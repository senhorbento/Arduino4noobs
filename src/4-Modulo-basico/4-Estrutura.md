# 4.4 Estrutura de um programa .ino

## O que é um programa .ino?

Antes de falarmos sobre a estrutura do programa .ino, vamos falar o que exatamente seria esse programa. O arquivo com extensão .ino é o arquivo gerado pela ide do Arduino e é ele que é carregado no microcontrolador da nossa placa.
<p></p>

## Estrutura

Um programa .ino, assim como um programa em C/C++, tem uma estrutura básica na qual dentro dela desenvolvemos nosso programa. A baixo um exemplo de como é a estrutura básica.

```C++
//Carrega a biblioteca com as funções do Arduino
//Em algumas IDE's não é necessária a declaração explicita dessa biblioteca
#include "Arduino.h"

//Bloco do programa que é executado apenas uma vez
//Normalmente é utilizado para definir os pinos como entrada ou saída
void setup(){

}

//Bloco do programa que fica em execução enquanto o Arduino estiver ligado
//Tudo que estiver dentro dele ficará sendo executado repetidamente
void loop(){

}
```

# Funções

Agora iremos falar sobre algumas das funções utilizadas dentro do nosso programa, caso queira uma lista completa você pode encontra-lá no site oficial do Arduino ou através desse [link.](https://www.arduino.cc/reference/pt/)

# Funções de uso geral

## pinMode();

Sintaxe: pinMode(pino, modo);

A função pinMode(); tem como finalidade definir o modo de operação de um pino. Para isso é utilizado o parâmetro que diz qual o número do pino e em seguida **INPUT** ou **OUTPUT**. A baixo um exemplo de utilização.
<p></p>

```C++
#include "Arduino.h"

void setup(){
    //Define o pino 13 como saída
    pinMode(13, OUTPUT);
    //Define o pino 12 como entrada
    pinMode(12, INPUT);
}
```
Normalmente essa função é utilizada dentro do void setup(), já que o modo de operação só precisa ser definido uma vez.
<p></p>

## delay();

Sintaxe: delay(tempo em milissegundos);

A função delay(); tem como finalidade pausar por completo a execução do programa no Arduino durante o tempo que foi inserido como parâmetro. A baixo um exemplo de utilização.
<p></p>

```C++
#include "Arduino.h"

void setup(){
    //Define o pino 13 como saída
    pinMode(13, OUTPUT);
}

void loop(){
    //Define que a tensão pode passar no pino 13
    digitalWrite(13, HIGH);
    //Aguarda 1000ms ou 1 segundo
    delay(1000);
    //Define que a tensão não pode passar no pino 13
    digitalWrite(13, LOW);
    //Aguarda 500ms ou 0.5 segundo
    delay(500);
}
```

## millis();

Sintaxe: millis();

A função millis(); retorna o quantos milissegundos já passaram desde a inicialização do Arduino, pode ser usado como o delay(), porém está função não pausa o programa. A baixo um exemplo de utilização.
<p></p>

```C++
#include "Arduino.h"

//Declaração da variável tempo que recebe o tempo atual
unsigned long int tempo = millis();

void setup(){
    pinMode(13, OUTPUT);
}

void loop(){
    //Se a diferença tempo (atual - tempo antigo) 
    //for menor que 500 mantem o led aceso
    if((millis() - tempo) < 500){
        //Define que a tensão pode passar no pino 13
        digitalWrite(13, HIGH);
    }
    //Caso contrario apaga o led
    else{
        //Define que a tensão não pode passar no pino 13
        digitalWrite(13, LOW);
    }

    // Verifica se já passou 1500 milisegundos
    if((millis() - tempo) > 1500){
        //Redefine a variável tempo
        tempo = millis();
    }
}
```

Essa função é um pouco mais complexa de ser utilizada, porém ela traz a vantagem de não pausa por completo a execução do programa.
<p></p>

# Funções de comunicação serial

As funções de comunicação serial são amplamente utilizadas quando queremos enviar mensagens de um Arduino para o outro ou até mesmo mostrar algo no monitor serial de nossa IDE, no [projeto 3](/src/Projetos/3-Projeto-Rede.md) iremos falar melhor delas, a baixo um exemplo de como podem ser utilizadas.
<p></p>

```C++
#include "Arduino.h"

void setup(){
    //Define a velocidade da comunicação serial
    //Obrigatório essa definição com o mesmo valor
    //tanto no receptor quanto no emissor
    Serial.begin(9600);
}

void loop(){
    //Declaração da variável recebido
    char recebido;
    //Escreve na comunicação serial o valor 1;
    Serial.write('1');
    //Verifica se tem algum dado para ser lido pela comunicação serial
    if(Serial.available()){
        //Define a variavel recebido com o valor que foi lido
        recebido = Serial.read();
    } 
}
```

# Funções utilizadas com os pinos digitais

## digitalWrite();

Sintaxe: digitalWrite(pino, valor);

A função digitalWrite(); tem como finalidade definir o estado de um pino digital. Para isso é utilizado o parâmetro que diz qual o número do pino e em seguida **HIGH** ou **LOW**, ou ainda pode ser usado respectivamente **1** ou **0**. A baixo um exemplo de utilização com ambos os casos.
<p></p>

```C++
#include "Arduino.h"

void setup(){
    //Define o pino 13 como saída
    pinMode(13, OUTPUT);
}

void loop(){
    //Define que a tensão pode passar no pino 13
    digitalWrite(13, HIGH);
    //Define que a tensão não pode passar no pino 13
    digitalWrite(13, LOW);

    //Define que a tensão pode passar no pino 13
    digitalWrite(13, 1);
    //Define que a tensão não pode passar no pino 13
    digitalWrite(13, 0);
}
```
Normalmente essa função é utilizada dentro do void loop(), já que essa manipulação, normalmente, é feita mais de uma vez durante a execução do programa, mas nada impede de utiliza-la no void setup().
<p></p>

## digitalRead();

Sintaxe: digitalRead(pino);

A função digitalRead(); tem como finalidade ler o estado de um pino digital. Para isso é utilizado somente o parâmetro que diz qual o número do pino. A baixo um exemplo de utilização.
<p></p>

```C++
#include "Arduino.h"

void setup(){
    //Define o pino 13 como saída
    pinMode(13, OUTPUT);
}

void loop(){
    //Se a tensão estiver passando no pino 13
    if(digitalRead(13) == HIGH){
        //Define que a tensão não pode passar no pino 13
        digitalWrite(13, LOW);
    }

    //Se a tensão não estiver passando no pino 13
    if(digitalRead(13) == LOW){
        //Define que a tensão pode passar no pino 13
        digitalWrite(13, HIGH);
    } 
}
```
Normalmente essa função é utilizada dentro do void loop(), já que essa manipulação, normalmente, é feita mais de uma vez durante a execução do programa.
<p></p>

# Funções utilizadas com os pinos analógicos

## analogWrite();

Sintaxe: analogWrite(pino, valor)

A função analogWrite(); tem como finalidade definir o estado de um pino analógico. Para isso é utilizado o parâmetro que diz qual o número do pino e em seguida um valor que pode variar de 0 a 255, essa função pode ser utilizada tanto nos pinos PWM quanto nos pinos analógicos. A baixo um exemplo de utilização.
<p></p>

```C++
#include "Arduino.h"

void setup(){
    //Define o pino analógico 0 como saída
    pinMode(A0, OUTPUT);
}

void loop(){
    //Define que a tensão não pode passar no pino 13
    analogWrite(A0, 0);
    //Define que parte da tensão pode passar
    analogWrite(A0, 120);
    //Define que a tensão total pode passar
    analogWrite(A0, 255);
}
```
Essa função é comumente utilizada quando se quer controlar a intensidade de um led.
<p></p>

## analogRead();

Sintaxe: analogRead(pino);

Sintaxe: analogWrite(pino, valor)

A função analogWrite(); tem como ler o valor de um pino analógico. Para isso é utilizado o parâmetro que diz qual o número do pino e em seguida um valor que pode variar de 0 a 1024. A baixo um exemplo de utilização.
<p></p>

```C++
#include "Arduino.h"

void setup(){
    //Define o pino analógico 0 como entrada
    pinMode(A0, INPUT);
}

void loop(){
    //Lê o valor da porta analógica 0 e mostra no monitor serial
    Serial.println(analogRead(A0));
}
```