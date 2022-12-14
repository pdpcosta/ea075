# `Estufa Inteligente`
# `Smart Eco Greenhouse`

## Apresentação

O presente projeto foi originado no contexto das atividades da disciplina de graduação *EA075 - Sistemas Embarcados*, 
oferecida no segundo semestre de 2022, na Unicamp, sob supervisão da Profa. Dra. Paula Dornhofer Paro Costa, do Departamento de Engenharia de Computação e Automação (DCA) da Faculdade de Engenharia Elétrica e de Computação (FEEC).

|Nome  | RA | Curso|
|--|--|--|
| Pedro Henrique Carosso Christensen  | 243048  | Eng. Elétrica|
| Juliana Nicolette  | 171244  | Eng. Elétrica|

## Arquivos Importantes

[Esquemático em PDF](https://github.com/juuhnicolette/ea075/blob/612c9111519774235c16353964eb563e56315b2f/2022.2/Estufa%20Inteligente/pdf/Esquematico.pdf)

[Lista de Componentes](https://github.com/juuhnicolette/ea075/blob/a07f31901fcd4d004bec73706969db310a6d21b4/2022.2/Estufa%20Inteligente/components.md)

## Descrição do Projeto
Com o desenvolvimento tecnológico crescendo exponencialmente, automatizações de processos acabam sendo cada vez mais comuns, trazendo segurança e autonomia a processos industriais e domésticos.

Foi pensando nisso que o projeto Estufa Inteligente surgiu. A intenção é possibilitar controles de temperatura, umidade e irrigação em um modo automático, criando um ecossistema funcional.

Além disso, as possibilidades de rotatividade do plantio são infinitas, já que o proprietário consegue configurar faixas de temperatura, umidade e ciclos de irrigação manualmente, permitindo assim a economia energia conforme o clima local. E no quesito sustentabilidade, a eficácia é garantida: além da economia energética, há também a economia de água.

Com o sistema Estufa Inteligente, além de garantir a qualidade do produto na colheita, você evita a proliferação de pragas, automatiza todos os processos de plantio sem precisar estar presente no local.

A idealização do projeto possui como público alvo qualquer pessoa que deseje automatizar suas estufas.

Um valor seria melhor definido quando o projeto estiver em uma etapa de desenvolvimento mais avançada, por conta de não conseguirmos estipular os custos inicialmente. 

## Descrição Funcional
Para demonstrar e funcionalidade no sistema podemos apresentar isoladamente cada sensor e com qual parte do sistema o seu atuador vai reagir dependendo do sinal de entrada, então segue a descrição de cada comportamento:

Controle da temperatura: Ao definir uma faixa de temperatura o sensor de temperatura vai mandar sinais para os ar-condicionados quando:  Atingir temperatura limite superior -> Ligar resfriamento. Esse sinal de ligar será único e outro sinal de desligamento será enviado quando o sensor de temperatura detectar a temperatura ideal atingida (geralmente leva-se a faixa de temperatura com a temperatura ideal posicionada exatamente no meio dessa faixa).

Controle de umidade: Ao definir a faixa de umidade desejada o sensor de umidade vai mandar sinais para os irrigadores quando: Atingir umidade limite inferior -> Ligar os irrigadores. Porém o controle para diminuir a umidade do ambiente não será necessária, pois a umidade dentro da estufa terá que ser maior que a umidade externa. Para desligar os irrigadores, um sinal será enviado do sensor de umidade quando a umidade ideal for atingida, com o tempo a umidade tende a cair e o ciclo se repete.

Controle de irrigação: Com uma periodicidade programada os irrigadores irão acionar, porém isso será programado pelo cliente, pois os sensores de umidade também irão acionar os irrigadores, então temos que pensar em um intervalo padronizado para não irrigar em excesso as plantas, isso vai ser variável para cada tipo de planta, conforme o desejo do cliente.


### Funcionalidades
Como funcionalidades do projeto, podemos listar:
- Controle de temperatura através de ares condicionados;
- Controle de irrigação através de irrigadores aspersores¹;  
- Controle de umidade através de aspersores (os mesmos utilizados no controle da irrigação);

### Configurabilidade
Em nosso projeto, vamos definir apenas um modo de operação, que é automático. As definições de faixa de temperatura e controle de umidade serão feitas na implantação do sistema.

### Eventos
Ditamos como evento periódico o controle de irrigação, que ocorre uma vez ao dia em situações normais. Dependendo do plantio e da configuração do cliente, é possível ajustar tornando-o mais/menos frequente. É possível configurar também o tempo de duração da irrigação para cada vez que ela for ativada, buscando um melhor aproveitamento e economia de água.

Como eventos não-periódicos listamos o controle de temperatura e umidade, que vão ocorrer com base nos dados recebidos pelos sensores. Portanto, os ajustes de temperatura e umidade terão definidos pontos limites mínimos e pontos limites máximos para cada um, para que esses parâmetros fiquem dentro de uma faixa ideal definida pelo cliente e que consiga ser eficiente para não ocorrer gasto desnecessário de energia.


### Tratamento de Eventos
Modo automático ligado:

  - Se temperatura for superior à Xº - acionamento dos ares condicionados por 1 hora
  
  - Se temperatura for inferior à Xº - desligamento dos ares condicionados por 30 minutos
  
  - Se umidade for superior à Y% - acionamento dos aspersores por 30 minutos
  
  - Se umidade for inferior à Y% - desligamento dos aspersores por 2 horas

Observação: A temperatura X e a umidade Y serão definidos pelo usuário no momento da aquisição do produto.


## Descrição Estrutural do Sistema
Estruturalmente o projeto foi divido em três partes, sendo elas: a entrada, o módulo de controle, e a saída. Em cada uma das partes, foram inseridos os dispositivos principais para o funcionamento da estufa, conforme ilustrado na imagem abaixo.

![image](https://user-images.githubusercontent.com/113607245/197598182-65b5ef60-90c1-4b89-b3dc-6712cc2c7038.png)


O bloco "Chave de controle" contido na etapa "Entrada" do diagrama será o responsável por ligar e desligar o sistema.

Além disso, foram desenvolvidos dois fluxogramas que determinam o comportamento do sistema, tanto para o controle de temperatura como para o controle de umidade.

![diagramacontroletemperatura](https://user-images.githubusercontent.com/113607245/191367051-de9a27ac-5c74-43c3-bffc-4759951f76da.png)

![diagramacontroleumidade](https://user-images.githubusercontent.com/113607245/191367053-6f095790-2c18-4e20-9bbc-e61497113d34.png)


## Especificações

Buscando desenvolver um projeto simples, barato e fácil de configurar, optamos pelo Arduíno² ATmega328P como plataforma de prototipagem, aproveitando o microcontrolador interno com suporte de entrada/saída embutido.

A umidade relativa mais favorável depende da espécie de planta cultivada, com uma faixa típica que varia entre 50% e 70%. Já a temperatura mais favorável depende da espécie de planta cultivada e do nível  desejado de atividade fotossintética. A temperatura típica de uma estufa varia entre 10 °C  e 20 °C. Temperaturas muito altas reduzem o crescimento das plantas, fazendo com que elas murchem e morram; por outro lado, temperaturas muito baixas limitam o crescimento das plantas.³

A distribuição dos sensores de temperatura e umidade será feita a cada 12m² no espaço da estufa, e o posicionamento dos ares-condicionados dependerá da potência e área de alcance, mas inicialmente manteremos essa mesma distância de 12m² entre eles. Para irrigação, serão dispostos aspersores de raio de pequeno a médio alcance (entre 6 e 12 metros) também a cada 12m². Nessa etapa é importante que haja um equilíbrio na pressão da água, para não haver locais que sejam regados por dois aspersores simultaneamente.

### Especificação Estrutural

Para medição de umidade e temperatura foi escolhido o sensor DHT-11⁴. Este sensor faz medições de temperatura de 0º C até 50º C e mede a umidade do ar nas faixas de 20% a 90%. A precisão (margem de erro) do sensor para medição de temperatura é de aproximadamente 2 °C e para umidade é de 5%. Assim, mesmo que haja necessidade de alteração da faixa de temperatura e umidade mínima pelo plantio específico do cliente, temos certeza que esse sensor atenderá todos os requisitos.

Para acionamento e desligamento dos ares-condicionados, será utilizado o sensor IRM-3638 para leitura do sinal infravermelho emitido pelo controle remoto dele. Dessa forma, permitimos que o cliente escolha o modelo de ar condicionado desejado e utilizamos um LED IR (emissor de infravermelho) para ligar e desligar o ar condicionado, emitindo o mesmo código que seria emitido pelo controle remoto de fábrica do equipamento.⁵

Os aspersores serão os responsáveis por irrigar e umidificar o ambiente, controlados por válvulas de vazão solenóides 12 VDC normalmente fechadas, ou seja, só permitirão a passagem de fluido se forem energizadas, enquanto estiverem desenergizadas elas bloquearão a passagem do fluido (água). Em nosso projeto, serão utilizados relês para acionamento das válvulas.⁶


### Especificação de Algoritmos 

Os algoritmos do projeto serão baseados adicionando as bibliotecas prontas que foram previamente cadastradas, compatíveis com cada um dos materiais utilizados. 

Para o sensor de temperatura e umidade, a seguinte lógica será seguida:
![image](https://user-images.githubusercontent.com/113607245/199123615-191ae3a9-8833-48d8-b8a2-99a8760b32b0.png)

As bibliotecas utilizadas serão:

[Dht.h](https://github.com/adafruit/DHT-sensor-library)

[IRremote](https://github.com/Arduino-IRremote/Arduino-IRremote)


## Referências
1. [Irrigação](https://pt.wikipedia.org/wiki/Irriga%C3%A7%C3%A3o)

2. [Arduino](https://pt.wikipedia.org/wiki/Arduino)

3. [Medir o clima da estufa garante melhor
crescimento das plantas](https://www.vaisala.com/sites/default/files/documents/CEN-BAU-Greenhouse-Climate-Application-Note-B211142PT-A.pdf)

4. [Veja as diferenças dos sensores DHT11 e DHT22 na prática - Arduino](http://www.squids.com.br/arduino/index.php/projetos-arduino/projetos-squids/basico/292-projeto-89-veja-as-diferencas-dos-sensores-dht11-e-dht22-na-pratica-arduino)

5. [Ar Condicionado Controlado Por Arduino, Via Infravermelho E Com Medição De Temperatura](https://www.instructables.com/Ar-Condicionado-controlado-por-Arduino-via-infrave/)

6. [Controle uma válvula solenoide com o Arduino](https://www.filipeflop.com/blog/controle-uma-valvula-solenoide-com-o-arduino/)



