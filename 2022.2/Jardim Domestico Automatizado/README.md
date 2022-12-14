# `<Jardim Doméstico Automatizado>`

# `<Automated Home Garden>`

## Apresentação

O presente projeto foi originado no contexto das atividades da disciplina de graduação _EA075 - Sistemas Embarcados_, oferecida no segundo semestre de 2022, na Unicamp, sob supervisão da Profa. Dra. Paula Dornhofer Paro Costa, do Departamento de Engenharia de Computação e Automação (DCA) da Faculdade de Engenharia Elétrica e de Computação (FEEC).

Thiago Miguel dos Santos 187607, Eng. Elétrica.
Bruna Erica Santana Santos de Oliveira 167770, Eng Elétrica.

## Descrição do Projeto

O contato com a natureza é essencial para a saúde mental de um indivíduo, desde um caminhar pela floresta até o simples olhar para uma decoração composta por plantas e flores. Tendo em vista a necessidade deste contato, muitas pessoas recorrem ao cultivo de plantas em seus lares, o que é considerado uma terapia [1]. Porém nem todos conseguem manter os cuidados constantes com as plantas e muitas espécies demandam cuidados mais rígidos. Essa é a motivação para o projeto em questão, “Jardim Doméstico Automatizado” é a proposta de um dispositivo que ajude o cultivo de plantas no ambiente doméstico. Seu objetivo é fazer com que mesmo os tutores mais atarefados possam desfrutar de plantas saudáveis em seu ambiente de vivência. Plantas essas que podem ser até mesmo para uso em refeições, como temperos e hortaliças em pequena quantidade. Ou então flores que dão vida ao ambiente.

## Descrição Funcional

### Funcionalidades

A finalidade deste projeto é manter a planta saudável através dos atuadores de luz em frequências otimizadas para a planta (Luzes ultravioleta, luzes coloridas e infravermelho) [2], e irrigação. O controle é alimentado pela informação de sensores de umidade e luz. Além disso, é aplicado um sensor de temperatura para acompanhamento ambiental, que deve auxiliar o tutor da planta em seus cuidados, alertando em caso de desconforto térmico da planta.
  
 
__Irrigação:__ O sistema é capaz de regar a terra a partir da informação de umidade proveniente do sensor específico.

__Iluminação:__ O sistema é capaz de prover doses de luz de acordo com informações dadas pelo usuário em relação à planta e também do sensor de luz presente.

# `<Jardim Doméstico Automatizado>`

# `<Automated Home Garden>`

## Apresentação

O presente projeto foi originado no contexto das atividades da disciplina de graduação _EA075 - Sistemas Embarcados_, oferecida no segundo semestre de 2022, na Unicamp, sob supervisão da Profa. Dra. Paula Dornhofer Paro Costa, do Departamento de Engenharia de Computação e Automação (DCA) da Faculdade de Engenharia Elétrica e de Computação (FEEC).

Thiago Miguel dos Santos 187607, Eng. Elétrica. Bruna Erica Santana Santos de Oliveira 167770, Eng Elétrica.

## Descrição do Projeto

O contato com a natureza é essencial para a saúde mental de um indivíduo, desde um caminhar pela floresta até o simples olhar para uma decoração composta por plantas e flores. Tendo em vista a necessidade deste contato, muitas pessoas recorrem ao cultivo de plantas em seus lares, o que é considerado uma terapia [1]. Porém nem todos conseguem manter os cuidados constantes com as plantas e muitas espécies demandam cuidados mais rígidos. Essa é a motivação para o projeto em questão, “Jardim Doméstico Automatizado” é a proposta de um dispositivo que ajude o cultivo de plantas no ambiente doméstico. Seu objetivo é fazer com que mesmo os tutores mais atarefados possam desfrutar de plantas saudáveis em seu ambiente de vivência. Plantas essas que podem ser até mesmo para uso em refeições, como temperos e hortaliças em pequena quantidade. Ou então flores que dão vida ao ambiente.

## Descrição Funcional

### Funcionalidades

A finalidade deste projeto é manter a planta saudável através dos atuadores de luz em frequências otimizadas para a planta (Luzes ultravioleta, luzes coloridas e infravermelho) [2], e irrigação. O controle é alimentado pela informação de sensores de umidade e luz. Além disso, é aplicado um sensor de temperatura para acompanhamento ambiental, que deve auxiliar o tutor da planta em seus cuidados, alertando em caso de desconforto térmico da planta.

**Irrigação:** O sistema é capaz de regar a terra a partir da informação de umidade proveniente do sensor específico.

**Iluminação:** O sistema é capaz de prover doses de luz de acordo com informações dadas pelo usuário em relação à planta e também do sensor de luz presente.

**Histórico:** O sistema faz um acompanhamento dos atributos de leitura e atuadores para que seja possível um acompanhamento e correlações do desenvolvimento da planta pelo tutor.

**Alertas:** O acompanhamento contínuo de sensores pode emitir alertas ao tutor de acordo com as seguintes severidades: Umidades extremas (alta e baixa), temperaturas extremas, quantidades de luz extremas.

### Configurabilidade

O usuário pode escolher o perfil da planta escolhida de acordo com a família. Isso ajusta níveis no controle de irrigação e iluminação. O usuário pode configurar manualmente pontos de operação das variáveis controladas: umidade e iluminação.

### Eventos

**Falta de água:** Quando o sensor de umidade do solo faz uma leitura abaixo da recomendada.

**Falta de iluminação:** Ocorre quando a integração de iluminação em uma janela de tempo não é suficiente para suprir a planta.

**Temperaturas extremas:** Ocorre quando o sensor de temperatura atinge temperaturas inadequadas para a família selecionada.

### Tratamento de Eventos

**Falta de água:** Aciona válvula para liberação de água e liga a bomba de água do reservatório.

**Falta de Iluminação:** Ajusta a intensidade das lâmpadas de iluminação através de PWM [3] com razão de intensidade regulada para a família da planta para cada comprimento de onda: Ultravioleta, azul, magenta e infravermelho.

**Temperaturas extremas:** Emite um alerta ao usuário através de aplicativo próprio e/ou aplicativos de mensagem.

## Descrição Estrutural do Sistema

Atuadores:

-   Bomba de água
    
-   Válvula solenóide para água
    
-   Lâmpada LED com emissão em Infravermelho
    
-   Lâmpada LED com emissão em Azul
    
-   Lâmpada LED com emissão em Vermelho
    
-   Lâmpada LED com emissão em Ultra Violeta

- Transistor
    

Sensores:

-   Sensor de umidade de solo
    
-   Sensor de temperatura
    
-   Sensor de luz em Infravermelho
    
-   Sensor de luz RGB
    
-   Sensor de luz em Ultra Violeta
    

Comunicação

-   Comunicação sem fio WiFi

[![](https://github.com/thiago-m-s/ea075/raw/main/2022.2/Jardim%20Domestico%20Automatizado/diagrama_blocos2.png)](https://github.com/thiago-m-s/ea075/blob/main/2022.2/Jardim%20Domestico%20Automatizado/diagrama_blocos2.png)

Comunicação

-   Comunicação sem fio WiFi

# Especificações

## Especificação Estrutural

Nos tópicos a seguir são apresentadas as especificações estruturais de cada bloco apresentado no diagrama anterior.

### Sensores

O desenvolvimento de uma planta é lento e contínuo. Por este motivo a aquisição de dados dos sensores é realizada pontualmente em um intervalo de tempo. Para o projeto este intervalo seria da ordem de minutos, o que daria tempo suficiente para realizar algumas médias em sensores mais ruidosos ou sujeitos a variações rápidas pelo ambiente.

### Sensor de Luz

O sensor de luz deve conseguir medir as bandas de luz necessárias para o crescimento da planta. Essas bandas são:

-   Infravermelho, 700 a 1000 nm
    
-   Luz Vermelha, 620 a 700 nm
    
-   Verde, 500 a 575 nm
    
-   Azul/violeta, 400 a 500 nm
    
-   Ultra violeta (UV-A), 315 a 400 nm
    

O modelo escolhido foi o AS7261 por conta da comunicação ser tanto I2C quanto UART facilitando a integração com outros dispositivos do projeto. Além de cumprir com o objetivo de identificar as cores das luzes. Ele identifica na faixa de 350nm a 1000nm que é satisfatório para o projeto.  O sensor se comunica utilizando interface I2C.

![](https://camo.githubusercontent.com/bf6351c616573e25dd0a72057cf7249ce1977bc07b802c081b440e5c22c4e425/68747470733a2f2f6c68362e676f6f676c6575736572636f6e74656e742e636f6d2f6a7569426146437130796237694858395151495456793364447937596c325750332d55684b767a356d482d4e493268497069524d62375f684e38786353334a737762534d663651466e375f6d4d3459486a6a5a434674555367594e52356f6e3873664f574c496b56653866397933576238706b68426256323632565f316642324e74356141304137734e454c56725876726b35306f6a645439726c476f4e386943466f486d6a413036725f4f58715f7574753957496f4369674765307567)](https://camo.githubusercontent.com/bf6351c616573e25dd0a72057cf7249ce1977bc07b802c081b440e5c22c4e425/68747470733a2f2f6c68362e676f6f676c6575736572636f6e74656e742e636f6d2f6a7569426146437130796237694858395151495456793364447937596c325750332d55684b767a356d482d4e493268497069524d62375f684e38786353334a737762534d663651466e375f6d4d3459486a6a5a434674555367594e52356f6e3873664f574c496b56653866397933576238706b68426256323632565f316642324e74356141304137734e454c56725876726b35306f6a645439726c476f4e386943466f486d6a413036725f4f58715f7574753957496f4369674765307567)

### Sensor de Umidade

O sensor de umidade é específico para solo. Seu modelo é “Soil Moisture V1.0” do fabricante STEMinds. Seu contato elétrico é colocado diretamente na terra. É alimentado com 5 Vcc e o sinal gerado é analógico, sendo necessário um conversor AD para leitura no microcontrolador.

### Sensor de Temperatura

O sensor de temperatura modelo DS18B20, do fabricante Maxim Integrated, disponibiliza o valor da temperatura ambiente em até 12 bits. O sensor disponibiliza leituras de -30 ºC a 100 ºC com erro de ± 1 ºC.

## Atuadores

###  Lâmpadas LED

Serão utilizadas lâmpadas LED visíveis nas cores, Azul, Vermelho e Verde que são centradas, respectivamente, em 465 nm, 515 nm e 640 nm. Para maior facilidade de montagem serão adotados, para visível, LEDs RGB de 5mm modelo T-1 ¾, do fabricante Kingbright. A tensão nominal de trabalho é de 3 V, a corrente consumida pelas três cores é de 85 mA.

[![](https://camo.githubusercontent.com/7ec2321499b127620918e6a2f42bb5dc51bac18217a2b28e312983e183ef1133/68747470733a2f2f6c68342e676f6f676c6575736572636f6e74656e742e636f6d2f696b546c346b3936776944586d4f6772585a53474b6c38494558466f6b713839654c46336874416f716e5f68747339396c726a744a7544487436316d6854546364547254725578335a5a4c577933766f5446396a3251425532506b595a52545a5f4f6c33304235535931704d3366324b356b4b794f6f426d3945446e383637724c4a524a493733426f71763448514e4d613758423230533673716c6366656d444f423156467067574c6739574453356c4f5543547a5761464f7132355777)](https://camo.githubusercontent.com/7ec2321499b127620918e6a2f42bb5dc51bac18217a2b28e312983e183ef1133/68747470733a2f2f6c68342e676f6f676c6575736572636f6e74656e742e636f6d2f696b546c346b3936776944586d4f6772585a53474b6c38494558466f6b713839654c46336874416f716e5f68747339396c726a744a7544487436316d6854546364547254725578335a5a4c577933766f5446396a3251425532506b595a52545a5f4f6c33304235535931704d3366324b356b4b794f6f426d3945446e383637724c4a524a493733426f71763448514e4d613758423230533673716c6366656d444f423156467067574c6739574453356c4f5543547a5761464f7132355777) O LED de infravermelho utilizado é do modelo TSHF6210 do fabricante Vishay. A tensão nominal de trabalho é de 5 V, a corrente consumida é de 100 mA.

[![](https://camo.githubusercontent.com/b5cb381aa77b4f5a2535b6ab9e0d4c4c44c4a4f042b502e0739d60fe0f0f906e/68747470733a2f2f6c68332e676f6f676c6575736572636f6e74656e742e636f6d2f2d35576c627570683853732d4654444f66556469354a73374338304e6863474f677a4175532d336e306a58374b565536314631627375676d3734705f555359557064545f6a5476617838567a376d73427a4e6558646930755f615a714d737838595641505550634676566f61784c6b3674557a6e615279714c5772474b5571565a6e4b7076344b4f4a71346b7543664463775f786b733331775a6a36344c506b4a5f6e636d6e72505a453455364e447941744b4a4e3033506d5847624751)](https://camo.githubusercontent.com/b5cb381aa77b4f5a2535b6ab9e0d4c4c44c4a4f042b502e0739d60fe0f0f906e/68747470733a2f2f6c68332e676f6f676c6575736572636f6e74656e742e636f6d2f2d35576c627570683853732d4654444f66556469354a73374338304e6863474f677a4175532d336e306a58374b565536314631627375676d3734705f555359557064545f6a5476617838567a376d73427a4e6558646930755f615a714d737838595641505550634676566f61784c6b3674557a6e615279714c5772474b5571565a6e4b7076344b4f4a71346b7543664463775f786b733331775a6a36344c506b4a5f6e636d6e72505a453455364e447941744b4a4e3033506d5847624751) Para a faixa de ultravioleta é aplicado o LED modelo UV3TZ-385-15 do fabricante Bivar. Sua emissão é centrada em 385 nm.

[![](https://camo.githubusercontent.com/8ecb4b140fe208542cd1097e3b501a6b21517785289d9a66ece4851b3beb3d32/68747470733a2f2f6c68362e676f6f676c6575736572636f6e74656e742e636f6d2f7433537435593362453630366c736e6d4376564967696b2d675f41447635486a387336305146365069786a4e796d4937614f6f76645f6f4b7a6d647550534e78664355364b47335139436e316e4351745a37426f545a42325333584b6d7551476638726333794649754a6a5356735a394159414e54524b6e4c374d574b4354546435664875316e783745597177745332322d6c506e6541394e65333838382d696f63334556765345636e534c3747564c304f4a74745a7130587343666f67)](https://camo.githubusercontent.com/8ecb4b140fe208542cd1097e3b501a6b21517785289d9a66ece4851b3beb3d32/68747470733a2f2f6c68362e676f6f676c6575736572636f6e74656e742e636f6d2f7433537435593362453630366c736e6d4376564967696b2d675f41447635486a387336305146365069786a4e796d4937614f6f76645f6f4b7a6d647550534e78664355364b47335139436e316e4351745a37426f545a42325333584b6d7551476638726333794649754a6a5356735a394159414e54524b6e4c374d574b4354546435664875316e783745597177745332322d6c506e6541394e65333838382d696f63334556765345636e534c3747564c304f4a74745a7130587343666f67)

#### Bomba de Água

A bomba de água aplicada no projeto é o modelo 350 GPH do fabricante Sparkfun Electronics. Possui alimentação 12V, 1.5 A. Sua capacidade é de 350 galões por hora, que representa 1324 litros por hora ou 22 litros por minuto.

#### Comunicação Sem Fio

A comunicação sem fio do microcontrolador é feita através de um módulo Wi-Fi modelo ESP8266 do fabricante Parallax Inc. A comunicação é feita através de uma porta serial através dos pinos 7 e P sendo TX e RX. Sua alimentação é de 5 V.

#### Módulo PWM

O modelo escolhido foi o LED1642GWPTR, pois estava presente no software KiCAD. Facilitando, desta forma, o seu uso no projeto e atende às demandas por se tratar de um dispositivo com 16 canais de 12 bits sendo suficiente para realizar o controle dos LEDs e ampliação futura.

#### Circuitos de Interface

É necessário circuito de interface para acionamento da bomba de água. Esse circuito se limita a um contator magnético (relé) acionado a partir de uma saída digital do microcontrolador.

Para acionamento dos LEDs será utilizado o módulo PWM já apresentado.

### Micro Controlador

O microcontrolador escolhido é o PIC32, de 32 bits, pois possui várias entradas com diferentes interfaces de comunicação (6 UART, 5 I2C, 4 SPI, CTMU e I²S). Desta forma, é possível conectar todos os sensores e atuadores utilizados no projeto. Tem cerca de 512KB de memória Flash e 128KB de memória SRAM (volátil).

## Fontes de Alimentação

As fontes de alimentação foram escolhidas a partir das necessidades dos dispositivos. Optou-se por fontes do fabricante Mean Well pois seus modelos já estão inclusos no software KiCAD.

 - Modelo IRM-02-5: Para componentes com alimentação de 5V (Utilizada no Sensor de umidade);
 -  Modelo IRM-03-3.3: Para componentes com alimentação de 3V (Utilizada nos demais componentes);
 - IRM-60-12: Para componentes com alimentação de 12V (Utilizada na bomba d’água).

### Especificação de Algoritmos

Segue abaixo os fluxogramas dos eventos do projeto:

1.  Fluxograma do evento: Falta de iluminação RGB [![](https://camo.githubusercontent.com/e86d5c2445fc3f92090e6240eb9856027b296cd5a2386ca23f1ad34028bbabe2/68747470733a2f2f6c68332e676f6f676c6575736572636f6e74656e742e636f6d2f4e49615546484e4e7262463633774d4f7358637a3638614f314856736d483848484d4e5561684271766444476a4d72734341664f50354c59684e6c326a786b51385744493767547a696436654d3163556b2d4c7468534f33374a464d596f70585a4f456f415042695853773977524573734c5a70555a4f4e6f503569313355364759593436384b6853705575595349323070496875384747374b784579675f624f414e51376b48746f4530704858367748684e69656871456654765f5667)](https://camo.githubusercontent.com/e86d5c2445fc3f92090e6240eb9856027b296cd5a2386ca23f1ad34028bbabe2/68747470733a2f2f6c68332e676f6f676c6575736572636f6e74656e742e636f6d2f4e49615546484e4e7262463633774d4f7358637a3638614f314856736d483848484d4e5561684271766444476a4d72734341664f50354c59684e6c326a786b51385744493767547a696436654d3163556b2d4c7468534f33374a464d596f70585a4f456f415042695853773977524573734c5a70555a4f4e6f503569313355364759593436384b6853705575595349323070496875384747374b784579675f624f414e51376b48746f4530704858367748684e69656871456654765f5667)
    
    2.  Fluxograma do evento: Temperatura extrema

[![](https://camo.githubusercontent.com/9005499e11b5d567b1411921abfda9f611eb758676ed87eb808cf6a63d34ce00/68747470733a2f2f6c68342e676f6f676c6575736572636f6e74656e742e636f6d2f4459564268677a78586151715477427671656c73384c465976706c4d58675370426f3355316845347156523269354d794541573748354b4546343835537746485f38663755774b6242445468756f685344784a676e55322d5437742d6f755530776d586f545374656d4b58745a595f555f693543794a2d754b6c6e6c6e7742524b3359336e5f33446a766a41646272546551656971434231655572753072435a6241727446374e70746c735f5a6f6c5a796769487a713673774774663067)](https://camo.githubusercontent.com/9005499e11b5d567b1411921abfda9f611eb758676ed87eb808cf6a63d34ce00/68747470733a2f2f6c68342e676f6f676c6575736572636f6e74656e742e636f6d2f4459564268677a78586151715477427671656c73384c465976706c4d58675370426f3355316845347156523269354d794541573748354b4546343835537746485f38663755774b6242445468756f685344784a676e55322d5437742d6f755530776d586f545374656d4b58745a595f555f693543794a2d754b6c6e6c6e7742524b3359336e5f33446a766a41646272546551656971434231655572753072435a6241727446374e70746c735f5a6f6c5a796769487a713673774774663067)

3.  Fluxograma do evento: Umidade baixa [![](https://camo.githubusercontent.com/a19f29883b6e32687460190e22fd70abb901657d3591b46fb1b02972964f0b17/68747470733a2f2f6c68352e676f6f676c6575736572636f6e74656e742e636f6d2f4f784c5672694b6152594741704e714a45596c58612d6b316d447871666178772d474a7070426c76614232335a617534764f61697665414370707750337971657a47365f785275585f6f61634852532d546266627244535559352d73614a464543316a306e523777623048305a51536c336146574d79674d7a494d454955724344376378326c776b45624a59425a70336a785074474742537242724346575673566d63502d47535a55614c45326a64657142794251654f357a5650485751)](https://camo.githubusercontent.com/a19f29883b6e32687460190e22fd70abb901657d3591b46fb1b02972964f0b17/68747470733a2f2f6c68352e676f6f676c6575736572636f6e74656e742e636f6d2f4f784c5672694b6152594741704e714a45596c58612d6b316d447871666178772d474a7070426c76614232335a617534764f61697665414370707750337971657a47365f785275585f6f61634852532d546266627244535559352d73614a464543316a306e523777623048305a51536c336146574d79674d7a494d454955724344376378326c776b45624a59425a70336a785074474742537242724346575673566d63502d47535a55614c45326a64657142794251654f357a5650485751)
    
4.  Fluxograma do evento: Falta de iluminação ultravioleta [![](https://camo.githubusercontent.com/6ac50052b3e434ba8708dc27341ac3b7a77408c4aca45b8c79ae8dd9b2b597eb/68747470733a2f2f6c68342e676f6f676c6575736572636f6e74656e742e636f6d2f3545357533476f556b4630654858636c70786c612d6b6d43764b4651456b4a49494c7a4a6c717a37544b79624e6f307546674b4c774f745269794451624147566435456d3131305f305a366c71504a5064476451784667456264515059675748684d64775249787032535533553847754e5764566b4957726f395970757946626464355177506f474343475f55315f4f774149534f3272445937566d73316c424e735f6f5142357a314e374c32654c426b3835754a7247664b365a624e41)](https://camo.githubusercontent.com/6ac50052b3e434ba8708dc27341ac3b7a77408c4aca45b8c79ae8dd9b2b597eb/68747470733a2f2f6c68342e676f6f676c6575736572636f6e74656e742e636f6d2f3545357533476f556b4630654858636c70786c612d6b6d43764b4651456b4a49494c7a4a6c717a37544b79624e6f307546674b4c774f745269794451624147566435456d3131305f305a366c71504a5064476451784667456264515059675748684d64775249787032535533553847754e5764566b4957726f395970757946626464355177506f474343475f55315f4f774149534f3272445937566d73316c424e735f6f5142357a314e374c32654c426b3835754a7247664b365a624e41)
    
5.  Fluxograma do evento: Falta de iluminação infravermelho [![](https://camo.githubusercontent.com/d49f64aa136a2e31916553302c19616e038e9ef3b0c13de5db2e73763a335a03/68747470733a2f2f6c68362e676f6f676c6575736572636f6e74656e742e636f6d2f46496b66317735715538525477716e37316d555f63785f304e3655376454716c48416572486848374b63333747546435636c47746b7352795971456c4e4d574e4f5550656b6457426e68512d43674c374632473649692d76315f7336733844695375735f467176574c7145774f585232343870685675496a6438435a516c716e6f62304d466e3848413448346646706e6664477748543850413957496d6b4b5f5874625a4c474d397a58627255657a766e79375477636142546546457741)](https://camo.githubusercontent.com/d49f64aa136a2e31916553302c19616e038e9ef3b0c13de5db2e73763a335a03/68747470733a2f2f6c68362e676f6f676c6575736572636f6e74656e742e636f6d2f46496b66317735715538525477716e37316d555f63785f304e3655376454716c48416572486848374b63333747546435636c47746b7352795971456c4e4d574e4f5550656b6457426e68512d43674c374632473649692d76315f7336733844695375735f467176574c7145774f585232343870685675496a6438435a516c716e6f62304d466e3848413448346646706e6664477748543850413957496d6b4b5f5874625a4c474d397a58627255657a766e79375477636142546546457741)
    

## Referências

1.  [https://edition.cnn.com/2018/08/03/health/sw-horticultural-therapy/index.html](https://edition.cnn.com/2018/08/03/health/sw-horticultural-therapy/index.html)
    
2.  [https://www.ul.com/services/horticultural-lighting?utm_mktocampaign=lightingglobal_googleads&utm_mktoadid=534750355857&campaignid=13972433958&adgroupid=127913040191&matchtype=b&device=c&creative=534750355857&keyword=horticultural%20light&gclid=CjwKCAjwpqCZBhAbEiwAa7pXeeyfFV-wXcNtfY-oTxTUw52vPz036KG_f6bVc6y8Rdku19TboTax-xoCd2IQAvD_BwE](https://www.ul.com/services/horticultural-lighting?utm_mktocampaign=lightingglobal_googleads&utm_mktoadid=534750355857&campaignid=13972433958&adgroupid=127913040191&matchtype=b&device=c&creative=534750355857&keyword=horticultural%20light&gclid=CjwKCAjwpqCZBhAbEiwAa7pXeeyfFV-wXcNtfY-
