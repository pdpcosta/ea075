## Microcontrolador ATMEGA328P
Devido a sua ampla utilização e disponibilidade no mercado foi adotado o microcontrolador ATMEGA328P para ser o responsável por tratar e gerenciar as rotinas do nosso dispositivo. O ATMEGA328P possui como características principais o fato de possuir 3 memórias internas, sendo elas uma memória Flash (32 KB), uma SRAM (2 KB) e uma EEPROM (1 KB), possui também 23 I/Os, opera com uma tensão de 5V e as suas saídas fornecem uma corrente de 40 mA, além disso, consegue operar com um clock entre 0 à 20 MHz.

[Datasheet](https://br.mouser.com/datasheet/2/268/ATmega48A_PA_88A_PA_168A_PA_328_P_DS_DS40002061B-3050139.pdf)

## Sensores para detecção de gás

Estes sensores, de modo geral, apresentam um material sensível ao gás que precisa ser detectado. Em contato com o ar puro sua condutividade elétrica é baixa enquanto na presença do gás desejado sua condutividade aumenta com a concentração. Desta forma, essa diferença de condutividade é explorada para obtenção de um sinal indicador da presença da substância desejada. 

Os sensores utilizados nesta aplicação serão o MQ-7, MQ-6 e MQ-4, responsáveis pela detecção de monóxido de carbono, gás inflamável (GLP) e gás metano, respectivamente. 

O sinal de saída de cada um destes componentes é analógico, entretanto, a conexão dos sensores MQ-7 e MQ-4 com o microcontrolador será feita via porta digital visto que estes componentes possuem módulos comerciais com conversão AD integrada. O sensor MQ-6 será conectado diretamente à porta analógica do microcontrolador. 

### MQ-7 (Monóxido de Carbono)

Para realizar a detecção do monóxido de carbono o módulo do sensor MQ-7 com conversão analógico-digital já integrada será utilizado, sua conexão com o microcontrolador será feita via porta digital 24.

[Datasheet](https://www.filipeflop.com/img/files/download/Datasheet_Sensor_Gas_MQ7.pdf)

### MQ-4 (Metano)

Para realizar a detecção do gás metano o sensor MQ-4 com conversão analógico-digital já integrada será utilizado, sua conexão com o microcontrolador será feita via porta digital 25.

[Datasheet](https://www.filipeflop.com/img/files/download/Datasheet_Sensor_Gas_MQ4.pdf)

### MQ-6 (GLP)

Para realizar a detecção de GLP o sensor MQ-6 será utilizado, sua conexão com o microcontrolador será feita via porta analógica 23.

[Datasheet](https://www.sparkfun.com/datasheets/Sensors/Biometric/MQ-6.pdf)


## Sensor infravermelho

O sensor infravermelho implementado é o E18-D80NK-N. Este sensor com saída digital possui um emissor e um detector de sinal infravermelho. Caso haja algum objeto na frente deste dispositivo, o sinal infravermelho é refletido pela superfície do objeto e retorna ao detector, ocasionando um sinal de nível lógico baixo na saída, sendo assim, o sensor apresenta saída em nível baixo quando detecta algo e apresenta saída em nível alto quando não está sendo obstruído.

Este sensor opera com 5V e pode ser ajustado para detectar um objeto entre 6cm e 80cm. De acordo com o datasheet, este dispositivo pode apresentar ligeiras variações no range de detecção frente a cor e composição do objeto, assim, recomenda-se que seja feita a calibração antes do uso final.  

A conexão do sensor com o microcontrolador será feita via porta digital (portas 4 e 5 ) com um resistor de pull-up de 10k.

[Datasheet](https://datasheetspdf.com/pdf-file/1311838/ETT/E18-D80NK-N/1)

## Buzzer

Caso um gás seja detectado acima do nível de concentração especificado um alerta sonoro será emitido por meio de um buzzer ativo de 5V conectado ao microcontrolador por meio de uma porta digital. A corrente necessária para suprir o buzzer será fornecida por meio de um transistor, evitando, assim, danos na porta do microcontrolador.

