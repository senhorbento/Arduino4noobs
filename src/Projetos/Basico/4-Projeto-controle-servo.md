# P.4 Projeto controle de um servo motor através de um potênciometro

## Objetivo do projeto

Esse projeto tem como finalidade aprofundar os conhecimentos adquiridos na [aula 7](/src/4-Modulo-basico/7-Potenciometro.md) e [aula 8](/src/4-Modulo-basico/8-Servo-motor.md) 

## O que o projeto deve ter?

O projeto consiste em basicamente um servor motor que deve ser controlado utilizando um potênciometro:
<p></p>

- 1 Arduino Uno (Ou algum outro de preferência);
- 1 Protoboard (Opcional);
- 1 Servo motor;
- 1 Potênciometro (No caso usaremos de 1KΩ, mas pode ser de outra medida, isso só interferirá na precisão do movimento);
- Alguns jumpers (Se você estiver usando a placa fisicamente);
<p></p>

Inicialmente estaremos montando o circuito da maneira mostrada a baixo, dentro do possível experimente outras maneiras.

<p align="center">
    <img src="../imgs/Projetos/4-Servo/Esquema.png" alt="Esquema de ligação">
</p>

Você é capaz de fazê-lo funcionar? Uma resposta para o programa estará mais a baixo, porém tente fazê-lo a principio sem consulta-la.

<details>
    <summary>Código que pode resolver o problema</summary>

```C++
//Inclui a biblioteca com funções para o servo
#include <Servo.h>

//Instância um objeto do tipo Servo
Servo servoMotorObj; 

//Define qual pino faz a leitura do potenciômetro
#define _PIN_POTENCIOMETRO_ 0

//Define qual o pino controla o servo
#define _PIN_SERVO_ 4

void setup()
{
  	//Seta o pino do servo ao objeto de tipo servo
  	servoMotorObj.attach(_PIN_SERVO_);
}

//Definido uma variavel para a leitura do potenciômetro
int leituraPotenciometro;

void loop()
{  	
	//Inicio
  	//Faz a leitura do valor do potenciômetro e armazena o valor
	leituraPotenciometro = analogRead(_PIN_POTENCIOMETRO_);
  	//Pega o valor da leitura e faz uma regra de 3 com o valor de 180
  	//180 seria relacionado ao grau maximo que o servomecanismo suporta
	leituraPotenciometro = map(leituraPotenciometro, 0, 1023, 0, 180);
  	//Define no objeto a angulação
	servoMotorObj.write(leituraPotenciometro);
  	//Pausa o programa por 10 milésimos de segundo
	delay(10);
  
  	//Volta para o inicio
}
```
</details>
<p></p>

Você pode ver o projeto funcionando através desse [link](https://www.tinkercad.com/things/eq0WrMoQxxx).
<p></p>

## Desafio

Como de costume, temos um desafio, o desafio da vez é o de adicionar mais alguns servos, você é capaz de resolver esse problema? Espero que sim, boa sorte =)
<p></p>

[Algumas das cores que consegui vão estar nessa linha caso tenha curiosidade =)](https://www.tinkercad.com/things/k7Dux258KN1)