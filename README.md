# simulador-portatil-de-alarme-para-treinamentos-de-brigada-e-evacuacao

Este projeto é destinado a simulações de emergência e treinamentos de evacuação.  

O sistema opera em modo Access Point,
permitindo que o instrutor ative remotamente o modo 2 “ALARME” por meio de um dispositivo móvel conectado à rede Wi-Fi local.  

Uma vez acionado, o sistema emite sinais visuais e
sonoros — com LED piscante, buzzer ativo — e exibe, no
display OLED, a mensagem “EVACUAR”, simulando uma
situação real de emergência, sem depender de infraestrutura
de rede externa.

### **Instruções:**   
**Descrição do sistema:**  
+ Ação 1 - função: Configurar o módulo de rede Wi-Fi do Raspberry Pi Pico W para operar
em modo Access Point, permitindo a criação de uma rede.
+ Ação 2 - função: Estabelecer um servidor HTTP embutido no firmware do microcontrolador, capaz de responder a requisições de uma interface web básica.
+ Ação 3 - função: Desenvolver a interface HTML contendo os botões de controle remoto.
(“Ligar” e “Desligar”), que serão interpretados como comandos pelo
microcontrolador.
+ Ação 4 - função: O LED é empregado como sinalizador luminoso, com a finalidade de
indicar o estado de acionamento do sistema. No modo “Alerta”, o
dispositivo opera em modo intermitente, simulando visualmente uma
situação de emergência. 
+ Ação 5 - função: De maneira análoga ao LED, o buzzer é empregado como gerador de
alerta sonoro, com a função de reforçar a sinalização de alarme. 
+ Ação 6 - função: Utilizar o display OLED do modelo SSD1306 para a exibição de
mensagens textuais que informam o estado operacional do sistema ao
usuário. Quando o sistema estiver ativado, será exibida a mensagem
“Evacuar”; quando desativado, a mensagem apresentada será “Sistema
em repouso”.

**Materiais e conceitos envolvidos:** 
1. Wi-Fi em Modo Access Point
+ Pico W atua como servidor local, criando sua própria rede
sem fio.
+ Dispositivos móveis conectam-se diretamente ao Pico W.
+ Não requer roteador ou internet.
2. LED de Sinalização
+ Componente visual para indicar o estado do sistema.
+ Controlado por pino GPIO configurado como saída digital.
+ Pisca em modo “Alarme” para simular situação de
emergência.
3. Buzzer
+ Emissor de alerta sonoro.
+ Controlado por pino GPIO com sinal digital.
+ Ativado para emitir som intermitente durante simulação.
4. Comunicação I2C
+ Protocolo serial de dois fios usado para comunicar com o
display OLED.
+ Requer configuração dos pinos SDA e SCL.
5. Display OLED SSD1306
+ Interface de comunicação via I²C.
+ Exibe mensagens como “Evacuar” e “Sistema em
repouso”.
6. Formatação e Exibição de Texto
+ Conversão do valor de temperatura (float) para string.
+ Envio da string para o display com posicionamento
correto.
7. Interface Web HTTP
+ Pico W atua como servidor local, criando sua própria rede
sem fio.
+ Dispositivos móveis conectam-se diretamente ao Pico W.
+ Não requer roteador ou internet.

**Requisitos técnicos:**  
1. Comunicação e Rede
+ Configuração do Wi-Fi em modo Access Point.
  + Nome e senha da rede definidos no firmware.
  + Endereço IP fixo.
+ Interface web responsiva.
  + Página HTML com botões de controle incorporada
ao firmware.  
  
 2. Lógica de Controle
+ Interpretação de comandos via HTTP.
  + Mapeamento de URLs como /ligar e /desligar.
+ Controle dos periféricos via GPIO.
  + Ações específicas em resposta aos comandos
recebidos.
+ Atualização do display OLED.
  + Mensagens informativas baseadas no estado atual
do sistema.
+ Controle de temporização.
  + Piscar do LED e som do buzzer em intervalos
programados.
  + Evitar bloqueios com delays excessivos.
