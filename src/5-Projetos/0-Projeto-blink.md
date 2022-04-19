# 5.0 Testando o ambiente

Feito todas as configurações necessárias, caso não tenha feito ainda, ou queira revisar o ambiente, aqui vai alguns atalhos:

- [Configurando o Ambiente Windows](/src/2-Ambiente/1-Ambiente-windows.md)
- [Configurando o Ambiente Linux](/src/2-Ambiente/2-Ambiente-linux.md)
- [Configurando o Ambiente Online](/src/2-Ambiente/3-Ambiente-online.md)

Certo disso vamos ao primeiro projeto, não se preocupe, o código para esse projeto já vem incluso na IDE do Arduino e no Tinkercad. Sabendo disso, vamos ao que interessa.
<p></p>

## Projeto blink

O projeto blink é basicamente o nosso "Hello World!", caso você não saiba, o "Hello World!" é tido como o projeto inicial para todo programador quando inicia em uma nova linguagem, alguns programadores dizem que se você não fize-lo as coisas tendem a dar errado, então não vamos arriscar não é mesmo?
<p></p>

<details> 
    <summary>Utilizando a Arduino IDE - Em desenvolvimento</summary>
</details> 

<details> 
    <summary>Utilizando o Tinkercad</summary>

No Tinkercad esse projeto já vem por padrão quando você insere o Arduino no ambiente de trabalho, irei mostrar como inserir o Arduino e como checar o código que está sendo executado dentro do Arduino.
<p></p>

Você já deve saber como criar um novo circuito, caso não se lembre irei recapitular a parte de configuração do [ambiente online](/src/2-Ambiente/3-Ambiente-online.md). Para criar um novo projeto utilizando o arduino basta clicar na aba "Circuitos" (1) no canto esquerdo e em seguida "Criar novo Circuito"(2)  
<p align="center">
    <img src="../imgs/TinkerCad/CriandoCircuito.png" alt="Criando circuito">
</p>

Após criar um novo projeto, no canto direito é possível localizar uma barra de pesquisa (1), digite Arduino, como na imagem a baixo. No resultado deverá aparecer o "Arduino Uno R3" (2), basta clicar na figura dele e depois clica na parte branca da tela (3) para adicionar o Arduino ao seu ambiente de trabalho.

<p align="center">
    <img src="../imgs/Projetos/0-blink/tinkercad_arduino.png" alt="Selecionado o Arduino">
</p>

Após adicionar o Arduino ao ambiente de trabalho, basta clicar no botão "Iniciar simulação" (1), repare que 2 leds na placa se acenderam, o LED que indica que o Arduino está ligado, "ON" (2) e o LED "L" (3) este LED em questão estará piscando, mas porque? Veremos mais a baixo.

<p align="center">
    <img src="../imgs/Projetos/0-blink/tinkercad_arduino_blink.png" alt="Resultado">
</p>

Ao clicarmos em "Código" (1), podemos visualizar como o algoritmo funciona (2), os passos descritos ali são seguidos durante a execução do programa que está rodando no Arduino. Ao clicarmos em "Blocos" (3), temos a opção "Texto" que é a opção que mais iremos utilizar.

<p align="center">
    <img src="../imgs/Projetos/0-blink/tinkercad_arduino_cod_blocks.png" alt="Codigo">
</p>

Ao selecionar a opção "Texto" uma mensagem como essa irá surgir, basta clicar em "Continuar":

<p align="center">
    <img src="../imgs/Projetos/0-blink/tinkercad_arduino_alert.png" alt="Alerta">
</p>

E por fim veremos um código (1) como na imagem a baixo:

<p align="center">
    <img src="../imgs/Projetos/0-blink/tinkercad_arduino_cod.png" alt="Codigo">
</p>

A explicação superficial deste código está mais a baixo, no proximo tópico, iremos aprofundar melhor em como ele funciona na [aula 4](/src/4-Modulo-basico/zEm-desenvolvimento.md).

</details>    

<details> 
    <summary>Código explicado</summary>

```C++
//Esta parte do codigo é executada somente uma vez
void setup()
{
    //Define o pino onde o LED está internamente ligado como saida
    pinMode(LED_BUILTIN, OUTPUT);
}
//Fim da parte que é executada somente uma vez


//Esta parte do codigo é executada enquanto o Arduino estiver energizado
void loop()
{
    //Inicio

    //Define a porta do LED como ligada
    digitalWrite(LED_BUILTIN, HIGH);
    //Pausa a execução por 1 segundo
    delay(1000);
    //Define a porta do LED como desligada
    digitalWrite(LED_BUILTIN, LOW);
    //Pausa a execução por 1 segundo
    delay(1000); 
    
    //Volta para o inicio
}
//Fim da parte que é executada enquanto o Arduino estiver energizado
```
</details> 
