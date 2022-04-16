# 4.1 Conhecendo o Arduino

<p>Atualmente no mercado existe uma grande quantidade de tipos de Arduino, o mais utilizado é o o Arduino UNO. Durante o curso iremos utilizar somente o modelo UNO. Porém ao fim dessa explicação irei citar algum outros modelos.</p>
<p align="center">
    <img src="../imgs/ModuloBasico/Uno/Uno.jpg" alt="Arduino Uno">
</p>

<p>Na parte superior da imagem é possível notar que existe alguns "furos" com uma numeração em baixo deles, esses "furos" são comumente chamados de pinos, e será como irei menciona-los.
</p>

<p align="center">
    <img src="../imgs/ModuloBasico/Uno/UnoSup.jpg" alt="Arduino Uno">
</p>

<p>Os pinos que vão de 0 a 13 são pinos programáveis, através de comandos, que veremos mais a frente, é possível executar uma infinidade de funções com eles, seja acender um LED, controlar um servomecanismo ou até mesmo controlar as luzes de sua residência. Todos eles possuem pelo menos o estado de 1 ou HIGH para ligado e 0 ou LOW para desligado. </p>

Ainda nesses pinos de 0 a 13 é possível notar alguns outros pontos, como no pino 0 que recebe a sigla RX e o pino 1 que recebe a sigla TX. A sigla (TX) significa que este é um pino que pode ser utilizado para transmissão e a (RX) significa que este é um pino que pode ser utilizado para recepção de dados. Mais a frente na [aula 4](/src/4-Modulo-basico/4-IO), iremos falar mais aprofudandamente sobre eles, o importante no momento é saber que eles servem para comunicação.
<p></p>

É possível notar que existem pinos com o simbolo til (~), que no caso são os pinos 11, 10, 9, 6, 5 e 3. Esses pinos são os chamados pinos de PWM, nesses pinos é possível controlar não somente o estado de ligado ou desligado, como também estados intermediários, um bom exemplo é o controle de intensidade de um LED, ele pode ficar mais ou menos "brilhante" de acordo com a programação. Iremos aprofundar melhor nesses pinos na [aula 3](/src/4-Modulo-basico/2-Eletronica-basica).
<p></p>

<p>Ainda na parte superior da nossa placa, é possível notar os pinos AREF e GND, o pino GND serve como o nosso pino (-) negativo, um exemplo de onde vemos isso é em pilhas, onde o lado chato é o negativo e o pontudo o positivo. Já o pino AREF é utilizado quando queremos limitar a voltagem dos pinos analógicos, por padrão esse valor é de 5v, podemos limitar apenas para valores menores.
</p>

Na parte esquerda da nossa imagem podem notar 3 grandes componentes, vamos falar melhor deles a baixo.
<p></p>

<p align="center">
    <img src="../imgs/ModuloBasico/Uno/UnoEsq.jpg" alt="Arduino Uno">
</p>

(1) Este botão é o botão chamado de reset, ele serve basicamente para reiniciar o arduino, assim como o botão reset de um computador.  
<p></p>

(2) Esta é a porta de comunicação do arduino, é possível conectar-la em um computador por exemplo. Por ela é possivel passar o programa para ele e também é possível ler os dados gerados nele, essa porta é internamente conectada com os pinos 0 e 1, que são os pinos de comunicação.  
<p></p>

(3) Esta é a porta de entrada de energia, caso você queria utilizar seu Arduino sem um computador é possível liga-lo utilizando essa porta. Lembrando que a fonte deve ter entre 9 à 12v e pelo menos 1a.
<p></p>

Já na parte inferior é possível notar 2 conjuntos de pinos, vamos falar primeiro dos pinos power ou pinos de energia.
<p></p>

<p align="center">
    <img src="../imgs/ModuloBasico/Uno/UnoInf.jpg" alt="Arduino Uno">
</p>

O pino IOREF diferente do AREF, tem a funcionalidade de dizer qual a voltagem que está saindo por padrão do Arduino, que no caso é 5v.
<p></p>

O pino reset tem a mesma funcionalidade do botão de reset.
<p></p>

Os pinos 3.3v e 5v são pinos de saída de energia, que tem como objetivo alimentar nossos componentes, sejam eles LEDs, relés ou até mesmo sensores de presença. Como cada componente tem uma voltagem diferente, existem esses 2 pinos para que possamos ter maior suporte a diferentes componentes.
<p></p>

Os pinos GND são internamente conectados com o GND da parte de cima, e tem a mesma funcionalidade.
<p></p>

O pino Vin tem como finalidade ser mais uma forma de entrada de energia para o Arduino, ele é internamente conectado com a porta de alimentação que se encontra no canto esquerdo.
<p></p>

Os pinos de A0 à A5 são os pinos analógico, normalmente são utilizados como entrada de dados para componentes como por exemplo um potenciômetro.
<p></p>

Existem ainda alguns componentes que estão mais ao centro da placa que serão explicados de forma mais detalhada na [aula 3](/src/4-Modulo-basico/2-Eletronica-basica).
<p></p>

Existem ainda uma infinidade de outros modelos de Arduino, caso queira conhece-los recomendo esse [artigo](https://www.arduino.cc/en/hardware). A baixo temos uma imagem com alguns deles.
<p></p>

<p align="center">
    <img src="http://1.bp.blogspot.com/-V3RlUkAgP2c/UHo6unaVgNI/AAAAAAAAALQ/Aenlp91DQHs/s1600/arduinos.png" alt="Tipos de Arduinos">
</p>

Imagem retirada do site: http://ardufc.blogspot.com/2012/10/modelos-do-arduino.html
