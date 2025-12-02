<H1>BOLA NO TUBO</H1>

Este projeto, desenvolvido para a disciplina de Eletrônica Embarcada, consiste em um desenvolvimento de firmware para controlar a posição vertical de uma bola por meio de um fluxo de ar gerado através de uma ventoinha controlada pela abertura ou fechamento de uma válvula acoplada a um motor de passo.

Serão utilizados um sensor óptico refletivo para detecção da abertura total da válvula, um sensor ultrassonico para medição da altura da bola e um sensor de temperatura para compensação da medição da altura da bola. A transmissão e recepção de dados será realizada utilizando uma interface bluetooth que possibilitará a comunicação entre o sistema e o usuário (via celular ou computador).

O firmware desenvolvido será implementado em um microcontrolador PIC16F1827/I-P e utilizadas as ferramentas SNAP, que permite programar e debuggar o código desenvolvido, da Microchip, e um Analisador Lógico de 8 canais para visualização e aferição dos sinais digitais. O diagrama de blocos do projeto está apresentado conforme a Figura 1:

<div align="center">
  
  <img src="https://github.com/fernandarmuro/wingardium-levibola/blob/be5bb0134b2ad3a82d7c9f4d4b3726b2a49a7895/Diagrama_de_blocos.png" alt="Diagrama da FSM do Bola no Tubo" width="600"/> 
  
  <em>Figura 1: Diagrama de blocos do projeto bola no tubo.</em>
  
</div>



O projeto será dividido em 4 módulos, os quais o desenvolvimento, teste e simulação do código será de responsabilidade individual à cada integrante do grupo. Ao final, cada parte desenvolvida será integrada e testada em um protótipo físico disponibilizado para validadação e verificação do funcionamento do firmware.

O projeto e as atividades de cada integrante seguem a seguinte divisão:

1. Douglas Rodrigues: Medição da altura da bola e temperatura.

   1.1. Medição de Altura (Sensor HC-SR04):
   
    - Implementar a Ativação do Trigger;
      
    - Medir o Tempo de Voo do Sinal Echo;
      
    - Assegurar resolução suficiente para detectar variações de 0,1 mm na faixa de 3 mm a 460 mm;
      
    - Assegurar um período de medição maior ou igual a 10 ms para evitar erros por reflexões.


 		1.2. Compensação de Velocidade do Som;
    
    - Aquisição da Temperatura (Sensor LM35):
      
    - Leitura do sensor de temperatura para obtenção do valor em ∘C;
    
    - Compensação de temperatura utilizando uma tabela de busca (look-up) para compensar a velocidade do som na faixa de 0∘C a 50∘C com resolução de 1∘C;
      
    - Correção do valor da temperatura utilizando a fórmula de compensação disponível no roteiro do experimento;​
      
    - Calcular a altura final utilizando o Tempo de Voo e a Velocidade do Som Compensada.​
     
  2. Fernanda Muro: Comunicação bluetooth.

   2.1. Configuração UART:
   
   - Configuração da comunicação serial assíncrona com baud rate de 115200 BPS, 8 bits de dados contendo 1 bit para indicar o início e o fim da mensagem e sem paridade;
     
   - Implementação da detecção do fim do quadro de comunicação por timeout definido por tempo, 40ms, utilizando a interrupção;

   2.2. Transmissão entre o microcontrolador e o dispositivo externo:

   - Estruturar o quadro de transmissão com 15 bytes de tamanho, sendo: 1 byte para modo e 2 bytes para cada um dos 7 dados: setpoint e medição da altura, valor médio do tempo        de vôo, temperatura, setpoint e posição da válvula (passo do motor) e valor do ciclo útil;

   - Envio do quadro completo de dados a cada 100ms no formato hexadecimal como inteiro em big-endian;
  
   2.3. Recepção entre o dispositivo externo e o microcontrolador:
   
   - Estruturar o quadro de recepção com 7 bytes de tamanho, sendo: 1 byte para modo e 2 bytes para cada um dos 3 dados> altura, posição da válcula (passo do motor) e ciclo útil      do motor;
   
     - Recepção dos dados codificados para as variáveis do projeto no formato hexadecimal como inteiro em big-endian.

   
  3. Matheus Neves: Controle dos atuadores (ventoinha e válvula).

  3.1. Geração do PWM;
   
  - Gerar o sinal de Modulação por Largura de Pulso (PWM) para o sinal Vent;
        
  - Configurar o PWM com frequência próxima a 250 Hz;
        
  - Configurar o PWM com 10 bits de resolução (ciclo útil entre 0 e 1023).


  3.2 Controle da Válvula Motorizada (Motor de Passo 28BYJ-48)
      
  - Implementar o Movimento por Passos:
 			
  - Implementar a sequência de ativação dos sinais (SM1, SM2, SM3, SM4) para movimento de abertura (horário) e a sequência inversa para fechamento (anti-horário).
 				
  - Criar variáveis SM1 (ABRE), SM2 (FECHA), SM3 (SENTIDO HORARIO), SM4 (SENTIDO ANTI HORARIO) (DEFINIR O TIPO)
 				
  - Garantir um tempo de passo ≥3 ms. (TIMER 1)
 				
  - Limitar a quantidade máxima de passos em 420 (aberta ao fechada).
 				
  - Implementar lógica de detenção de movimento para evitar travamento nos extremos.
 				
  3.3: Detecção de Limite da Válvula (TCRT-5000)
 				
  - Leitura da tensão analógica através do sensor TCRT-5000 para detectar a posição de fim de curso (totalmente aberta).
 					
  - Inicialização da posição da válvula a partir do valor mínimo de tensão (detecção de limite de abertura).

   
  4. Pedro Barros: Algoritmo de controle PID.

    4.1: Implementação do Algoritmo PI/PID Posicional;
      
 		- Implementar o cálculo do erro;
    
​		- Implementar a equação de controle;
 
 	  4.2: Gerenciamento da Ação de Controle;

    4.3: Limitação da Saída do Controlador;
    
 	  8.4: Implementação dos Modos de Operação:

 		- A0:
    
    - Modo manual: atribuir setpoints (válvula/ventoinha) diretamente aos atuadores, ignorando o controlador;
      
    - A1:
      
    - Modo Ventoinha: atuação do controlador sobre o ciclo útil da ventoinha.
      
    - A2: 
      
    - Modo Válvula: atuação do controlador sobre a posição da válvula.
        
    - A3:
      
    - Modo reset: implementa o reset do microcontrolador por software.


O detalhamento de cada módulo desenvolvido no projeto, assim como os arquivos mcc.c e mcc.h de cada um, estão disponíveis nas pastas nominais de cada integrante.
